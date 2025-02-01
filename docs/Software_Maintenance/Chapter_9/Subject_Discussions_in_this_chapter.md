---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

----

Both types of testing below are vital, but as an experienced iOS developer, I focus on employing both using their strengths and weaknesses to my advantage rather than trying to force an unrealistic testing philosophy.

I prefer a balanced approach, aligning testing efforts to the actual business needs of the software, ensuring a high return on investment.

These two subjects provide a real-world perspective on testing from my perspective.

This perspective will bring in some practical, real-world considerations specific to the iOS development ecosystem.


---


# Subject 1: Test-Driven Development (TDD) and its Nuances in iOS Development

*   **The Core Concept in TDD:** As a seasoned iOS developer, I've found that TDD, at its heart, is about writing tests *before* you write the actual code, not afterward or sometimes. For every requirement or feature, we first write a unit test that outlines *exactly* what that code needs to do. This test, initially, will fail. Then, we would write the simplest code to make that test pass. And then we refactor the code so it becomes efficient and more readable while always keeping the tests running. This cycle of Test-Code-Refactor helps ensure that code is always testable, has high coverage, and works as intended.

*   **TDD in iOS: Beyond Core Logic:** Many resources will emphasize TDD on business logic and core algorithms. I find that in iOS it is equally important to get into the habit of TDD in areas like custom UI components or even network handling layers. Often iOS code, especially dealing with UIKit or SwiftUI has a higher tendency to be spaghetti code or become unmanageable because it intermixes a lot of responsibilities into a single class while, at the same time, also have higher coupling, especially with view controllers. Applying TDD in these areas forces us to consider:

    *   **UI Component Behavior:** The various interactions between the component and the user must be tested; not just the views that it renders at a certain state, but the actions and state transitions as well. For example: testing is a UIButton is disabled, can it be tapped? Using the XCTests framework is paramount in these situations.
    *   **Network Layer Robustness:** We might use URLSession, or an abstraction layer such as Alamofire, but that layer needs unit and integration tests to ensure network calls produce and parse expected payloads and gracefully handle errors and edge cases.
    *  **Asynchronous Operations, such as using GCD or Combine**: The tests must also ensure that asynchronous work behaves as intended, and it's correctly managed and cancelled when it's no longer is necessary. This will include testing the actual concurrent behavior, such as what happens when 2 or more asynchronous work is updating the same data. This sort of test typically is a huge source of headaches and bugs for junior developers.

*   **Specific iOS Challenges:** The Apple ecosystem introduces certain hurdles:

    *   **UIKit & SwiftUI:** Testing UI frameworks can be tricky. You can have snapshot tests but not tests for actions and events. Some third-party libraries like ViewInspector and SnapshotTesting might simplify this a little. The new XCUITest provides a UI testing framework but doesn't provide unit test coverage.
    *   **Mocking:** Mocking Apple frameworks can be a headache. You'll end up writing an abstraction every time you have to use a framework to avoid mocking the actual system libraries. This can be seen as a good or bad thing depending on the view. Using dependency injection effectively is good practice to enable mocking and testing of your own code. However sometimes it requires substantial effort for junior developers.
    *   **Asynchronous Nature:** The iOS UI is highly asynchronous; it pushes developers towards multi-threaded environments, which if not tested properly, can create difficult to debug edge cases. I have lost days trying to figure out issues with UI updates that doesn't happen due to how the GCD queues are designed or how locks are implemented.

*   **Benefits for a Seasoned Pro:** For me, TDD is not just a habit; it's a design philosophy. I've learned that:
      *   It guides me to design better, more decoupled, and testable code from the start. Thus, reducing the cost of development. It has been observed that it takes less time and effort to design for testability upfront than tacking it on at the end of a project.
      *   It forces us to think like a user of an API, which results in better designed and more simple to use interfaces.
      *  It helps me catch bugs quicker and with lower cost because these bugs tends to be found much earlier in the life cycle and at the lowest possible level – which is cheaper compared to finding bugs at integration and at user acceptance levels.
      *  It acts as an up-to-date specification of every component as I often forget the fine details of things, even in my own code from weeks ago.

---


# Subject 2: UI Testing vs. Unit Testing and the Practical Trade-Offs in iOS

*   **The Dichotomy:** As an experienced iOS developer, I see the stark differences in the value proposition of UI tests compared to Unit tests:

    *   **Unit Tests:** Aim to test specific units of code in complete isolation (functions, classes, etc.). Unit tests are *fast* to run, and provide a tight feedback loop on functionality changes and code coverage. This is *where I spend most of my testing time*.
    *   **UI Tests (XCUITest):** Simulates a user's interaction with the app's UI. They are *slower, more fragile*, and test a much wider functionality from the end-user view. UI test coverage is therefore much lower and they provide, a rather general functionality coverage with a slower feedback loop.

*   **The Real-World Tradeoffs:** The theoretical ideal of high unit and UI test coverage rarely pans out in a project because of the high level of effort required. It isn't always the sensible commercial and pragmatic decision to have both at 100% coverage. My experience dictates a strategy of:

    *   **Heavy Investment in Unit Tests:** I find it's crucial to have rigorous unit tests for all core logic, data processing, business rules, networking and data persistence layers. These tests are fast, stable and provide me the peace of mind in knowing that the app's core functionality is working as it should, even during rapid changes.
    *   **Targeted UI Tests:** Rather than striving for 100% UI test coverage, I prefer to focus on critical user paths, main use-cases and workflows, key screens, and those paths where errors are most likely to have a high impact. For UI tests I tend to focus on the use-cases and not necessarily the underlying implementation. I still keep them high level and try to test the use-cases as a user would see the app and not from a developer's view. There is little point in investing to test all combinations, because of the high cost-reward tradeoff.
    *   **Balancing Effort and Reward:** As a senior developer, I also provide guidance in making pragmatic discussions on coverage levels. My goal is not just having high quality code, but also the understanding that our work adds value to the overall organization. A 100% test coverage for non-critical use cases, and with a high cost of test implementation does not bring value to the business, but will certainly add more cost.

*   **Specific iOS Concerns:** When deciding on UI testing vs. Unit testing I take the following into consideration:

    *   **Flakiness:** UI Tests are inherently flaky due to dependencies on system animations, UI element loading and screen transitions - particularly when dealing with a networking stack. The main issues are test timing and speed at which tests are executed. I like to spend time on making unit tests as close to perfect as possible, but rarely would I spend time fixing flakiness issues with UI tests if all core functionality is covered in unit test level.
    *   **Maintenance Cost:** UI tests break readily with small UI changes. This is a major consideration when developing an application with a constantly evolving design and user interface. This typically will result in a re-evaluation of the UI testing and a re-implementation of the UI tests, often rendering the previous UI test efforts fruitless. Unit tests are far more resilient to change and therefore are much more useful in reducing future development and maintenance efforts.
    *   **Integration with Swift Playgrounds:** I often use Playgrounds to explore concepts related to complex business and domain logic before I write unit tests. Playgrounds are a great way to see how a system behaves and how to structure your unit tests.

*   **My Takeaways:** I don’t view UI tests as a replacement for unit tests, or vice versa. I see them as a validation step with different goals. UI tests should give a good understanding *that the system works*. Unit tests should show that it *is built correctly*.

    *   **Unit tests:** are my primary tool for driving design and catching regressions, forming the foundation of reliable software.
    *  **UI tests:** are a means for ensuring key user journeys are intact as a user of the application, and a way to keep an eye on a system end-to-end.

---
