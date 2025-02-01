---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---


----

Reverse engineering is an essential skill for iOS developers, especially when dealing with frameworks and legacy code.

However there are always challenges, especially in weighing the potential benefits against time constraints and resources.


---


# Subject 1: Reverse Engineering Frameworks and SDKs in iOS Development

**Context:**

As an experienced iOS developer, I often find myself needing to understand the inner workings of frameworks like UIKit, SwiftUI, or even third-party SDKs. While Apple provides extensive documentation, sometimes the "why" behind certain design choices, or the specific sequences of events during framework operations, isn't entirely clear. This is where reverse engineering comes into play.

**Reverse Engineering Perspective:**

*   **Dynamic Analysis:** Tools like the Xcode debugger (LLDB) become crucial. I use breakpoints strategically to trace execution paths, inspect variable values, and understand how specific UIKit components or SwiftUI views react to user input or changes in the application's state. Especially valuable is the ability to step into the framework code, letting me to peek under the hood (where possible). This "black box" testing lets me check the interfaces’ response.
*   **Static Analysis:** While I can't directly access Apple's source code for its frameworks, tools like `otool` and `class-dump` become essential. I use them to inspect the headers, method signatures, and class hierarchies of frameworks. This process provides insights into the available APIs and how they might interact with each other. It helps immensely with comprehending the framework's architectural design, and how I might best use it within our application.
    *   For third-party SDKs, if access to headers is publicly available, I'll also use `class-dump` (or similar tools) to reveal hidden APIs or internals, sometimes uncovering potential issues or limitations before I encounter them at run-time, saving considerable debugging time later.
*   **"Hacking" and Prototyping:** In some situations when faced with a challenging or poorly documented API, I'll create small, targeted "test" apps that isolate specific parts of the SDK or framework, this way, I can more precisely understand their operational behavior in a controlled setup. This allows me to test alternative hypotheses or workarounds for a bug that may lie within a framework or API, rather than within my own implementation. This almost constitutes the process of reengineering, discussed in the chapter.
*   **Implications on Code Maintainability**: By "reverse engineering" frameworks, I not only address immediate bugs or implementation needs but also write better code. By understanding how UIKit or SwiftUI works, I can leverage their functionality more efficiently and avoid workarounds that may become technical debt later. In essence it becomes part of the standard operating procedures. The resulting more elegant solution is also easier to maintain overall, and to expand on in the future.
    *   Also for third party libraries: It is important to have this level of understanding so that issues can be identified early, rather than later where they may become more deeply enmeshed.
*   **Limitations:**
    *   **Security and Ethical Concerns:** While "reverse engineering", particularly of third party libraries might give useful insights, care is always required on ensuring that we are not violating their terms of service. This is particularly important for those libraries that enforce a specific license.
    *   **Complexity:** Many frameworks are huge and complex; reverse engineering often requires a very detailed step by step approach. Without having complete technical documentation for a framework, building a comprehensive understanding can be exceptionally time consuming. I will always make a call as to whether or not that time might be more effectively used elsewhere, if the outcome is unlikely to be worth the investment.

---


# Subject 2: Applying Reverse Engineering for Legacy iOS Codebases

**Context:**

As iOS evolves rapidly, we often inherit legacy iOS codebases often written in Objective-C, using older design paradigms like MVC or even not adhering to a well structured paradigm. These codebases are often undocumented and represent a huge challenge for maintenance and future evolution.

**Reverse Engineering Perspective:**

*   **Code Analysis Tools:** Source code analysers, particularly those that can visualise class relationships and call chains, are vital. These tools enable an initial understanding of the system’s high-level structure. I use these specifically to map out the architecture of legacy code, looking for dependencies and points of coupling.
     *   I will also look for patterns in code; these might indicate an intended solution that should be adhered to while implementing changes. Similarly, recognition of known anti-patterns might indicate issues that should be addressed during reverse engineering to enable improved maintainability in the future.
*  **Documentation Recovery:**
    *   Using tools that can auto generate documentation from source code, is particularly important. Even if these tools do not give completely accurate information (and they never do), it is a very useful base on which a good documentation can be built.
    *   I'll also extract design rationales from code comments, commit history and even naming conventions on modules and data structures (the beacons discussed in the chapter), all of which can help in redocumenting legacy code.
    *   It is essential also to analyse the business rules that the software implements, as, often business rules are poorly represented or even missing in older systems.
    *   Understanding the intended goal of components is very important for the long term survivability of the system for reuse.

*   **Reengineering:** Once I have a good mental model of the architecture and what the system is attempting to do, I consider options for implementing change and improvements to the legacy system.
    *   Often the first step is to refactor code into clearly defined modules or functions representing high-level features (bottom-up chunking). This often helps to highlight sections of code that could be reusable or are redundant, but also gives a good indication of the level of coupling between different parts of the code.
    * I will also try to encapsulate different functionalities in small and isolated components to enhance reusability and long term maintenance of the software: an example of this is when dealing with I/O routines and data extraction from a database.
*   **Refactoring towards Modern Patterns:** Where feasible, and where there is a good return for investment, I use reverse engineering to re-implement legacy components using more modern approaches like MVVM or SwiftUI, leveraging the newer features that will lead to better maintainability, especially when this refactoring can encapsulate older code allowing an evolutionary migration to a new framework system.
*   **Testing and Validation:** Legacy systems often have poor or non-existent test suites. Reverse engineering helps create test harnesses that make testing feasible and repeatable, and to identify the most important tests to be made. Then I might create a comprehensive test suite so that we can guarantee our changes did not break other parts of the system (regression tests).

*   **Limitations:**
    *   **Time Investment:** Reverse engineering legacy codebases is often time consuming, and not always a cost-effective approach.
    *   **Inaccurate Documentation:** Relying purely on automatically generating documentation may produce documentation that may not reveal the full picture as it contains information about how the code is written and not why.
    *   **Risk of Further Degradation:** Ad Hoc and badly targeted changes have the potential to cause more harm than good - it is important that the whole development team has a common understanding about the goals. A poorly planned and executed migration to a new paradigm can easily lead to further problems.

---
