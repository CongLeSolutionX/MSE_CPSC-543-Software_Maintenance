---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---


---


Chapter 3, "Fundamentals of Software Change," lays the groundwork for understanding software maintenance by exploring the nature and reasons for software evolution.  It starts by **defining key terms** such as "software evolution," "maintenance," and different types of "change" (corrective, adaptive, perfective, preventive).

The chapter then went more details into the **classification of software changes**, categorizing them into four main types:

*   **Corrective Change:**  These are modifications triggered by **defects or bugs** in the software. They aim to restore correct operation and fix errors from design flaws, logic mistakes, or coding errors.  The chapter highlights the danger of "patching" and the resulting "spaghetti code" when corrective changes are not managed well.
*   **Adaptive Change:**  This type of maintenance is driven by **changes in the software's environment**, which can include new hardware, operating systems, supporting software, or even changes in business rules and government policies (like VAT or Euro adoption examples).  The focus here is on ensuring the software remains compatible and functional within its evolving surroundings.
*   **Perfective Change:**  Perfective changes are initiated to **enhance or improve the existing system**.  This includes adding new features, improving performance, or meeting evolving user needs beyond the original requirements.  The chapter uses an example of a system growing from a basic version to an enhanced version with added modules and outputs, demonstrating the progressive nature of software evolution.
*   **Preventive Change:**  This is **proactive maintenance** aimed at making the software **easier to maintain in the future**. It is internally driven by the maintenance team and focuses on improving the system's structure, code, or documentation to prevent future problems and reduce long-term maintenance costs. Examples include code restructuring, optimization, and documentation updates.

The chapter emphasizes the **importance of categorizing these changes**, even though in practice they often overlap.  Categorization helps in prioritizing change requests, allocating resources effectively, and understanding the different response times each type of change might require. A case study about an obsolete payroll system at ACME Health Clinic highlights the real-world challenges and trade-offs in balancing maintenance of old systems with the development of new ones.  It introduces the concept of **incremental release** as a common mechanism for managing software evolution, where changes are introduced gradually over multiple versions.

Beyond classifications, the chapter explores **"Ongoing Support"** as a vital, though not strictly a "change," aspect of maintenance.  Ongoing support encompasses user training, providing business information to aid decision-making, and establishing effective communication channels between users and maintainers.

A crucial element of the chapter is the introduction of **Lehman's Laws of Software Evolution**. These eight laws, developed over decades of research, describe the inherent tendencies of E-type (Evolutionary) software systems:

*   **Continuing Change:** E-type systems must continually adapt or become progressively less satisfactory.
*   **Increasing Complexity:** System complexity increases with evolution unless actively combatted.
*   **Self-Regulation:**  Evolutionary processes are statistically regular and self-regulating.
*   **Conservation of Organization Stability:** Average work rate in E-type processes tends to remain constant.
*   **Conservation of Familiarity:** Incremental growth tends to remain constant or decline.
*   **Continuing Growth:** Functional capability must continually increase to maintain user satisfaction.
*   **Declining Quality:** System quality will appear to decline without rigorous adaptation.
*   **Feedback Systems:** Evolution processes are multi-level, multi-loop, multi-agent feedback systems.

These laws highlight the inherent evolutionary nature of software and the challenges this presents for maintenance. Despite their "law" designation being debated, they provide valuable observations about the dynamics of software evolution.

In **summary**, Chapter 3 provides a foundational understanding of software change, classifying its types, explaining the need for ongoing support, and introducing Lehman's Laws as a theoretical framework to comprehend the inherent evolutionary nature of software and the ongoing maintenance challenges it creates.


----
