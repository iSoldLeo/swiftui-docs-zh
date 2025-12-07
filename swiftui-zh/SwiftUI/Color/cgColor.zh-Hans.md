---
来源： https://developer.apple.com/documentation/SwiftUI/Color/cgColor
抓取时间：2025-12-03T05:40:00Z
---

# cgColor

**实例属性**

颜色的核心图形表示（如果有）。

## 声明

```swift
var cgColor: CGColor? { get }
```

## 讨论

您可以从恒定的 SwiftUI 颜色中获取[doc://com.apple.documentation/documentation/CoreGraphics/CGColor] 实例。这包括您从 Core Graphics 颜色、RGB 或 HSB 组件或 UIKit 和 AppKit 常量颜色创建的颜色。

对于动态颜色，如使用[init(_:bundle:)](init___bundle.zh-Hans.md) 从资产目录加载的颜色，或从动态 UIKit 或 AppKit 颜色创建的颜色，该属性为`nil`。要评估所有类型的颜色，请使用 `resolve(in:)` 方法。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/cgColor
crawled: 2025-12-03T05:40:00Z
---

# cgColor

**Instance Property**

A Core Graphics representation of the color, if available.

## Declaration

```swift
var cgColor: CGColor? { get }
```

## Discussion

You can get a [doc://com.apple.documentation/documentation/CoreGraphics/CGColor] instance from a constant SwiftUI color. This includes colors you create from a Core Graphics color, from RGB or HSB components, or from constant UIKit and AppKit colors.

For a dynamic color, like one you load from an Asset Catalog using [init(_:bundle:)](init___bundle.zh-Hans.md), or one you create from a dynamic UIKit or AppKit color, this property is `nil`. To evaluate all types of colors, use the `resolve(in:)` method.

