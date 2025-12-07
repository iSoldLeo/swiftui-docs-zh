---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:content:)
抓取时间： 2025-12-01T02:38:10Z
---

# init(id:for:content:)

**Initializer**

为指定类型的展示数据创建与标识符相关的沉浸式空间。

### 声明

```swift
init(id: String, for type: Data.Type, @ImmersiveSpaceContentBuilder content: @escaping (Binding<Data?>) -> Content)
```

## 参数

- **id**：唯一标识沉浸式空间的字符串。确保您应用程序中的沉浸式空间的标识符是唯一的。
- **type**：该沉浸式空间接受的展示数据类型。
- **content**：沉浸式空间内容构建器，用于定义沉浸式空间每个实例的内容。当您调用[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 动作打开沉浸式空间时，闭包会收到与您传递给[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 动作的值的绑定。在恢复状态时，系统会自动持续并恢复该绑定的值。

## 讨论

空间使用指定的内容生成器来生成内容。您的应用程序在使用 `type` 操作显示指定的 `type` 值时，会调用此初始化器。

## 创建数据驱动的沉浸式空间

- **init(for:content:)**：为指定类型的呈现数据创建沉浸式空间。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:content:)
crawled: 2025-12-01T02:38:10Z
---

# init(id:for:content:)

**Initializer**

Creates the immersive space associated with an identifier for a specified type of presented data.

## Declaration

```swift
init(id: String, for type: Data.Type, @ImmersiveSpaceContentBuilder content: @escaping (Binding<Data?>) -> Content)
```

## Parameters

- **id**: A string that uniquely identifies the immersive space. Ensure that identifiers are unique among the immersive spaces in your app.
- **type**: The type of presented data this immersive space accepts.
- **content**: An immersive space content builder that defines the content for each instance of the immersive space. The closure receives a binding to the value that you pass to the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action when you call that action to open an immersive space. The system automatically persists and restores the value of this binding during state restoration.

## Discussion

The space uses the specified content builder to form the content. Your app invokes this initializer when it presents a value of the specified `type` using the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action.

## Creating a data-driven immersive space

- **init(for:content:)**: Creates the immersive space for a specified type of presented data.

