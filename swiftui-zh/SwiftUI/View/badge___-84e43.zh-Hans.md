--- 来源：https://developer.apple.com/documentation/SwiftUI/View/badge(_:)-84e43
抓取时间：2025-11-30T20:49:56Z

---

# badge(_:)

**实例方法**

根据本地化的字符串键为视图生成徽章。

## 声明

```swift
nonisolated func badge(_ key: LocalizedStringKey?) -> some View

```

## 参数

- **key**：可选的字符串键，用于显示为徽章。将值设置为 `nil` 可隐藏徽章。

## 说明

使用徽章来传达视图的可选补充信息。徽章内容应尽可能简短。徽章会显示在列表行、标签栏、工具栏项和菜单中。

此修饰符会为您创建一个 [Text](../Text.zh-Hans.md) 视图，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。以下示例显示了一个列表，其中一行带有“默认”徽章。

```swift
NavigationView {
    List(servers) { server in
        Text(server.name)
            .badge(server.isDefault ? "Default" : nil)
    }
    .navigationTitle("Servers")
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/badge(_:)-84e43
crawled: 2025-11-30T20:49:56Z
---

# badge(_:)

**Instance Method**

Generates a badge for the view from a localized string key.

## Declaration

```swift
nonisolated func badge(_ key: LocalizedStringKey?) -> some View

```

## Parameters

- **key**: An optional string key to display as a badge. Set the value to `nil` to hide the badge.

## Discussion

Use a badge to convey optional, supplementary information about a view. Keep the contents of the badge as short as possible. Badges appear in list rows, tab bars, toolbar items, and menus.

This modifier creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). For more information about localizing strings, see [Text](../Text.zh-Hans.md). The following example shows a list with a “Default” badge on one of its rows.

```swift
NavigationView {
    List(servers) { server in
        Text(server.name)
            .badge(server.isDefault ? "Default" : nil)
    }
    .navigationTitle("Servers")
}
```



