---
来源：https://developer.apple.com/documentation/SwiftUI/UtilityWindow/init(_:id:content:)
抓取时间： 2025-12-03T05:31:33Z
---

# init(_:id:content:)

**Initializer**

创建带有标题和标识符的实用程序窗口。

## 声明

```swift
init(_ title: Text, id: String, @ViewBuilder content: () -> Content)
```

## 参数

- **title**：在实用程序窗口标题栏中使用的 [Text](../Text.zh-Hans.md) 视图。提供描述实用程序窗口用途的标题。
- **id**：用于打开实用程序窗口的唯一字符串标识符。
- **content**：要在实用程序窗口中显示的视图内容。

## 讨论




---
source: https://developer.apple.com/documentation/SwiftUI/UtilityWindow/init(_:id:content:)
crawled: 2025-12-03T05:31:33Z
---

# init(_:id:content:)

**Initializer**

Creates a utility window with a title and identifier.

## Declaration

```swift
init(_ title: Text, id: String, @ViewBuilder content: () -> Content)
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use in the utility window’s title bar. Provide a title that describes the purpose of the utility window.
- **id**: An unique string identifier that you can use to open the utility window.
- **content**: The view content to display in the utility window.

## Discussion



