--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollInputKind
抓取时间：2025-12-02T17:40:48Z

---

# ScrollInputKind

**Structure**

用于滚动视图的输入框。

## 声明

```swift
struct ScrollInputKind
```

## 类型属性

- **handGestureShortcut**：用户可以通过手指或手腕的移动来滚动视图。

- **look**：在 VisionOS 系统中，用户注视滚动视图的边缘即可自动滚动内容。滚动轴将自动确定。

## 类型方法

- **look(axes:)**：在 VisionOS 系统中，用户注视滚动视图的边缘即可自动滚动内容。此构造函数方法接受一组可滚动轴。

## 管理不同输入的滚动

- **scrollInputBehavior(_:for:)**：启用或禁用使用特定输入时可滚动视图的滚动功能。

- **ScrollInputBehavior**：定义输入是否应滚动视图的类型。

## 符合以下规范

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollInputKind
crawled: 2025-12-02T17:40:48Z
---

# ScrollInputKind

**Structure**

Inputs used to scroll views.

## Declaration

```swift
struct ScrollInputKind
```

## Type Properties

- **handGestureShortcut**: A finger or wrist movement that the user can perform in order to scroll a view.
- **look**: On visionOS, by looking at the edge of a scroll view the content can automatically scroll. The axes will be determined automatically.

## Type Methods

- **look(axes:)**: On visionOS, by looking at the edge of a scroll view the content can automatically scroll. This contructor method takes a set of the scrollable axes.

## Managing scrolling for different inputs

- **scrollInputBehavior(_:for:)**: Enables or disables scrolling in scrollable views when using particular inputs.
- **ScrollInputBehavior**: A type that defines whether input should scroll a view.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

