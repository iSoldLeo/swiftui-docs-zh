--- 来源：https://developer.apple.com/documentation/SwiftUI/ConcentricRectangle/init(corners:isUniform:)

抓取时间：2025-12-03T05:40:16Z

---

# init(corners:isUniform:)

**Initializer**

创建一个四个角都设置相同角样式的矩形。

## 声明

```swift
init(corners: Edge.Corner.Style, isUniform: Bool = false)
```

## 参数

- **corners**：四个角的角样式。

- **isUniform**：每个角的角样式是单独应用还是统一应用。

## 讨论

[ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) 四个角都设置为同心圆的矩形，其解析半径可能会有所不同。当矩形未位于容器形状的中心，或者容器形状本身每个角的半径不同时，就会出现这种情况。如果设置为统一半径，[ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) 会先分别计算每个角的半径，然后选择已计算出的半径最大的角，并将其统一应用，以实现对称效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ConcentricRectangle/init(corners:isUniform:)
crawled: 2025-12-03T05:40:16Z
---

# init(corners:isUniform:)

**Initializer**

Create a rectangle with the same corner style set on four corners.

## Declaration

```swift
init(corners: Edge.Corner.Style, isUniform: Bool = false)
```

## Parameters

- **corners**: The corner style for all four corners.
- **isUniform**: Should the corner style on each corner be applied individually or uniformly.

## Discussion

A [ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) with all four corners set to concentric individually can vary in resolved radius. This can happen when the rectangle is not centered within the container shape, or the container shape itself has different radius per corner. If set to be uniform, [ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) will resolve each corner on its own first, then pick the largest resolved radius out of the corners and apply it uniformly to achieve the symmetric look.

