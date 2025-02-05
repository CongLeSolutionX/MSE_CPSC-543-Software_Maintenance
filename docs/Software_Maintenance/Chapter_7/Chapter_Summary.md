---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---


# Chapter 7

## A Textual Summary

Chapter 7 delves into the crucial practice of reverse engineering within the context of software maintenance. It underscores that before any meaningful changes can be made to a system, a thorough understanding of its existing state is essential, and that reverse engineering provides the tools and techniques to achieve that understanding when documentation is missing, inaccurate, or outdated.

## Key Concepts and Definitions

*   **Reverse Engineering** is defined as the process of analyzing a subject system to identify its components, their interrelationships, and to create representations of the system in a different form or abstraction level. It's a fact-finding mission that enables us to understand a system by working backward from its current state and then using that understanding to transform the system.
*   **Forward Engineering,** on the other hand, is the traditional software development approach, moving from requirements to design, onto implementation and testing of a system.
*   **Reengineering** combines forward and reverse engineering. It begins by using reverse engineering to understand a system and represent it in a new form, followed by forward engineering to implement desired changes or enhancements.
*   **Restructuring** is the transformation of a system from one representational form to another at the same level of abstraction, without changing its functionality. It’s often aimed at improving the system’s structure and maintainability.
*   **Abstraction** involves creating a simplified model of a system, highlighting essential features while ignoring irrelevant details. The chapter introduces three types:
    *   **Function Abstraction:** Focusing on *what* a function does, not *how* it achieves the result.
    *   **Data Abstraction:** The essence of data types and operations, independent of specific implementations, and using abstract data types.
    *   **Process Abstraction:** Understanding the order of operations, particularly for concurrent or distributed systems.

## Purpose and Objectives of Reverse Engineering

The primary goal of reverse engineering is to facilitate change by improving system understanding. The specific objectives include:

*   **Recovering lost information:** Obtaining missing specifications, designs, or rationales.
*   **Facilitating platform migration:** Assisting with transferring code to new software or hardware environments.
*   **Improving or providing documentation:** Creating or updating system documentation to support maintainers.
*   **Providing alternative views:** Generating new perspectives on the system via different representations (e.g. flowcharts or diagrams).
*   **Extracting reusable components:** Identifying and isolating modules to be reused in other systems.
*   **Coping with complexity:** Making large, complex systems more comprehensible.
*   **Detecting side effects:** Identifying unintended consequences of software changes.
*   **Reducing maintenance effort:** Streamlining the process of making changes to the system using a clear understanding of its structure and function.

## Levels of Reverse Engineering

The chapter categorizes the abstraction levels of reverse engineering:

*   **Redocumentation:** Creating alternative representations at the same level of abstraction, which includes restructuring code, refining code and generating diagrams to improve understanding.
*   **Design Recovery:** Extracting design information and creating models at a higher level of abstraction than code. This is not necessarily the original design but a representation of system organization.
*    **Specification Recovery:** Recovering system specifications at the highest level of abstraction from the source code or design.

## Supporting Techniques

The different techniques discussed are:

*   **Forward Engineering:**  The traditional software creation, starting from the requirements going through design, implementation and testing. Not for maintenance itself, but the end point for Reengineering.
*   **Restructuring:** Transforms existing code to improve its structure or performance without adding or changing functionality, it reorganizes the code, and optimizes code making it easier to understand and maintain.
*   **Reengineering:** Uses Reverse Engineering first to understand a software system before transforming it, or developing new functionalities by moving through to a forward engineering approach.

## Benefits of Reverse Engineering

The benefits of this approach are:

*   In **Maintenance:**  Better system understanding, easier identification and correction of errors, with ripple effect awareness and accurate documentation.
*   For **Software Reuse:** Makes components readily available for future uses, as a by product of the process of understanding the current system.
*   **Quality Improvement:** Leads to higher quality, more maintainable, and more robust systems.

## Case Study: US Department of Defense

This case study describes a large project to integrate and maintain numerous disparate DoD information systems. It emphasizes the complex nature of legacy systems data reverse engineering. Key insights included the necessity of:
*   Management commitment.
*   Human analysis combined with automated tools which reveal data dependencies.
*       The importance of standardizing interfaces and data models, and the difficultly in cost estimating.

## Current Problems

Chapter 7 notes some ongoing and difficult challenges in the field of reverse engineering:

*   **Automation:** Existing technology cannot fully automate tasks requiring design and high-level specification extraction with a high degree of accuracy.
*   **Naming:** Semantic clues from the code may be lost if naming strategies are not meaningful; particularly in code intended for reuse..

By understanding how reverse engineering operates on a software system, the maintenance programmer can improve its long-term maintainability. These techniques often require a large initial effort, but are intended to repay that investment in the long-term management of the system through improved understandability.



---
