---
来源： https://developer.apple.com/documentation/SwiftUI/LazyVStack
抓取时间： 2025-12-02T17:27:26Z
---

# LazyVStack

**Structure**

一种视图，它将其子视图排列成一行，并垂直增长，只在需要时创建项目。

### 声明

```swift
struct LazyVStack<Content> where Content : View
```

## 概览

堆栈是 "懒惰 "的，因为堆栈视图在需要在屏幕上呈现项目时才会创建项目。

在下面的示例中，一个[ScrollView](ScrollView.zh-Hans.md)包含一个`LazyVStack`，该⟦由一竖排文本视图组成。堆栈与滚动视图的前缘对齐，文本视图之间使用默认间距。

```swift
ScrollView {
    LazyVStack(alignment: .leading) {
        ForEach(1...100, id: \.self) {
            Text("Row \($0)")
        }
    }
}
```

## 创建懒加载垂直堆栈

- **init(alignment:spacing:pinnedViews:content:)**：以给定的间距、垂直对齐方式、固定行为和内容创建懒加载垂直堆栈视图。

## 在一个维度上动态排列视图

- 用懒惰堆栈视图分组数据**：在懒堆叠视图中将内容分割成逻辑部分。
- 创建性能良好的可滚动堆栈**：使用滚动视图、堆栈视图和懒堆栈高效显示大量重复视图。
- **LazyHStack**：一种视图，可将其子视图排列成一条水平增长的线，只在需要时创建项目。
- **PinnedScrollableViews**：可固定在滚动视图边界上的视图类型集。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/LazyVStack
crawled: 2025-12-02T17:27:26Z
---

# LazyVStack

**Structure**

A view that arranges its children in a line that grows vertically, creating items only as needed.

## Declaration

```swift
struct LazyVStack<Content> where Content : View
```

## Overview

The stack is “lazy,” in that the stack view doesn’t create items until it needs to render them onscreen.

In the following example, a [ScrollView](ScrollView.zh-Hans.md) contains a `LazyVStack` that consists of a vertical row of text views. The stack aligns to the leading edge of the scroll view, and uses default spacing between the text views.

```swift
ScrollView {
    LazyVStack(alignment: .leading) {
        ForEach(1...100, id: \.self) {
            Text("Row \($0)")
        }
    }
}
```

## Creating a lazy-loading vertical stack

- **init(alignment:spacing:pinnedViews:content:)**: Creates a lazy vertical stack view with the given spacing, vertical alignment, pinning behavior, and content.

## Dynamically arranging views in one dimension

- **Grouping data with lazy stack views**: Split content into logical sections inside lazy stack views.
- **Creating performant scrollable stacks**: Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.
- **LazyHStack**: A view that arranges its children in a line that grows horizontally, creating items only as needed.
- **PinnedScrollableViews**: A set of view types that may be pinned to the bounds of a scroll view.

## Conforms To

- View

