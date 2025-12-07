--- 来源：https://developer.apple.com/documentation/SwiftUI/DisclosureTableRow
抓取时间：2025-12-02T17:40:06Z

---

# DisclosureTableRow

**Structure**

一种表格行，可根据展开控件的状态显示或隐藏其他行。

## 声明

```swift
struct DisclosureTableRow<Label, Content> where Label : TableRowContent, Content : TableRowContent, Label.TableRowValue == Content.TableRowValue
```

## 概述

展开组行由一个始终可见的标签行和一些根据状态有条件显示的内容行组成。切换控件状态会在“展开”和“折叠”之间切换。

在以下示例中，展开组的标签行是 `allDevices`，并通过绑定属性 `expanded` 公开其展开状态。切换显示控件后，用户可以更新展开状态，从而显示或隐藏 `iPhone`、`iPad` 和 `Mac` 这三个内容行。

```swift
private struct DeviceStats: Identifiable {
    // ...
}
@State private var expanded: Bool = true
@State private var allDevices: DeviceStats = /* ... */
@State private var iPhone: DeviceStats = /* ... */
@State private var iPad: DeviceStats = /* ... */
@State private var Mac: DeviceStats = /* ... */

var body: some View {
    Table(of: DeviceStats.self) {
        // ...
    } rows: {
        DisclosureTableRow(allDevices, isExpanded: $expanded) {
            TableRow(iPhone)
            TableRow(iPad)
            TableRow(Mac)
        }
    }
}
```

## 创建显示表行

- **init(_:isExpanded:content:)**：创建一个包含给定值和表行的显示组，并将其绑定到展开状态（展开或折叠）。

## 添加渐进式显示

- **TableOutlineGroupContent**：由表的层次结构初始化器创建的不透明表行类型。

## 符合以下规范

- TableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureTableRow
crawled: 2025-12-02T17:40:06Z
---

# DisclosureTableRow

**Structure**

A kind of table row that shows or hides additional rows based on the state of a disclosure control.

## Declaration

```swift
struct DisclosureTableRow<Label, Content> where Label : TableRowContent, Content : TableRowContent, Label.TableRowValue == Content.TableRowValue
```

## Overview

A disclosure group row consists of a label row that is always visible, and some content rows that are conditionally visible depending on the state. Toggling the control will flip the state between “expanded” and “collapsed”.

In the following example, a disclosure group has `allDevices` as the label row, and exposes its expanded state with the bound property, `expanded`. Upon toggling the disclosure control, the user can update the expanded state which will in turn show or hide the three content rows for `iPhone`, `iPad`, and `Mac`.

```swift
private struct DeviceStats: Identifiable {
    // ...
}
@State private var expanded: Bool = true
@State private var allDevices: DeviceStats = /* ... */
@State private var iPhone: DeviceStats = /* ... */
@State private var iPad: DeviceStats = /* ... */
@State private var Mac: DeviceStats = /* ... */

var body: some View {
    Table(of: DeviceStats.self) {
        // ...
    } rows: {
        DisclosureTableRow(allDevices, isExpanded: $expanded) {
            TableRow(iPhone)
            TableRow(iPad)
            TableRow(Mac)
        }
    }
}
```

## Creating a disclosure table row

- **init(_:isExpanded:content:)**: Creates a disclosure group with the given value and table rows, and a binding to the expansion state (expanded or collapsed).

## Adding progressive disclosure

- **TableOutlineGroupContent**: An opaque table row type created by a table’s hierarchical initializers.

## Conforms To

- TableRowContent

