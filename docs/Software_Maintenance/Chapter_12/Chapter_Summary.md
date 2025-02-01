---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

----

# Chapter 12 - Maintenance Measures - A textual  summary

Chapter 12, "Maintenance Measures," emphasizes the importance of quantifying maintainability through various software metrics. It starts by defining fundamental concepts: *measurement* as the process of assigning numbers to entities, *software measurement* applied to software products and processes, a *software measure* as the specific number assigned, and a *software metric* as the measurement method or formula.  Integrity in measurement is crucial, requiring measures to be *empirical* (based on observation), *objective* (unbiased and reliable), and *encodable* (quantifiable).  The objectives of measurement include *evaluation* (comparing alternatives), *control* (managing resources), *assessment* (understanding the current state), *improvement* (enhancing quality), and *prediction* (forecasting future needs).

The chapter introduces several example measures:

*   **Size:** Lines of Code (LOC), which measures code volume.
*   **Complexity:** McCabe's Cyclomatic Complexity (number of linearly independent paths) assesses control flow complexity, while Halstead's Measures (based on operator and operand counts) evaluate program volume, length, and mental effort.
*   **Quality:**  Assessed via product quality (e.g. change requests, fault detection, user satisfaction) and process quality (e.g. schedule variance, defects injected).
*   **Understandability:**  Reflecting how easy a program is to comprehend by humans, negatively correlated with complexity.
*   **Maintainability:**  Often measured externally via attributes such as Mean Time To Repair (MTTR).
*   **Cost Estimation:** Using models like COCOMO, or estimates based on past data.

The relationship between a software entity (the product being measured), its attribute (the aspect being measured, e.g. complexity), and the measure (the resultant number) is explained.

Guidelines for selecting measures are provided:

*   **Clearly Defined Objectives:** Understanding the purpose of measurement.
*   **Fitness for Purpose:** Choosing metrics relevant to the maintenance task.
*   **Ease of Use:**  Employing simply applied measures - ideally automated.
*   **Low Implementation Cost:** Considering cost-effective tools and minimal training.
*   **Sensitivity:**  Metrics that change with changes in relevant attributes.
*   **Personnel Involvement:**  Engaging maintenance personnel to ensure accurate measurement.


The chapter highlights the difficulty of directly measuring internal attributes like maintainability, often relying on external measures.  It concludes by emphasizing the importance of proper metric selection and interpretation, advocating for a measurement program that enhances maintenance decision making, supports process improvement, and aids in resource and effort prediction.


----

Applying these concepts in practice, especially for iOS development, requires adapting traditional metrics, considering UI-specific factors, leveraging Xcode and Instruments, and prioritizing actionable measures relevant to the fast-paced iOS ecosystem.  Future trends emphasize system-level metrics, predictive maintenance using machine learning, measuring non-code artifacts, and incorporating security and privacy measures. The core principle remains: thoughtful application of appropriate measures can significantly improve software maintainability and reduce long-term maintenance costs.


----

