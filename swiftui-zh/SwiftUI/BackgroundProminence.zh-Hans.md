--- 来源：https://developer.apple.com/documentation/SwiftUI/BackgroundProminence
抓取时间：2025-12-02T17:39:41Z

---

# BackgroundProminence

**Structure**

其他视图下方背景的突出显示程度。

## 声明

```swift
struct BackgroundProminence
```

## 概述

背景突出显示程度应影响前景样式，以保持与背景的足够对比度。例如，`List` 和 `Table` 中选定的行在获得焦点时可以具有更高的突出显示度和强调色填充；背景上方的前景内容应进行调整以反映该突出显示程度。

此属性可用于具有 `EnvironmentValues.backgroundProminence` 属性的视图的读写操作。

## 设置背景突出显示

- **standard**：背景的标准突出显示级别

- **increased**：更突出显示的背景，可能需要对其上方的视图进行一些更改。

## 配置背景

- **listRowBackground(_:)**：在列表行项后放置自定义背景视图。

- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替行背景。

- **AlternatingRowBackgroundBehavior**：视图相对于交替行背景的样式。

- **backgroundProminence**：与此环境关联的视图下方背景的突出显示级别。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundProminence
crawled: 2025-12-02T17:39:41Z
---

# BackgroundProminence

**Structure**

The prominence of backgrounds underneath other views.

## Declaration

```swift
struct BackgroundProminence
```

## Overview

Background prominence should influence foreground styling to maintain sufficient contrast against the background. For example, selected rows in a `List` and `Table` can have increased prominence backgrounds with accent color fills when focused; the foreground content above the background should be adjusted to reflect that level of prominence.

This can be read and written for views with the `EnvironmentValues.backgroundProminence` property.

## Getting background prominence

- **standard**: The standard prominence of a background
- **increased**: A more prominent background that likely requires some changes to the views above it.

## Configuring backgrounds

- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **AlternatingRowBackgroundBehavior**: The styling of views with respect to alternating row backgrounds.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

