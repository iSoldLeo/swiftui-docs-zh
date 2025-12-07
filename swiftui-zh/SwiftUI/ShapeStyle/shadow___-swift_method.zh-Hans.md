--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/shadow(_:)-swift.method

抓取时间：2025-12-03T06:25:25Z

---

# shadow(_:)

**实例方法**

将指定的阴影效果应用于形状样式。

## 声明

```swift
func shadow(_ style: ShadowStyle) -> some ShapeStyle

```

## 参数

- **style**：要应用的阴影样式。

## 返回值

使用指定阴影样式的新形状样式。

## 说明

例如，您可以创建一个矩形，并为其添加阴影效果。[red](red.zh-Hans.md)

```swift
Rectangle().fill(.red.shadow(.drop(radius: 2, y: 3)))
```

## 修改形状样式

- **blendMode(_:)**：基于 `self` 返回一个新样式，该样式在绘制时应用指定的混合模式。

- **opacity(_:)**：基于 `self` 返回一个新样式，该样式在绘制时乘以指定的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/shadow(_:)-swift.method
crawled: 2025-12-03T06:25:25Z
---

# shadow(_:)

**Instance Method**

Applies the specified shadow effect to the shape style.

## Declaration

```swift
func shadow(_ style: ShadowStyle) -> some ShapeStyle

```

## Parameters

- **style**: The shadow style to apply.

## Return Value

A new shape style that uses the specified shadow style.

## Discussion

For example, you can create a rectangle that adds a drop shadow to the [red](red.zh-Hans.md) shape style.

```swift
Rectangle().fill(.red.shadow(.drop(radius: 2, y: 3)))
```

## Modifying a shape style

- **blendMode(_:)**: Returns a new style based on `self` that applies the specified blend mode when drawing.
- **opacity(_:)**: Returns a new style based on `self` that multiplies by the specified opacity when drawing.

