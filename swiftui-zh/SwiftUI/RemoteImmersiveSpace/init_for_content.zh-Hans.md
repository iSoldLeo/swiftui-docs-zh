--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(for:content:)

抓取时间：2025-12-03T05:33:47Z
---

# init(for:content:)

**Initializer**

为指定类型的呈现数据创建远程沉浸式空间。

## 声明

```swift
nonisolated init<C>(for type: Data.Type, @CompositorContentBuilder content: @escaping (Binding<Data?>) -> C) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## 参数

- **type**：此沉浸式空间接受的呈现数据类型。

- **content**：一个合成器内容构建器，用于定义每个沉浸式空间实例的内容。闭包接收一个绑定，该绑定指向您调用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作以打开沉浸式空间时传递给该操作的值。系统会在状态恢复期间自动持久化并恢复此绑定的值。

## 讨论

此空间使用指定的内容构建器来生成内容。当您的应用使用 [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作呈现指定 `type` 的值时，会调用此初始化器。


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(for:content:)
crawled: 2025-12-03T05:33:47Z
---

# init(for:content:)

**Initializer**

Creates the remote immersive space for a specified type of presented data.

## Declaration

```swift
nonisolated init<C>(for type: Data.Type, @CompositorContentBuilder content: @escaping (Binding<Data?>) -> C) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

## Parameters

- **type**: The type of presented data this immersive space accepts.
- **content**: A compositor content builder that defines the content for each instance of the immersive space. The closure receives a binding to the value that you pass to the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action when you call that action to open an immersive space. The system automatically persists and restores the value of this binding during state restoration.

## Discussion

The space uses the specified content builder to form the content. Your app invokes this initializer when it presents a value of the specified `type` using the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action.

