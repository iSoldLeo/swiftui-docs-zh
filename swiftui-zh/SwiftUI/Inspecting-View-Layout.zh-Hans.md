--- 来源：https://developer.apple.com/documentation/SwiftUI/Inspecting-View-Layout

抓取时间：2025-12-02T17:38:29Z

---

# 检查视图布局

**Article**

使用 Xcode 预览或添加临时边框来确定视图的位置和范围。

## 概述

要了解 SwiftUI 如何调整视图的大小和位置，请利用 Xcode 预览来检查单个视图的边界。您还可以添加临时边框来查看 SwiftUI 如何同时调整多个视图的大小和位置。

### 使用 Xcode 预览高亮显示视图

使用 Xcode 预览，您可以通过在编辑器中选择视图或子视图来快速查看特定视图元素的大小。为了说明这一点，以下示例使用 [VStack](VStack.zh-Hans.md) 将由 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] 提供的图像垂直分组到名称上方：

```swift
struct StatusRow: View {
    let name: String

    var body: some View {
        VStack {
            Image(systemName: "person.circle")
            Text(name)
        }            
    }
}

struct StatusRow_Previews: PreviewProvider {
    static var previews: some View {
        StatusRow(name: "Maria")
    }
}
```

选中 [VStack](VStack.zh-Hans.md) 后，您会在 Xcode 预览中看到视图周围出现蓝色边框：

### 使用临时边框探索复杂布局

要查看多个视图的边框，或在视图未被选中时查看边框，请使用视图修饰符 [border(_:width:)](View/border___width.zh-Hans.md) 临时添加边框。将边框颜色设置为除 [blue](ShapeStyle/blue.zh-Hans.md) 以外的颜色，以便轻松将其与 Xcode 添加的边框区分开来：

```swift
struct StatusRow: View {
    let name: String

    var body: some View {
        VStack {
            Image(systemName: "person.circle")
            Text(name)
                .border(Color.red)
        }
        .padding()
        .border(Color.gray)
    }
}
```

## 微调布局

- **布局简单视图**：通过调整视图的大小来创建视图布局。


---
source: https://developer.apple.com/documentation/SwiftUI/Inspecting-View-Layout
crawled: 2025-12-02T17:38:29Z
---

# Inspecting view layout

**Article**

Determine the position and extent of a view using Xcode previews or by adding temporary borders.

## Overview

To learn how SwiftUI sizes and positions views, take advantage of Xcode previews to inspect a single view’s boundaries. You can also add temporary borders to see how SwiftUI positions and sizes multiple views together.

### Highlight views with Xcode previews

Using Xcode previews, you can quickly see the size of a specific view element by selecting the view or child view in the editor. To illustrate this, the following example uses a [VStack](VStack.zh-Hans.md) to vertically group an image, provided by [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols], above a name:

```swift
struct StatusRow: View {
    let name: String

    var body: some View {
        VStack {
            Image(systemName: "person.circle")
            Text(name)
        }            
    }
}

struct StatusRow_Previews: PreviewProvider {
    static var previews: some View {
        StatusRow(name: "Maria")
    }
}
```

With the [VStack](VStack.zh-Hans.md) selected, you’ll see a blue border around the view in the Xcode preview:



### Use temporary borders to explore complex layouts

To see the border of more than one view, or to see a border when the view isn’t selected, temporarily add a border with the view modifier [border(_:width:)](View/border___width.zh-Hans.md). Set the border’s color to something other than [blue](ShapeStyle/blue.zh-Hans.md) to easily distinguish it from a border added by Xcode:

```swift
struct StatusRow: View {
    let name: String

    var body: some View {
        VStack {
            Image(systemName: "person.circle")
            Text(name)
                .border(Color.red)
        }
        .padding()
        .border(Color.gray)
    }
}
```



## Finetuning a layout

- **Laying out a simple view**: Create a view layout by adjusting the size of views.

