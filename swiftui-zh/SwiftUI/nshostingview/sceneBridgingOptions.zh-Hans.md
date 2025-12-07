--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingView/sceneBridgingOptions
抓取时间：2025-12-03T06:56:31Z

---

# sceneBridgingOptions

**实例属性**

用于指定此宿主视图将管理窗口的哪些方面。

## 声明

```swift
@MainActor @preconcurrency var sceneBridgingOptions: NSHostingSceneBridgingOptions { get set }
```

## 说明

`NSHostingView` 将根据指定的选项填充其关联窗口的某些方面。

例如，宿主视图可以通过包含 `.toolbars` 选项来管理其窗口的工具栏：

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                MyToolbarContent()
            }
    }
}

let view = NSHostingView(rootView: RootView())
view.sceneBridgingOptions = [.toolbars]
```

当此宿主视图设置为窗口的 `contentView` 时，此属性的默认值为 `.all`，其中包含 `.toolbars` 和 `.title` 选项。否则，默认值为 `[]`。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingView/sceneBridgingOptions
crawled: 2025-12-03T06:56:31Z
---

# sceneBridgingOptions

**Instance Property**

The options for which aspects of the window will be managed by this hosting view.

## Declaration

```swift
@MainActor @preconcurrency var sceneBridgingOptions: NSHostingSceneBridgingOptions { get set }
```

## Discussion

`NSHostingView` will populate certain aspects of its associated window, depending on which options are specified.

For example, a hosting view can manage its window’s toolbar by including the `.toolbars` option:

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                MyToolbarContent()
            }
    }
}

let view = NSHostingView(rootView: RootView())
view.sceneBridgingOptions = [.toolbars]
```

When this hosting view is set as the `contentView` for a window, the default value for this property will be `.all`, which includes the options for `.toolbars` and `.title`. Otherwise, the default value is `[]`.

