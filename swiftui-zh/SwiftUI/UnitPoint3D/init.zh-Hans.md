---
来源： https://developer.apple.com/documentation/SwiftUI/UnitPoint3D/init()
抓取时间： 2025-12-01T11:24:45Z
---

# init()

**Initializer**

在原点创建一个 3D 单位点。

## 声明

```swift
init()
```

## 讨论

在从左到右的语言环境中，视图的原点位于左后上角，正 x 向右。在从右到左的语言环境中，视图的原点位于右上角，正 x 向左。正 y 始终朝向视图的底部，而正 z 则朝向视图的前部。

## 创建点

- **init(x:y:z:)**：以指定的偏移量创建一个 3D 单位点。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitPoint3D/init()
crawled: 2025-12-01T11:24:45Z
---

# init()

**Initializer**

Creates a 3D unit point at the origin.

## Declaration

```swift
init()
```

## Discussion

A view’s origin appears in the top-left-back corner in a left-to-right language environment, with positive x toward the right. It appears in the top-right-back corner in a right-to-left language, with positive x toward the left. Positive y is always toward the bottom of the view, and positive z points toward the front.

## Creating a point

- **init(x:y:z:)**: Creates a 3D unit point with the specified offsets.

