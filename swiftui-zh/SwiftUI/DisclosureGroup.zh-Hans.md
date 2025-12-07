---
来源： https://developer.apple.com/documentation/SwiftUI/DisclosureGroup
抓取时间： 2025-12-02T17:26:55Z
---

# DisclosureGroup

**Structure**

根据披露控件的状态显示或隐藏另一个内容视图的视图。

## 声明

```swift
struct DisclosureGroup<Label, Content> where Label : View, Content : View
```

## 概览

信息公开组视图包括一个用于标识内容的标签，以及一个用于显示和隐藏内容的控件。显示内容会使信息披露组处于 "展开 "状态，而隐藏内容则会使信息披露组处于 "折叠 "状态。

在下面的示例中，一个信息公开组包含两个切换按钮和一个嵌入式信息公开组。顶层信息公开组通过绑定属性`topLevelExpanded` 显示其展开状态。通过扩展信息披露组，用户可以使用切换按钮更新`toggleStates` 结构的状态。

```swift
struct ToggleStates {
    var oneIsOn: Bool = false
    var twoIsOn: Bool = true
}
@State private var toggleStates = ToggleStates()
@State private var topExpanded: Bool = true

var body: some View {
    DisclosureGroup("Items", isExpanded: $topExpanded) {
        Toggle("Toggle 1", isOn: $toggleStates.oneIsOn)
        Toggle("Toggle 2", isOn: $toggleStates.twoIsOn)
        DisclosureGroup("Sub-items") {
            Text("Sub-item 1")
        }
    }
}
```

## 创建信息披露组

- **init(_:content:)**：创建信息披露组，使用提供的本地化字符串键为标签创建文本视图。
- **init(content:label:)**：用给定的标签和内容视图创建信息披露组。
- **init(_:isExpanded:content:)**：使用提供的本地化字符串键为标签创建文本视图，并绑定到展开状态（展开或折叠），从而创建信息披露组。
- **init(isExpanded:content:label:)**：用给定的标签和内容视图创建一个披露组，并绑定到展开状态（展开或折叠）。

## 逐步公开信息

- **OutlineGroup**：**OutlineGroup**：一种结构，可根据需要从树状结构的底层识别数据集合中计算视图和披露组。
- **disclosureGroupStyle(_:)**：设置此视图中披露组的样式。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroup
crawled: 2025-12-02T17:26:55Z
---

# DisclosureGroup

**Structure**

A view that shows or hides another content view, based on the state of a disclosure control.

## Declaration

```swift
struct DisclosureGroup<Label, Content> where Label : View, Content : View
```

## Overview

A disclosure group view consists of a label to identify the contents, and a control to show and hide the contents. Showing the contents puts the disclosure group into the “expanded” state, and hiding them makes the disclosure group “collapsed”.

In the following example, a disclosure group contains two toggles and an embedded disclosure group. The top level disclosure group exposes its expanded state with the bound property, `topLevelExpanded`. By expanding the disclosure group, the user can use the toggles to update the state of the `toggleStates` structure.

```swift
struct ToggleStates {
    var oneIsOn: Bool = false
    var twoIsOn: Bool = true
}
@State private var toggleStates = ToggleStates()
@State private var topExpanded: Bool = true

var body: some View {
    DisclosureGroup("Items", isExpanded: $topExpanded) {
        Toggle("Toggle 1", isOn: $toggleStates.oneIsOn)
        Toggle("Toggle 2", isOn: $toggleStates.twoIsOn)
        DisclosureGroup("Sub-items") {
            Text("Sub-item 1")
        }
    }
}
```

## Creating a disclosure group

- **init(_:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label.
- **init(content:label:)**: Creates a disclosure group with the given label and content views.
- **init(_:isExpanded:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label, and a binding to the expansion state (expanded or collapsed).
- **init(isExpanded:content:label:)**: Creates a disclosure group with the given label and content views, and a binding to the expansion state (expanded or collapsed).

## Disclosing information progressively

- **OutlineGroup**: A structure that computes views and disclosure groups on demand from an underlying collection of tree-structured, identified data.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.

## Conforms To

- View

