# PARA (PIEAS Academic Resource Archive)

> *The open-source, community-driven academic archive for PIEAS—centralizing lectures, past papers, and syllabus resources into a searchable, version-controlled ecosystem.*

## About
PARA solves the fragmentation of academic resources at PIEAS. Instead of scattered WhatsApp files or broken links, PARA provides a **Headless Content Management System** where materials are:
1.  **Centralized:** Organized by Semester > Course.
2.  **Syllabus-Aware:** Metadata allows filtering of excluded/outdated topics.
3.  **Community-Maintained:** Students and alumni update the repo via Pull Requests.

## Directory Structure
The repository follows a strict hierarchy to ensure the search engine can parse it correctly:

```text
├── Semester 1/
│   ├── [Course Name]/
│   │   ├── syllabus.json      # Metadata (exclusions, topics)
│   │   ├── lectures/          # PDFs, PPTs
│   │   ├── diagrams/          # Images, Whiteboard snaps
│   │   └── code/              # Source code examples
├── docs/                      # Project Documentation
└── README.md
```

## Getting Started

### For Users (Students)
Currently, you can browse the folders manually to find resources. Coming Soon: The PARA Web Interface (Search Engine).

### For Contributors
We welcome contributions! Whether you are adding a missing past paper, fixing a typo in code, or updating a syllabus exclusion.

1. Fork this repository.
2. Clone your fork.
3. Create a Feature Branch.
4. Submit a Pull Request.

Please read our [CONTRIBUTING.md](CONTRIBUTING.md) before making changes.

## License

**1. The Code:**
The underlying source code, directory structure, and automation scripts of this repository are licensed under the **MIT License**. You are free to use this architecture to build archives for other departments or universities.

**2. The Content:**
Lecture slides, books, past papers, and other academic materials stored in this repository are the intellectual property of their respective authors (Professors, PIEAS, or Publishers).
* These files are shared strictly for **non-commercial, educational purposes** to facilitate student learning.
* If you are a copyright holder and wish to have your material removed, please open an Issue with the tag `copyright` and we will comply immediately.