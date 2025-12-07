--- 来源：https://developer.apple.com/documentation/SwiftUI/View/badge(_:)

抓取时间：2025-12-02T17:39:41Z

---

# badge(_:)

**实例方法**

根据整数值生成视图的徽章。

## 声明

```swift
nonisolated func badge(_ count: Int) -> some View

```

## 参数

- **count**：要在徽章中显示的整数值。将值设置为零可隐藏徽章。

## 说明

使用徽章来传达有关视图的可选补充信息。徽章的内容应尽可能简短。徽章会出现在列表行、标签栏、工具栏项和菜单中。

以下示例展示了值 `recentItems.count` 的 [List](../List.zh-Hans.md) 在其中一行中以徽章的形式呈现：

```swift
List {
    Text("Recents")
        .badge(recentItems.count)
    Text("Favorites")
}
```

## 在列表项上显示徽章

- **badgeProminence(_:)**：指定此视图创建的徽章的显著性。

- **badgeProminence**：应用于与此环境关联的徽章的显著性。

- **BadgeProminence**：徽章的视觉显著性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/badge(_:)
crawled: 2025-12-02T17:39:41Z
---

# badge(_:)

**Instance Method**

Generates a badge for the view from an integer value.

## Declaration

```swift
nonisolated func badge(_ count: Int) -> some View

```

## Parameters

- **count**: An integer value to display in the badge. Set the value to zero to hide the badge.

## Discussion

Use a badge to convey optional, supplementary information about a view. Keep the contents of the badge as short as possible. Badges appear in list rows, tab bars, toolbar items, and menus.

The following example shows a [List](../List.zh-Hans.md) with the value of `recentItems.count` represented by a badge on one of the rows:

```swift
List {
    Text("Recents")
        .badge(recentItems.count)
    Text("Favorites")
}
```



## Displaying a badge on a list item

- **badgeProminence(_:)**: Specifies the prominence of badges created by this view.
- **badgeProminence**: The prominence to apply to badges associated with this environment.
- **BadgeProminence**: The visual prominence of a badge.

