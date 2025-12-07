---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:makeContent:)
抓取时间： 2025-12-02T21:47:46Z
---

# init(id:makeContent:)

**Initializer**

创建与指定标识符相关的沉浸式空间。

### 声明

```swift
init(id: String, @ImmersiveSpaceContentBuilder makeContent: @escaping () -> Content) where Data == Never
```

## 参数

- **id**：唯一标识沉浸式空间的字符串。确保您应用程序中的沉浸式空间的标识符是唯一的。

##讨论

该空间使用指定的内容生成器来生成内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:makeContent:)
crawled: 2025-12-02T21:47:46Z
---

# init(id:makeContent:)

**Initializer**

Creates the immersive space associated with the specified identifier.

## Declaration

```swift
init(id: String, @ImmersiveSpaceContentBuilder makeContent: @escaping () -> Content) where Data == Never
```

## Parameters

- **id**: A string that uniquely identifies the immersive space. Ensure that identifiers are unique among the immersive spaces in your app.

## Discussion

The space uses the specified content builder to form the content.

