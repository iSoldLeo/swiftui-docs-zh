--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarRole
抓取时间：2025-12-02T17:31:22Z

---

# ToolbarRole

**Structure**

工具栏内容的用途。

## 声明

```swift
struct ToolbarRole
```

## 概述

工具栏角色描述了工具栏内容的用途。内容的用途会影响工具栏呈现内容的方式。例如，[browser](ToolbarRole/browser.zh-Hans.md) 会在 iPadOS 中自动将工具栏标题前导对齐。

将此类型提供给 [toolbarRole(_:)](View/toolbarRole.zh-Hans.md) 修饰符：

```swift
ContentView()
    .navigationTitle("Browser")
    .toolbarRole(.browser)
    .toolbar {
        ToolbarItem(placement: .primaryAction) {
            AddButton()
        }
     }
```

## 行为特定角色

- **browser**：浏览器角色。

- **editor**：编辑器角色。

- **navigationStack**：导航堆栈角色。

## 自动角色

- **automatic**：自动角色。

## 指定工具栏内容的角色

- **toolbarRole(_:)**：配置填充工具栏的内容的语义角色。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarRole
crawled: 2025-12-02T17:31:22Z
---

# ToolbarRole

**Structure**

The purpose of content that populates the toolbar.

## Declaration

```swift
struct ToolbarRole
```

## Overview

A toolbar role provides a description of the purpose of content that populates the toolbar. The purpose of the content influences how a toolbar renders its content. For example, a [browser](ToolbarRole/browser.zh-Hans.md) will automatically leading align the title of a toolbar in iPadOS.

Provide this type to the [toolbarRole(_:)](View/toolbarRole.zh-Hans.md) modifier:

```swift
ContentView()
    .navigationTitle("Browser")
    .toolbarRole(.browser)
    .toolbar {
        ToolbarItem(placement: .primaryAction) {
            AddButton()
        }
     }
```

## Behavior-specific roles

- **browser**: The browser role.
- **editor**: The editor role.
- **navigationStack**: The navigationStack role.

## Automatic roles

- **automatic**: The automatic role.

## Specifying the role of toolbar content

- **toolbarRole(_:)**: Configures the semantic role for the content populating the toolbar.

## Conforms To

- Sendable
- SendableMetatype

