--- 来源：https://developer.apple.com/documentation/SwiftUI/View/Body-swift.associatedtype

抓取时间：2025-12-02T17:22:07Z

---

# Body

**关联类型**

表示此视图主体的视图类型。

## 声明

```swift
associatedtype Body : View
```

## 讨论

创建自定义视图时，Swift 会根据您对所需 [body-8kl5o](body-8kl5o.zh-Hans.md) 属性的实现来推断此类型。

## 实现自定义视图

- **body**：视图的内容和行为。

- **modifier(_:)**：对视图应用修饰符并返回一个新视图。

- **在 Xcode 中预览**：生成自定义视图的动态交互式预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/Body-swift.associatedtype
crawled: 2025-12-02T17:22:07Z
---

# Body

**Associated Type**

The type of view representing the body of this view.

## Declaration

```swift
associatedtype Body : View
```

## Discussion

When you create a custom view, Swift infers this type from your implementation of the required [body-8kl5o](body-8kl5o.zh-Hans.md) property.

## Implementing a custom view

- **body**: The content and behavior of the view.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **Previews in Xcode**: Generate dynamic, interactive previews of your custom views.

