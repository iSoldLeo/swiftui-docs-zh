---
来源： https://developer.apple.com/documentation/SwiftUI/DismissImmersiveSpaceAction/callAsFunction()
抓取时间： 2025-12-03T05:33:40Z
---

# callAsFunction()

**实例方法**

解除当前打开的沉浸式空间。

## 声明

```swift
@MainActor func callAsFunction() async
```

## 讨论

不要直接调用此方法。SwiftUI 会在您调用 [dismissImmersiveSpace](../EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) 操作时调用它：

```swift
await dismissImmersiveSpace()
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names]。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissImmersiveSpaceAction/callAsFunction()
crawled: 2025-12-03T05:33:40Z
---

# callAsFunction()

**Instance Method**

Dismisses the currently opened immersive space.

## Declaration

```swift
@MainActor func callAsFunction() async
```

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [dismissImmersiveSpace](../EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) action:

```swift
await dismissImmersiveSpace()
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations/#Methods-with-Special-Names] in *The Swift Programming Language*.

