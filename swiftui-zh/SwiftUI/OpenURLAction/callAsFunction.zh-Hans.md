--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/callAsFunction(_:)

抓取时间：2025-12-03T06:48:05Z

---

# callAsFunction(_:)

**实例方法**

按照系统约定打开一个 URL。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction(_ url: URL)
```

## 参数

- **url**：要打开的 URL。

## 说明

请勿直接调用此方法。当您使用 URL 作为参数调用从 [Environment](../Environment.zh-Hans.md) 获取的 [OpenURLAction](../OpenURLAction.zh-Hans.md) 结构时，SwiftUI 会调用它：

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                openURL(url) // Implicitly calls openURL.callAsFunction(url)
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(_:completion:)**：异步打开 URL，遵循系统约定。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/callAsFunction(_:)
crawled: 2025-12-03T06:48:05Z
---

# callAsFunction(_:)

**Instance Method**

Opens a URL, following system conventions.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction(_ url: URL)
```

## Parameters

- **url**: The URL to open.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [OpenURLAction](../OpenURLAction.zh-Hans.md) structure that you get from the [Environment](../Environment.zh-Hans.md), using a URL as an argument:

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                openURL(url) // Implicitly calls openURL.callAsFunction(url)
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(_:completion:)**: Asynchronously opens a URL, following system conventions.

