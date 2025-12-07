---
来源：https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction/callAsFunction(value:)
抓取时间： 2025-12-03T05:33:38Z
---

# callAsFunction(value:)

**实例方法**

呈现处理所呈现值类型的沉浸式空间。

## 声明

```swift
@discardableResult @MainActor func callAsFunction<D>(value: D) async -> OpenImmersiveSpaceAction.Result where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **value**：要显示的值。

## 讨论

不要直接调用此方法。SwiftUI 会在您调用带有值的[openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) 操作时调用该方法：

```swift
await openImmersiveSpace(value: planet.ID)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names]。

## 调用操作

- **callAsFunction(id:)**：为具有指定标识符的场景呈现沉浸式空间。
- **callAsFunction(id:value:)**：显示您的应用程序为指定标识符定义的沉浸式空间，并处理所显示值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction/callAsFunction(value:)
crawled: 2025-12-03T05:33:38Z
---

# callAsFunction(value:)

**Instance Method**

Presents the immersive space that handles the type of the presented value.

## Declaration

```swift
@discardableResult @MainActor func callAsFunction<D>(value: D) async -> OpenImmersiveSpaceAction.Result where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **value**: The value to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [openImmersiveSpace](../EnvironmentValues/openImmersiveSpace.zh-Hans.md) action with a value:

```swift
await openImmersiveSpace(value: planet.ID)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(id:)**: Presents an immersive space for the scene with the specified identifier.
- **callAsFunction(id:value:)**: Presents the immersive space that your app defines for the specified identifier and that handles the type of the presented value.

