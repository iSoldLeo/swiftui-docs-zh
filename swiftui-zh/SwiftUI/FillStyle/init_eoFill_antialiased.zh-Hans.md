---
来源：https://developer.apple.com/documentation/SwiftUI/FillStyle/init(eoFill:antialiased:)
抓取时间：2025-12-03T06:24:36Z
---

# init(eoFill:antialiased:)

**Initializer**

使用指定的设置创建新的填充样式。

## 声明

```swift
init(eoFill: Bool = false, antialiased: Bool = true)
```

## 参数

- **eoFill**：布尔值，表示是否使用偶数规则渲染形状。通过 `false`，可以使用非零绕组数规则。
- **antialiased**：布尔值，用于指示在渲染形状边缘时是否使用抗锯齿。


---
source: https://developer.apple.com/documentation/SwiftUI/FillStyle/init(eoFill:antialiased:)
crawled: 2025-12-03T06:24:36Z
---

# init(eoFill:antialiased:)

**Initializer**

Creates a new fill style with the specified settings.

## Declaration

```swift
init(eoFill: Bool = false, antialiased: Bool = true)
```

## Parameters

- **eoFill**: A Boolean value that indicates whether to use the even-odd rule for rendering a shape. Pass `false` to use the non-zero winding number rule instead.
- **antialiased**: A Boolean value that indicates whether to use antialiasing when rendering the edges of a shape.

