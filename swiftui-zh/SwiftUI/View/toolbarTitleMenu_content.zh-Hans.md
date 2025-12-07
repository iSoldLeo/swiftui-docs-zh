--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarTitleMenu(content:)

抓取时间：2025-12-02T17:31:29Z

---

# toolbarTitleMenu(content:)

**实例方法**

配置工具栏的标题菜单。

## 声明

```swift
nonisolated func toolbarTitleMenu<C>(@ViewBuilder content: () -> C) -> some View where C : View

```

## 参数

- **content**：与工具栏标题菜单关联的内容。

## 说明

标题菜单表示可以对应用工具栏或导航标题所代表的内容执行的常用功能。此菜单可以通过应用的命令（例如 [saveItem](../CommandGroupPlacement/saveItem.zh-Hans.md) 或 [printItem](../CommandGroupPlacement/printItem.zh-Hans.md)）填充。

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu()
    }
```

您可以提供自定义操作来覆盖此默认行为。

```swift
ContentView()
    .toolbarTitleMenu {
        DuplicateButton()
        PrintButton()
    }
```

在 iOS 和 iPadOS 中，这将创建一个菜单，点击应用导航栏中的导航标题即可显示该菜单。

## 设置工具栏标题菜单

- **ToolbarTitleMenu**：工具栏的标题菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarTitleMenu(content:)
crawled: 2025-12-02T17:31:29Z
---

# toolbarTitleMenu(content:)

**Instance Method**

Configure the title menu of a toolbar.

## Declaration

```swift
nonisolated func toolbarTitleMenu<C>(@ViewBuilder content: () -> C) -> some View where C : View

```

## Parameters

- **content**: The content associated to the toolbar title menu.

## Discussion

A title menu represent common functionality that can be done on the content represented by your app’s toolbar or navigation title. This menu may be populated from your app’s commands like [saveItem](../CommandGroupPlacement/saveItem.zh-Hans.md) or [printItem](../CommandGroupPlacement/printItem.zh-Hans.md).

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu()
    }
```

You can provide your own set of actions to override this behavior.

```swift
ContentView()
    .toolbarTitleMenu {
        DuplicateButton()
        PrintButton()
    }
```

In iOS and iPadOS, this will construct a menu that can be presented by tapping the navigation title in the app’s navigation bar.

## Setting the toolbar title menu

- **ToolbarTitleMenu**: The title menu of a toolbar.

