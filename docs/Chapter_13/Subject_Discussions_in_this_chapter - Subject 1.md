---
source_url: ""
created: 2025-01-31 03:50:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
---


---


Below are a subject related to Chapter 13, "Building and Sustaining Maintainability", through the lens of an experienced iOS developer.

----

# Subject 1:  The Practical Realities of Applying Object-Oriented Principles (and their limitations) in iOS Development

Chapter 13 emphasizes the advantages of Object-Oriented Programming (OOP) for building maintainable systems.  As an experienced iOS developer, I can attest to the benefits of OOP principles like encapsulation, inheritance, and polymorphism in structuring code, promoting reuse, and managing complexity.  Swift, the primary language for iOS development, is inherently object-oriented, and frameworks like Foundation, UIKit, and SwiftUI heavily rely on these concepts.

Here's a breakdown from an iOS perspective:

*   **Encapsulation:**  Swift's access control modifiers (e.g., `private`, `fileprivate`, `internal`, `public`, `open`) allow us to control the visibility and accessibility of class members. This is crucial for encapsulation, ensuring that internal implementation details are hidden and only the necessary interfaces are exposed. This promotes modularity, reduces dependencies, and makes it easier to change implementations without affecting other parts of the codebase.
*   **Inheritance:**  Swift's class inheritance and protocol conformance enables us to create class hierarchies and share functionality between related classes.  For example, creating custom UI elements by subclassing `UIView` or `UIViewController` and overriding or extending their methods is common practice.  Protocols also provide a form of interface inheritance, enabling us to define behavior that multiple unrelated classes can adopt.
*   **Polymorphism:**  Swift supports polymorphism through protocol conformance and method overriding. This allows us to write more generic code that can operate on different types of objects. For instance, a `UITableView` can display different types of cells, as long as they conform to the `UITableViewCell` protocol.

*   **Practical Limitations of OOP in iOS:**  Even with diligent application of OOP, there are challenges in iOS:
    *   **Massive View Controllers:**  In large projects, view controllers can sometimes become very complex, handling too many responsibilities and breaking the "Single Responsibility Principle" from SOLID. Architectural patterns like MVVM (Model-View-ViewModel) and VIPER (View-Interactor-Presenter-Entity-Router) help mitigate this.  SwiftUI's declarative approach further reduces complexity.
    *   **Delegate and Notification Overuse:** While delegates and notifications are essential for decoupling, overuse can make data flow and control flow hard to trace and understand.  Combine's reactive programming provides a more structured approach.
    *    **Delegation can hinder inheritance.**



---

# Swift Code Implementation demo
Below are Swift code examples and descriptions provide a clearer understanding of the practical realities—both benefits and limitations—of Object-Oriented Principles when applied to contemporary iOS Development.

----


## 1. Encapsulation in Swift (Access Control)

Encapsulation is about bundling data and methods that operate on that data within a single unit (like a class) and controlling access to the internal workings. Swift's access control modifiers are key here.

```swift
import UIKit

class BankAccount {
    // Private property - only accessible within BankAccount class
    private var balance: Double = 0

    // Internal property - accessible within the same module (e.g., app)
    internal let accountNumber: String

    // Public method - accessible from anywhere
    public func deposit(amount: Double) {
        if amount > 0 {
            balance += amount
            print("Deposited \(amount). New balance: \(balance)")
        } else {
            print("Deposit amount must be positive.")
        }
    }

    // Private method - only accessible within BankAccount class
    private func withdrawInternal(amount: Double) -> Bool {
        if amount > 0 && balance >= amount {
            balance -= amount
            print("Withdrawn \(amount). New balance: \(balance)")
            return true
        } else {
            print("Insufficient funds or invalid withdrawal amount.")
            return false
        }
    }

    // Public method that uses the private withdrawInternal method
    public func withdraw(amount: Double) -> Bool {
        return withdrawInternal(amount: amount) // Internal logic encapsulated
    }

    // Internal (or public) method to get balance - controlled access to data
    internal func getBalance() -> Double {
        return balance // Controlled access to balance
    }

    // Initializer (public)
    public init(accountNumber: String) {
        self.accountNumber = accountNumber
    }
}

let myAccount = BankAccount(accountNumber: "1234567890")
myAccount.deposit(amount: 100) // OK - Public access
myAccount.withdraw(amount: 50) // OK - Public access to controlled withdrawal

// myAccount.balance = 1000 // Error: 'balance' is private - Encapsulation enforced!
print("Account balance: \(myAccount.getBalance())") // OK - Controlled access via public/internal methods
```

**Explanation:**

*   `private var balance`:  The `balance` is intentionally made `private`. External code cannot directly modify it, enforcing data integrity and encapsulation.
*   `internal let accountNumber`:  `accountNumber` is `internal`, meaning accessible within the same module. This is a good default for parts of your app's internal logic.
*   `public func deposit` and `public func withdraw`: These methods are `public`, providing the controlled interface to interact with the `BankAccount`. The `withdraw` function internally uses `withdrawInternal`, demonstrating how encapsulation hides the details of the withdrawal logic.
*   `getBalance()`: This `internal` (or could be `public`) method provides *read-only* access to the `balance`, further controlling how external code interacts with the account's data.

---

## 2. Inheritance in iOS (UIView Subclassing)

Inheritance allows us to create new classes that inherit properties and behaviors from existing classes. In iOS, `UIView` and its subclasses are excellent examples.

```swift
import UIKit

// Base class: Reusable button with common properties
class CustomButton: UIButton {
    override init(frame: CGRect) {
        super.init(frame: frame)
        setupButton()
    }

    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }

    private func setupButton() {
        self.backgroundColor = .systemBlue
        self.setTitleColor(.white, for: .normal)
        self.layer.cornerRadius = 8
        self.clipsToBounds = true
    }
}

// Subclass 1: Primary Action Button - Inherits from CustomButton, adding specific style
class PrimaryActionButton: CustomButton {
    override init(frame: CGRect) {
        super.init(frame: frame)
        customizePrimaryButton()
    }

    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }

    private func customizePrimaryButton() {
        self.titleLabel?.font = UIFont.boldSystemFont(ofSize: 18)
        self.backgroundColor = .systemGreen
    }
}


// Subclass 2: Secondary Action Button - Inherits from CustomButton, adding different style
class SecondaryActionButton: CustomButton {
    override init(frame: CGRect) {
        super.init(frame: frame)
        customizeSecondaryButton()
    }

    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }

    private func customizeSecondaryButton() {
        self.backgroundColor = .systemGray
        self.setTitleColor(.black, for: .normal)
    }
}


let primaryButton = PrimaryActionButton(frame: CGRect(x: 20, y: 50, width: 200, height: 50))
primaryButton.setTitle("Primary Action", for: .normal)

let secondaryButton = SecondaryActionButton(frame: CGRect(x: 20, y: 120, width: 200, height: 50))
secondaryButton.setTitle("Secondary Action", for: .normal)
```

**Explanation:**

*   `CustomButton`:  This is the **base class** defining common button properties (background color, text color, corner radius).
*   `PrimaryActionButton` and `SecondaryActionButton`: These are **subclasses** that **inherit** from `CustomButton`. They reuse the common setup logic and add specific customizations (font, background color) relevant to their particular button type.
*   `override init(frame: CGRect)`: Subclasses `override` the initializer to call the superclass initializer (`super.init(frame: frame)`) and then add their own setup code, demonstrating inheritance in action.


-----


## 3. Polymorphism in iOS (Protocols and UITableView)

Polymorphism allows objects of different classes to respond to the same method call in their own way. Protocols in Swift enable polymorphism, particularly useful in iOS for components like `UITableView`.

```swift
import UIKit

// Protocol defining common behavior for data items in a list
protocol ListDataItem {
    var title: String { get }
    var subtitle: String? { get }
    var icon: UIImage? { get }
}

// Concrete data item types conforming to ListDataItem
struct User: ListDataItem {
    let name: String
    let email: String
    var title: String { return name }
    var subtitle: String? { return email }
    var icon: UIImage? { return UIImage(systemName: "person.circle.fill") }
}

struct Product: ListDataItem {
    let productName: String
    let price: Double
    var title: String { return productName }
    var subtitle: String? { return String(format: "$%.2f", price) }
    var icon: UIImage? { return UIImage(systemName: "cube.box.fill") }
}


class ListViewController: UITableViewController {
    var items: [ListDataItem] = []

    override func viewDidLoad() {
        super.viewDidLoad()
        tableView.register(UITableViewCell.self, forCellReuseIdentifier: "cell")
        items = [
            User(name: "Alice Smith", email: "alice@example.com"),
            Product(productName: "Awesome Gadget", price: 99.99),
            User(name: "Bob Johnson", email: "bob@example.com")
        ]
    }

    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return items.count
    }

    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
        let item = items[indexPath.row]

        cell.textLabel?.text = item.title // Polymorphic access via protocol
        cell.detailTextLabel?.text = item.subtitle
        cell.imageView?.image = item.icon

        return cell
    }
}
```

**Explanation:**

*   `ListDataItem` Protocol: Defines the common interface (`title`, `subtitle`, `icon`) for any item that can be displayed in a list.
*   `User` and `Product` Structs:  These concrete types conform to the `ListDataItem` protocol and provide their specific data and implementations for the protocol requirements.
*   `ListViewController`: The `UITableView` in this controller works with an array of `ListDataItem`. The `cellForRowAt` method demonstrates **polymorphism**: it accesses `item.title`, `item.subtitle`, and `item.icon` **polymorphically**. The code doesn't need to know if `item` is a `User` or a `Product`; it just knows it conforms to `ListDataItem` and has those properties.

----


## 4. Limitations of OOP in Contemporary iOS Development (Massive View Controllers & Delegate Overuse)

These examples are more descriptive, highlighting common iOS development pitfalls that OOP, if not applied thoughtfully, can sometimes worsen:

### Massive View Controllers (Problem)

```swift
// Imagine a very large UIViewController subclass...
class ShoppingCartViewController: UIViewController, UITableViewDataSource, UITableViewDelegate, UITextFieldDelegate, ProductSelectionDelegate, PaymentProcessingDelegate, LocationServicesDelegate, ... {

    // ... hundreds or thousands of lines of code ...

    // Managing UI, data fetching, business logic, presentation,
    // networking, location services, payments, etc. within ONE class!

    // Hard to understand, test, and maintain.
}
```

**Explanation:**  While OOP encourages modularity within *objects*, it's easy to create "God Objects" like Massive View Controllers that manage too much. This leads to tight coupling, reduced reusability, and difficulty in testing (as the diagram illustrates). OOP alone doesn't prevent this; architectural patterns are needed alongside OOP to further decompose responsibilities.

### Delegate and Protocol Overuse (Potential Problem, if Uncontrolled)

```swift
// Example of delegate callback hell - hard to trace execution
class MyObject {
    weak var delegate: MyDelegate?

    func doSomethingAsync() {
        // ... async operation ...
        delegate?.myObjectDidComplete(self, withResult: result) // Delegate callback
    }
}


class  ViewController: UIViewController, MyDelegate, AnotherDelegate, YetAnotherDelegate, ... {

    // ... implementing multiple delegate protocols ...

    func myObjectDidComplete(_ object: MyObject, withResult result: ResultType) {
        // ... handle callback, potentially triggering other async operations
        anotherObject.performAnotherAsyncAction(delegate: self) // Another delegate call
    }

    func anotherObjectDidComplete(_ object: AnotherObject, withAnotherResult result: AnotherResultType) {
        // ... and so on ...

    }
}
```

**Explanation:** Delegates are essential for decoupling *object communication* in iOS (e.g., UITableViewDelegate). However, deeply nested delegate callbacks can create "callback hell," making control flow and data updates difficult to track. This isn't OOP's fault *per se*, but it's a common pattern where protocol-based OOP designs, if not carefully managed, can become complex to maintain.  Reactive programming (Combine) and state management solutions (like Redux with SwiftUI) are often used to simplify asynchronous data flow and state updates instead of relying solely on delegates.


----
