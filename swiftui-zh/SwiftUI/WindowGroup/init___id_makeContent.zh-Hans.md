---
来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:id:makeContent:)
抓取时间：2025-12-02T21:48:55Z
---

# init(_:id:makeContent:)

**Initializer**

创建带有文本视图标题和标识符的窗口组。

### 声明

```swift
nonisolated init(_ title: Text, id: String, @ViewBuilder makeContent: @escaping () -> Content)
```

## 参数

- **title**：用于组标题的 [Text](../Text.zh-Hans.md) 视图。
- **id**：唯一标识窗口组的字符串。标识符在应用程序中的窗口组之间必须是唯一的。
- **makeContent**：为组的每个实例创建内容的闭包。

## 讨论

窗口组使用指定的内容作为模板来创建组中的每个窗口。系统会在用户界面中使用标题来区分窗口组，例如在与该组相关的命令名称中。




---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:id:makeContent:)
crawled: 2025-12-02T21:48:55Z
---

# init(_:id:makeContent:)

**Initializer**

Creates a window group with a text view title and an identifier.

## Declaration

```swift
nonisolated init(_ title: Text, id: String, @ViewBuilder makeContent: @escaping () -> Content)
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use for the group’s title.
- **id**: A string that uniquely identifies the window group. Identifiers must be unique among the window groups in your app.
- **makeContent**: A closure that creates the content for each instance of the group.

## Discussion

The window group uses the specified content as a template to create each window in the group. The system uses the title to distinguish the window group in the user interface, such as in the name of commands associated with the group.



