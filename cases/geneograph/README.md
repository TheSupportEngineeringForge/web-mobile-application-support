# GeneoGraph - Product Overview & Support Engineering Research

## 1. Project Overview

**GeneoGraph** is a genealogy and family-history management application designed to help users organize, explore, and maintain information about family members, relationships, historical events, photographs, documents, research notes, and geographical locations.

The application provides a connected workspace in which genealogical information can be explored through multiple functional modules.

The currently available demonstration is accessible through a web browser. The product's positioning as a desktop application, its intended deployment model, and the relationship between the browser-based demo and any desktop implementation require clarification.

### Purpose of This Project

This project documents an ongoing, module-by-module examination of GeneoGraph from an **Application / Product Support Engineering perspective**.

Its objectives are to:

- Establish a functional understanding of the application.
- Document independently verified user workflows.
- Investigate application behavior through controlled reproduction.
- Examine HTTP requests, API interactions, and browser-side behavior where applicable.
- Identify inconsistencies, unexpected behavior, and potential defects.
- Collect reproducible technical evidence.
- Document findings and communicate relevant issues to the developer.

The initial Product Overview is based on the application's built-in guided walkthrough. Detailed functional verification and technical investigations will be documented separately.

## 2. Product Overview

GeneoGraph brings together several categories of genealogical information:

- People and family relationships.
- Family trees and genealogical structures.
- Historical and personal events.
- Photographs and albums.
- Research documents and archived files.
- Notes, hypotheses, and research tasks.
- Geographical locations and historical place names.
- Sources and supporting references.

The application's interface allows users to explore relationships between these categories rather than managing them exclusively as isolated records.

### Core Application Modules

#### Family Tree

A dedicated workspace for exploring family relationships and genealogical structures.

Detailed relationship-management operations, editing capabilities, and validation rules will be examined during independent functional testing.

#### People

A module for accessing and managing individual person records.

Person records are referenced throughout the application, including in photographs, historical events, notes, and geographical locations.

#### Geneograph

A separate module available through the application's primary navigation.

Its specific purpose, functionality, and relationship to the Family Tree module require further examination.

#### Albums

A workspace for organizing photographs associated with family history.

The guided walkthrough demonstrates:

- Browsing albums and photographs.
- Opening photo previews and detail panels.
- Viewing photo metadata, including titles, dates, locations, captions, dimensions, and file sizes.
- Tagging people in photographs.
- Identifying individuals within specific regions of an image.
- Managing photograph membership across albums.
- Accessing photo-related notes, sources, and metadata.
- Favourite and photo-management controls.

Photographs can be associated with people, albums, and places through the interface.

#### Archive

A hierarchical workspace for organizing research documents, files, and supporting materials.

The guided walkthrough demonstrates:

- Folder-based file organization.
- Navigation through folders and subfolders.
- Breadcrumb navigation and folder history controls.
- Creating folders and selecting their parent locations.
- File lists with descriptive metadata.
- File preview and detail panels.
- Search and filtering by file attributes and associated records.
- Favourites and Sources navigation.
- File-related references to people, events, and notes.

Archive provides a dedicated structure for managing supporting research materials.

#### Notes

A workspace for documenting research findings, observations, hypotheses, and follow-up tasks.

The guided walkthrough demonstrates:

- Creating and organizing notes.
- Rich-text editing and formatting controls.
- Checklists for research tasks.
- Grouping notes into collections.
- Search, filtering, sorting, favourites, and archiving.
- Associating notes with people, events, photographs, files, places, sources, and other notes.

The interface also presents workflows for selecting specific events associated with a person.

Notes therefore function as interconnected research records rather than standalone text entries.

#### Places

A geographical workspace for exploring and organizing locations associated with genealogical information.

The guided walkthrough demonstrates:

- Interactive map and location markers.
- Map and list-based navigation.
- Grouping locations by country.
- Place search and filtering.
- Saved filters.
- Route-related functionality.
- Place creation and editing interfaces.
- Geographic coordinates and manual map positioning.
- Historical and alternative place names.
- Place details containing references to associated records.
- Indicators for places requiring review.

Place details expose relationships with people, events, photographs, files, notes, and sources.

The map interface displays attribution to **Leaflet, MapTiler, and OpenStreetMap contributors**. The actual integration architecture and network behavior have not yet been investigated.

## 3. Cross-Module Data Relationships

The guided walkthrough demonstrates that GeneoGraph uses interconnected records across its functional modules.

| Entity | Relationships presented in the interface |
|---|---|
| Person | Family relationships, events, photographs, places, notes |
| Photo | People, albums, places, notes, sources |
| Album | Photographs |
| Archive file | Folders, people, events, notes, places |
| Note | People, events, photos, files, places, sources, other notes |
| Place | People, events, photos, files, notes, sources |
| Event | People, places, notes |
| Source | References from research-related records |

These relationships represent functionality presented through the user interface and guided tour.

They do not establish the application's underlying database schema, API design, relationship constraints, or data-persistence mechanisms.

## 4. Documentation Structure

The project is organized by application module.

Each module will maintain its own functional documentation, technical investigations, and supporting evidence.

```text
cases/
└── geneograph/
    ├── README.md
    └── modules/
        ├── family-tree/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        │       └── case-01/
        │           ├── README.md
        │           └── evidence/
        ├── people/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        ├── geneograph/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        ├── albums/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        ├── archive/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        ├── notes/
        │   ├── README.md
        │   ├── evidence/
        │   └── investigations/
        └── places/
            ├── README.md
            ├── evidence/
            └── investigations/
```

The directory tree represents the intended project architecture. Individual module directories and investigation files will be created as research progresses.

### Documentation Levels

**General Product Overview**

This README provides the overall functional context based on the guided walkthrough.

**Detailed Module Overview**

Each module's README will document independently investigated functionality, user workflows, expected behavior, data relationships, and observed limitations.

**Technical Investigations**

Individual investigations will document specific scenarios, reproduction steps, technical evidence, findings, and validation results.

**Evidence Organization**

Two levels of evidence are maintained:

- `modules/<module>/evidence/` — evidence supporting general module-level functional observations.
- `modules/<module>/investigations/<case>/evidence/` — evidence associated with a specific technical investigation.

This structure keeps functional observations and case-specific technical evidence separate.

## 5. Module Documentation Index

Detailed module documentation will be linked here as independent investigation progresses.

| Module | Detailed Documentation | Status |
|---|---|---|
| Family Tree | Not yet published | Guided walkthrough reviewed |
| People | Not yet published | Guided walkthrough reviewed |
| Geneograph | Not yet published | Guided walkthrough reviewed |
| Albums | Not yet published | Guided walkthrough reviewed |
| Archive | Not yet published | Guided walkthrough reviewed |
| Notes | Not yet published | Guided walkthrough reviewed |
| Places | Not yet published | Guided walkthrough reviewed |

Module README links will be added when the corresponding documentation becomes available.

## 6. Open Questions & Clarifications

This section tracks product-related questions identified during the initial review and subsequent investigations.

Questions remain open until they are clarified by the developer or resolved through supported technical evidence.

### 6.1 Product Architecture & Functionality

| ID | Area | Question | Status |
|---|---|---|---|
| Q-001 | Product Positioning | GeneoGraph is presented as a desktop application, but the available demo runs in a browser without installation. Is the browser version a standalone product, a demonstration of a desktop application, or part of a planned cross-platform solution? | Open |
| Q-002 | Data Storage | Where is genealogical project data stored: locally on the user's device, on remote servers, or through a hybrid storage model? | Open |
| Q-003 | Demo Scope | Which features are fully functional in the current demonstration, and are any operations restricted or simulated? | Open |
| Q-004 | Application Architecture | Does the browser-based application communicate with backend APIs, or are some operations processed entirely on the client side? | Open |
| Q-005 | Geneograph Module | What is the intended functional distinction between Geneograph and Family Tree? | Open |
| Q-006 | Map Integration | Which mapping, geocoding, and geographical search operations rely on external services, and how are these integrations configured? | Open |

### 6.2 Data Privacy, Storage & Security

GeneoGraph may process personal information relating not only to registered users but also to their family members and other individuals represented in genealogical records.

Potentially sensitive information includes names, dates of birth, family relationships, photographs, geographical information, and historical documents.

The following questions aim to clarify the application's data-handling practices, privacy safeguards, and user controls.

| ID | Area | Question | Status |
|---|---|---|---|
| Q-007 | Data Privacy | What personal data is collected, processed, and retained by the application? | Open |
| Q-008 | GDPR & Compliance | What privacy policies and GDPR-related safeguards are implemented or planned for the product? | Open |
| Q-009 | Data Security | How is personal data protected during transmission and storage? | Open |
| Q-010 | Data Sharing | Are genealogical records private by default? How can users share them, and what access controls are available? | Open |
| Q-011 | Data Ownership & Deletion | Can users export and permanently delete their genealogical data, including associated files and photographs? | Open |
| Q-012 | Third-party Services | Which external services receive user data, and what information is transmitted to them? | Open |

These questions do not imply that security, privacy, or compliance deficiencies have been identified.

Their purpose is to establish the product's intended behavior and documented data-handling practices before conducting related technical investigations.

### Question Statuses

- **Open** — clarification or investigation required.
- **Clarified** — supported answer documented.
- **Closed** — resolved through verification or no longer applicable.

Answers and supporting references will be added as information becomes available.

## 7. Planned Technical Investigation Areas

Potential investigation areas identified during the guided walkthrough include:

**Authentication and session behavior**

Login and logout flows, session persistence, authorization behavior, and error handling, where applicable.

**File and photo management**

Upload requests, file validation, metadata handling, file associations, and error responses.

**Cross-module data consistency**

Behavior of linked records across People, Albums, Notes, Archive, and Places.

**Search and filtering**

Filter combinations, search results, saved filters, and UI state consistency.

**Mapping and geographical services**

Map loading, tile requests, location search, coordinate handling, markers, and external service responses.

**Record creation and editing**

Input validation, saving, updates, deletion behavior, and persistence.

**Data Privacy, Storage & Security**

Investigation of observable data-storage behavior, browser-side persistence, session-related data handling, network transmission, third-party service interactions, and user-facing data export or deletion workflows, where available.

The investigation will focus on technically verifiable application behavior and will not constitute a formal security audit or GDPR compliance assessment.

These are candidate investigation areas rather than confirmed issues or completed tests.

## 8. Research Methodology

Technical investigations will follow a consistent workflow:

1. Define the functional or business scenario.
2. Identify the expected behavior.
3. Reproduce the scenario under controlled conditions.
4. Examine browser, network, or application evidence as applicable.
5. Compare expected and observed behavior.
6. Document findings, limitations, and remaining uncertainties.
7. Validate the outcome and communicate relevant issues to the developer.

Where a root cause cannot be established from available evidence, the investigation will distinguish confirmed observations from hypotheses.

An investigation does not require a defect to be considered complete. Verified expected behavior can also provide useful technical documentation.

## 9. Current Research Status

**Phase:** Initial Product Discovery completed; independent functional investigation pending.

Completed:

- Reviewed the built-in guided walkthrough.
- Identified seven primary application modules.
- Documented the principal UI capabilities presented by the tour.
- Identified cross-module record relationships.
- Identified the mapping technologies attributed in the interface.
- Established the documentation architecture and initial investigation scope.

Not yet completed:

- Independent end-to-end functional testing.
- Authentication and session analysis.
- API and network traffic investigation.
- Data persistence verification.
- Reproducible technical investigations.
- Developer clarification of open product questions.

No application defects have been confirmed at this stage.

## 10. Collaboration and Publication

This is an independent Support Engineering research project conducted with the developer's permission to reference GeneoGraph by name and publish illustrative examples and ongoing project updates.

Relevant technical findings may be discussed through GitHub Issues or linked investigation documentation.

Published evidence will exclude credentials, authentication tokens, sensitive user data, and other information that should not be publicly disclosed.

Potential security-sensitive findings will be handled separately rather than disclosed through public issue reports.

---

**Documentation principle:** The business scenarios are simulated where necessary. The technical implementation is real.
