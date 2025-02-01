---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---


---


Let's discuss two subjects from "Part V - Looking to the Future" through the lens of an experienced iOS developer:

----

# Subject 1: The Threesome Marriage (Reengineering, Reuse, and Object-Oriented Techniques) Applied to iOS Development

As an experienced iOS developer, the "Threesome Marriage" resonates deeply.  iOS development heavily relies on object-oriented principles using Swift or Objective-C.  This makes reengineering and reuse natural parts of our workflow.

*   **Reengineering in iOS:**  We often encounter legacy Objective-C codebases that need modernization. Reengineering involves understanding this code (often with poor documentation), restructuring it using Swift, and leveraging newer frameworks like SwiftUI. This improves maintainability, performance, and allows integration of modern features.  Tools like Swiftify can assist in automated conversion, but careful review and refactoring are crucial.
*   **Reuse in iOS:**  Apple encourages reuse through its frameworks (UIKit, Foundation, SwiftUI) and design patterns (MVC, MVVM, etc.). We reuse UI components, networking code, data models, and algorithms extensively.  Swift packages and CocoaPods also promote reuse of third-party libraries.  However, challenges remain in finding and assessing the quality and suitability of these components for our projects.  Understanding the inner workings (white-box reuse) is often necessary for proper integration and customization.
*   **Interplay of Reengineering, Reuse, and OO:** Reengineering older apps often involves adopting CocoaPods/Swift Packages and replacing large, monolithic classes with smaller, reusable components following SOLID design principles.  This might mean introducing protocols and generics to improve flexibility and reduce coupling.  It also means building our own reusable component libraries within our organization for faster prototyping and implementation.

The Threesome Marriage is not just a research area; it's the daily reality of a modern iOS developer striving to build maintainable, scalable, and feature-rich applications.

---


# Subject 2: The Best of Both Worlds (Balancing New Tech and Legacy Systems) in the Context of iOS and Apple's Ecosystem

Apple's relentless pace of introducing new technologies (SwiftUI, Combine, ARKit, etc.) presents a constant "Best of Both Worlds" challenge.  As iOS developers, we need to adopt these advancements while maintaining support for older devices and OS versions and also ensuring backward compatibility with older components written using Objective-C.

*   **Incremental Adoption:** We rarely rewrite entire apps from scratch. Instead, we adopt new technologies incrementally. For example, integrating SwiftUI views into existing UIKit-based projects allows us to experiment, modernize parts of the UI, and progressively enhance the codebase.
*   **Interoperability:**  Swift's interoperability with Objective-C is crucial. It allows us to gradually transition legacy projects without a complete rewrite.  We can wrap Objective-C components in Swift interfaces or reuse Objective-C libraries within Swift projects.
*   **Balancing Act:**  Deciding when to adopt a new technology is a constant balancing act.  Factors to consider include project timelines, developer expertise, team resources, maintainability trade-offs, target OS versions, and potential benefits (performance improvements, reduced code complexity).
*   **Community and Resources:** The iOS development community plays a vital role.  Blogs, forums, open-source projects, and conferences help us stay updated, learn best practices, and find solutions for integration challenges.  Apple's documentation and WWDC sessions are essential resources.

As experienced iOS developers, navigating the "Best of Both Worlds" is part of our job description. It's about carefully planning our adoption strategies to leverage the latest advancements while preserving the stability and functionality of our existing applications.



---
