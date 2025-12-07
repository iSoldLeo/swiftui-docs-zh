---
来源： https://developer.apple.com/documentation/swiftui/nshostingcontroller/scenebridgingoptions
抓取时间： 2025-12-04T13:40:43Z
---

# 场景桥接选项

**实例属性**

该控制器的托管视图将管理窗口哪些方面的选项。

## 声明

```swift
@MainActor @preconcurrency var sceneBridgingOptions: NSHostingSceneBridgingOptions { get set }
```

## 讨论

根据指定的选项，`NSHostingController` 将填充相关窗口的某些方面。

例如，托管控制器可以通过加入`.toolbars` 选项来管理其窗口的工具栏：

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                MyToolbarContent()
            }
    }
}

let controller = NSHostingController(rootView: RootView())
controller.sceneBridgingOptions = [.toolbars]
```

当该托管控制器被设置为窗口的`contentViewController` 时，该属性的默认值将为`.all`，其中包括`.toolbars` 和`.title` 选项。否则，默认值为 `[]`。

## 配置控制器

- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **preferredContentSize**：计算并返回当前视图最合适的尺寸。
- **sizingOptions**：托管控制器视图如何根据 SwiftUI 内容的大小创建和更新约束的选项。
- **safeAreaRegions**：该视图控制器添加到其视图的安全区域。


---
source: https://developer.apple.com/documentation/swiftui/nshostingcontroller/scenebridgingoptions
crawled: 2025-12-04T13:40:43Z
---

# sceneBridgingOptions

**Instance Property**

The options for which aspects of the window will be managed by this controller’s hosting view.

## Declaration

```swift
@MainActor @preconcurrency var sceneBridgingOptions: NSHostingSceneBridgingOptions { get set }
```

## Discussion

`NSHostingController` will populate certain aspects of its associated window, depending on which options are specified.

For example, a hosting controller can manage its window’s toolbar by including the `.toolbars` option:

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                MyToolbarContent()
            }
    }
}

let controller = NSHostingController(rootView: RootView())
controller.sceneBridgingOptions = [.toolbars]
```

When this hosting controller is set as the `contentViewController` for a window, the default value for this property will be `.all`, which includes the options for `.toolbars` and `.title`. Otherwise, the default value is `[]`.

## Configuring the controller

- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **preferredContentSize**
- **sizingOptions**: The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.

