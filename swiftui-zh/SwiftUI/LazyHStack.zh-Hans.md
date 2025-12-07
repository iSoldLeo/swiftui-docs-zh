---
来源： https://developer.apple.com/documentation/SwiftUI/LazyHStack
抓取时间： 2025-12-02T17:27:24Z
---

# LazyHStack

**Structure**

一种视图，它将其子视图排列成一条水平增长的线，只在需要时创建项目。

## 声明

```swift
struct LazyHStack<Content> where Content : View
```

## 概览

堆栈是 "懒惰 "的，因为堆栈视图在需要在屏幕上呈现项目时才会创建项目。

在下面的示例中，一个[ScrollView](ScrollView.zh-Hans.md)包含一个`LazyHStack`，该⟦由一列水平的文本视图组成。堆栈与滚动视图的顶部对齐，每个文本视图之间使用 10 点间距。

```swift
ScrollView(.horizontal) {
    LazyHStack(alignment: .top, spacing: 10) {
        ForEach(1...100, id: \.self) {
            Text("Column \($0)")
        }
    }
}
```

## 创建懒加载水平堆栈

- **init(alignment:spacing:pinnedViews:content:)**：以给定的间距、垂直对齐方式、固定行为和内容创建一个懒加载的水平堆栈视图。

## 在一个维度上动态排列视图

- 用懒惰堆栈视图**分组数据**：在懒堆叠视图中将内容分割成逻辑部分。
- 创建性能良好的可滚动堆栈**：使用滚动视图、堆栈视图和懒堆栈高效显示大量重复视图。
- **LazyVStack**：一种视图，可将其子视图排列成一条垂直增长的线，只在需要时创建项目。
- **PinnedScrollableViews**：可固定在滚动视图边界上的视图类型集。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/LazyHStack
crawled: 2025-12-02T17:27:24Z
---

# LazyHStack

**Structure**

A view that arranges its children in a line that grows horizontally, creating items only as needed.

## Declaration

```swift
struct LazyHStack<Content> where Content : View
```

## Overview

The stack is “lazy,” in that the stack view doesn’t create items until it needs to render them onscreen.

In the following example, a [ScrollView](ScrollView.zh-Hans.md) contains a `LazyHStack` that consists of a horizontal row of text views. The stack aligns to the top of the scroll view and uses 10-point spacing between each text view.

```swift
ScrollView(.horizontal) {
    LazyHStack(alignment: .top, spacing: 10) {
        ForEach(1...100, id: \.self) {
            Text("Column \($0)")
        }
    }
}
```

## Creating a lazy-loading horizontal stack

- **init(alignment:spacing:pinnedViews:content:)**: Creates a lazy horizontal stack view with the given spacing, vertical alignment, pinning behavior, and content.

## Dynamically arranging views in one dimension

- **Grouping data with lazy stack views**: Split content into logical sections inside lazy stack views.
- **Creating performant scrollable stacks**: Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.
- **LazyVStack**: A view that arranges its children in a line that grows vertically, creating items only as needed.
- **PinnedScrollableViews**: A set of view types that may be pinned to the bounds of a scroll view.

## Conforms To

- View

