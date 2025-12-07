---
来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:for:content:)
抓取时间： 2025-12-02T21:48:53Z
---

# init(id:for:content:)

**Initializer**

创建带有标识符的数据显示窗口组。

### 声明

```swift
nonisolated init<D, C>(id: String, for type: D.Type, @ViewBuilder content: @escaping (Binding<D?>) -> C) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## 参数

- **id**：唯一标识窗口组的字符串。在应用程序的窗口组中，标识符必须是唯一的。
- **type**：窗口组接受的显示数据类型。
- **content**：为窗口组的每个实例创建内容的闭包。打开窗口时，闭包将接收与传入[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作的值的绑定。SwiftUI 会自动持久保存并恢复此绑定的值，作为状态恢复过程的一部分。

## 讨论

窗口组使用指定的内容作为模板来创建组中的每个窗口。

当您使用[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作显示指定类型的值时，SwiftUI 会从组中创建一个窗口。

## 识别数据驱动的窗口组

- **init(_:id:for:content:)**：创建带有文本视图标题和标识符的数据显示窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(id:for:content:)
crawled: 2025-12-02T21:48:53Z
---

# init(id:for:content:)

**Initializer**

Creates a data-presenting window group with an identifier.

## Declaration

```swift
nonisolated init<D, C>(id: String, for type: D.Type, @ViewBuilder content: @escaping (Binding<D?>) -> C) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## Parameters

- **id**: A string that uniquely identifies the window group. Identifiers must be unique among the window groups in your app.
- **type**: The type of presented data this window group accepts.
- **content**: A closure that creates the content for each instance of the group. The closure receives a binding to the value that you pass into the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action when you open the window. SwiftUI automatically persists and restores the value of this binding as part of the state restoration process.

## Discussion

The window group uses the specified content as a template to create each window in the group.

SwiftUI creates a window from the group when you present a value of the specified type using the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action.

## Identifying a data-driven window group

- **init(_:id:for:content:)**: Creates a data-presenting window group with a text view title and an identifier.

