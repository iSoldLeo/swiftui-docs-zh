--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewThatFits

抓取时间：2025-12-02T17:28:02Z

---

# ViewThatFits

**Structure**

一种能够适应可用空间的视图，它会提供第一个合适的子视图。

## 声明

```swift
@frozen struct ViewThatFits<Content> where Content : View
```

## 概述

`ViewThatFits` 会按照您提供给初始化器的顺序评估其子视图。它会选择第一个在约束轴上的理想尺寸符合建议尺寸的子视图。这意味着您需要按优先级顺序提供视图。通常，此顺序是从大到小，但由于视图可能在一个约束轴上合适，而在另一个约束轴上不合适，因此并非总是如此。默认情况下，`ViewThatFits` 会同时在水平和垂直轴上进行约束。

以下示例展示了一个使用 `ViewThatFits` 以三种方式之一显示上传进度的 `UploadProgressView`。它依次尝试显示：

- 一个包含 [Text](Text.zh-Hans.md) 视图和 [ProgressView](ProgressView.zh-Hans.md) 的 [HStack](HStack.zh-Hans.md)。

- 仅显示 `ProgressView`。

- 仅显示 `Text` 视图。

进度视图的宽度固定为 100 磅。

```swift
struct UploadProgressView: View {
    var uploadProgress: Double

    var body: some View {
        ViewThatFits(in: .horizontal) {
            HStack {
                Text("\(uploadProgress.formatted(.percent))")
                ProgressView(value: uploadProgress)
                    .frame(width: 100)
            }
            ProgressView(value: uploadProgress)
                .frame(width: 100)
            Text("\(uploadProgress.formatted(.percent))")
        }
    }
}
```

此处对 `ViewThatFits` 的使用仅评估水平轴上的尺寸。以下代码将 `UploadProgressView` 调整为几个固定宽度：

```swift
VStack {
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 200)
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 100)
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 50)
}
```

## 创建合适的视图

- **init(in:content:)**：根据视图构建器提供的几个备选方案之一，生成一个在给定坐标轴上受限的视图。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/ViewThatFits
crawled: 2025-12-02T17:28:02Z
---

# ViewThatFits

**Structure**

A view that adapts to the available space by providing the first child view that fits.

## Declaration

```swift
@frozen struct ViewThatFits<Content> where Content : View
```

## Overview

`ViewThatFits` evaluates its child views in the order you provide them to the initializer. It selects the first child whose ideal size on the constrained axes fits within the proposed size. This means that you provide views in order of preference. Usually this order is largest to smallest, but since a view might fit along one constrained axis but not the other, this isn’t always the case. By default, `ViewThatFits` constrains in both the horizontal and vertical axes.

The following example shows an `UploadProgressView` that uses `ViewThatFits` to display the upload progress in one of three ways. In order, it attempts to display:

- An [HStack](HStack.zh-Hans.md) that contains a [Text](Text.zh-Hans.md) view and a [ProgressView](ProgressView.zh-Hans.md).
- Only the `ProgressView`.
- Only the `Text` view.

The progress views are fixed to a 100-point width.

```swift
struct UploadProgressView: View {
    var uploadProgress: Double

    var body: some View {
        ViewThatFits(in: .horizontal) {
            HStack {
                Text("\(uploadProgress.formatted(.percent))")
                ProgressView(value: uploadProgress)
                    .frame(width: 100)
            }
            ProgressView(value: uploadProgress)
                .frame(width: 100)
            Text("\(uploadProgress.formatted(.percent))")
        }
    }
}
```

This use of `ViewThatFits` evaluates sizes only on the horizontal axis. The following code fits the `UploadProgressView` to several fixed widths:

```swift
VStack {
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 200)
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 100)
    UploadProgressView(uploadProgress: 0.75)
        .frame(maxWidth: 50)
}
```



## Creating a view that fits

- **init(in:content:)**: Produces a view constrained in the given axes from one of several alternatives provided by a view builder.

## Conforms To

- View

