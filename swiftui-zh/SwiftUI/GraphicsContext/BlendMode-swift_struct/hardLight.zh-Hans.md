---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/hardLight
抓取时间： 2025-12-03T17:20:13Z
---

# 硬光

**类型属性**

根据源图像样本颜色，对颜色进行倍增或筛选的模式。

## 声明

```swift
static var hardLight: GraphicsContext.BlendMode { get }
```

## 讨论

如果源图像样本颜色浅于 50% 灰色，背景会变亮，类似于筛选。如果源图像样本颜色比 50% 灰色深，背景会变暗，类似于乘法。如果源图像样本颜色等于 50% 灰色，则不改变源图像。如果图像样本颜色等于纯黑或纯白，则会产生纯黑或纯白的效果。整体效果类似于用刺眼的聚光灯照射源图像。使用此功能可为场景添加高光。

## 添加对比度

- **overlay**：根据背景颜色，将源图像样本与背景图像样本相乘或截屏的模式。
- **softLight**：根据源图像样本的颜色，使颜色变暗或变亮的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/hardLight
crawled: 2025-12-03T17:20:13Z
---

# hardLight

**Type Property**

A mode that either multiplies or screens colors, depending on the source image sample color.

## Declaration

```swift
static var hardLight: GraphicsContext.BlendMode { get }
```

## Discussion

If the source image sample color is lighter than 50% gray, the background is lightened, similar to screening. If the source image sample color is darker than 50% gray, the background is darkened, similar to multiplying. If the source image sample color is equal to 50% gray, the source image is not changed. Image samples that are equal to pure black or pure white result in pure black or white. The overall effect is similar to what you’d achieve by shining a harsh spotlight on the source image. Use this to add highlights to a scene.

## Adding contrast

- **overlay**: A mode that either multiplies or screens the source image samples with the background image samples, depending on the background color.
- **softLight**: A mode that either darkens or lightens colors, depending on the source image sample color.

