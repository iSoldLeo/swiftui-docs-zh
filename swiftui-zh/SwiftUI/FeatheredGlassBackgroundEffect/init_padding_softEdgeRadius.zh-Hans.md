---
来源：https://developer.apple.com/documentation/SwiftUI/FeatheredGlassBackgroundEffect/init(padding:softEdgeRadius:)
抓取时间：2025-12-01T11:01:05Z


# init(padding:softEdgeRadius:)

**Initializer**

创建羽状玻璃背景效果。

## 声明

```swift
init(padding length: CGFloat, softEdgeRadius: CGFloat? = nil)
```

## 返回值

羽化背景效果。

## 讨论

- padding.填充：以点为单位的数量，用于在渲染样式时填充所有边缘。不过，它不会影响布局大小，布局大小基于内容大小。当它小于效果的模糊大小时，模糊将被剪切。
- 软边缘半径：当模糊被剪切时，模糊边缘的径向尺寸。如果将值设置为 `nil`，SwiftUI 将使用默认值。该参数的默认值为 `nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/FeatheredGlassBackgroundEffect/init(padding:softEdgeRadius:)
crawled: 2025-12-01T11:01:05Z
---

# init(padding:softEdgeRadius:)

**Initializer**

Creates a feathered glassBackground effect.

## Declaration

```swift
init(padding length: CGFloat, softEdgeRadius: CGFloat? = nil)
```

## Return Value

A feathered background effect.

## Discussion

- padding: An amount, given in points, to pad all edges when style is renderding. However, it does not affect layout size, which is based on the content size. When it is less than effect’s blur size, the blur will be clipped.
- softEdgeRadius: When a blur is clipped, the radial size of the blur’s edge. If you set the value to `nil`, SwiftUI uses a default amount. The default value of this parameter is `nil`.

