--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/blendMode(_:)-swift.type.method

抓取时间：2025-12-03T06:25:26Z

---

# blendMode(_:)

**类型方法**

返回一个基于当前样式的新样式，该样式在绘制时使用 `mode` 作为其混合模式。

## 声明

```swift
static func blendMode(_ mode: BlendMode) -> some ShapeStyle

```

## 讨论

在大多数情况下，当前样式是前景样式，但例如，当设置背景样式的值时，该值会成为当前隐式样式。

例如，一个填充了当前前景样式和叠加混合模式的圆形：

```swift
Circle().fill(.blendMode(.overlay))
```

## 配置默认形状样式

- **opacity(_:)**：返回一个基于当前样式的新样式，绘制时乘以 `opacity`。

- **shadow(_:)**：返回一个将指定的阴影样式应用于当前样式的形状样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/blendMode(_:)-swift.type.method
crawled: 2025-12-03T06:25:26Z
---

# blendMode(_:)

**Type Method**

Returns a new style based on the current style that uses `mode` as its blend mode when drawing.

## Declaration

```swift
static func blendMode(_ mode: BlendMode) -> some ShapeStyle

```

## Discussion

In most contexts the current style is the foreground but e.g. when setting the value of the background style, that becomes the current implicit style.

For example, a circle filled with the current foreground style and the overlay blend mode:

```swift
Circle().fill(.blendMode(.overlay))
```

## Configuring the default shape style

- **opacity(_:)**: Returns a new style based on the current style that multiplies by `opacity` when drawing.
- **shadow(_:)**: Returns a shape style that applies the specified shadow style to the current style.

