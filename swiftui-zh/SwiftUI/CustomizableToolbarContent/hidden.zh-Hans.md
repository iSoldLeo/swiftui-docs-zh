--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/hidden(_:)

抓取时间：2025-12-03T06:04:53Z

---

# hidden(_:)

**实例方法**

隐藏工具栏中的某个工具栏项。

## 声明

```swift
nonisolated func hidden(_ hidden: Bool = true) -> some CustomizableToolbarContent

```

## 参数

- **hidden**：工具栏项是否隐藏。

## 说明

使用此修饰符可以根据条件显示工具栏中的某个工具栏项。在 macOS 和 iOS 上，隐藏的项会在用户自定义期间显示。

以下示例会在没有下载项时隐藏下载按钮，但在自定义期间显示该按钮。

```swift
struct ContentView {
    @State private var showDownloads = false

    var body: some View {
        BrowserView()
            .toolbar(id: "browserToolbar") {
                ToolbarItem(id: "downloads") {
                    DownloadsButton()
                }
                .hidden(!showDownloads)
            }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/hidden(_:)
crawled: 2025-12-03T06:04:53Z
---

# hidden(_:)

**Instance Method**

Hides a toolbar item within its toolbar.

## Declaration

```swift
nonisolated func hidden(_ hidden: Bool = true) -> some CustomizableToolbarContent

```

## Parameters

- **hidden**: Whether the toolbar item is hidden.

## Discussion

Use this modifier to conditionally display a toolbar item in its toolbar. On macOS and iOS, hidden items will be displayed during user customization.

The following example hides a downloads button when there are no downloads, but it is displayed during customization.

```swift
struct ContentView {
    @State private var showDownloads = false

    var body: some View {
        BrowserView()
            .toolbar(id: "browserToolbar") {
                ToolbarItem(id: "downloads") {
                    DownloadsButton()
                }
                .hidden(!showDownloads)
            }
    }
}
```

