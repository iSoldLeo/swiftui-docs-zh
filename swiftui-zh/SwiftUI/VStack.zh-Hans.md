---
来源： https://developer.apple.com/documentation/SwiftUI/VStack
抓取时间： 2025-12-02T16:24:20Z
---

# VStack

**Structure**

垂直排列子视图的视图。

## 声明

```swift
@frozen struct VStack<Content> where Content : View
```

## 概览

与只在应用程序需要显示视图时才渲染视图的[LazyVStack](LazyVStack.zh-Hans.md) 不同，`VStack` 会一次性渲染所有视图，无论它们是在屏幕上还是屏幕外。如果您的子视图数量较少，或者不需要 "懒惰 "版本的延迟渲染行为，请使用常规`VStack`。

下面的示例显示了一个由 10 个文本视图组成的简单垂直堆叠：

```swift
var body: some View {
    VStack(
        alignment: .leading,
        spacing: 10
    ) {
        ForEach(
            1...10,
            id: \.self
        ) {
            Text("Item \($0)")
        }
    }
}
```





## 创建堆栈

- **init(alignment:spacing:content:)**：以给定的间距和水平对齐方式创建一个实例。

## 静态排列一维视图

- 使用堆栈视图构建布局**：从原始容器视图组成复杂布局。
- **HStack**：将子视图排列成水平线的视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/VStack
crawled: 2025-12-02T16:24:20Z
---

# VStack

**Structure**

A view that arranges its subviews in a vertical line.

## Declaration

```swift
@frozen struct VStack<Content> where Content : View
```

## Overview

Unlike [LazyVStack](LazyVStack.zh-Hans.md), which only renders the views when your app needs to display them, a `VStack` renders the views all at once, regardless of whether they are on- or offscreen. Use the regular `VStack` when you have a small number of subviews or don’t want the delayed rendering behavior of the “lazy” version.

The following example shows a simple vertical stack of 10 text views:

```swift
var body: some View {
    VStack(
        alignment: .leading,
        spacing: 10
    ) {
        ForEach(
            1...10,
            id: \.self
        ) {
            Text("Item \($0)")
        }
    }
}
```





## Creating a stack

- **init(alignment:spacing:content:)**: Creates an instance with the given spacing and horizontal alignment.

## Statically arranging views in one dimension

- **Building layouts with stack views**: Compose complex layouts from primitive container views.
- **HStack**: A view that arranges its subviews in a horizontal line.

## Conforms To

- View

