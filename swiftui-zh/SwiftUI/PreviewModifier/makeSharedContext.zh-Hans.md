---
来源： https://developer.apple.com/documentation/SwiftUI/PreviewModifier/makeSharedContext()
抓取时间： 2025-12-01T11:56:35Z
---

# makeSharedContext()

**类型方法**

创建应用于预览的共享上下文。此处返回的上下文将被缓存并传入每个应用此类型修改器的预览的`body` 方法中。

### 声明

```swift
@MainActor static func makeSharedContext() async throws -> Self.Context
```


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewModifier/makeSharedContext()
crawled: 2025-12-01T11:56:35Z
---

# makeSharedContext()

**Type Method**

Create shared context to apply to previews. The context returned here will be cached and passed into the `body` method for every preview that applies a modifier of this type.

## Declaration

```swift
@MainActor static func makeSharedContext() async throws -> Self.Context
```

