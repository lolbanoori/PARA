# Project Proposal: The PIEAS Academic Resource Archive (PARA)
**Date:** January 3<sup>rd</sup>, 2026

**Author:** [Syed Zohair Ali Shah Banoori](https://github.com/lolbanoori)
## 1. Executive Summary
**PARA (PIEAS Academic Resource Archive)** is a proposed open-source initiative designed to solve the chronic fragmentation of academic resources at the Pakistan Institute of Engineering and Applied Sciences (PIEAS). By leveraging modern version control systems (`Git`) and a headless content architecture, PARA aims to create a centralized, student-maintained repository for lectures, past papers, and diagrams. This system ensures data persistence, syllabus accuracy, and equitable access for all students, regardless of their network location.

## 2. Problem Statement
Currently, the distribution of academic material suffers from critical inefficiencies:

* **Fragmentation:** Resources are scattered across ephemeral WhatsApp groups, restricted local file servers (inaccessible to day-scholars), and inconsistent LMS uploads.
* **Data Loss:** Valuable resources, particularly past papers and supplementary notes, are lost as senior batches graduate.
* **Syllabus Ambiguity:** Lecture slides often contain material that is excluded from the final syllabus. Students struggle to identify exactly which sub-topics are relevant for examinations.
* **Access Barriers:** Pre-reading material is rarely available before lectures are delivered.

## 3. The Solution: A "Headless" Archive
PARA is not just a file storage folder; it is an intelligent **Content Management System (CMS)** built on the "Infrastructure as Code" philosophy.

### 3.1 Core Features
* **Centralized Repository:** A structured hierarchy organized by logical academic flow:
    ```text
    Semester > Course > Material Type (Lectures, Labs, Code, Books)
    ```
* **Syllabus-Aware Filtering:** A unique metadata layer allows students to filter out "excluded topics" or "omitted slides" based on the current academic year's curriculum.
* **Universal Access:** Hosted on GitHub, ensuring availability outside the campus network.
* **Legacy Protection:** A version-controlled history ensures that even if professors change, the archive retains previous versions of knowledge.

### 3.2 Technical Architecture
To achieve the requirement of a "Search Engine" with "Smart Zipping" capabilities, PARA utilizes a Headless Architecture.

**The Backend (Source of Truth)**
```yaml
Platform: GitHub (lolbanoori/PARA)
Role: Stores raw files (PDFs, PPTs) and JSON metadata.
Integrity: Protected by strict "Pull Request" protocols. Direct pushes to the main branch are forbidden.
```

### 3.3 The Frontend (User Experience)
```yaml
Platform: Next.js Web Application (Planned)
Role: Fetches data from repo via API.
Capabilities: Search interface, syllabus exclusion processing, custom ZIP generation.
```

## 4. Operational Strategy
Maintenance is critical for longevity. We will adopt industry-standard DevOps practices:
1. **Community-Driven:** Any student can contribute. To maintain quality, we enforce Issue-Driven Development: a ticket must be created to define the addition before code/files are submitted.
2. **Quality Assurance:** All contributions are vetted via Code Reviews and Pull Requests. A Maintainer must approve changes before they enter the `main` branch.
3. **Scalability:** The pilot phase targets the BS-CIS department. The directory structure is designed to scale horizontally to other departments (BS-EE, BS-ME) without architectural changes.

## 5. Roadmap
* **Phase 1 (Foundation):** Repository initialization, directory scaffolding for Semester 1 & 2, and defining the `syllabus.json` metadata schema (see [SYLLABUS-METADATA.md](SYLLABUS-METADATA.md)).
* **Phase 2 (Content Population):** Mobilizing initial contributors to populate the `CIS/` directory.
* **Phase 3 (Platform Launch):** Development and deployment of the Web Interface (Search Engine).

## 6. Conclusion
PARA represents a shift from "hoarding knowledge" to "distributing knowledge." By treating academic notes with the same rigor as production-grade software, we create a sustainable asset that serves current students and future generations at PIEAS.