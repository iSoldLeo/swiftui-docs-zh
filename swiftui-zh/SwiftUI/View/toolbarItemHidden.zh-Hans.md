--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarItemHidden(_:)

抓取时间：2025-12-02T17:26:14Z

---

# toolbarItemHidden(_:)

**实例方法**

隐藏控制组工具栏项中的单个视图。

## 声明

```swift
nonisolated func toolbarItemHidden(_ hidden: Bool = true) -> some View

```

## 参数

- **hidden**：是否隐藏控制组工具栏项中的视图。

## 说明

使用此修饰符可以隐藏 `ControlGroup` 中的单个视图，而不会隐藏整个组。在 macOS 和 iOS 上，隐藏的项将在用户自定义期间显示。

以下示例在存在活动协作会话时显示组中的协作按钮。

```swift
struct ContentView {
    @State private var inCollaboration = false

    var body: some View {
        BrowserView()
            .toolbar(id: "browserToolbar") {
                ToolbarItem(id: "share") {
                    ControlGroup {
                        ShareButton()
                        CollaborationButton()
                            .toolbarItemHidden(!inCollaboration)
                    }
                }
            }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarItemHidden(_:)
crawled: 2025-12-02T17:26:14Z
---

# toolbarItemHidden(_:)

**Instance Method**

Hides an individual view within a control group toolbar item.

## Declaration

```swift
nonisolated func toolbarItemHidden(_ hidden: Bool = true) -> some View

```

## Parameters

- **hidden**: Whether the view in a control group toolbar item is hidden.

## Discussion

Use this modifier to hide individual views of a `ControlGroup` without hiding the entire group. On macOS and iOS, hidden items will be displayed during user customization.

The following example displays a collaboration button in a group when there is an active collaboration session.

```swift
struct ContentView {
    @State private var inCollaboration = false

    var body: some View {
        BrowserView()
            .toolbar(id: "browserToolbar") {
                ToolbarItem(id: "share") {
                    ControlGroup {
                        ShareButton()
                        CollaborationButton()
                            .toolbarItemHidden(!inCollaboration)
                    }
                }
            }
    }
}
```

