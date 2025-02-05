---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

----


# Chapter 8: Reuse and Reusability

## A Textual Summary

Chapter 8 explores the critical concept of software reuse and reusability as a means to address common problems like low productivity and poor software quality in software development and maintenance. The chapter breaks down the "why, what, and how" of software reuse.

**Core Concepts:**

*   **Reuse vs. Reusability:** The chapter distinguishes between *reuse*, the broad concept of reapplying software knowledge, and *reusability*, the attribute of a component that makes it suitable for reuse.

*   **Targets for Reuse:** Reuse is not limited to code. The chapter broadens reuse to include:
    *   **Processes:** Reusing successful software development and maintenance methods including testing methodologies
    *   **Personnel:** Reusing the knowledge and expertise of developers, most importantly capturing and sharing domain knowledge.
    *   **Products:** This includes reusable code, designs, and data schemas. These are further broken down into:
        *   **Data:** Reusing existing data formats and structures.
        *   **Design:** Reusing architectural patterns, interfaces, and models.
        *   **Program:** Reusing code components like libraries, functions, and classes.

*   **Objectives and Benefits of Reuse:**
    *   **Increased Productivity:** Reuse helps developers focus on new aspects of a system, reducing time spent on standard components.
    *   **Improved Quality:** Well-tested, reusable components lead to more reliable, standardized software with fewer errors.
     *  **Facilitated Code Transportation**: Portability and interoperability are naturally increased
    *    **Reduced Maintenance Costs**: Reusing components makes systems more consistent and predictable which eases future maintenance.

**Approaches to Reuse:** The chapter explains two main approaches to software reuse:
*   **Composition-Based Reuse:** This involves assembling reusable "building blocks," categorized by:
    *   **Black-box Reuse:** Reusing components without any modification. Focus is on the functionality of the reusable component.
    *   **White-box Reuse:** Reusing components that are modified based on a projects needs, which include having full access to source code for change.
*   **Generation-Based Reuse:** This approach uses reusable components as 'generators' to create the target systems:
    *   **Application Generator Systems:** These systems generate entire applications within specific domains.
    *   **Transformation-Based Systems:** These take high-level specifications as input and use step-wise refinement or linguistic transformation techniques to convert them to operational programs.

**Key Techniques for Reuse:**

*   **Domain Analysis:** The process of identifying and structuring reusable knowledge from a specific problem domain. It's key to identifying what's truly reusable and how much effort it will take.
*  **Components Engineering**:  This concentrates on identifying reusable software building blocks that have a very high potential of reuse.
  *   **Design for Reuse**: Designing systems from the perspective of reuse and to make sure reuse is a strategic part of development.
  *   **Reverse Engineering for Reuse**: Extracting components from already existing code base and leveraging for future projects

**Process Considerations:**

*   **Reuse Process Model:** A generic model is presented to promote integration of reuse into existing methodologies. It includes steps for understanding the problem, reconfiguration, acquisition/modification, integration, and evaluation.
* **Accommodating Reuse**: Reuse should be a top of mind consideration in the workflow and life cycle as it greatly enhances long term value and quality.

**Factors Impacting Reuse:**
    *   **Technical Factors:** These include the choice of programming language, methods for representing reusable design information, access to existing component libraries, and the potential of creating a "reuse-maintenance" vicious cycle.
    *   **Non-Technical Factors:** These include initial capital outlay, the "Not Invented Here" (NIH) syndrome, commercial interests, the education level of the people involved, project coordination and applicable legal issues.

 **Case Study:**

 * A discussion of use case of Patient Identification system in the ACME Health Clinic.

**Chapter Conclusion**:

Chapter 8 emphasizes that successful reuse practice depends on more than technical proficiency; it also requires changes in organizational culture, a focus on strategic planning and proactive implementation of systematic procedures to promote component reusability. It also looks at where reuse can be applied and how different implementations help or hinder it.




---
