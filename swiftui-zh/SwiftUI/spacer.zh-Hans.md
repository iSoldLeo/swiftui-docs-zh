---
来源： https://developer.apple.com/documentation/swiftui/spacer
抓取时间： 2025-12-03T07:18:38Z
---

# 垫片

**Structure**

一个灵活的空间，可沿其包含的堆栈布局的主轴展开，如果不包含在堆栈中，则沿两个轴展开。

### 声明

```swift
@frozen struct Spacer
```

## 概览

间隔符可创建一个没有内容的自适应视图，并尽可能地扩展。例如，当被放置在[HStack](HStack.zh-Hans.md)中时，间隔视图会在堆栈允许的范围内水平扩展，并在堆栈大小的限制内将同级视图移开。SwiftUI 会根据堆栈子视图内容的理想宽度总和来调整不包含间隔条的堆栈的大小。

下面的示例提供了一个简单的核对表行来说明如何使用间隔条：

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Image(systemName: "checkmark")
            Text(name)
        }
        .border(Color.blue)
    }
}
```



在图像前添加间隔后，会创建一个没有内容的自适应视图，该视图会展开，将图像和文本推到堆栈的右侧。现在，堆栈也会展开，占用父视图所允许的空间，蓝色边框表示堆栈的边界：

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Spacer()
            Image(systemName: "checkmark")
            Text(name)
        }
        .border(Color.blue)
    }
}
```



移动图像和名称之间的间隔条，会将这些元素分别推到[HStack](HStack.zh-Hans.md) 的左右两侧。由于堆栈中包含了间隔条，因此它会根据父视图允许的水平空间进行扩展；蓝色边框表示其大小：

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Image(systemName: "checkmark")
            Spacer()
            Text(name)
        }
        .border(Color.blue)
    }
}
```



在堆叠外侧添加两个间隔视图，使图像和文本保持在一起，同时堆叠扩展到父视图允许的最大水平空间：

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Spacer()
            Image(systemName: "checkmark")
            Text(name)
            Spacer()
        }
        .border(Color.blue)
    }
}
```



## 创建隔板

- **init(minLength:)**
- **minLength**：沿一个或多个膨胀轴，该间隔条可以收缩到的最小长度。

## 分隔线

- **Divider**：可用于分隔其他内容的视觉元素。

## 符合

- 比特可复制
- 可复制
- 可发送
- 可发送元类型
- 查看


---
source: https://developer.apple.com/documentation/swiftui/spacer
crawled: 2025-12-03T07:18:38Z
---

# Spacer

**Structure**

A flexible space that expands along the major axis of its containing stack layout, or on both axes if not contained in a stack.

## Declaration

```swift
@frozen struct Spacer
```

## Overview

A spacer creates an adaptive view with no content that expands as much as it can. For example, when placed within an [HStack](HStack.zh-Hans.md), a spacer expands horizontally as much as the stack allows, moving sibling views out of the way, within the limits of the stack’s size. SwiftUI sizes a stack that doesn’t contain a spacer up to the combined ideal widths of the content of the stack’s child views.

The following example provides a simple checklist row to illustrate how you can use a spacer:

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Image(systemName: "checkmark")
            Text(name)
        }
        .border(Color.blue)
    }
}
```



Adding a spacer before the image creates an adaptive view with no content that expands to push the image and text to the right side of the stack. The stack also now expands to take as much space as the parent view allows, shown by the blue border that indicates the boundary of the stack:

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Spacer()
            Image(systemName: "checkmark")
            Text(name)
        }
        .border(Color.blue)
    }
}
```



Moving the spacer between the image and the name pushes those elements to the left and right sides of the [HStack](HStack.zh-Hans.md), respectively. Because the stack contains the spacer, it expands to take as much horizontal space as the parent view allows; the blue border indicates its size:

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Image(systemName: "checkmark")
            Spacer()
            Text(name)
        }
        .border(Color.blue)
    }
}
```



Adding two spacer views on the outside of the stack leaves the image and text together, while the stack expands to take as much horizontal space as the parent view allows:

```swift
struct ChecklistRow: View {
    let name: String

    var body: some View {
        HStack {
            Spacer()
            Image(systemName: "checkmark")
            Text(name)
            Spacer()
        }
        .border(Color.blue)
    }
}
```



## Creating a spacer

- **init(minLength:)**
- **minLength**: The minimum length this spacer can be shrunk to, along the axis or axes of expansion.

## Separators

- **Divider**: A visual element that can be used to separate other content.

## Conforms To

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- View

