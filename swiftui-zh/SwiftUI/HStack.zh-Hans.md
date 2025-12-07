---
来源： https://developer.apple.com/documentation/SwiftUI/HStack
抓取时间： 2025-12-02T17:27:16Z
---

# HStack

**Structure**

按水平线排列子视图的视图。

## 声明

```swift
@frozen struct HStack<Content> where Content : View
```

## 概览

[LazyHStack](LazyHStack.zh-Hans.md)仅在应用程序需要在屏幕上显示视图时才渲染视图，而`HStack`则不同，无论视图是在屏幕上还是屏幕外，它都会一次性渲染视图。如果您的子视图数量较少，或者不需要 "懒惰 "版本的延迟渲染行为，请使用常规`HStack`。

下面的示例显示了一个由五个文本视图组成的简单水平堆栈：

```swift
var body: some View {
    HStack(
        alignment: .top,
        spacing: 10
    ) {
        ForEach(
            1...5,
            id: \.self
        ) {
            Text("Item \($0)")
        }
    }
}
```





## 创建堆栈

- **init(alignment:spacing:content:)**：按照给定的间距和垂直对齐方式创建水平堆栈。

## 静态排列一维视图

- 使用堆栈视图构建布局**：从原始容器视图组成复杂布局。
- **VStack**：以垂直线排列子视图的视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/HStack
crawled: 2025-12-02T17:27:16Z
---

# HStack

**Structure**

A view that arranges its subviews in a horizontal line.

## Declaration

```swift
@frozen struct HStack<Content> where Content : View
```

## Overview

Unlike [LazyHStack](LazyHStack.zh-Hans.md), which only renders the views when your app needs to display them onscreen, an `HStack` renders the views all at once, regardless of whether they are on- or offscreen. Use the regular `HStack` when you have a small number of subviews or don’t want the delayed rendering behavior of the “lazy” version.

The following example shows a simple horizontal stack of five text views:

```swift
var body: some View {
    HStack(
        alignment: .top,
        spacing: 10
    ) {
        ForEach(
            1...5,
            id: \.self
        ) {
            Text("Item \($0)")
        }
    }
}
```





## Creating a stack

- **init(alignment:spacing:content:)**: Creates a horizontal stack with the given spacing and vertical alignment.

## Statically arranging views in one dimension

- **Building layouts with stack views**: Compose complex layouts from primitive container views.
- **VStack**: A view that arranges its subviews in a vertical line.

## Conforms To

- View

