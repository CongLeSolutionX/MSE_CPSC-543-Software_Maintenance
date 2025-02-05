---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---



# Chapter 9: Testing 

## A Textual Summary



Chapter 9 delves into the crucial practice of software testing, emphasizing that it's not about *proving* software works, but rather about *finding* where it doesn't. This realistic perspective shapes the whole chapter.

**Why Test Software?**

*   **We Cannot Prove Correctness:** Unlike mathematical equations, software, especially complex systems, can't be definitively proven correct. Testing is the *only* way to explore behavior and identify imperfections.
*   **Testing Finds Errors:** The real purpose of testing is to uncover bugs, limitations, and deviations from what's expected, rather than confirming it's perfect.
*   **Testing is a Necessity:** Despite its limitations, thorough testing is vital for reliability and user safety.

**The Software Tester's Role:**

*   **More Than a Bug Finder:** It's a job focused on effective and proactive planning to achieve a good ROI.
*   **Key Responsibilities**: A tester not only finds bugs but designs effective test cases, prioritizes critical issues, and ensures that all bugs are fixed. The most important step a good tester might take is to ensure that the bugs are fixed and not just that they are reported.
*   **Value Driven:** A good tester adds value to the software by finding bugs, reducing risks, identifying critical areas that are most problematic.

**What and How to Test:**

*   **Exhaustive Testing is Impossible**: The number of possible test cases is infinite, so practical strategies are crucial.
*   **Key Aspects of Test Data**: Create practical tests by understanding what to test, and prioritize certain test data sets, namely:

    *   **Valid and Invalid Inputs**: Check the behaviour in typical scenarios as well as error conditions.
    *   **Boundary Conditions and Data Classes**: Divide the inputs into known types with representative data, focusing on edge conditions.
    *   **Error-prone areas**: Prioritize testing for identified high-risk areas of code or workflows.
    *   **Combinations of Inputs**: Focus on the combinations of different inputs that might lead to a problematic states.
    * **Real World scenarios**: Focus on what users might do with the software, including unexpected uses of the system

*   **When to Stop Testing**: The level of testing required is driven by risk and real-world consequences of system failures. Safety-critical systems need far more rigour than game applications.

**Categorizing Tests:**

*    **Black Box Testing:** Tests the system based on the specification and has an external perspective, focusing on what the system does, and without the knowledge of internal structures.
*   **White Box Testing:** Tests based on code structure and specific execution paths, with an internal view designed to detect logical errors.
*   **Structured Testing:** Provides a systematic approach for identifying the most important paths and conditions to test.
 *   **Integration Testing:** Focuses on verifying how different components of the system work together. It involves tests on the connections between components rather than just testing their individual behaviour.
*   **Regression Testing:** Verifies that changes in one area do not introduce new errors or break the existing functionality, and is used to validate that any fixed bug doesn't introduce other bugs, and also to ensure core functionality that had not been affected by the changes continues to work as intended.

**Verification and Validation (V&V):**

*   **Verification:** It ensures systems meet agreed-upon requirements and specifications. It takes place at different levels as the system is built to maintain consistency of implementation with specifications and design principles of the project.
*   **Validation:** It confirms that the system fulfills the overall intended purpose and meets the needs of the users, as a part of an external certification process.
*   **Documentation:** Thorough documentation of both steps is vital in meeting legal, design and regulatory requirements.

**Test Plans:**

*   **Purpose**: They are used both as tools (for guiding the testing process) and as products (useful documentation for later use).
*   **Key Components**: A good test plan should cover the scope, approach, resources, schedule, test items, features to test, testing tasks, responsibilities, risk mitigation and contingency planning.
*   **Key Points**: Plan tests by assuming that the program has errors; record all details on a step by step manner on how and what to test; and have clear expectations for all tests.

**Case Study: The Therac-25**

*   **Real-World Failure**: This case study illustrates the tragic outcome of inadequate testing and the complex interaction of technical, managerial, and procedural issues in software systems. Even with the best approach, it is almost impossible to get software testing completely fool proof, but structured testing has shown a greater capability of catching the most important and catastrophic type of errors.
*   **Lessons Learned:** It illustrates the high cost of inadequate planning, development, testing, and communication, underscoring the need for a systemic view of software development and deployment.

**In summary**, Chapter 9 stresses the real-world challenges of software testing and moves away from an idealized perspective. Effective testing requires structured approaches, detailed planning, a focus on finding errors, awareness of real-world constraints, and an understanding of the purpose to be served by each type of testing method used. Its focus is not an idealized pursuit of perfection, but on the pragmatic goal of minimizing the negative impacts of software faults, and on the value addition of a structured approach to software production and maintenance.

---
