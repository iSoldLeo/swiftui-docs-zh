---
来源： https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction/callAsFunction(id:)
抓取时间： 2025-12-01T10:22:40Z
---

# callAsFunction(id:)

**实例方法**

使用指定的标识符为场景呈现一个沉浸式空间。

## 声明

```swift
@discardableResult @MainActor func callAsFunction(id: String) async -> OpenImmersiveSpaceAction.Result
```

## 参数

- **id**：要呈现的沉浸式空间的标识符。

## 讨论

不要直接调用此方法。SwiftUI 会在您使用字符串标识符调用[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作时调用该方法：

```swift
await openImmersiveSpace(id: "planet")
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names]。

## 调用操作

- **callAsFunction(id:value:)**：显示应用程序为指定标识符定义的沉浸式空间，该空间处理所显示值的类型。
- **callAsFunction(value:)**：显示处理显示值类型的沉浸式空间。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction/callAsFunction(id:)
crawled: 2025-12-01T10:22:40Z
---

# callAsFunction(id:)

**Instance Method**

Presents an immersive space for the scene with the specified identifier.

## Declaration

```swift
@discardableResult @MainActor func callAsFunction(id: String) async -> OpenImmersiveSpaceAction.Result
```

## Parameters

- **id**: The identifier of the immersive space to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action with a string identifier:

```swift
await openImmersiveSpace(id: "planet")
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(id:value:)**: Presents the immersive space that your app defines for the specified identifier and that handles the type of the presented value.
- **callAsFunction(value:)**: Presents the immersive space that handles the type of the presented value.

