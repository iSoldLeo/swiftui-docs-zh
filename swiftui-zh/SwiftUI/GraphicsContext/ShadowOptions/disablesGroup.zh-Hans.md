---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions/disablesGroup
抓取时间： 2025-12-03T17:20:42Z
---

# disablesGroup

**类型属性**

使滤镜在当前图层中分别合成对象及其阴影的选项。

## 声明

```swift
static var disablesGroup: GraphicsContext.ShadowOptions { get }
```

## 获取阴影选项

- **invertsAlpha**：使滤镜反转阴影 alpha 值的选项。
- **shadowAbove**：使滤镜将阴影绘制在对象上方而非下方的选项。
- **shadowOnly**：使滤波器只绘制阴影而省略源对象的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions/disablesGroup
crawled: 2025-12-03T17:20:42Z
---

# disablesGroup

**Type Property**

An option that causes the filter to composite the object and its shadow separately in the current layer.

## Declaration

```swift
static var disablesGroup: GraphicsContext.ShadowOptions { get }
```

## Getting shadow options

- **invertsAlpha**: An option that causes the filter to invert the alpha of the shadow.
- **shadowAbove**: An option that causes the filter to draw the shadow above the object, rather than below it.
- **shadowOnly**: An option that causes the filter to draw only the shadow, and omit the source object.

