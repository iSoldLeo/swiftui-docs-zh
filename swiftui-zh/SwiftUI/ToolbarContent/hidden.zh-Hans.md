--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarContent/hidden(_:)

抓取时间：2025-12-03T06:03:20Z

---

# hidden(_:)

**实例方法**

隐藏工具栏中的某个工具栏项。

## 声明

```swift
nonisolated func hidden(_ hidden: Bool = true) -> some ToolbarContent

```

## 参数

- **hidden**：工具栏项是否隐藏。

## 说明

使用此修饰符可以根据条件显示工具栏中的某个工具栏项。

```swift
struct ContentView {
    @State private var showDownloads = false

    var body: some View {
        BrowserView()
            .toolbar {
                ToolbarItem {
                    DownloadsButton()
                }
                .hidden(!showDownloads)
            }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarContent/hidden(_:)
crawled: 2025-12-03T06:03:20Z
---

# hidden(_:)

**Instance Method**

Hides a toolbar item within its toolbar.

## Declaration

```swift
nonisolated func hidden(_ hidden: Bool = true) -> some ToolbarContent

```

## Parameters

- **hidden**: Whether the toolbar item is hidden.

## Discussion

Use this modifier to conditionally display a toolbar item in its toolbar.

```swift
struct ContentView {
    @State private var showDownloads = false

    var body: some View {
        BrowserView()
            .toolbar {
                ToolbarItem {
                    DownloadsButton()
                }
                .hidden(!showDownloads)
            }
    }
}
```

