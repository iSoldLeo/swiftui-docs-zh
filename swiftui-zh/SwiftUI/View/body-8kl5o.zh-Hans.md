--- 来源：https://developer.apple.com/documentation/SwiftUI/View/body-8kl5o
抓取时间：2025-12-02T17:22:06Z

---

# body

**实例属性**

视图的内容和行为。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

实现自定义视图时，必须实现一个计算属性 `body` 来提供视图的内容。返回一个由 SwiftUI 提供的内置视图以及您已定义的其他复合视图组成的视图：

```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
```

有关组合视图和视图层次结构的更多信息，请参阅 [Declaring-a-Custom-View](../Declaring-a-Custom-View.zh-Hans.md)。

## 实现自定义视图

- **Body**：表示此视图主体的视图类型。

- **modifier(_:)**：对视图应用修饰符并返回一个新视图。

- **在 Xcode 中预览**：生成自定义视图的动态交互式预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/body-8kl5o
crawled: 2025-12-02T17:22:06Z
---

# body

**Instance Property**

The content and behavior of the view.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

When you implement a custom view, you must implement a computed `body` property to provide the content for your view. Return a view that’s composed of built-in views that SwiftUI provides, plus other composite views that you’ve already defined:

```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
```

For more information about composing views and a view hierarchy, see [Declaring-a-Custom-View](../Declaring-a-Custom-View.zh-Hans.md).

## Implementing a custom view

- **Body**: The type of view representing the body of this view.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **Previews in Xcode**: Generate dynamic, interactive previews of your custom views.

