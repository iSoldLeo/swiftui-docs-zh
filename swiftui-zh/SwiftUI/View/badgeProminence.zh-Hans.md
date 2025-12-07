--- 来源：https://developer.apple.com/documentation/SwiftUI/View/badgeProminence(_:)

抓取时间：2025-12-02T17:39:42Z

---

# badgeProminence(_:)

**实例方法**

指定此视图创建的徽章的突出显示程度。

## 声明

```swift
nonisolated func badgeProminence(_ prominence: BadgeProminence) -> some View

```

## 参数

- **prominence**：要应用于徽章的突出显示程度。

## 说明

徽章可用于显示各种信息，从容器中的项目数量到所需操作的数量。列表中的徽章突出显示程度可以进行调整，以反映这些信息，并使其更加引人注目或不那么引人注目。

除非另有指定，否则徽章的默认突出显示程度为 `standard`。

以下示例展示了一个 [List](../List.zh-Hans.md)，其中显示了一个文件夹列表，并带有一个低亮度的信息徽章，用于显示文件夹中的项目数量。

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## 在列表项上显示徽章

- **badge(_:)**：根据整数值生成视图的徽章。

- **badgeProminence**：应用于与此环境关联的徽章的亮度级别。

- **BadgeProminence**：徽章的视觉亮度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/badgeProminence(_:)
crawled: 2025-12-02T17:39:42Z
---

# badgeProminence(_:)

**Instance Method**

Specifies the prominence of badges created by this view.

## Declaration

```swift
nonisolated func badgeProminence(_ prominence: BadgeProminence) -> some View

```

## Parameters

- **prominence**: The prominence to apply to badges.

## Discussion

Badges can be used for different kinds of information, from the passive number of items in a container to the number of required actions. The prominence of badges in Lists can be adjusted to reflect this and be made to draw more or less attention to themselves.

Badges will default to `standard` prominence unless specified.

The following example shows a [List](../List.zh-Hans.md) displaying a list of folders with an informational badge with lower prominence, showing the number of items in the folder.

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## Displaying a badge on a list item

- **badge(_:)**: Generates a badge for the view from an integer value.
- **badgeProminence**: The prominence to apply to badges associated with this environment.
- **BadgeProminence**: The visual prominence of a badge.

