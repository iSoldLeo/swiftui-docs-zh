--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(content:)

抓取时间：2025-12-03T05:33:46Z

---

# init(content:)

**Initializer**

创建一个远程沉浸式空间。

## 声明

```swift
nonisolated init<C>(@CompositorContentBuilder content: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

## 参数

- **content**：一个用于定义空间内容的合成器内容构建器。

## 说明

该空间使用指定的内容构建器来生成内容。


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace/init(content:)
crawled: 2025-12-03T05:33:46Z
---

# init(content:)

**Initializer**

Creates a remote immersive space.

## Declaration

```swift
nonisolated init<C>(@CompositorContentBuilder content: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

## Parameters

- **content**: A compositor content builder that defines the content of the space.

## Discussion

The space uses the specified content builder to form the content.

