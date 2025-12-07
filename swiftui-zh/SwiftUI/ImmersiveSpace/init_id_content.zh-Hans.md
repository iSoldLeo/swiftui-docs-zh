---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:content:)
抓取时间： 2025-12-01T02:38:09Z
---

# init(id:content:)

**Initializer**

创建与指定标识符相关联的沉浸式空间。

### 声明

```swift
init(id: String, @ImmersiveSpaceContentBuilder content: () -> Content) where Data == Never
```

## 参数

- **id**：唯一标识沉浸式空间的字符串。确保您应用程序中的沉浸式空间的标识符是唯一的。
- **content**：沉浸式空间内容生成器，用于定义空间的内容。

## 讨论

空间使用指定的内容创建器来创建内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:content:)
crawled: 2025-12-01T02:38:09Z
---

# init(id:content:)

**Initializer**

Creates the immersive space associated with the specified identifier.

## Declaration

```swift
init(id: String, @ImmersiveSpaceContentBuilder content: () -> Content) where Data == Never
```

## Parameters

- **id**: A string that uniquely identifies the immersive space. Ensure that identifiers are unique among the immersive spaces in your app.
- **content**: An immersive space content builder that defines the content of the space.

## Discussion

The space uses the specified content builder to form the content.

