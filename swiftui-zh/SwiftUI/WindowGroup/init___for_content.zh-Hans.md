---
来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:for:content:)
抓取时间： 2025-12-02T21:48:50Z
---

# init(_:for:content:)

**Initializer**

创建带有文本视图标题的数据显示窗口组。

## 声明

```swift
nonisolated init<D, C>(_ title: Text, for type: D.Type, @ViewBuilder content: @escaping (Binding<D?>) -> C) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## 参数

- **title**：用于组标题的 [Text](../Text.zh-Hans.md) 视图。
- **type**：该窗口组接受的显示数据类型。
- **content**：为窗口组的每个实例创建内容的闭包。打开窗口时，闭包将接收与传入[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作的值的绑定。SwiftUI 会自动持久保存并恢复此绑定的值，作为状态恢复过程的一部分。

## 讨论

窗口组使用给定的视图作为模板来形成组中每个窗口的内容。

系统使用标题在用户界面中区分窗口组，例如在与该组相关的命令名称中。



当您使用[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作显示指定类型的值时，SwiftUI 将从该组中创建一个窗口。

## 创建数据驱动的窗口组

- **init(for:content:)**：创建数据显示窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:for:content:)
crawled: 2025-12-02T21:48:50Z
---

# init(_:for:content:)

**Initializer**

Creates a data-presenting window group with a text view title.

## Declaration

```swift
nonisolated init<D, C>(_ title: Text, for type: D.Type, @ViewBuilder content: @escaping (Binding<D?>) -> C) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use for the group’s title.
- **type**: The type of presented data this window group accepts.
- **content**: A closure that creates the content for each instance of the group. The closure receives a binding to the value that you pass into the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action when you open the window. SwiftUI automatically persists and restores the value of this binding as part of the state restoration process.

## Discussion

The window group uses the given view as a template to form the content of each window in the group.

The system uses the title to distinguish the window group in the user interface, such as in the name of commands associated with the group.



SwiftUI creates a window from the group when you present a value of the specified type using the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action.

## Creating a data-driven window group

- **init(for:content:)**: Creates a data-presenting window group.

