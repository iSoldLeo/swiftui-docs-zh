--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/callAsFunction(_:completion:)

抓取时间：2025-12-01T11:37:18Z

---

# callAsFunction(_:completion:)

**实例方法**

异步打开 URL，遵循系统约定。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction(_ url: URL, completion: @escaping (Bool) -> Void)
```

## 参数

- **url**：要打开的 URL。

- **completion**：一个闭包，该方法在确定是否可以打开 URL 后调用，但可能在完全打开 URL 之前调用。该闭包接受一个布尔值，指示该方法是否可以打开 URL。

## 说明

请勿直接调用此方法。当您使用 URL 和完成处理程序作为参数调用从 [Environment](../Environment.zh-Hans.md) 获取的 [OpenURLAction](../OpenURLAction.zh-Hans.md) 结构时，SwiftUI 会调用它：

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                // Implicitly calls openURL.callAsFunction(url) { ... }
                openURL(url) { accepted in
                    print(accepted ? "Success" : "Failure")
                }
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(_:)**：打开一个 URL，遵循系统约定。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/callAsFunction(_:completion:)
crawled: 2025-12-01T11:37:18Z
---

# callAsFunction(_:completion:)

**Instance Method**

Asynchronously opens a URL, following system conventions.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction(_ url: URL, completion: @escaping (Bool) -> Void)
```

## Parameters

- **url**: The URL to open.
- **completion**: A closure the method calls after determining if it can open the URL, but possibly before fully opening the URL. The closure takes a Boolean value that indicates whether the method can open the URL.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [OpenURLAction](../OpenURLAction.zh-Hans.md) structure that you get from the [Environment](../Environment.zh-Hans.md), using a URL and a completion handler as arguments:

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                // Implicitly calls openURL.callAsFunction(url) { ... }
                openURL(url) { accepted in
                    print(accepted ? "Success" : "Failure")
                }
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(_:)**: Opens a URL, following system conventions.

