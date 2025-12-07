--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarTitleDisplayMode(_:)

抓取时间：2025-12-02T17:31:27Z

---

# toolbarTitleDisplayMode(_:)

**实例方法**

配置此视图的工具栏标题显示模式。

## 声明

```swift
nonisolated func toolbarTitleDisplayMode(_ mode: ToolbarTitleDisplayMode) -> some View

```

## 说明

使用此修饰符可以覆盖默认的工具栏标题显示模式。

```swift
NavigationStack {
    ContentView()
        .toolbarTitleDisplayMode(.inlineLarge)
}
```

有关不同显示模式的更多信息，请参阅 [ToolbarTitleDisplayMode](../ToolbarTitleDisplayMode.zh-Hans.md)。此修饰符在 macOS 上无效。

## 配置工具栏标题显示模式

- **ToolbarTitleDisplayMode**：定义工具栏标题行为的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarTitleDisplayMode(_:)
crawled: 2025-12-02T17:31:27Z
---

# toolbarTitleDisplayMode(_:)

**Instance Method**

Configures the toolbar title display mode for this view.

## Declaration

```swift
nonisolated func toolbarTitleDisplayMode(_ mode: ToolbarTitleDisplayMode) -> some View

```

## Discussion

Use this modifier to override the default toolbar title display mode.

```swift
NavigationStack {
    ContentView()
        .toolbarTitleDisplayMode(.inlineLarge)
}
```

See [ToolbarTitleDisplayMode](../ToolbarTitleDisplayMode.zh-Hans.md) for more information on the different kinds of display modes. This modifier has no effect on macOS.

## Configuring the toolbar title display mode

- **ToolbarTitleDisplayMode**: A type that defines the behavior of title of a toolbar.

