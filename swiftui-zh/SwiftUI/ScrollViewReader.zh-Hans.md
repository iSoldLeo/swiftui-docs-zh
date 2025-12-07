--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollViewReader
抓取时间：2025-12-02T17:27:47Z

---

# ScrollViewReader

**Structure**

一个通过与代理交互，滚动到已知子视图，从而提供程序化滚动的视图。

## 声明

```swift
@frozen struct ScrollViewReader<Content> where Content : View
```

## 概述

ScrollViewReader 的内容视图构建器接收一个 [ScrollViewProxy](ScrollViewProxy.zh-Hans.md) 实例；您可以使用代理的 [scrollTo(_:anchor:)](ScrollViewProxy/scrollTo___anchor.zh-Hans.md) 来执行滚动。

以下示例创建了一个包含 100 个视图的 [ScrollView](ScrollView.zh-Hans.md)，这些视图共同显示一个颜色渐变。它还包含两个按钮，分别位于顶部和底部。顶部按钮指示 [ScrollViewProxy](ScrollViewProxy.zh-Hans.md) 滚动到底部按钮，反之亦然。

```swift
@Namespace var topID
@Namespace var bottomID

var body: some View {
    ScrollViewReader { proxy in
        ScrollView {
            Button("Scroll to Bottom") {
                withAnimation {
                    proxy.scrollTo(bottomID)
                }
            }
            .id(topID)

            VStack(spacing: 0) {
                ForEach(0..<100) { i in
                    color(fraction: Double(i) / 100)
                        .frame(height: 32)
                }
            }

            Button("Top") {
                withAnimation {
                    proxy.scrollTo(topID)
                }
            }
            .id(bottomID)
        }
    }
}

func color(fraction: Double) -> Color {
    Color(red: fraction, green: 1 - fraction, blue: 0.5)
}
```

## 创建滚动视图阅读器

- **init(content:)**：创建一个实例，该实例可以对其子滚动视图执行编程滚动。

## 配置滚动视图阅读器

- **content**：创建阅读器内容的视图构建器。

## 创建滚动视图

- **ScrollView**：一个可滚动视图。

- **ScrollViewProxy**：一个代理值，支持对视图层次结构中的可滚动视图进行编程滚动。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollViewReader
crawled: 2025-12-02T17:27:47Z
---

# ScrollViewReader

**Structure**

A view that provides programmatic scrolling, by working with a proxy to scroll to known child views.

## Declaration

```swift
@frozen struct ScrollViewReader<Content> where Content : View
```

## Overview

The scroll view reader’s content view builder receives a [ScrollViewProxy](ScrollViewProxy.zh-Hans.md) instance; you use the proxy’s [scrollTo(_:anchor:)](ScrollViewProxy/scrollTo___anchor.zh-Hans.md) to perform scrolling.

The following example creates a [ScrollView](ScrollView.zh-Hans.md) containing 100 views that together display a color gradient. It also contains two buttons, one each at the top and bottom. The top button tells the [ScrollViewProxy](ScrollViewProxy.zh-Hans.md) to scroll to the bottom button, and vice versa.

```swift
@Namespace var topID
@Namespace var bottomID

var body: some View {
    ScrollViewReader { proxy in
        ScrollView {
            Button("Scroll to Bottom") {
                withAnimation {
                    proxy.scrollTo(bottomID)
                }
            }
            .id(topID)

            VStack(spacing: 0) {
                ForEach(0..<100) { i in
                    color(fraction: Double(i) / 100)
                        .frame(height: 32)
                }
            }

            Button("Top") {
                withAnimation {
                    proxy.scrollTo(topID)
                }
            }
            .id(bottomID)
        }
    }
}

func color(fraction: Double) -> Color {
    Color(red: fraction, green: 1 - fraction, blue: 0.5)
}
```





## Creating a scroll view reader

- **init(content:)**: Creates an instance that can perform programmatic scrolling of its child scroll views.

## Configuring a scroll view reader

- **content**: The view builder that creates the reader’s content.

## Creating a scroll view

- **ScrollView**: A scrollable view.
- **ScrollViewProxy**: A proxy value that supports programmatic scrolling of the scrollable views within a view hierarchy.

## Conforms To

- View

