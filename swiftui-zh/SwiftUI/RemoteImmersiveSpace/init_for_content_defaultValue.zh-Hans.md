--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(for:content:defaultValue:)

抓取时间：2025-12-01T10:22:51Z

---

# init(for:content:defaultValue:)

**Initializer**

为指定类型的呈现数据创建远程沉浸式空间，如果未设置数据，则使用默认值。

## 声明

```swift
nonisolated init<C>(for type: Data.Type = Data.self, @CompositorContentBuilder content: @escaping (Binding<Data>) -> C, defaultValue: @escaping () -> Data) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## 参数

- **type**：此沉浸式空间接受的呈现数据类型。

- **content**：沉浸式空间内容构建器，用于定义每个沉浸式空间实例的内容。闭包接收一个绑定，该绑定指向您调用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作以打开沉浸式空间时传递给该操作的值。系统会在状态恢复期间自动持久化和恢复此绑定的值。

- **defaultValue**：一个闭包，当 SwiftUI 没有收到您的值时（例如，当您调用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作但未提供值时），它会返回一个值。

## 讨论

沉浸式空间使用指定的内容构建器作为模板来构建空间内容。当您的应用使用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作呈现指定 `type` 的值时，它会调用此初始化器。


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(for:content:defaultValue:)
crawled: 2025-12-01T10:22:51Z
---

# init(for:content:defaultValue:)

**Initializer**

Creates the remote immersive space for a specified type of presented data, and a default value, if the data is not set.

## Declaration

```swift
nonisolated init<C>(for type: Data.Type = Data.self, @CompositorContentBuilder content: @escaping (Binding<Data>) -> C, defaultValue: @escaping () -> Data) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## Parameters

- **type**: The type of presented data this immersive space accepts.
- **content**: An immersive space content builder that defines the content for each instance of the immersive space. The closure receives a binding to the value that you pass to the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action when you call that action to open an immersive space. The system automatically persists and restores the value of this binding during state restoration.
- **defaultValue**: A closure that returns a value that SwiftUI presents when it doesn’t receive one from you, like when you call the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action without providing a value.

## Discussion

The immersive space uses the specified content builder as a template to form the content of the space. Your app invokes this initializer when it presents a value of the specified `type` using the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action.

