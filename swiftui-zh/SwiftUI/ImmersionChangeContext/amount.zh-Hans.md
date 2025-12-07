---
来源： https://developer.apple.com/documentation/SwiftUI/ImmersionChangeContext/amount
抓取时间： 2025-12-03T05:33:45Z
---

# 数量

**实例属性**

当前的浸入量。

## 声明

```swift
let amount: Double?
```

## 讨论

您的应用程序可以使用[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 和不同的沉浸式样式显示虚拟内容，以创建身临其境的体验。根据沉浸式风格的不同，您的应用程序在打开沉浸式空间时，可以不遮挡、部分遮挡或全部遮挡视频直通内容，其遮挡量由该值表示。

某些沉浸式风格允许通过转动数字表冠来交互式地改变数量。

如果您的应用程序目前完全不提供任何沉浸式体验，则此值为`nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionChangeContext/amount
crawled: 2025-12-03T05:33:45Z
---

# amount

**Instance Property**

The current amount of immersion.

## Declaration

```swift
let amount: Double?
```

## Discussion

Your app can display virtual content using [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) and the different immersion styles to create immersive experiences. Depending on the immersion style, none of it, parts of it, or a all of video pass-through are occluded by your app while having an Immersive Space opened, and the amount of it is represented by this value.

Some immersion styles allow changing the amount interactively by turning the Digital Crown.

This value is `nil`, if your app currently does not provide any immersive experience at all.

