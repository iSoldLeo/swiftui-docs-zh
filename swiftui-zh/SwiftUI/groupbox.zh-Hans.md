--- 来源：https://developer.apple.com/documentation/swiftui/groupbox

抓取时间：2025-12-04T11:34:33Z

---

# GroupBox

**Structure**

一个带有可选标签的样式化视图，用于以视觉方式将内容进行逻辑分组。

## 声明

```swift
struct GroupBox<Label, Content> where Label : View, Content : View
```

## 概述

当您希望通过为框内内容添加可选标题来以视觉方式区分用户界面的一部分时，可以使用分组框。

以下示例设置了一个带有标签“最终用户协议”的 `GroupBox`，以及一个包含在 [Text](Text.zh-Hans.md) 视图中的长字符串 `agreementText`，该视图又被 [ScrollView](ScrollView.zh-Hans.md) 包裹。该框还包含一个 [Toggle](Toggle.zh-Hans.md)，供用户在阅读文本后进行交互。

```swift
var body: some View {
    GroupBox(label:
        Label("End-User Agreement", systemImage: "building.columns")
    ) {
        ScrollView(.vertical, showsIndicators: true) {
            Text(agreementText)
                .font(.footnote)
        }
        .frame(height: 100)
        Toggle(isOn: $userAgreed) {
            Text("I agree to the above terms")
        }
    }
}
```

## 创建分组框

- **init(content:)**：创建一个未标记的分组框，并包含提供的视图内容。

- **init(content:label:)**：创建一个分组框，并包含提供的标签和视图内容。

- **init(_:content:)**：创建一个分组框，并包含提供的视图内容和标题。

## 根据配置创建分组框

- **init(_:)**：根据样式配置创建分组框。

## 已弃用的初始化器

- **init(label:content:)**

## 将视图分组到一个框中

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/swiftui/groupbox
crawled: 2025-12-04T11:34:33Z
---

# GroupBox

**Structure**

A stylized view, with an optional label, that visually collects a logical grouping of content.

## Declaration

```swift
struct GroupBox<Label, Content> where Label : View, Content : View
```

## Overview

Use a group box when you want to visually distinguish a portion of your user interface with an optional title for the boxed content.

The following example sets up a `GroupBox` with the label “End-User Agreement”, and a long `agreementText` string in a [Text](Text.zh-Hans.md) view wrapped by a [ScrollView](ScrollView.zh-Hans.md). The box also contains a [Toggle](Toggle.zh-Hans.md) for the user to interact with after reading the text.

```swift
var body: some View {
    GroupBox(label:
        Label("End-User Agreement", systemImage: "building.columns")
    ) {
        ScrollView(.vertical, showsIndicators: true) {
            Text(agreementText)
                .font(.footnote)
        }
        .frame(height: 100)
        Toggle(isOn: $userAgreed) {
            Text("I agree to the above terms")
        }
    }
}
```



## Creating a group box

- **init(content:)**: Creates an unlabeled group box with the provided view content.
- **init(content:label:)**: Creates a group box with the provided label and view content.
- **init(_:content:)**: Creates a group box with the provided view content and title.

## Creating a group box from a configuration

- **init(_:)**: Creates a group box based on a style configuration.

## Deprecated initializers

- **init(label:content:)**

## Grouping views into a box

- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.

## Conforms To

- View

