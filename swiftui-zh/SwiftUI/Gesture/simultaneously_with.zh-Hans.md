--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/simultaneously(with:)

抓取时间：2025-12-01T11:33:23Z

---

# simultaneous(with:)

**实例方法**

将一个手势与另一个手势组合，创建一个可以同时识别这两个手势的新手势。

## 声明

```swift
nonisolated func simultaneously<Other>(with other: Other) -> SimultaneousGesture<Self, Other> where Other : Gesture
```

## 参数

- **other**：要与当前手势组合以创建新的组合手势的手势。

## 返回值

一个包含两个同时出现的手势的手势。

## 组合手势

- **sequenced(before:)**：将一个手势与另一个手势排序以创建一个新手势，这样第二个手势只有在第一个手势成功后才会接收到事件。

- **exclusively(before:)**：将两个手势组合成一个新手势，但只有一个手势会成功执行，且优先执行第一个手势。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/simultaneously(with:)
crawled: 2025-12-01T11:33:23Z
---

# simultaneously(with:)

**Instance Method**

Combines a gesture with another gesture to create a new gesture that recognizes both gestures at the same time.

## Declaration

```swift
nonisolated func simultaneously<Other>(with other: Other) -> SimultaneousGesture<Self, Other> where Other : Gesture
```

## Parameters

- **other**: A gesture that you want to combine with your gesture to create a new, combined gesture.

## Return Value

A gesture with two simultaneous gestures.

## Composing gestures

- **sequenced(before:)**: Sequences a gesture with another one to create a new gesture, which results in the second gesture only receiving events after the first gesture succeeds.
- **exclusively(before:)**: Combines two gestures exclusively to create a new gesture where only one gesture succeeds, giving precedence to the first gesture.

