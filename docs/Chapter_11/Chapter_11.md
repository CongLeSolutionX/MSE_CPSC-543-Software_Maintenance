---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

----

# Chapter 11: Configuration Management

Below are diagrams and illustrations provide a visual summary of Chapter 11, breaking down the concepts of Configuration Management and Change Control into understandable segments using Mermaid syntax.


----


# Diagram 1: Configuration Management - Mindmap

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Chapter 11:<br>Configuration Management))
    node(Introduction)
      label(Importance of CM)
      label(Control of Software Change)
      label(Maintaining Product Integrity)
    node(Definitions)
      label(Key Terminology)
        label(Configuration)
        label("Configuration Management <br> (CM)")
        label(Software Configuration)
        label("Software Configuration Management <br> (SCM)")
        label(Baseline)
        label(Version)
        label(Variant)
        label(Change Control)
        label(Documentation)
        label(Life-Cycle)
        label(Process)
        label(Model)
        label(Software Maintenance Process)
    node(Configuration Management)
      label(Purpose of CM)
        label(Control of Evolution)
        label(Product Reproducibility)
      label(Objectives of CM)
        label(Control)
        label(Consistency)
          label(Consistent Sets of Documents)
          label(Consistent Software Releases)
        label(Minimising Cost)
      label(Components of Software Configuration Management)
        label(Version Control)
        label(Building)
        label(Environment Management)
        label(Process Control)
    node(Change Control)
      label(Definition & Purpose)
      label(Activities of Change Control)
        label(Selection from Priority List)
        label(Problem Reproduction)
        label(Code Analysis)
        label(Change Incorporation)
        label(Design of Changes & Tests)
        label(Quality Assurance)
      label(Management Responsibilities)
        label(Deciding if Change is Needed)
        label(Managing Implementation)
        label(Verifying Quality)
    node(Documentation)
      label(Importance of Documentation in CM)
      node(Categories)
        label(User Documentation)
          label(System Overview)
          label(Installation Guide)
          label(Beginner's Guide/Tutorial)
          label(Reference Guide)
          label(Enhancement Booklet)
          label(Quick Reference Card)
          label(System Administration)
        node(System Documentation)
          label(Specification/Requirements)
          label(Design)
          label(Implementation)
          label(System Test Plan)
          label(Acceptance Test Plan)
          label(Data Dictionaries)
    node(Summary)
      label(Key Takeaways of Chapter 11)

```


This mindmap provides a hierarchical overview of Chapter 11, starting with the core concept of Configuration Management and branching out to cover definitions, objectives, key components, Change Control and the pivotal role of Documentation within CM.

---

# Diagram 2: Configuration Management Processes

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Configuration Management] --> B(Version Control);
    A --> C(Building);
    A --> D(Environment Management);
    A --> E(Process Control);

    style A fill:#c3cf,stroke:#333,stroke-width:1px

    B --> B1[Identify Configuration Items];
    B1 --> B2["Version Numbering/Naming"];
    B2 --> B3[Change Logging];
    B3 --> B4[Access Control];
    B4 --> B5[Branching & Merging];

    C --> C1[Automated Build Scripts];
    C1 --> C2[Dependency Management];
    C2 --> C3[Reproducible Builds];
    C3 --> C4[Build Documentation];

    D --> D1[Controlled Workspaces];
    D1 --> D2[Isolation of Changes];
    D2 --> D3[Reproducible Environments];
    D3 --> D4[Shared Repository Access];

    E --> E1[Change Request Management];
    E1 --> E2[Process Enforcement];
    E2 --> E3[Audit Trails];
    E3 --> E4["Reporting & Status"];
    
```


This flowchart illustrates the four core processes within Configuration Management as presented in Chapter 11. For each process (Version Control, Building, Environment Management, Process Control), it outlines key sub-activities and goals, providing a clearer picture of their respective roles in CM.

---

# Diagram 3: Change Control Process

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Change Request Triggered];
    B["Change Request Submitted & Logged"];
    C["Initial Impact Analysis & Costing"];
    D["Change Control Board (CCB) Review"];
    E{"Approve/Reject Change?"};
    F["Change Planning & Scheduling"];
    G["Change Request Rejected & <br>Archived"];
    H["Detailed Impact Analysis & <br>Resource Allocation"];
    I["Change Implementation <br> (Code, Docs, Tests)"];
    J["Testing & <br>Quality Assurance"];
    K["Review & <br>Approval of Change"];
    L["Configuration Update & <br>Version Control"];
    M["Release & Deployment <br>(if applicable)"];
    N["Post-Implementation Review"];
    O["Change Control Process Complete"];

    A --> B
    B --> C
    C --> D
    D --> E
    E -- Approve --> F
    E -- Reject --> G
    F --> H
    H --> I
    I --> J
    J --> K
    K --> L
    L --> M
    M --> N
    N --> O


	classDef Process fill:#c359,stroke:#333,stroke-width:1px
    class A,B,C,D,F,H,I,J,K,L,M,N,O Process
    
    style E fill:#f3d9,stroke:#333,stroke-width:1px
    style G fill:#f33c,stroke:#333,stroke-width:1px
    
```


This flowchart details the steps within a typical Change Control process, as discussed in Chapter 11. It begins with a change request and progresses through submission, impact analysis, CCB review, implementation, testing, approval, and finalization, clearly showing the workflow and decision points.  Color-coding is used to highlight decision points (yellow) and rejection paths (red).

---


# Diagram 4: Version Control Activities

```mermaid
---
config:
  look: handDrawn
  theme: dark
---
graph LR
    A[Version Control];
    B{Initial Check-In};
    C[Create Baseline];
    D{Object Modification Needed};
    F{Check-Out Object};
    G[Continue with Current Version];
    H[Developer Edits Object];
    I[Compare To Prior Version];
    J{"Merge if Needed?"};
    K[Merge New Changes];
    L[Continue to Check-In];
    M[Check-In Object and New Version Created];
    N[Update Version History];
    O[Make Check-in notes];
    P[Updated Baseline and History Files];


    A --> B
    B --> C
    C --> D
    D -- Yes --> F
    D -- No --> G
    
    F --> H
    H --> I
    I --> J
    J -- Yes --> K
    J -- No --> L
	
    K --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P --> D

    classDef Decision_Point fill:#9398,stroke:#333,stroke-width:2px;
    class D,J Decision_Point

    classDef No_Choice fill:#f998,stroke:#33,stroke-width:2px;
    class G,L No_Choice;

    classDef Yes_Choice fill:#f118,stroke:#33,stroke-width:2px;
    class F,K Yes_Choice;
    
```

This flowchart illustrates the step-by-step process of version control, from initial check-in to creating a new version. It includes decision points for modification needs and highlights steps for merging code changes and updating history.

---

# Diagram 5: Types of Documentation

```mermaid
---
config:
 themeVariables:
      darkMode: true
---
table Diagram
    title Chapter 11: Documentation Types
    header  Type | Description | Intended Audience
    row User Documentation | Describes system functions from user perspective without implementation details | End-Users/Clients
    row System Documentation | Describes all aspects of the system &  how it works under the hood | Developers, Maintainers, Technical Staff
    row System Overview | Provides a broad overview of  system function, usage | End-Users, Management
    row Installation guide | Detailed explanation to setup & configure a specific system | System Admins, Technical Staff
    row Beginner's guide/tutorial | Provides basic instructions with a guided learning approach for general use | New Users, non-technical staff
    row Reference Guide | Detailed documentation on individual features and function  | All Users, Technical Staff
    row Enhancement Booklet | Summary of the new features and improvements | End-Users
    row Quick Reference Card | Short factual lookup and reminder on key points| All Users
    row System Administration Guide | Detailed guide of  administration of operation, security and upgrades | System Admins, Technical Staff
    row Functional Specification | Details of the functional and non functional requirements, agreements| Project Stakeholders, Developers
    row System Design Documentation | System Architecture, Design Details & interactions| Programmers, Designers, QA
    row Implementation Documentation | Technical details on source code organization, implementation guidelines | Developers, fellow code reviewers
    row System test plan | Strategies, and procedures on how to test | Verification Teams, Testers
    row Acceptance test plan | Documents tests and conditions for user acceptance | Stakeholders, Clients & End Users
    row Data Dictionaries | Documents describing  all data terms, structure and requirements | Developers, DBAs, Data Scientists

```


This table summarizes various categories of user and system documentation as described in Chapter 11. It outlines what is included in each type of document and who the intended audience is, and explains its purpose

---

# Diagram 6: Software Configuration Management Components

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Software Configuration Management Components))
        node(Version Control)
          label(Identify different versions, Changes, History)
          label(Support Parallel Development)
          label(Branching & Merging)
          label(Manage and Track changes)
        node(Building)
          label(Reproducible Builds)
          label(Ensure appropriate objects & Versions are used)
          label(Automated Build Scripts)
          label(Dependency Management)
        node(Environment Management)
          label(Reproducible Environments)
          label(Controlled Workspaces)
          label(Share & Isolate Objects)
        node(Process Control)
          label(Manage & Enforce Processes)
          label(Change Request & Reporting)
          label(Audit Trails)

```

This mindmap visually structures the four main components of Software Configuration Management as mentioned in Chapter 11, (Version Control, Building, Environment Management, and Process Control). For each, it details key functions and goals in a clear and concise manner.

---

# Diagram 7: Version Control Concepts

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Main Branch];
    B[Version 1];
    C[Version 2 - Update 1];
    D[Branch A];
    E[Version 3 - Update 2];
    F[Version 2.1 - Bug Fix];
    G[Version 2.2 - Branch A Updated];
    H[Version 4 - MainBranch Update];
    I[Version 4.1];

    A --> B
    B --> C
    B --> D
    C --> E
    D --> F
    F --> G
    E --> H
    H --> I

    classDef MainBranch fill:#f3f9,stroke:#333,stroke-width:1px
    class A MainBranch

    classDef Version1 fill:#f329,stroke:#333,stroke-width:1px
    class B Version1

    classDef Version2 fill:#f399,stroke:#333,stroke-width:1px
    class C,F,G Version2

    classDef Version3 fill:#f114,stroke:#333,stroke-width:1px
    class E Version3

    classDef Version4 fill:#119,stroke:#333,stroke-width:1px
    class H,I Version4

```

This diagram gives a visual, non-technical example of branching in version control, showing a development path and how new versions and branches can appear as a result of updates, bug fixes, and new features. This more illustrates in practice what is represented in Chapter 11 as part of the software CM, especially in the version control sections.




----
