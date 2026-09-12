# 🗂️ Simplified Git Version Control System (SGVCS) — OOAD Design Project

![Status](https://img.shields.io/badge/Status-Academic%20Project-brightgreen.svg)
![Type](https://img.shields.io/badge/Type-Design%20Documentation-orange.svg)
![UML](https://img.shields.io/badge/UML-Complete%20Suite-blue.svg)

A complete **Object-Oriented Analysis and Design (OOAD)** documentation package modeling a **Simplified Git Version Control System** — covering functional requirements, structural design, and behavioral modeling through a full suite of UML diagrams. Developed as a group project for an OOAD course.

---

## 📋 About This Project

This repository contains a documentation-only deliverable — there is no implementation, only the complete design specification. The goal was to apply core OOAD principles (encapsulation, state management, modular design, separation of concerns) to model the essential mechanisms behind a real-world tool: Git.

**System modeled:** A simplified version control system supporting local operations (init, add, commit, status), branching and merging, and distributed collaboration (clone, push, pull) with role-based access control.

## 📖 Document Structure

| Section | Contents |
|---|---|
| **1. Executive Summary & System Overview** | Problem statement, project goals, system actors (Developer, Administrator) |
| **2–3. Functional Requirements** | 10 use cases (UC-01 to UC-10) covering local operations, branching/merging, and network operations, with use case diagrams |
| **4. Behavioral Analysis (Activity Modeling)** | System-level workflow, swimlane diagram, and detailed activity diagrams for repository initialization, staging, status monitoring, branch creation/switching/merging, and cloning |
| **5. Structural Modeling (Class Diagram)** | High-fidelity class diagram defining `Repository`, `Branch`, `Commit`, `StagingArea`, `File`, `RemoteServer`, and `User`, with composition, aggregation, and association relationships |
| **6. Behavioral Modeling (Sequence Diagrams)** | Sequence diagrams for Commit Changes, Merge Branches, Push to Remote, and Clone Repository, plus a system-wide collaboration map |
| **7. Collaboration Diagram** | Communication diagram showing the CLI Interface, Repository Manager, Staging Manager, Commit Manager, Merge Manager, and Remote Manager coordinating a full command lifecycle |
| **8. State Diagrams** | Five state machines: Git file lifecycle, repository lifecycle, branch lifecycle, merge process, and remote access control (permission states) |
| **9. Component Diagram** | Ten system components (CLI Interface, Branch Manager, File System Access, Repository Manager, Staging Manager, Commit Manager, Merge Manager, Remote Manager, Status Tracker, Authentication) with their responsibilities |

## 🏗️ Key Design Decisions

- **Centralized coordination** — the `Repository` class acts as the central controller/orchestrator, delegating tasks to specialized components (`StagingArea`, `Commit`, `RemoteServer`) rather than allowing components to call each other directly
- **Immutable snapshots** — `Commit` objects persist an immutable list of `File` states, enabling "time-travel" (reverting to any past commit)
- **Separation of concerns** — network synchronization logic (`RemoteServer`) is kept isolated from local versioning logic, and role-based access (`User`: Developer vs. Administrator) gates sensitive operations
- **Conflict-safe merging** — the merge workflow explicitly models conflict detection and forces manual resolution before a merge commit is created, preventing silent data loss

## 👥 System Actors

- **Developer** (Primary) — manages the local repository, performs commits, and synchronizes with remote servers
- **Administrator** (Secondary) — configures remote repository access rights and server-side permissions

## 📚 What We Learned

- Translating a real-world tool's behavior into a full OOAD artifact set — use case, activity, class, sequence, state, and component diagrams — rather than jumping straight to code
- Modeling object relationships precisely (composition vs. aggregation vs. association) and understanding why each fits a given relationship (e.g., Repository *composes* Branches, but Branch *aggregates* Commits)
- Designing conflict-safe, state-driven workflows (merge conflict resolution, branch switching with uncommitted-changes checks)
- Collaborating as a team to produce a single, consistent design specification across multiple diagram types

## 🎓 Course

Object-Oriented Analysis and Design (OOAD) — BS Computer Science
*Group Project*

## 👩‍💻 Team

- Fabiya Noor
- Fatima Idrees
- **Fatima Nadeem**
- Zainab Shahid

**Submitted to:** Dr. Komal Bashir
**Department of Computer Science, Lahore College for Women University**

## 📄 File

- [`Simplified_Git_VCS_OOAD_Report.pdf`](./Simplified_Git_VCS_OOAD_Report.pdf) — full design documentation

## 📎 Notes

- This is a documentation-only academic deliverable; no implementation is included
- All diagrams follow standard UML notation
