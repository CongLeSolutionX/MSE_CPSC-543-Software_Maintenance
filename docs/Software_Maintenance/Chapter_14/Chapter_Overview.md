---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

# Chapter 14: Maintenance Tools

## Diagram 1: Criteria for Selecting Tools - Mindmap

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Chapter 14: Criteria for Selecting Tools))
    node(Capability)
      label(Supports required tasks)
      label(Technique works without tool first)
    node(Features)
      label(Essential functions offered)
      label(Rating feature importance)
    node(Cost and Benefits)
      label(Cost vs. Benefits Evaluation)
        label(Quality Improvement)
        label(Productivity Gains)
        label(Responsiveness)
        label(Cost Reduction)
        label(Overlap/Dichotomy Reduction)
    node(Platform)
      label(Hardware Platform)
      label(Software Environment)
      label(Compatibility)
    node(Programming Language)
      label(Supported Languages)
      label(Industry Standard Support)
      label(Paradigm Compatibility - e.g., OO)
    node(Ease of Use)
      label(User Friendliness)
      label(Learning Curve)
      label(Similarity to Familiar Tools)
    node(Openness of Architecture)
      label(Integration with Other Tools)
      label(Extensibility)
      label(Flexibility)
      label(Avoid Proprietary Lock-in)
    node(Stability of Vendor)
      label(Vendor Reputation)
      label(Longevity and Support)
      label(Company Background)
    node(Organizational Culture)
      label(Alignment with Work Patterns)
      label(User Acceptability)
      label(Cultural Fit)

```


This mindmap outlines the criteria for selecting maintenance tools as discussed in Chapter 14, including Capability, Features, Cost & Benefits, Platform, Programming Language, Ease of Use, Openness, Vendor Stability and Organisational Culture, providing a comprehensive overview for tool evaluation.

---

## Diagram 2: Taxonomy of Maintenance Tools

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Chapter 14: Taxonomy of Maintenance Tools))
    node(Comprehension & Reverse Engineering Tools)
      label(Goal: Program Understanding)
      node(Program Slicer)
        label(Focus: Relevant Code Sections)
        label(Highlight Affected Code)
      node("Static Analyser <br> (Browser)")
        label(Focus: Program Text Examination)
        label(Code Browsing)
        label(Summaries of Program Elements)
      node("Dynamic Analyser <br> (Tracer)")
        label(Focus: Program Execution Behaviour)
        label(Execution Path Tracing)
        label(Dynamic System Characteristics)
      node(Data Flow Analyser)
        label(Focus: Data & Control Flow)
        label(Track Data & Control Paths)
        label(Ripple Effect Analysis)
      node(Cross-Referencer)
        label(Focus: Program Entity Usage)
        label(Index of Entity Usage)
        label(Declaration & Usage Tracking)
      node(Dependency Analyser)
        label(Focus: Inter-Entity Relationships)
        label(Dependency Database)
        label(Graphical Representation)
      node(Transformation Tool)
        label(Focus: Representation Conversion)
        label(Code to Visual & vice versa)
        label(Browsing & Editing Capabilities)
    node(Testing Tools)
      label(Goal: Support Testing Process)
      node(Simulator)
        label(Focus: Controlled Test Environment)
        label(Simulate System)
        label(Rich Tool Set)
      node(Test Case Generator)
        label(Focus: Test Data Creation)
        label(Automated Test Data Generation)
        label(Criteria-Based Generation)
      node(Test Paths Generator)
        label(Focus: Path Coverage)
        label(Identify Data & Control Flow Paths)
        label(Path Selection Criteria)
    node(Configuration Management Tools)
      label(Goal: Control Software Change)
      node("Version Control System <br> (e.g., SCCS)")
        label(Focus: Object Version Tracking)
        label(History Files)
        label(Version & Variant Management)
        label(Parallel Development Support)
      node(Build Tools)
        label(Focus: System Building & Rebuilding)
        label(Automated Build Process)
        label(Minimal Rebuilding)
      node(Environment Management)
        label(Focus: File System Control)
        label(Reproducible Environments)
        label(Object Sharing & Isolation)
    node(Other Task Support Tools)
      label(Documentation Tools)
        label(Hypertext Tools)
        label(Chart Generators)
        label(Requirements Tracers)
        label(CASE Tools)
      node(Complexity Assessment Tools)
        label(Complexity Quantifiers)
        label(Automated Complexity Measurement)
        label(e.g., McCabe's Cyclomatic, Halstead's)

```

This mindmap illustrates the taxonomy of maintenance tools, categorizing them by their primary function as discussed in Chapter 14. Categories include tools for Comprehension & Reverse Engineering, Testing, Configuration Management and Other Task Support, further detailing specific tool types and their features within each category.


---


## Diagram 3: Reverse Engineering Process with Tools

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Start: Legacy System Code] --> B{Reverse Engineering Tools};
    B --> C[Code Parsers & Analysers];
    C --> D["Abstract Syntax Tree <br> (AST)"];
    D --> E{Redocumentation Tools};
    D --> F{Design Recovery Tools};
    E --> G[Redocumentation Output];
    F --> H[Design Model Output];
    B --> I[Data Extraction Tools];
    I --> J[Data Repositories];
    J --> K{Visualization Tools};
    K --> L[Improved Program Understanding];
    L --> M[Maintenance & Evolution Tasks];
    
    style A fill:#f3bf,stroke:#333,stroke-width:1px
    style M fill:#f3bf,stroke:#333,stroke-width:1px
    
    classDef Element fill:#e3ff,stroke:#333,stroke-width:1px
    class G,H,J,L Element

	classDef AnotherElement fill:#a3ef,stroke:#333,stroke-width:1px
    class B,C,D,E,F,I,K AnotherElement
    
```


This flowchart illustrates a typical Reverse Engineering process, highlighting the role of various tools. It starts with Legacy System Code, moves through Reverse Engineering Tools like Parsers, Analysers, Data Extraction Tools, and Visualization Tools, showing the progression from code to improved understanding and finally to Maintenance & Evolution Tasks.

---

## Table: Tool Categories and Benefits

```mermaid
---
config:
    themeVariables:
      darkMode: true
---
table Diagram
    title Chapter 14: Tool Categories and Benefits
    header Tool Category | Primary Benefit | Key Functionality | Examples
    row Program Comprehension & Reverse Engineering Tools | Enhanced Understanding of Existing Systems | Code Analysis, Visualization, Abstraction | Program Slicers, Static Analysers, Dynamic Analysers, Cross-Referencers
    row Testing Tools | Improved Software Quality & Reliability | Automated Test Creation, Execution, and Analysis | Simulators, Test Case Generators, Test Paths Generators
    row Configuration Management Tools | Controlled Software Evolution & Change Management | Version Control, Build Management, Environment Management | SCCS, RCS, Build Automation Scripts
    row Documentation Tools | Improved Communication & Knowledge Sharing | Automated Documentation Generation, Hyperlinking, Requirements Tracing | Hypertext Tools, Chart Generators, CASE Tools
    row Complexity Assessment Tools | Quantitative Analysis of Code & System Complexity | Complexity Measurement, Metric Calculation, Code Quality Evaluation | McCabe's Cyclomatic Complexity Tools, Halstead's Measures Tools
    
```

This table provides a concise overview of the Tool Categories from Chapter 14, outlining the Primary Benefit of each category, its Key Functionality and Examples of tools within each category, facilitating a quick comparison of different tool types.



---

## Table: Comparison of Example Maintenance Tools

```mermaid
---
config:
    themeVariables:
      darkMode: true
---
table Tool Categories & Example Tools
    header Category | Tool | Description
    row Comprehension | Program Slicer | Extracts relevant code sections
    row Comprehension | Static Analyser | Examines code structure, metrics, etc.
    row Reverse Engineering  | Design Recovery Tool | Extracts design information from code
    row Testing | Test Case Generator | Automates test data creation
    row Testing | Simulator | Creates controlled testing environment
    row Configuration Management | SCCS/RCS/CVS | Version control systems
    row Configuration Management | Build Tools (e.g., Make) | Automate system building processes
    row Other | Documentation generators | Automate documentation creation
    row Other | Complexity Measurement Tools | Calculate code complexity metrics
```

This table provides a summary of example maintenance tools categorized according to the taxonomy in the chapter.  It lists examples from different categories such as Comprehension, Reverse Engineering, Testing, Configuration Management and other tasks, giving a quick comparative reference.


---

## Diagram 4: Example SCCS Workflow in Configuration Management

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Start];
    B{"File Exists in SCCS?"};
    C["Check out file<br>(sccs get)"];
    D["Add file to SCCS<br>(sccs create)"];
    E[Edit File];
    F["Check In File<br>(sccs delta)"];
    G[End];

    A --> B
    B -- Yes --> C
    B -- No --> D
    C --> E
    D --> E
    E --> F
    F --> G
    
    classDef Start_and_End_Point fill:#1919,stroke:#333,stroke-width:2px;
    class A,G Start_and_End_Point;

    classDef Decision_Point fill:#9398,stroke:#333,stroke-width:2px;
    class B Decision_Point

    classDef Yes_Choice fill:#f118,stroke:#33,stroke-width:2px;
    class C Yes_Choice;

    classDef No_Choice fill:#f998,stroke:#33,stroke-width:2px;
    class D No_Choice;
    
```


This flowchart represents a simplified example of a workflow using SCCS (Source Code Control System) for version control, illustrating the processes involved in adding a new file to SCCS, checking out a file for editing, making changes and then checking back in the updated version.

---


## Diagram 5: Benefits of Using Maintenance Tools

```mermaid
---
config:
  theme: dark
---
mindmap
root((Benefits of Using Maintenance Tools))
  node(Increased Productivity)
    label(Faster Task Completion)
    label(Automated Processes)
  node(Improved Quality)
    label(Reduced Errors)
    label(Enhanced Reliability)
    label(Better Maintainability)
  node(Better Control and Management)
    label(Version Control)
    label(Change Tracking)
    label(Improved Communication)
  node(Reduced Costs)
    label(Lower Maintenance Effort)
    label(Faster Problem Solving)
  node(Support for Best Practices)
    label(Encourages Structured Processes)
    label(Promotes Documentation)
    
```

This mindmap visually represents the advantages of employing maintenance tools across different aspects of the maintenance process.  Benefits include increased productivity, improved quality, enhance control and management, cost reduction and support for best practices.

---

## Diagram 6: Example Output - Program Slicer

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Original Code Segment] --> B[Program Slicer Tool];
    B --> C{Select Variable & Point of Interest};
    C --> D[Slice Computation Algorithm];
    D --> E[Extracted Slice - Relevant Code Only];
    E --> F[Highlighted Code in Original Program View];
    F --> G[Improved Understanding of Variable's Influence];
    
    style A fill:#f399,stroke:#333,stroke-width:1px
    style G fill:#f399,stroke:#333,stroke-width:1px

	classDef Element fill:#a3a9,stroke:#333,stroke-width:1px
    class B,C,D Element

	classDef Component fill:#a3f9,stroke:#333,stroke-width:1px
    class E,F Component

	subgraph Original_Code_Segment["Original Code Segment"]
    style Original_Code_Segment fill:#a319,stroke:#333,stroke-width:1px
	    H["Line 1: x = input();"]
	    I["Line 2: y = 10;"]
	    J["Line 3: if (x > 5) {"]
	    K["Line 4:  z = x * y;"]
	    L["Line 5: } else {"]
	    M["Line 6:  z = x + y;"]
	    N["Line 7: }"]
	    O["Line 8: print z;"]
    end

    subgraph Extracted_Slice["Extracted Slice"]
    style Extracted_Slice fill:#a369,stroke:#333,stroke-width:1px
	    P["Line 1: x = input();"]
	    Q["Line 4:  z = x * y;"]
	    R["Line 6:  z = x + y;"]
	    S["Line 8: print z;"]
    end

    H --> B
    I --> B
    J --> B
    K --> B
    L --> B
    M --> B
    N --> B
    O --> B

    P --> E
    Q --> E
    R --> E
    S --> E

```


This flowchart illustrates the functionality of a Program Slicer tool. It shows an "Original Code Segment" being input into the "Program Slicer Tool". The user selects a variable and point of interest. The tool computes a "Slice" (Extract Slice), extracting only the relevant code which is then "Highlighted Code in Original Program View" leading to "Improved Understanding of Variable's Influence".  Example code segments are used to visually demonstrate input and output slices.

---

