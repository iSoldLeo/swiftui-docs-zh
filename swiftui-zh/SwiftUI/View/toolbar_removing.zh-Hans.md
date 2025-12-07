--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbar(removing:)

抓取时间：2025-12-02T16:23:35Z

---

# toolbar(removing:)

**实例方法**

移除默认工具栏项

## 声明

```swift
nonisolated func toolbar(removing defaultItemKind: ToolbarDefaultItemKind?) -> some View

```

## 参数

- **defaultItemKind**：要移除的默认项类型

## 说明

使用此修饰符可以移除其他 `View` 默认添加的工具栏项。例如，要移除由 `NavigationSplitView` 提供的侧边栏切换工具栏项：

```swift
NavigationSplitView {
    SidebarView()
        .toolbar(removing: .sidebarToggle)
} detail: {
    DetailView()
}
```

## 移除默认项

- **ToolbarDefaultItemKind**：一种由 `View` 默认添加的工具栏项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbar(removing:)
crawled: 2025-12-02T16:23:35Z
---

# toolbar(removing:)

**Instance Method**

Remove a toolbar item present by default

## Declaration

```swift
nonisolated func toolbar(removing defaultItemKind: ToolbarDefaultItemKind?) -> some View

```

## Parameters

- **defaultItemKind**: The kind of default item to remove

## Discussion

Use this modifier to remove toolbar items other `View`s add by default. For example, to remove the sidebar toggle toolbar item provided by `NavigationSplitView`:

```swift
NavigationSplitView {
    SidebarView()
        .toolbar(removing: .sidebarToggle)
} detail: {
    DetailView()
}
```

## Removing default items

- **ToolbarDefaultItemKind**: A kind of toolbar item a `View` adds by default.

