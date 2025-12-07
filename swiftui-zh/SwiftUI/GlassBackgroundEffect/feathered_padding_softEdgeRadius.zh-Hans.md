---
来源：https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect/feathered(padding:softEdgeRadius:)
抓取时间：2025-12-01T11:01:02Z


# feathered(padding:softEdgeRadius:)

**类型方法**

自定义填充和软边缘半径的羽毛背景效果。

## 声明

```swift
static func feathered(padding length: CGFloat, softEdgeRadius: CGFloat? = nil) -> FeatheredGlassBackgroundEffect
```

## 参数

- **softEdgeRadius**：剪切模糊时，模糊边缘的径向尺寸。如果将值设置为 `nil`，SwiftUI 将使用默认值。该参数的默认值为 `nil`。

## 返回值

羽化背景效果。


---
source: https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect/feathered(padding:softEdgeRadius:)
crawled: 2025-12-01T11:01:02Z
---

# feathered(padding:softEdgeRadius:)

**Type Method**

A feathered background effect with custom padding and soft edge radius.

## Declaration

```swift
static func feathered(padding length: CGFloat, softEdgeRadius: CGFloat? = nil) -> FeatheredGlassBackgroundEffect
```

## Parameters

- **softEdgeRadius**: When a blur is clipped, the radial size of the blur’s edge. If you set the value to `nil`, SwiftUI uses a default amount. The default value of this parameter is `nil`.

## Return Value

A feathered background effect.

