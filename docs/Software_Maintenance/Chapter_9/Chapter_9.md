---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

----

# Chapter 9 - Testing

Here are the diagrams and illustrations in Mermaid syntax to cover all the key concepts:

---

# Diagram 1: Testing - Mindmap Overview

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Chapter 9: Testing))
    node(Introduction)
      label(Define Testing)
      label(Purpose - Error Detection)
      label(Analogy - Imperfect Nature)
    node(Definitions)
      label(Proof)
      label(Test)
    node(Why Test Software)
      label(Cannot Prove Correctness)
      label(Find Errors - Primary Goal)
      label(Limitations of Testing)
      label(Importance of Testing)
    node(What is a Software Tester's Job)
      label(More than Finding Bugs)
      label(Design Effective Tests)
      label(Prioritize & Categorize Errors)
      label(Ensure Fixes)
      label(Value Driven - ROI)
    node(What to Test and How)
      label(Vast Test Case Possibilities)
      label(Constraints & Practicality)
      label(Key Aspects of Test Data)
        label(Valid & Invalid Inputs)
        label(Data Classes & Boundaries)
        label(Likely Error Locations)
        label(Combinations)
        label(Real-World Scenarios)
      label(When to Stop Testing - Risk-Based)
    node(Categorizing Tests)
      label(Testing Code - Focus)
      label(Categorization by Code Type)
        node(Black Box Testing)
          label(Specification-Based)
          label(External View)
        node(White Box Testing)
          label(Code-Based)
          label(Internal View)
        node(Structured Testing)
          label(Maximize Error Detection)
          label(Minimize Redundancy)
        node(Integration Testing)
          label(Component Interaction Focus)
          label(Use of Stubs)
        node(Regression Testing)
          label(Ensure Fix of Bugs)
          label(Prevent New Bugs)
          label(Maintain Test Sets)
    node(Verification and Validation)
      label(Verification - Against Specification)
      label(Validation - External Certification)
      label(Importance of Documentation)
      label(Goal - Reliability, Performance, Quality)
    node(Test Plans)
      label(Purpose - Guide & Product)
      label(IEEE Standard Definition)
      label(Key Elements of Test Plans)
        label(Scope)
        label(Approach)
        label(Resources)
        label(Schedule)
        label(Test Items)
        label(Features to Test)
        label(Testing Tasks)
        label(Responsibilities)
        label(Risk Planning)
      label(Points to Note in Test Planning)
        label(One Error at a Time)
        label(Test Unlikely Scenarios)
        label(Independent Testers)
        label(Expected Outcomes)
    node(Case Study - Therac-25)
      label(Real-World Example of Testing Failures)
      label(Consequences of Inadequate Testing)
      label(Lessons Learned)
    node(Summary)
      label(Key Takeaways from Chapter)

```


This mindmap provides a hierarchical overview of Chapter 9, outlining all the main sections and sub-topics within "Testing". It serves as a table of contents in diagram form, making it easy to see the chapter's structure.

---

# Diagram 2: Categorizing Tests

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    subgraph Testing_Code["Testing Code"]
    direction TB
        A[Testing Code] --> B[Black Box Testing];
        A --> C[White Box Testing];
        A --> D[Structured Testing];
        A --> E[Integration Testing];
        A --> F[Regression Testing];
    end

    subgraph Black_Box_Testing["Black Box Testing"]
    direction LR
        B --> B1[Specification-Based];
        B --> B2[Focus on Functionality];
        B --> B3[External View];
        
        style B fill:#f3dd,stroke:#333,stroke-width:1px
    end

    subgraph White_Box_Testing["White Box Testing"]
    direction LR
        C --> C1[Code-Based];
        C --> C2[Focus on Structure];
        C --> C3[Internal View];
        
        style C fill:#d3df,stroke:#333,stroke-width:1px
	end
    
    subgraph Structured_Testing["Structured Testing"]
    direction LR
        D --> D1[Maximize Error Detection];
        D --> D2[Minimize Redundancy];
        
        style D fill:#f3df,stroke:#333,stroke-width:1px
    end
    
    subgraph Integration_Testing
    direction LR
        E --> E1[Component Interaction];
        E --> E2[Use of Stubs];
        
	    style E fill:#d3fd,stroke:#333,stroke-width:1px
    end
    
    subgraph Regression_Testing
	direction LR
        F --> F1[Ensure Bug Fix];
        F --> F2[Prevent New Bugs];
        F --> F3[Maintain Test Sets];
        style F fill:#f3fd,stroke:#333,stroke-width:1px
    end

style Testing_Code fill:#32e,stroke:#333,stroke-width:1px

```


This flowchart focuses on the different categories of tests discussed in Chapter 9.  `Testing Code` is the main category, broken down into Black Box, White Box, Structured, Integration and Regression Testing. For each test type, key characteristics are highlighted in subgraphs, providing a clear comparison.

---

# Diagram 3: Test Plan Elements

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
mindmap
  root((Key Elements of a Test Plan))
    Concept((Test Plan))
    Concept -- Scope : Describes the extent of testing
    Concept -- Approach : Defines methodologies & techniques
    Concept -- Resources : Lists required tools & personnel
    Concept -- Schedule : Outlines timelines & milestones
    Concept -- Test Items : Specifies software components
    Concept -- Features to be Tested :  Functionalities to verify
    Concept -- Testing Tasks : Detailed activities involved
    Concept -- Responsibilities : Assigns tasks to team members
    Concept -- Risk Planning : Contingency for potential issues

%%style Concept fill:#e3fe,stroke:#333,stroke-width:1px
%% style root fill:#f3fe,stroke:#333,stroke-width:1px

```


This mindmap illustrates the Key Elements of a Test Plan as per the textbook, branching out from the central "Test Plan" concept to detail Scope, Approach, Resources, Schedule, Test Items, Features, Testing Tasks, Responsibilities and Risk Planning.  It highlights the structured nature of a comprehensive test plan.

---

# Diagram 4: Why Test Software - Comparison Table

```mermaid
table Diagram
    title Chapter 9 - Why Test Software: Core and Fallible Approach Comparison
    header Attributes | Core Belief | Evidence & Practicality
    row **Goal** | Determine if system works correctly | Primarily, find errors because systems are not perfect
    row **Method** | Strives to verify specifications as true | Identifies deviations from specs and expected behavior
    row **Approach** | Aims for confirmation | Focuses on detecting defects and limitations
    row **Perspective** | Assumes system is near-perfect | Expects and anticipates system errors
    row **Test Focus** | Seeks positive test cases for affirmation | Searches for problematic inputs and edge-cases to expose flaws
    row **Outcome Focus** |  Hopes for 'Pass' results | Aims to get most fix on identified bugs

```


This table captures the core difference between a core (idealized but not practical) belief in what testing does vs the practical, real-world approach. It emphasizes that the primary purpose of software testing should be the detection of defects rather than the affirmation of correctness. It highlights the mindset change required in testing.

---

# Diagram 5: Test Data Creation Process

```mermaid
---
config:
  look: handDrawn
  theme: dark
---
graph LR
    A[Start];
    B{Identify Test Object};
    C{Select Test Data Strategy Option};
    D[Specification Tests];
    E[White-Box Tests];
    F[Operational Tests];
    G[Create Test Sets from Requirements];
    H["Create Branch/Path Coverage Tests"];
    I["Create Real-World & Edge Cases"];
    J{Validate Test Data};
    K["Build Test Harness &<br>Execute Tests"];
    L{Record Test Result};
    M[End];


    A --> B
    B --> C
    C --> D
    C --> E
    C --> F
    D --> G
    E --> H
    F --> I

    G --> J
    H --> J
    I --> J

    J -- Yes --> K
    J -- No --> C;

    K --> L
    L --> M

    style B fill:#f319,stroke:#333,stroke-width:1px
    style L fill:#d115,stroke:#333,stroke-width:1px


    classDef Group1 fill:#f3fa,stroke:#333,stroke-width:1px
    class D,E,F Group1

    classDef Group2 fill:#a339,stroke:#333,stroke-width:1px
    class G,H,I Group2

    

    classDef Start_and_End_Point fill:#1919,stroke:#333,stroke-width:2px;
    class A,M Start_and_End_Point

    classDef Decision_Point fill:#9398,stroke:#333,stroke-width:2px;
    class J Decision_Point

    classDef Yes_Choice fill:#f118,stroke:#333,stroke-width:2px;
    class K Yes_Choice;

    classDef No_Choice fill:#f998,stroke:#33,stroke-width:2px;
    class C No_Choice;
    
```


This flowchart visually depicts the process of creating test data, from initial identification of the test object all the way to recording results. It outlines the different paths for deriving test sets - specification- based tests, white-box tests, and operational tests. This visual helps to understand how to approach designing test cases from multiple angles.

---
# Diagram 6: Verification and Validation using Levels

```mermaid
---
config:
  layout: elk
  look: handDrawn
  theme: dark
---
graph LR
    A[Requirements Specification]
     --> B{Verification}
     --> C[Design Phase]
     --> D{Verification}
     --> E[Implementation Phase]
     --> F{Testing Phase}
     --> G[Validation]
     --> H[Operation Phase]

    style A fill:#a3f9,stroke:#333,stroke-width:1px
    style G fill:#f3c9,stroke:#333,stroke-width:1px

    classDef Group1 fill:#c3c9,stroke:#333,stroke-width:1px
    class B,D,F Group1
    
    classDef Group2 fill:#f329,stroke:#333,stroke-width:1px
    class C,E,H Group2
    
    subgraph Requirements_Analysis["Requirements Analysis"]
    direction LR
        A
    end
    
    subgraph Design_Phase["Design Phase"]
    direction LR
        C
    end

    subgraph Implementation_Phase["Implementation Phase"]
    direction LR
        E
    end

    subgraph Testing_Phase["Testing Phase"]
    direction LR
        F
    end
    
    subgraph Operation_Phase["Operation Phase"]
    direction LR
        H
    end
    
```


This diagram outlines the role of Verification and Validation by showing where it is applied at each phase of the software life cycle. Verification is shown to be an internal "check" at requirements, design, and unit/integration/system testing phases, whereas Validation takes place at the end when the finished program is handed off to the users. It emphasizes that V&V are processes that ensure systems are built correctly and fulfill the intended usage.

---

# Diagram 7: Testing Levels and Focus

```mermaid
table Diagram
    title Chapter 9: Testing Levels and Focus
    header Testing Type | Focus | Purpose
    row Black Box Testing | Specifications, Interface  | External Functionality, Valid/Invalid Inputs
    row White Box Testing | Internal Structure, Code Path, Branches | Internal Logic, Coverage,  Code Path
    row Structured Testing | Error Minimization, Path Detection | Designed Test Sets that maximize error detection and minimize redundancy
    row Integration Testing | Module Interfaces, Component Interactions | Interactions among units, data flow integrity
    row Regression Testing | Change Impact, Prevent Regressions | Ensure Fixes, Prevent New Bugs, Maintain Test Sets

```


This table provides a quick comparison of the different testing types, highlighting their focus area and primary purpose of each type of testing discussed.



----
