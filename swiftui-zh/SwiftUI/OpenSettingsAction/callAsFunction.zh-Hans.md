--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenSettingsAction/callAsFunction()

抓取时间：2025-12-03T05:31:18Z

---

# callAsFunction()

**实例方法**

打开与此应用定义的场景 [Settings](../Settings.zh-Hans.md) 关联的窗口（如果存在）。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction()
```

## 说明

如果窗口已打开，调用此操作会将其置于最前。

请勿直接调用此方法。当您调用 [openSettings](../EnvironmentValues/openSettings.zh-Hans.md) 操作时，SwiftUI 会调用它：

```swift
openSettings()
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenSettingsAction/callAsFunction()
crawled: 2025-12-03T05:31:18Z
---

# callAsFunction()

**Instance Method**

Opens the window associated to the [Settings](../Settings.zh-Hans.md) scene defined by this app, if one exists.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction()
```

## Discussion

Calling this action when the window is already open will order it to the front.

Don’t call this method directly. SwiftUI calls it when you call the [openSettings](../EnvironmentValues/openSettings.zh-Hans.md) action:

```swift
openSettings()
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

