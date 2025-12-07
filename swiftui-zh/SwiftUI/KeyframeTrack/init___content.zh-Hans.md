---
来源： https://developer.apple.com/documentation/SwiftUI/KeyframeTrack/init(_:content:)
抓取时间： 2025-12-03T06:12:45Z
---

# init(_:content:)

**Initializer**

创建一个实例，在给定的键路径上为根值属性创建动画。

### 声明

```swift
init(_ keyPath: WritableKeyPath<Root, Value>, @KeyframeTrackContentBuilder<Value> content: () -> Content)
```

## 参数

- **keyPath**：要制作动画的属性。

## 创建关键帧轨迹

- **init(content:)**：创建一个实例，对关键帧路径根部的整个值进行动画处理。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrack/init(_:content:)
crawled: 2025-12-03T06:12:45Z
---

# init(_:content:)

**Initializer**

Creates an instance that animates the property of the root value at the given key path.

## Declaration

```swift
init(_ keyPath: WritableKeyPath<Root, Value>, @KeyframeTrackContentBuilder<Value> content: () -> Content)
```

## Parameters

- **keyPath**: The property to animate.

## Creating a keyframe track

- **init(content:)**: Creates an instance that animates the entire value from the root of the key path.

