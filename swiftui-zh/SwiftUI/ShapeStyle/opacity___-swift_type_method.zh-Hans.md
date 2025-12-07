--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/opacity(_:)-swift.type.method

抓取时间：2025-12-01T11:14:32Z

---

# opacity(_:)

**类型方法**

返回一个基于当前样式的新样式，该样式在绘制时乘以 `opacity`。

## 声明

```swift
static func opacity(_ opacity: Double) -> some ShapeStyle

```

## 讨论

在大多数情况下，当前样式是前景样式，但例如，当设置背景样式的值时，该样式会成为当前的隐式样式。

例如，一个填充了当前前景样式且不透明度为 50% 的圆形：

```swift
Circle().fill(.opacity(0.5))
```

## 配置默认形状样式

- **blendMode(_:)**：返回一个基于当前样式的新样式，该样式在绘制时使用 `mode` 作为混合模式。

- **shadow(_:)**：返回一个将指定的阴影样式应用于当前样式的形状样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/opacity(_:)-swift.type.method
crawled: 2025-12-01T11:14:32Z
---

# opacity(_:)

**Type Method**

Returns a new style based on the current style that multiplies by `opacity` when drawing.

## Declaration

```swift
static func opacity(_ opacity: Double) -> some ShapeStyle

```

## Discussion

In most contexts the current style is the foreground but e.g. when setting the value of the background style, that becomes the current implicit style.

For example, a circle filled with the current foreground style at fifty-percent opacity:

```swift
Circle().fill(.opacity(0.5))
```

## Configuring the default shape style

- **blendMode(_:)**: Returns a new style based on the current style that uses `mode` as its blend mode when drawing.
- **shadow(_:)**: Returns a shape style that applies the specified shadow style to the current style.

