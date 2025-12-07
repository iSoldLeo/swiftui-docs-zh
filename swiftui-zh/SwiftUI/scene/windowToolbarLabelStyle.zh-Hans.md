--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarLabelStyle(_:)

抓取时间：2025-11-30T21:06:07Z

---

# windowToolbarLabelStyle(_:)

**实例方法**

设置工具栏中项目的标签样式，并允许用户自定义。

## 声明

```swift
nonisolated func windowToolbarLabelStyle(_ toolbarLabelStyle: Binding<ToolbarLabelStyle>) -> some Scene

```

## 参数

- **toolbarLabelStyle**：要应用的标签样式。

## 说明

使用此修饰符将 [ToolbarLabelStyle](../ToolbarLabelStyle.zh-Hans.md) 绑定到 [AppStorage](../AppStorage.zh-Hans.md)。工具栏将默认使用指定的标签样式，但用户也可以进行配置。

```swift
    @main
    struct MyApp: App {
        @AppStorage("ToolbarLabelStyle")
        private var labelStyle: ToolbarLabelStyle = .iconOnly

        var body: some Scene {
            WindowGroup {
                ContentView()
                    .toolbar(id: "browserToolbar") {
                        ...
                    }
            }
            .windowToolbarLabelStyle($labelStyle)
        }
    }
```

## 设置关联工具栏的样式

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **windowToolbarLabelStyle(fixed:)**：设置工具栏中各项的标签样式。

- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarLabelStyle(_:)
crawled: 2025-11-30T21:06:07Z
---

# windowToolbarLabelStyle(_:)

**Instance Method**

Sets the label style of items in a toolbar and enables user customization.

## Declaration

```swift
nonisolated func windowToolbarLabelStyle(_ toolbarLabelStyle: Binding<ToolbarLabelStyle>) -> some Scene

```

## Parameters

- **toolbarLabelStyle**: The label style to apply.

## Discussion

Use this modifier to bind a [ToolbarLabelStyle](../ToolbarLabelStyle.zh-Hans.md) to [AppStorage](../AppStorage.zh-Hans.md). The toolbar will default to the label style specified but will also be user configurable.

```swift
    @main
    struct MyApp: App {
        @AppStorage("ToolbarLabelStyle")
        private var labelStyle: ToolbarLabelStyle = .iconOnly

        var body: some Scene {
            WindowGroup {
                ContentView()
                    .toolbar(id: "browserToolbar") {
                        ...
                    }
            }
            .windowToolbarLabelStyle($labelStyle)
        }
    }
```

## Styling the associated toolbar

- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **windowToolbarLabelStyle(fixed:)**: Sets the label style of items in a toolbar.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.

