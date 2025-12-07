---
来源： https://developer.apple.com/documentation/SwiftUI/LabelStyle/titleAndIcon
抓取时间： 2025-12-03T06:10:25Z
---

# 标题和图标

**类型属性**

一种标签样式，使用系统标准布局显示标签的标题和图标。

## 声明

```swift
@MainActor @preconcurrency static var titleAndIcon: TitleAndIconLabelStyle { get }
```

## 讨论

在大多数情况下，标签默认同时显示标题和图标。不过，某些容器可能会对其内容应用不同的默认标签样式，例如在 macOS 和 iOS 上只在工具栏中显示图标。要选择同时显示标题和图标，可以应用标题和图标标签样式：

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleAndIcon)
```

要将标题和图标样式应用于一组标签，请将该样式应用于包含标签的视图层次结构：

```swift
VStack {
    Label("Rain", systemImage: "cloud.rain")
    Label("Snow", systemImage: "snow")
    Label("Sun", systemImage: "sun.max")
}
.labelStyle(.titleAndIcon)
```

标题和图标的相对布局取决于显示的上下文。但在大多数情况下，标签水平排列，图标在前。

## 获取内置标签样式

- **automatic**：根据当前上下文自动调整外观的标签样式。
- **iconOnly**：只显示标签图标的标签样式。
- **titleOnly**：仅显示标签图标的标签样式：只显示标签标题的标签样式。


---
source: https://developer.apple.com/documentation/SwiftUI/LabelStyle/titleAndIcon
crawled: 2025-12-03T06:10:25Z
---

# titleAndIcon

**Type Property**

A label style that shows both the title and icon of the label using a system-standard layout.

## Declaration

```swift
@MainActor @preconcurrency static var titleAndIcon: TitleAndIconLabelStyle { get }
```

## Discussion

In most cases, labels show both their title and icon by default. However, some containers might apply a different default label style to their content, such as only showing icons within toolbars on macOS and iOS. To opt in to showing both the title and the icon, you can apply the title and icon label style:

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleAndIcon)
```

To apply the title and icon style to a group of labels, apply the style to the view hierarchy that contains the labels:

```swift
VStack {
    Label("Rain", systemImage: "cloud.rain")
    Label("Snow", systemImage: "snow")
    Label("Sun", systemImage: "sun.max")
}
.labelStyle(.titleAndIcon)
```

The relative layout of the title and icon is dependent on the context it is displayed in. In most cases, however, the label is arranged horizontally with the icon leading.

## Getting built-in label styles

- **automatic**: A label style that resolves its appearance automatically based on the current context.
- **iconOnly**: A label style that only displays the icon of the label.
- **titleOnly**: A label style that only displays the title of the label.

