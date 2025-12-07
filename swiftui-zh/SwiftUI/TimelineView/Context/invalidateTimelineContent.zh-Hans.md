---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/invalidateTimelineContent()
抓取时间： 2025-12-04T09:10:09Z
---

# invalidateTimelineContent()

**实例方法**

重置时间线中系统拥有的任何预渲染视图。

## 声明

```swift
func invalidateTimelineContent()
```

## 讨论

进入 "始终显示 "时，系统可能会预先渲染帧。如果这些框架的内容必须以计划表或时间线视图当前绑定无法反映的方式进行更改（例如，由于用户更改了未来日历事件的标题），请调用此方法请求重新生成框架。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/invalidateTimelineContent()
crawled: 2025-12-04T09:10:09Z
---

# invalidateTimelineContent()

**Instance Method**

Resets any pre-rendered views the system has from the timeline.

## Declaration

```swift
func invalidateTimelineContent()
```

## Discussion

When entering Always On Display, the system might pre-render frames. If the content of these frames must change in a way that isn’t reflected by the schedule or the timeline view’s current bindings — for example, because the user changes the title of a future calendar event — call this method to request that the frames be regenerated.

