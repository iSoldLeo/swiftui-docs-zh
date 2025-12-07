---
来源： https://developer.apple.com/documentation/SwiftUI/BadgeProminence
抓取时间： 2025-12-02T17:39:43Z
---

# 徽章荣誉

**Structure**

徽章的视觉突出度。

## 声明

```swift
struct BadgeProminence
```

## 概览

徽章可用于显示不同类型的信息，从容器中物品的被动数量到所需操作的数量。可以调整徽章在列表中的突出位置以反映这一点，或多或少地引起人们的注意。

除非指定，否则徽章默认为`standard`突出显示。

下面的示例显示[List](List.zh-Hans.md) 显示文件夹列表，信息徽章的突出度较低，显示文件夹中的项目数。

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## 获取背景突出显示

- **standard**：徽章突出显示的标准级别。
- **increased**：徽章的最高显著性级别。
- **decreased**：徽章的最低突出级别。

## 在列表项目中显示徽章

- **badge(_:)**：根据整数值为视图生成徽章。
- **badgeProminence(_:)**：指定此视图创建的徽章的显著性。
- **badgeProminence**：适用于与此环境相关联的徽章的突出显示。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/BadgeProminence
crawled: 2025-12-02T17:39:43Z
---

# BadgeProminence

**Structure**

The visual prominence of a badge.

## Declaration

```swift
struct BadgeProminence
```

## Overview

Badges can be used for different kinds of information, from the passive number of items in a container to the number of required actions. The prominence of badges in Lists can be adjusted to reflect this and be made to draw more or less attention to themselves.

Badges will default to `standard` prominence unless specified.

The following example shows a [List](List.zh-Hans.md) displaying a list of folders with an informational badge with lower prominence, showing the number of items in the folder.

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## Getting background prominence

- **standard**: The standard level of prominence for a badge.
- **increased**: The highest level of prominence for a badge.
- **decreased**: The lowest level of prominence for a badge.

## Displaying a badge on a list item

- **badge(_:)**: Generates a badge for the view from an integer value.
- **badgeProminence(_:)**: Specifies the prominence of badges created by this view.
- **badgeProminence**: The prominence to apply to badges associated with this environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

