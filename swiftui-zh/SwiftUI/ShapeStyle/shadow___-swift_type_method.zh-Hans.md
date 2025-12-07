--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/shadow(_:)-swift.type.method

抓取时间：2025-12-01T11:14:32Z

---

# shadow(_:)

**类型方法**

返回一个形状样式，该样式将指定的阴影样式应用于当前样式。

## 声明

```swift
static func shadow(_ style: ShadowStyle) -> some ShapeStyle

```

## 参数

- **style**：要应用的阴影样式。

## 返回值

一个基于当前样式并使用指定阴影样式的新形状样式。

## 说明

在大多数情况下，当前样式是前景样式，但并非总是如此。例如，当设置背景样式的值时，它将成为当前的隐式样式。

以下示例创建一个使用当前前景样式并带有内阴影的圆形：

```swift
Circle().fill(.shadow(.inner(radius: 1, y: 1)))
```

## 配置默认形状样式

- **blendMode(_:)**：返回一个基于当前样式的新样式，该样式在绘制时使用 `mode` 作为混合模式。

- **opacity(_:)**：返回一个基于当前样式的新样式，该样式在绘制时乘以 `opacity`。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/shadow(_:)-swift.type.method
crawled: 2025-12-01T11:14:32Z
---

# shadow(_:)

**Type Method**

Returns a shape style that applies the specified shadow style to the current style.

## Declaration

```swift
static func shadow(_ style: ShadowStyle) -> some ShapeStyle

```

## Parameters

- **style**: The shadow style to apply.

## Return Value

A new shape style based on the current style that uses the specified shadow style.

## Discussion

In most contexts the current style is the foreground, but not always. For example, when setting the value of the background style, that becomes the current implicit style.

The following example creates a circle filled with the current foreground style that uses an inner shadow:

```swift
Circle().fill(.shadow(.inner(radius: 1, y: 1)))
```

## Configuring the default shape style

- **blendMode(_:)**: Returns a new style based on the current style that uses `mode` as its blend mode when drawing.
- **opacity(_:)**: Returns a new style based on the current style that multiplies by `opacity` when drawing.

