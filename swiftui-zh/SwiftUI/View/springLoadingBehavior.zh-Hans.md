--- 来源：https://developer.apple.com/documentation/SwiftUI/View/springLoadingBehavior(_:)

抓取时间：2025-11-30T21:28:01Z

---

# springLoadingBehavior(_:)

**实例方法**

设置此视图的弹簧加载行为。

## 声明

```swift
nonisolated func springLoadingBehavior(_ behavior: SpringLoadingBehavior) -> some View

```

## 参数

- **behavior**：是否启用弹簧加载。如果未指定，则默认行为为 `.automatic.`

## 讨论

弹簧加载是指在拖放交互过程中激活视图。在 iOS 上，当用户短暂停留在包含拖动内容的视图上时，就会发生这种情况。在 macOS 上，类似的短暂停留或在压感系统中，通过拖动时“用力点击”也会发生这种情况。此功能对 tvOS 或 watchOS 无效。

此功能通常用于具有导航或展示效果的视图，允许在不暂停拖拽交互的情况下显示目标位置。例如，一个按钮可以显示一个文件夹列表，拖动的项目可以放置到该列表中。

```swift
Button {
    showFolders = true
} label: {
    Label("Show Folders", systemImage: "folder")
}
.springLoadingBehavior(.enabled)
```

与 `disabled(_:)` 不同，此修饰符会覆盖父视图设置的值，而不是与其合并。例如，以下按钮将启用弹簧加载：

```swift
HStack {
    Button {
        showFolders = true
    } label: {
        Label("Show Folders", systemImage: "folder")
    }
    .springLoadingBehavior(.enabled)

    ...
}
.springLoadingBehavior(.disabled)
```

## 配置弹簧加载

- **springLoadingBehavior**：与此环境关联的视图的弹簧加载交互行为。

- **SpringLoadingBehavior**：控制视图弹簧加载行为的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/springLoadingBehavior(_:)
crawled: 2025-11-30T21:28:01Z
---

# springLoadingBehavior(_:)

**Instance Method**

Sets the spring loading behavior this view.

## Declaration

```swift
nonisolated func springLoadingBehavior(_ behavior: SpringLoadingBehavior) -> some View

```

## Parameters

- **behavior**: Whether spring loading is enabled or not. If unspecified, the default behavior is `.automatic.`

## Discussion

Spring loading refers to a view being activated during a drag and drop interaction. On iOS this can occur when pausing briefly on top of a view with dragged content. On macOS this can occur with similar brief pauses or on pressure-sensitive systems by “force clicking” during the drag. This has no effect on tvOS or watchOS.

This is commonly used with views that have a navigation or presentation effect, allowing the destination to be revealed without pausing the drag interaction. For example, a button that reveals a list of folders that a dragged item can be dropped onto.

```swift
Button {
    showFolders = true
} label: {
    Label("Show Folders", systemImage: "folder")
}
.springLoadingBehavior(.enabled)
```

Unlike `disabled(_:)`, this modifier overrides the value set by an ancestor view rather than being unioned with it. For example, the below button would allow spring loading:

```swift
HStack {
    Button {
        showFolders = true
    } label: {
        Label("Show Folders", systemImage: "folder")
    }
    .springLoadingBehavior(.enabled)

    ...
}
.springLoadingBehavior(.disabled)
```

## Configuring spring loading

- **springLoadingBehavior**: The behavior of spring loaded interactions for the views associated with this environment.
- **SpringLoadingBehavior**: The options for controlling the spring loading behavior of views.

