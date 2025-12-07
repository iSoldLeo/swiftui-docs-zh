---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions/invertsAlpha
抓取时间： 2025-12-03T17:20:43Z
---

# invertsAlpha

**类型属性**

使滤镜反转阴影 alpha 值的选项。

## 声明

```swift
static var invertsAlpha: GraphicsContext.ShadowOptions { get }
```

## 讨论

将此选项与[shadowAbove](shadowAbove.zh-Hans.md) 结合并使用[sourceAtop](../BlendMode-swift_struct/sourceAtop.zh-Hans.md) 混合模式，可以创建 "内阴影 "效果。

## 获取阴影选项

- **disablesGroup**：使滤镜在当前图层中分别合成对象及其阴影的选项。
- **shadowAbove**：使滤镜将阴影绘制在对象上方而非下方的选项。
- **shadowOnly**：使滤波器只绘制阴影而省略源对象的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions/invertsAlpha
crawled: 2025-12-03T17:20:43Z
---

# invertsAlpha

**Type Property**

An option that causes the filter to invert the alpha of the shadow.

## Declaration

```swift
static var invertsAlpha: GraphicsContext.ShadowOptions { get }
```

## Discussion

You can create an “inner shadow” effect by combining this option with [shadowAbove](shadowAbove.zh-Hans.md) and using the [sourceAtop](../BlendMode-swift_struct/sourceAtop.zh-Hans.md) blend mode.

## Getting shadow options

- **disablesGroup**: An option that causes the filter to composite the object and its shadow separately in the current layer.
- **shadowAbove**: An option that causes the filter to draw the shadow above the object, rather than below it.
- **shadowOnly**: An option that causes the filter to draw only the shadow, and omit the source object.

