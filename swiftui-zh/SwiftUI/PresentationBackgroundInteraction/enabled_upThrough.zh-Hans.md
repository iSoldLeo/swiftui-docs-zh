--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/enabled(upThrough:)

抓取时间：2025-12-01T10:51:38Z

---

# enabled(upThrough:)

**类型方法**

用户可以与演示文稿背后的视图进行交互，交互范围上限为指定的距离。

## 声明

```swift
static func enabled(upThrough detent: PresentationDetent) -> PresentationBackgroundInteraction
```

## 参数

- **detent**：用户可以与演示文稿背后的视图进行交互的最大距离。

## 说明

如果距离大于您指定的距离，SwiftUI 将禁用交互。

## 获取交互类型

- **automatic**：演示文稿的默认后台交互方式。

- **disabled**：用户无法与演示文稿背后的视图进行交互。

- **enabled**：用户可以与演示文稿背后的视图进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/enabled(upThrough:)
crawled: 2025-12-01T10:51:38Z
---

# enabled(upThrough:)

**Type Method**

People can interact with the view behind a presentation up through a specified detent.

## Declaration

```swift
static func enabled(upThrough detent: PresentationDetent) -> PresentationBackgroundInteraction
```

## Parameters

- **detent**: The largest detent at which people can interact with the view behind the presentation.

## Discussion

At detents larger than the one you specify, SwiftUI disables interaction.

## Getting interaction types

- **automatic**: The default background interaction for the presentation.
- **disabled**: People can’t interact with the view behind a presentation.
- **enabled**: People can interact with the view behind a presentation.

