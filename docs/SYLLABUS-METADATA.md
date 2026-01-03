# Syllabus Metadata Standard (`syllabus.json`)

## 1. Overview
The `syllabus.json` file is the "Brain" of every course directory. It serves two critical functions:
1.  **Indexing:** It tells the PARA Search Engine which files exist and how to categorize them.
2.  **Curating:** It defines the "Active Syllabus" by explicitly flagging topics or pages that are excluded from the current academic year.

**Location:** Every course folder (e.g., `BS-CIS/Semester 5/CIS-304/`) must contain exactly one `syllabus.json`.

---

## 2. Naming Conventions (The Style Guide)
To ensure system stability, we enforce strict naming rules.

| Rule | Description | Example |
| :--- | :--- | :--- |
| **Casing** | All IDs, filenames, and folders must be **kebab-case** (lowercase with hyphens). | `lec-01-intro.pdf` (✅) <br> `Lec 01 Intro.pdf` (❌) |
| **IDs** | Unique identifiers must follow the format: `[course]_[category]_[descriptor]` | `cis304_lec_05` <br> `mth101_note_formulas` |
| **Versions** | Do not use `v1`, `v2` in filenames unless essential. Overwrite the file or use Git history. | `assignment-01.pdf` |

---

## 3. The Schema Object structure

The JSON file consists of two main objects: `meta` (Course Info) and `resources` (File List).

### 3.1 The `meta` Object
Global information about the course context.

| Field | Type | Description | Example |
| :--- | :--- | :--- | :--- |
| `courseCode` | String | The official university code (Dept-Number). | `"CIS-304"` |
| `courseName` | String | Full official title of the course. | `"Computer Security"` |
| `department` | String | The root department folder. | `"BS-CIS"` |
| `semester` | Number | The semester number (1-8). | `5` |
| `lastUpdated` | String | ISO 8601 Date format. | `"2026-01-03"` |
| `maintainers` | Array | GitHub usernames of the primary contributors. | `["zohair-banoori"]` |

### 3.2 The `resources` Object
An array of file objects. Each entry maps to a physical file in the directory.

| Field | Type | Description | Allowed Values / Standard |
| :--- | :--- | :--- | :--- |
| `id` | String | Unique Key for the DB. | Format: `course_type_desc` |
| `filename` | String | Exact filename including extension. | Must match file on disk exactly. |
| `folder` | String | The sub-directory containing the file. | `lectures`, `books`, `code`, `notes`, `papers`, `labs` |
| `type` | String | Broad category for UI icons. | `slides`, `book`, `code`, `cheatsheet`, `paper`, `material` |
| `title` | String | Human-readable display title. | "Lecture 01: Intro to Python" |
| `description` | String | Brief context (1 sentence). | "Covers syntax and variables." |
| `tags` | Array | Keywords for filtering. | `core`, `supplementary`, `midterm-prep`, `final-prep` |
| `exclusions` | Array | List of omitted topics (see Section 4). | `[]` if none. |

---

## 4. Exclusion Logic
This feature allows us to "edit" a PDF without physically changing the file. We tell the user which parts to ignore.

### Exclusion Object Fields
* **`scope`**: What kind of data are we excluding?
* **`value`**: The specific numbers or text.
* **`reason`**: Why is it excluded? (Displayed to the student).

### Allowed Scopes

| Scope | Value Format | Use Case |
| :--- | :--- | :--- |
| **`pages`** | `"10-15"` or `"5, 9, 12"` | **Textbooks/PDFs.** Standard page ranges. |
| **`slides`** | `"3-5"` | **Lecture Decks.** Specific slide numbers to skip. |
| **`topic`** | `"MD5 Hashing"` | **General.** Marks a topic as "out of syllabus" regardless of where it appears. |
| **`whole_file`** | `"true"` | **Archives.** Keeps the file in the repo but hides it from the default "Active Material" download bundle. |

---

## 5. Golden Example
A complete, valid entry for a Lecture Slide with exclusions.

```json
{
  "id": "cis304_lec_05",
  "filename": "lec05-cryptography.pdf",
  "folder": "lectures",
  "type": "slides",
  "title": "Lecture 05: Cryptography Basics",
  "description": "Introduction to symmetric and asymmetric encryption.",
  "tags": ["core", "slides"],
  "exclusions": [
    {
      "scope": "pages",
      "value": "24-30",
      "reason": "Topic 'Legacy DES' removed from Spring 2026 syllabus."
    },
    {
      "scope": "topic",
      "value": "Rot13 Algorithm",
      "reason": "Removed by Prof. Ahmed as obsolete."
    }
  ]
}