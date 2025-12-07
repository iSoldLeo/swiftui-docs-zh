---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarTitleDisplayMode
抓取时间： 2025-12-02T17:31:28Z
---

# 工具栏标题显示模式

**Structure**

定义工具栏标题行为的类型。

### 声明

```swift
struct ToolbarTitleDisplayMode
```

## 概览

使用 [toolbarTitleDisplayMode(_:)](View/toolbarTitleDisplayMode.zh-Hans.md) 修改器可配置工具栏的标题显示行为：

```swift
NavigationStack {
    ContentView()
        .toolbarTitleDisplayMode(.inlineLarge)
}
```

## 获取显示模式

- **automatic**：自动模式。
- **inline**：自动模式：内联模式。
- **inlineLarge**：内联模式：内联大号模式。
- **large**：大型模式。

## 配置工具栏标题显示模式

- **toolbarTitleDisplayMode(_:)**：配置此视图的工具栏标题显示模式。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarTitleDisplayMode
crawled: 2025-12-02T17:31:28Z
---

# ToolbarTitleDisplayMode

**Structure**

A type that defines the behavior of title of a toolbar.

## Declaration

```swift
struct ToolbarTitleDisplayMode
```

## Overview

Use the [toolbarTitleDisplayMode(_:)](View/toolbarTitleDisplayMode.zh-Hans.md) modifier to configure the title display behavior of your toolbar:

```swift
NavigationStack {
    ContentView()
        .toolbarTitleDisplayMode(.inlineLarge)
}
```

## Getting display modes

- **automatic**: The automatic mode.
- **inline**: The inline mode.
- **inlineLarge**: The inline large mode.
- **large**: The large mode.

## Configuring the toolbar title display mode

- **toolbarTitleDisplayMode(_:)**: Configures the toolbar title display mode for this view.

