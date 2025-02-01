---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---

---


Below are two subjects, viewed through the lens of an experienced iOS developer, showcase how the principles of reuse and reusability, outlined in Chapter 8, apply to practical iOS development challenges.

The discussion provides hands-on examples and specific scenarios where these concepts are most relevant.

---


# Subject 1: Reusability of Custom UI Components in SwiftUI vs. UIKit

*   **Context:** As an experienced iOS developer, I've seen firsthand how UI frameworks can both support and hinder reuse. Chapter 8 talks about the ideal of reusable components, but let's get into the practicalities on iOS.
*   **SwiftUI and Reuse:**
    *   **Declarative Approach:** SwiftUI encourages reusability through its declarative nature. You define your UI as a function of state. This makes components much more context-agnostic and easier to compose. For example, designing a custom button can be done with a few lines of SwiftUI code that can be reused across different views with slight modifications.
    *   **View Composition:**  Think `Text`, `Image`, `Button` - these are fundamental reusable views in SwiftUI. Building UIs through composition is central to SwiftUI. This naturally pushes you towards designing smaller, more specific, and thus more reusable view components.
    *   **Modifiers:** SwiftUI modifiers like `.padding()`, `.font()`, `.foregroundColor()` are highly reusable, declarative transformations to views. You are less inclined to build new classes for trivial stylistic changes but rather apply modifiers.
    *   **State Management:** SwiftUI's state management (using `@State`, `@ObservedObject`, `@EnvironmentObject`, etc) promotes reusable views that simply reflect some state value. For instance, a progress bar component is only responsible for representing current progress and not about logic that leads to the progress.

*   **UIKit and Reuse:**
    *   **Imperative & Messy:** UIKit encourages more imperative, bespoke views. You often find yourself creating custom `UIView` subclasses for simple variations, which is not great for reuse.
    *   **Less Clear Compositions:** `UIView` hierarchies can get deeply nested and complex. There isn't that same gentle push to think in terms of smaller, composable elements like SwiftUI.. While composable custom views are possible they necessitate careful planning.
    *   **Styles:** UIKit styles are often applied through coding, resulting in custom subclasses, rather than easily applicable style modifiers.
    *   **State Management:** UIKit often mixes state management within views, which can lead to coupled, less reusable code. Components often take on the responsibility of their associated data.

*   **Challenges and iOS Perspective:**
    *   **UIKit Legacy:** Many projects still rely heavily on UIKit. Refactoring existing UIKit views into fully reusable components can be challenging, requiring careful planning and refactor existing code.
    *   **Learning Curve** SwiftUI's declarative paradigm can present a learning curve for UIKit veterans. A change in mindset is needed to fully unlock the potential of reuse in SwiftUI.
    * **Performance**: SwiftUI is less optimal in performance. UIKit offers much lower level optimization and custom drawing. SwiftUI also depends heavily on the frameworks which can lead to large binary size if not careful.
    *   **Balancing abstraction and needs:** Sometimes excessive reuse can lead to generalized components that are difficult to customize. The challenge is getting the right balance for each use case. This isn't just about copy-pasting components, it's about making reusable "building blocks."

*   **Real-World Takeaway:** The rise of SwiftUI and the way it encourages composition, modifiers, and state management makes it easier to design reusable UI components from the outset. However, the world is not SwiftUI only and therefore knowledge of both UIKit and SwiftUI is essential.

---


# Subject 2:  Reuse of Networking Layers in iOS Development: A Case for Abstraction

*   **Context:** Chapter 8 emphasizes the reuse of software components. In my experience, a great example which directly saves long term developer time is reusing your Networking Layer in iOS Development. Let's examine how you can make a framework reusable and why it is important to abstract away the actual calls.
*   **The Problem:** Networking in iOS can be particularly messy. You often end up with similar code for fetch requests, error handling, authentication, etc., scattered across your codebase, thus impacting maintainability, readability and testing. Think of the traditional approach of using URLSession, manually converting decodable data types into the respective Model data structure and adding the logic each time.
*   **Abstraction Layers and Patterns:**
    *   **Protocol-Oriented Programming:** Using Swift protocols to define the interfaces for your networking operations. This makes it possible to plug different implementations or testing stubs for your calls. For instance define a protocol for your API endpoint, and make any concrete API calls conform to it
    *   **Abstract Model Layer:** The Model (or DTO / Data Transfer Object) layer is also prone to change. So, a generic type wrapper should be created which can easily be cast to different model data types.
    *  **Dependency Injection**: The client making the API call doesn't need to worry about instantiation of dependency requirements such as a URLSession. Using dependency injection allows the framework to abstract away from such details and improve code coverage
    *   **Error Handling Abstraction:** Define a consistent set of error types and responses as a reusable structure. This will enable handling of errors across different calls in a streamlined way.
    *   **Authentication Logic Layer:** The common header requirements for authentication such as Bearer tokens should be abstracted away into a layer which can be reused.
   *   **Framework approach**: Use a framework to contain well designed reusable network interfaces, protocols, handlers and configurations for all the above.
*   **iOS Specific Reuse Considerations**
    *   **URLSession and Combine:** `URLSession` is UIKit's primary tool for handling networking in a system, and Combine is a perfect fit for handling the asynchronous nature of network calls with well-defined publishers and subscribers. Designing the interfaces with Combine allows for better composition and reusability when making network calls.
    *  **Third-Party Libraries**: Third Party iOS library such as Alamofire, URLSession and Codable provide a good foundation to build a network layer abstraction. Using these can help with rapid development and testing.
 *   **Testing:** When your networking is well abstracted with clear interfaces, stubbing and mocking for unit testing becomes much easier. Your tests can now focus on testing data logic rather than being bogged down with testing the URL configuration, or raw json parsing code.
*   **Real-World Takeaway:** Building a robust, reusable networking layer demands strategic architecture and the usage of dependency injection, protocol based programming, well-defined types, consistent abstractions, error handling and use of Swift's structured concurrency. This upfront time investment pays off significantly with improved testability, easier maintenance, and adaptability to diverse data requirements over time.

----
