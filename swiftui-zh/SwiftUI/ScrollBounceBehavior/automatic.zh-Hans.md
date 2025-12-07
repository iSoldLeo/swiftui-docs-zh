---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior/automatic
抓取时间： 2025-12-03T06:43:05Z
---

# 自动

**类型属性**

自动行为。

## 声明

```swift
static var automatic: ScrollBounceBehavior { get }
```

## 讨论

当人们滚动到视图内容的末尾时，可滚动视图会自动选择内容是否跳转。默认情况下，可滚动视图使用[always](always.zh-Hans.md)行为。

## 跳转行为

- **always**：滚动视图总是弹跳。
- **basedOnSize**：当内容大到需要滚动时，滚动视图会弹起。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior/automatic
crawled: 2025-12-03T06:43:05Z
---

# automatic

**Type Property**

The automatic behavior.

## Declaration

```swift
static var automatic: ScrollBounceBehavior { get }
```

## Discussion

The scrollable view automatically chooses whether content bounces when people scroll to the end of the view’s content. By default, scrollable views use the [always](always.zh-Hans.md) behavior.

## Bounce behaviors

- **always**: The scrollable view always bounces.
- **basedOnSize**: The scrollable view bounces when its content is large enough to require scrolling.

