--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(id:content:)

抓取时间：2025-12-03T05:33:48Z

---

# init(id:content:)

**Initializer**

创建与指定标识符关联的远程沉浸式空间。

## 声明

```swift
nonisolated init<C>(id: String, @CompositorContentBuilder content: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

## 参数

- **id**：唯一标识沉浸式空间的字符串。请确保应用中所有沉浸式空间的标识符唯一。

- **content**：定义空间内容的合成器内容构建器。

## 说明

空间使用指定的内容构建器来生成内容。


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(id:content:)
crawled: 2025-12-03T05:33:48Z
---

# init(id:content:)

**Initializer**

Creates the remote immersive space associated with the specified identifier.

## Declaration

```swift
nonisolated init<C>(id: String, @CompositorContentBuilder content: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

## Parameters

- **id**: A string that uniquely identifies the immersive space. Ensure that identifiers are unique among the immersive spaces in your app.
- **content**: An compositor content builder that defines the content of the space.

## Discussion

The space uses the specified content builder to form the content.

