--- 来源：https://developer.apple.com/documentation/SwiftUI/View/previewContext(_:)

抓取时间：2025-11-30T21:31:00Z

---

# previewContext(_:)

**实例方法**

声明预览上下文。

## 声明

```swift
nonisolated func previewContext<C>(_ value: C) -> some View where C : PreviewContext

```

## 参数

- **value**：预览上下文；默认值为 `nil`。

## 设置上下文

- **PreviewContext**：用于预览的上下文类型。

- **PreviewContextKey**：预览上下文的键类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/previewContext(_:)
crawled: 2025-11-30T21:31:00Z
---

# previewContext(_:)

**Instance Method**

Declares a context for the preview.

## Declaration

```swift
nonisolated func previewContext<C>(_ value: C) -> some View where C : PreviewContext

```

## Parameters

- **value**: The context for the preview; the default is `nil`.

## Setting a context

- **PreviewContext**: A context type for use with a preview.
- **PreviewContextKey**: A key type for a preview context.

