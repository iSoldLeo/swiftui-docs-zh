---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/objectWillChange
抓取时间： 2025-12-03T06:21:49Z
---

# objectWillChange

**实例属性**

用于通知订阅者图像更改的发布者。

## 声明

```swift
final let objectWillChange: PassthroughSubject<Void, Never>
```

## 讨论

呈现器的[doc://com.apple.documentation/documentation/Combine/ObservableObject/ObjectWillChangePublisher] 会发布`Void` 元素。订阅者应将任何事件解释为图像内容可能已更改。

## 生成图像流

- **isObservationEnabled**：当生成的图像发生变化时，是否应通知该被观测对象的观测者。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/objectWillChange
crawled: 2025-12-03T06:21:49Z
---

# objectWillChange

**Instance Property**

A publisher that informs subscribers of changes to the image.

## Declaration

```swift
final let objectWillChange: PassthroughSubject<Void, Never>
```

## Discussion

The renderer’s [doc://com.apple.documentation/documentation/Combine/ObservableObject/ObjectWillChangePublisher] publishes `Void` elements. Subscribers should interpret any event as indicating that the contents of the image may have changed.

## Producing a stream of images

- **isObservationEnabled**: If observers of this observed object should be notified when the produced image changes.

