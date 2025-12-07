---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isActivityUpdateReduced
抓取时间： 2025-12-03T06:08:07Z
---

# isActivityUpdateReduced

**实例属性**

布尔值，表示是否降低了实时活动更新同步率。

## 声明

```swift
var isActivityUpdateReduced: Bool { get set }
```

## 讨论

在 Apple Watch 等远程设备上呈现活动时，根据系统情况，内容更新有时可能仅限于警报更新。当实时活动可见且系统只与远程设备同步警报更新时，`isActivityUpdateReduced` 的值为`true`。

例如，如果 Apple Watch 上的实时活动超出了配对 iPhone 的范围，`isActivityUpdateReduced` 可能是 `true`。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isActivityUpdateReduced
crawled: 2025-12-03T06:08:07Z
---

# isActivityUpdateReduced

**Instance Property**

A Boolean value that indicates whether the Live Activity update synchronization rate is reduced.

## Declaration

```swift
var isActivityUpdateReduced: Bool { get set }
```

## Discussion

When rendering an activity on a remote device such as Apple Watch, content updates may sometimes be limited to only alerting updates, depending on system conditions. When a Live Activity is visible and the system synchronizes only alerting updates with a remote device, the value of `isActivityUpdateReduced` is `true`.

For example, `isActivityUpdateReduced` may be `true` for Live Activities on an Apple Watch that’s out of range of the paired iPhone.

