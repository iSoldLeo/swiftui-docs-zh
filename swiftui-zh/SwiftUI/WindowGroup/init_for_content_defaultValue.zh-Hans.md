---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(for:content:defaultValue:)
抓取时间： 2025-12-02T21:48:51Z
---

# init(for:content:defaultValue:)

**Initializer**

创建具有默认值的数据显示窗口组。

### 声明

```swift
nonisolated init<D, C>(for type: D.Type = D.self, @ViewBuilder content: @escaping (Binding<D>) -> C, defaultValue: @escaping () -> D) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## 参数

- **type**：该窗口组接受的数据类型。
- **content**：为窗口组的每个实例创建内容的闭包。打开窗口时，闭包将接收与传入[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作的值的绑定。作为状态恢复过程的一部分，SwiftUI 会自动持久化和恢复此绑定的值。
- **defaultValue**：返回默认值的闭包。SwiftUI 在没有数据可提供时会调用此闭包，例如当有人从文件 > 新窗口菜单项打开一个新窗口时。

## 讨论

窗口组使用给定视图作为模板，形成组中每个窗口的内容。

当您使用 [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作显示指定类型的值时，SwiftUI 将从组中创建一个窗口。

## 为窗口组提供默认数据

- **init(_:for:content:defaultValue:)**：创建带有文本视图标题和默认值的数据显示窗口组。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup/init(for:content:defaultValue:)
crawled: 2025-12-02T21:48:51Z
---

# init(for:content:defaultValue:)

**Initializer**

Creates a data-presenting window group with a default value.

## Declaration

```swift
nonisolated init<D, C>(for type: D.Type = D.self, @ViewBuilder content: @escaping (Binding<D>) -> C, defaultValue: @escaping () -> D) where Content == PresentedWindowContent<D, C>, D : Decodable, D : Encodable, D : Hashable, C : View
```

## Parameters

- **type**: The type of presented data this window group accepts.
- **content**: A closure that creates the content for each instance of the group. The closure receives a binding to the value that you pass into the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action when you open the window. SwiftUI automatically persists and restores the value of this binding as part of the state restoration process.
- **defaultValue**: A closure that returns a default value to present. SwiftUI calls this closure when it has no data to provide, like when someone opens a new window from the File > New Window menu item.

## Discussion

The window group using the given view as a template to form the content of each window in the group.

SwiftUI creates a window from the group when you present a value of the specified type using the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action.

## Providing default data to a window group

- **init(_:for:content:defaultValue:)**: Creates a data-presenting window group with a text view title and a default value.

