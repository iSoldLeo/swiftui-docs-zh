---
来源：https://developer.apple.com/documentation/SwiftUI/MatchedTransitionSourceConfiguration/shadow(颜色:半径:x:y:)
抓取时间：2025-12-01T11:06:25Z
---

# shadow(color:radius:x:y:)

**实例方法**

将指定的阴影效果应用到匹配的过渡源。

## 声明

```swift
func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> some MatchedTransitionSourceConfiguration

```

## 参数

- **color**：阴影的颜色。
- **radius**： 阴影的颜色：用于衡量阴影的模糊程度。数值越大，模糊程度越高。
- **x**：阴影与视图的水平偏移量。
- **y**：从视图垂直偏移阴影的量。


---
source: https://developer.apple.com/documentation/SwiftUI/MatchedTransitionSourceConfiguration/shadow(color:radius:x:y:)
crawled: 2025-12-01T11:06:25Z
---

# shadow(color:radius:x:y:)

**Instance Method**

Applies the specified shadow effect to the matched transition source.

## Declaration

```swift
func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> some MatchedTransitionSourceConfiguration

```

## Parameters

- **color**: The shadow’s color.
- **radius**: A measure of how much to blur the shadow. Larger values result in more blur.
- **x**: An amount to offset the shadow horizontally from the view.
- **y**: An amount to offset the shadow vertically from the view.

