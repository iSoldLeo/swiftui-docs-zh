--- 来源：https://developer.apple.com/documentation/SwiftUI/Label
抓取时间：2025-12-02T17:27:18Z

---

# 标签

**Structure**

用户界面元素的标准标签，由图标和标题组成。

## 声明

```swift
struct Label<Title, Icon> where Title : View, Icon : View
```

## 概述

图标和标签的组合是最常见且最容易识别的用户界面组件之一。这种组合方式出现在各种类型的应用程序中，例如集合、列表、操作菜单和可展开列表等等。

最简单的标签创建方式是提供标题和图像名称，例如 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] 图标集中的图标：

```swift
Label("Lightning", systemImage: "bolt.fill")
```

您还可以通过多种方式为标签应用样式。例如，在设备旋转或窗口大小改变后，视图会发生动态变化，此时您可能希望仅显示标签的文本部分，可以使用 [titleOnly](LabelStyle/titleOnly.zh-Hans.md) 标签样式：

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleOnly)
```

此外，还有仅显示图标的标签样式：

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.iconOnly)
```

某些容器可能会应用不同的默认标签样式，例如 macOS 和 iOS 上的工具栏可能仅显示图标。要同时显示标题和图标，您可以应用 [titleAndIcon](LabelStyle/titleAndIcon.zh-Hans.md) 标签样式：

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleAndIcon)
```

您还可以通过修改现有样式来创建自定义标签样式；以下示例为默认标签样式添加了红色边框：

```swift
struct RedBorderedLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
        Label(configuration)
            .border(Color.red)
    }
}
```

要进行更高级的自定义或创建全新的标签样式，您需要采用 [LabelStyle](LabelStyle.zh-Hans.md) 协议并为新样式实现 [LabelStyleConfiguration](LabelStyleConfiguration.zh-Hans.md)。

要将通用标签样式应用于一组标签，请将该样式应用于包含这些标签的视图层次结构：

```swift
VStack {
    Label("Rain", systemImage: "cloud.rain")
    Label("Snow", systemImage: "snow")
    Label("Sun", systemImage: "sun.max")
}
.labelStyle(.iconOnly)
```

也可以使用视图以编程方式组合标签图标，而不是使用预先制作的图像。在此示例中，标签的图标部分使用填充的 [Circle](Circle.zh-Hans.md)，并叠加用户的姓名首字母：

```swift
Label {
    Text(person.fullName)
        .font(.body)
        .foregroundColor(.primary)
    Text(person.title)
        .font(.subheadline)
        .foregroundColor(.secondary)
} icon: {
    Circle()
        .fill(person.profileColor)
        .frame(width: 44, height: 44, alignment: .center)
        .overlay(Text(person.initials))
}
```

## 创建标签

- **init(_:image:)**：创建一个带有图标图像和由本地化字符串生成的标题的标签。

- **init(_:systemImage:)**：创建一个带有系统图标图像和由本地化字符串生成的标题的标签。

- **init(title:icon:)**：创建一个带有自定义标题和图标的标签。

- **init(_:)**：创建一个表示家庭活动应用程序的标签。

- **init(_:image:)**：创建一个带有图标图像和由本地化字符串生成的标题的标签。

## 显示文本

- **Text**：显示一行或多行只读文本的视图。

- **labelStyle(_:)**：设置此视图中标签的样式。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Label
crawled: 2025-12-02T17:27:18Z
---

# Label

**Structure**

A standard label for user interface items, consisting of an icon with a title.

## Declaration

```swift
struct Label<Title, Icon> where Title : View, Icon : View
```

## Overview

One of the most common and recognizable user interface components is the combination of an icon and a label. This idiom appears across many kinds of apps and shows up in collections, lists, menus of action items, and disclosable lists, just to name a few.

You create a label, in its simplest form, by providing a title and the name of an image, such as an icon from the [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] collection:

```swift
Label("Lightning", systemImage: "bolt.fill")
```

You can also apply styles to labels in several ways. In the case of dynamic changes to the view after device rotation or change to a window size you might want to show only the text portion of the label using the [titleOnly](LabelStyle/titleOnly.zh-Hans.md) label style:

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleOnly)
```

Conversely, there’s also an icon-only label style:

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.iconOnly)
```

Some containers might apply a different default label style, such as only showing icons within toolbars on macOS and iOS. To opt in to showing both the title and the icon, you can apply the [titleAndIcon](LabelStyle/titleAndIcon.zh-Hans.md) label style:

```swift
Label("Lightning", systemImage: "bolt.fill")
    .labelStyle(.titleAndIcon)
```

You can also create a customized label style by modifying an existing style; this example adds a red border to the default label style:

```swift
struct RedBorderedLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
        Label(configuration)
            .border(Color.red)
    }
}
```

For more extensive customization or to create a completely new label style, you’ll need to adopt the [LabelStyle](LabelStyle.zh-Hans.md) protocol and implement a [LabelStyleConfiguration](LabelStyleConfiguration.zh-Hans.md) for the new style.

To apply a common label style to a group of labels, apply the style to the view hierarchy that contains the labels:

```swift
VStack {
    Label("Rain", systemImage: "cloud.rain")
    Label("Snow", systemImage: "snow")
    Label("Sun", systemImage: "sun.max")
}
.labelStyle(.iconOnly)
```

It’s also possible to make labels using views to compose the label’s icon programmatically, rather than using a pre-made image. In this example, the icon portion of the label uses a filled [Circle](Circle.zh-Hans.md) overlaid with the user’s initials:

```swift
Label {
    Text(person.fullName)
        .font(.body)
        .foregroundColor(.primary)
    Text(person.title)
        .font(.subheadline)
        .foregroundColor(.secondary)
} icon: {
    Circle()
        .fill(person.profileColor)
        .frame(width: 44, height: 44, alignment: .center)
        .overlay(Text(person.initials))
}
```

## Creating a label

- **init(_:image:)**: Creates a label with an icon image and a title generated from a localized string.
- **init(_:systemImage:)**: Creates a label with a system icon image and a title generated from a localized string.
- **init(title:icon:)**: Creates a label with a custom title and icon.
- **init(_:)**: Creates a label representing a family activity application.
- **init(_:image:)**: Creates a label with an icon image and a title generated from a localized string.

## Displaying text

- **Text**: A view that displays one or more lines of read-only text.
- **labelStyle(_:)**: Sets the style for labels within this view.

## Conforms To

- View

