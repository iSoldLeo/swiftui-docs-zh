--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/modifiers(_:)

抓取时间：2025-12-01T11:33:25Z

---

# modifiers(_:)

**实例方法**

将手势与键盘修饰键结合使用。

## 声明

```swift
@MainActor @preconcurrency func modifiers(_ modifiers: EventModifiers) -> _ModifiersGesture<Self>
```

## 参数

- **modifiers**：一组标志，对应于用户需要按住的修饰键。

## 返回值

一个结合了手势和键盘修饰键的新手势。

## 说明

当用户按下与给定修饰键选项集对应的修饰键时，该手势会接收更新。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/modifiers(_:)
crawled: 2025-12-01T11:33:25Z
---

# modifiers(_:)

**Instance Method**

Combines a gesture with keyboard modifiers.

## Declaration

```swift
@MainActor @preconcurrency func modifiers(_ modifiers: EventModifiers) -> _ModifiersGesture<Self>
```

## Parameters

- **modifiers**: A set of flags that correspond to the modifier keys that the user needs to hold down.

## Return Value

A new gesture that combines a gesture with keyboard modifiers.

## Discussion

The gesture receives updates while the user presses the modifier keys that correspond to the given modifiers option set.

