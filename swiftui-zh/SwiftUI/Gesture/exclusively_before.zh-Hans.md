--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/exclusively(before:)

抓取时间：2025-12-03T06:44:08Z

---

# exclusive(before:)

**实例方法**

将两个手势组合在一起，创建一个新的手势，其中只有一个手势会成功执行，优先执行第一个手势。

## 声明

```swift
nonisolated func exclusively<Other>(before other: Other) -> ExclusiveGesture<Self, Other> where Other : Gesture
```

## 参数

- **other**：用于与当前手势组合以创建一个新的组合手势的手势。

## 返回值

一个由两个手势组合而成的手势，其中只有一个手势会成功执行。SwiftUI 优先执行第一个手势。

## 组合手势

- **simultaneously(with:)**：将一个手势与另一个手势组合，创建一个新的手势，该手势可以同时识别这两个手势。

- **sequenced(before:)**：将一个手势与另一个手势依次排列，创建一个新的手势，该手势只有在第一个手势识别成功后，第二个手势才能接收到事件。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/exclusively(before:)
crawled: 2025-12-03T06:44:08Z
---

# exclusively(before:)

**Instance Method**

Combines two gestures exclusively to create a new gesture where only one gesture succeeds, giving precedence to the first gesture.

## Declaration

```swift
nonisolated func exclusively<Other>(before other: Other) -> ExclusiveGesture<Self, Other> where Other : Gesture
```

## Parameters

- **other**: A gesture you combine with your gesture, to create a new, combined gesture.

## Return Value

A gesture that’s the result of combining two gestures where only one of them can succeed. SwiftUI gives precedence to the first gesture.

## Composing gestures

- **simultaneously(with:)**: Combines a gesture with another gesture to create a new gesture that recognizes both gestures at the same time.
- **sequenced(before:)**: Sequences a gesture with another one to create a new gesture, which results in the second gesture only receiving events after the first gesture succeeds.

