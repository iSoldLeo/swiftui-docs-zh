--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarLabelStyle(fixed:)

抓取时间：2025-12-02T17:21:03Z

---

# windowToolbarLabelStyle(fixed:)

**实例方法**

设置工具栏中项目的标签样式。

## 声明

```swift
nonisolated func windowToolbarLabelStyle(fixed: ToolbarLabelStyle) -> some Scene

```

## 说明

使用此修饰符设置工具栏应使用的静态样式。[ToolbarLabelStyle](../ToolbarLabelStyle.zh-Hans.md) 用户无法配置此样式。

```swift
    @main
    struct MyApp: App {
        var body: some Scene {
            WindowGroup {
                ContentView()
                    .toolbar(id: "browserToolbar") {
                        ...
                    }
            }
            .windowToolbarLabelStyle(fixed: .iconOnly)
        }
    }
```

## 设置关联工具栏的样式

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **windowToolbarLabelStyle(_:)**：设置工具栏中项目的标签样式，并允许用户自定义。

- **WindowToolbarStyle**：窗口工具栏外观和行为的规范。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarLabelStyle(fixed:)
crawled: 2025-12-02T17:21:03Z
---

# windowToolbarLabelStyle(fixed:)

**Instance Method**

Sets the label style of items in a toolbar.

## Declaration

```swift
nonisolated func windowToolbarLabelStyle(fixed: ToolbarLabelStyle) -> some Scene

```

## Discussion

Use this modifier to set a static [ToolbarLabelStyle](../ToolbarLabelStyle.zh-Hans.md) the toolbar should use. The style will not be configurable by the user.

```swift
    @main
    struct MyApp: App {
        var body: some Scene {
            WindowGroup {
                ContentView()
                    .toolbar(id: "browserToolbar") {
                        ...
                    }
            }
            .windowToolbarLabelStyle(fixed: .iconOnly)
        }
    }
```

## Styling the associated toolbar

- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **windowToolbarLabelStyle(_:)**: Sets the label style of items in a toolbar and enables user customization.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.

