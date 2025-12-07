---
来源：https://developer.apple.com/documentation/SwiftUI/Edge/Corner/Style/concentric(最小值:)
抓取时间： 2025-12-04T13:15:43Z
---

# concentric(minimum:)

**类型方法**

同心角样式，可选择最小角样式。当一个角与其容器同心时，它会调整当前角半径，以确保容器角半径等于当前角半径加上角之间的距离。如果当前角与容器角相距太远，除非提供最小角样式，否则半径将被解析为零。

## 声明

```swift
static func concentric(minimum: Edge.Corner.Style? = nil) -> Edge.Corner.Style
```


---
source: https://developer.apple.com/documentation/SwiftUI/Edge/Corner/Style/concentric(minimum:)
crawled: 2025-12-04T13:15:43Z
---

# concentric(minimum:)

**Type Method**

The concentric corner style with an optional minimum corner style. When a corner is concentric to its container, it will adjust the current corner radius to ensure that the container corner radius equals to current corner radius plus the distance between corners. If the current corner is too far away from the container corner, the radius will be resolved as zero unless a minimum corner style is provided.

## Declaration

```swift
static func concentric(minimum: Edge.Corner.Style? = nil) -> Edge.Corner.Style
```

