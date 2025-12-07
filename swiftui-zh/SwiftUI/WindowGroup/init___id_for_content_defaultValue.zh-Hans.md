---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:id:for:content:defaultValue:)
抓取时间： 2025-12-02T21:48:55Z


# init(_:id:for:content:defaultValue:)

**Initializer**

创建具有文本视图标题、标识符和默认值的数据显示窗口组。

### 声明

```swift
nonisolated init<D, C>(_ title: Text, id: String, for type: D.Type = D.self, @ViewBuilder content: @escaping (Binding<D>) -> C, defaultValue: @escaping () -> D) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## 参数

- **title**：用于组标题的 [Text](../Text.zh-Hans.md) 视图。
- **id**：唯一标识窗口组的字符串。标识符在应用程序中的窗口组之间必须是唯一的。
- **type**：窗口组接受的显示数据类型。
- **content**：为窗口组的每个实例创建内容的闭包。打开窗口时，闭包将接收与传入[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作的值的绑定。作为状态恢复过程的一部分，SwiftUI 会自动持久化和恢复此绑定的值。
- **defaultValue**：返回默认值的闭包。SwiftUI 在没有数据可提供时会调用此闭包，例如当有人从文件 > 新窗口菜单项打开一个新窗口时。

## 讨论

窗口组使用指定的内容作为模板来创建组中的每个窗口。

系统使用标题在用户界面中区分窗口组，例如在与该组相关的命令名称中。



当您使用[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作显示指定类型的值时，SwiftUI 将从该组中创建一个窗口。

## 识别具有默认数据的窗口组

- **init(id:for:content:defaultValue:)**：创建具有标识符和默认值的数据显示窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(_:id:for:content:defaultValue:)
crawled: 2025-12-02T21:48:55Z
---

# init(_:id:for:content:defaultValue:)

**Initializer**

Creates a data-presenting window group with a text view title, an identifier, and a default value.

## Declaration

```swift
nonisolated init<D, C>(_ title: Text, id: String, for type: D.Type = D.self, @ViewBuilder content: @escaping (Binding<D>) -> C, defaultValue: @escaping () -> D) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## Parameters

- **title**: The [Text](../Text.zh-Hans.md) view to use for the group’s title.
- **id**: A string that uniquely identifies the window group. Identifiers must be unique among the window groups in your app.
- **type**: The type of presented data this window group accepts.
- **content**: A closure that creates the content for each instance of the group. The closure receives a binding to the value that you pass into the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action when you open the window. SwiftUI automatically persists and restores the value of this binding as part of the state restoration process.
- **defaultValue**: A closure that returns a default value to present. SwiftUI calls this closure when it has no data to provide, like when someone opens a new window from the File > New Window menu item.

## Discussion

The window group uses the specified content as a template to create each window in the group.

The system uses the title to distinguish the window group in the user interface, such as in the name of commands associated with the group.



SwiftUI creates a window from the group when you present a value of the specified type using the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action.

## Identifying a window group that has default data

- **init(id:for:content:defaultValue:)**: Creates a data-presenting window group with an identifier and a default value.

