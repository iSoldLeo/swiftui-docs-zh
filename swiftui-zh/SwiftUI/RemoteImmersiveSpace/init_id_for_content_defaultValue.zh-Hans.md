--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(id:for:content:defaultValue:)

抓取时间：2025-12-01T10:22:53Z

---

# init(id:for:content:defaultValue:)

**Initializer**

创建与指定数据类型的标识符关联的远程沉浸式空间，并在未设置数据时设置默认值。

## 声明

```swift
nonisolated init<C>(id: String, for type: Data.Type = Data.self, @CompositorContentBuilder content: @escaping (Binding<Data>) -> C, defaultValue: @escaping () -> Data) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## 参数

- **id**：唯一标识沉浸式空间的字符串。请确保应用中所有沉浸式空间的标识符唯一。

- **type**：此沉浸式空间接受的数据类型。

- **content**：一个合成器内容构建器，用于定义沉浸式空间每个实例的内容。闭包接收一个绑定，该绑定指向您调用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作打开沉浸式空间时传递给该操作的值。系统会在状态恢复期间自动持久化和恢复此绑定的值。

- **defaultValue**：一个闭包，用于返回 SwiftUI 在未收到您提供的值时呈现的值，例如当您调用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作但未提供值时。

## 讨论

该空间使用指定的内容构建器来生成内容。当您的应用使用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作呈现指定的 `type` 值时，会调用此初始化器。


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(id:for:content:defaultValue:)
crawled: 2025-12-01T10:22:53Z
---

# init(id:for:content:defaultValue:)

**Initializer**

Creates the remote immersive space associated with an identifier for a specified type of presented data, and a default value, if the data is not set.

## Declaration

```swift
nonisolated init<C>(id: String, for type: Data.Type = Data.self, @CompositorContentBuilder content: @escaping (Binding<Data>) -> C, defaultValue: @escaping () -> Data) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## Parameters

- **id**: A string that uniquely identifies the immersive space. Ensure that identifiers are unique among the immersive spaces in your app.
- **type**: The type of presented data this immersive space accepts.
- **content**: A compositor content builder that defines the content for each instance of the immersive space. The closure receives a binding to the value that you pass to the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action when you call that action to open an immersive space. The system automatically persists and restores the value of this binding during state restoration.
- **defaultValue**: A closure that returns a value that SwiftUI presents when it doesn’t receive one from you, like when you call the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action without providing a value.

## Discussion

The space uses the specified content builder to form the content. Your app invokes this initializer when it presents a value of the specified `type` using the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action.

