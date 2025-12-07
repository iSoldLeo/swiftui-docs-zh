--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/sequenced(before:)

抓取时间：2025-12-03T06:44:07Z

---

# sequenced(before:)

**实例方法**

将一个手势与另一个手势组合成一个新手势，该新手势只有在第一个手势成功执行后才会接收事件。

## 声明

```swift
@MainActor @preconcurrency func sequenced<Other>(before other: Other) -> SequenceGesture<Self, Other> where Other : Gesture
```

## 参数

- **other**：要与另一个手势组合以创建新的序列手势的手势。

## 返回值

由两个手势组成的序列手势。

## 组合手势

- **simultaneously(with:)**：将一个手势与另一个手势组合以创建一个可以同时识别这两个手势的新手势。

- **exclusively(before:)**：将两个手势组合成一个新手势，但只有一个手势会成功执行，且优先执行第一个手势。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/sequenced(before:)
crawled: 2025-12-03T06:44:07Z
---

# sequenced(before:)

**Instance Method**

Sequences a gesture with another one to create a new gesture, which results in the second gesture only receiving events after the first gesture succeeds.

## Declaration

```swift
@MainActor @preconcurrency func sequenced<Other>(before other: Other) -> SequenceGesture<Self, Other> where Other : Gesture
```

## Parameters

- **other**: A gesture you want to combine with another gesture to create a new, sequenced gesture.

## Return Value

A gesture that’s a sequence of two gestures.

## Composing gestures

- **simultaneously(with:)**: Combines a gesture with another gesture to create a new gesture that recognizes both gestures at the same time.
- **exclusively(before:)**: Combines two gestures exclusively to create a new gesture where only one gesture succeeds, giving precedence to the first gesture.

