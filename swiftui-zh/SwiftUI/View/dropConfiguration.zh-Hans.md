--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dropConfiguration(_:)

抓取时间：2025-12-02T17:23:43Z

---

# dropConfiguration(_:)

**实例方法**

配置 Drop 会话。

## 声明

```swift
nonisolated func dropConfiguration(_ configuration: @escaping (DropSession) -> DropConfiguration) -> some View

```

## 参数

- **configuration**：描述 Drop 会话配置的值。

## 返回值

返回一个视图，该视图根据 `configuration` 参数的返回值配置 Drop 会话。

## 说明

以下是一个接受 `Image` 类型 Drop 请求的视图示例。如果源端支持删除操作（源端会在删除操作后从其存储中删除图像），则视图会优先选择删除操作 `move`。如果源端不支持移动图像，则目标端会创建副本。

```swift
       ExampleView()
           .dropDestination(for: Image.self) { images, _ in
               process(images)
           }
           .dropConfiguration { dropSession in
               if dropSession.suggestedOperations.contains(.move) {
                   return DropConfiguration(operation: .move)
               }
               return DropConfiguration(operation: .copy)
           }
```

⟦

---
source: https://developer.apple.com/documentation/SwiftUI/View/dropConfiguration(_:)
crawled: 2025-12-02T17:23:43Z
---

# dropConfiguration(_:)

**Instance Method**

Configures a drop session.

## Declaration

```swift
nonisolated func dropConfiguration(_ configuration: @escaping (DropSession) -> DropConfiguration) -> some View

```

## Parameters

- **configuration**: A value that describes the configuration of a drop session.

## Return Value

A view that configures a drop session in a way, described by the return value of the `configuration` parameter.

## Discussion

Below is an example of a view that accepts drop of `Image` type. The view prefers drop operation `move` in a case when the source supports it (the source will remove the images from its storage after the drop operation). If the source does not support moving images, the destination will make copies.

```swift
       ExampleView()
           .dropDestination(for: Image.self) { images, _ in
               process(images)
           }
           .dropConfiguration { dropSession in
               if dropSession.suggestedOperations.contains(.move) {
                   return DropConfiguration(operation: .move)
               }
               return DropConfiguration(operation: .copy)
           }
```



