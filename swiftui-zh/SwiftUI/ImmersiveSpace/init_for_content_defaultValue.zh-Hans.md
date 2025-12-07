---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(for:content:defaultValue:)
抓取时间： 2025-12-02T21:47:18Z
---

# init(for:content:defaultValue:)

**Initializer**

创建一个身临其境的空间。

## 声明

```swift
init(for type: Data.Type = Data.self, @ImmersiveSpaceContentBuilder content: @escaping (Binding<Data>) -> Content, defaultValue: @escaping () -> Data)
```

## 参数

- **type**：该沉浸式空间接受的展示数据类型。
- **content**：沉浸式空间内容构建器，用于定义沉浸式空间每个实例的内容。当您调用[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 动作打开沉浸式空间时，闭包会收到与您传递给[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 动作的值的绑定。在恢复状态时，系统会自动持续并恢复此绑定的值。
- **defaultValue**：当 SwiftUI 没有从您那里接收到一个值时（例如，当您调用[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作而没有提供一个值时），返回值的闭包。

## 讨论

沉浸式空间使用指定的内容创建器作为模板来创建空间内容。当您的应用程序使用 `type` 动作显示指定的 `type` 值时，会调用该初始化器。

## 为沉浸式空间提供默认数据

- **init(id:for:content:defaultValue:)**：为指定类型的展示数据创建与标识符相关联的沉浸式空间，如果未设置数据，则创建默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(for:content:defaultValue:)
crawled: 2025-12-02T21:47:18Z
---

# init(for:content:defaultValue:)

**Initializer**

Creates an immersive space.

## Declaration

```swift
init(for type: Data.Type = Data.self, @ImmersiveSpaceContentBuilder content: @escaping (Binding<Data>) -> Content, defaultValue: @escaping () -> Data)
```

## Parameters

- **type**: The type of presented data this immersive space accepts.
- **content**: An immersive space content builder that defines the content for each instance of the immersive space. The closure receives a binding to the value that you pass to the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action when you call that action to open an immersive space. The system automatically persists and restores the value of this binding during state restoration.
- **defaultValue**: A closure that returns a value that SwiftUI presents when it doesn’t receive one from you, like when you call the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action without providing a value.

## Discussion

The immersive space uses the specified content builder as a template to form the content of the space. Your app invokes this initializer when it presents a value of the specified `type` using the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action.

## Providing default data to an immersive space

- **init(id:for:content:defaultValue:)**: Creates the immersive space associated with an identifier for a specified type of presented data, and a default value, if the data is not set.

