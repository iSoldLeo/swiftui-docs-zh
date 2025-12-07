--- 来源：https://developer.apple.com/documentation/SwiftUI/Window/init(_:id:content:)

抓取时间：2025-12-03T05:31:32Z

---

# init(_:id:content:)

**Initializer**

创建一个带有标题和标识符的窗口。

## 声明

```swift
init(_ title: Text, id: String, @ViewBuilder content: () -> Content)
```

## 参数

- **title**：用于系统菜单和窗口标题栏中窗口标题的视图。提供一个描述窗口用途的标题。

- **id**：一个可用于打开窗口的唯一字符串标识符。

- **content**：要在窗口中显示的视图内容。

## 讨论

窗口显示您指定的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Window/init(_:id:content:)
crawled: 2025-12-03T05:31:32Z
---

# init(_:id:content:)

**Initializer**

Creates a window with a title and an identifier.

## Declaration

```swift
init(_ title: Text, id: String, @ViewBuilder content: () -> Content)
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use for the window’s title in system menus and in the window’s title bar. Provide a title that describes the purpose of the window.
- **id**: A unique string identifier that you can use to open the window.
- **content**: The view content to display in the window.

## Discussion

The window displays the view that you specify.



