--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationTransition/zoom(sourceID:in:)

抓取时间：2025-12-03T06:17:12Z

---

# zoom(sourceID:in:)

**类型方法**

一种导航过渡效果，用于缩放当前视图，使其与给定的源视图保持一致。

## 声明

```swift
static func zoom(sourceID: some Hashable, in namespace: Namespace.ID) -> ZoomNavigationTransition
```

## 参数

- **sourceID**：您提供给相应 `matchedTransitionSource` 修饰符的标识符。

- **namespace**：您定义 `id` 的命名空间。您可以通过向 [View](../View.zh-Hans.md) 类型添加 [Namespace](../Namespace.zh-Hans.md) 属性来创建新的命名空间，然后在视图的 body 方法中读取其值。

## 讨论

使用 `View/matchedTransitionSource(id:namespace:)` 修饰符指示源视图。

## 获取内置过渡效果

- **automatic**：一种样式，可根据当前上下文自动选择合适的呈现过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationTransition/zoom(sourceID:in:)
crawled: 2025-12-03T06:17:12Z
---

# zoom(sourceID:in:)

**Type Method**

A navigation transition that zooms the appearing view from a given source view.

## Declaration

```swift
static func zoom(sourceID: some Hashable, in namespace: Namespace.ID) -> ZoomNavigationTransition
```

## Parameters

- **sourceID**: The identifier you provide to a corresponding `matchedTransitionSource` modifier.
- **namespace**: The namespace where you define the `id`. You can create new namespaces by adding the [Namespace](../Namespace.zh-Hans.md) attribute to a [View](../View.zh-Hans.md) type, then reading its value in the view’s body method.

## Discussion

Indicate the source view using the `View/matchedTransitionSource(id:namespace:)` modifier.

## Getting built-in transitions

- **automatic**: A style that automatically chooses the appropriate presentation transition for the current context.

