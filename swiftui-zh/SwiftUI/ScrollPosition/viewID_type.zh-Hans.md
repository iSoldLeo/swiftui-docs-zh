--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/viewID(type:)

抓取时间：2025-12-03T06:42:08Z

---

# viewID(type:)

**实例方法**

如果滚动视图配置为位于该位置，或者用户滚动浏览过 ID 匹配的视图，则返回当前滚动视图的 ID。

## 声明

```swift
func viewID<T>(type: T.Type) -> T? where T : Hashable, T : Sendable
```


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/viewID(type:)
crawled: 2025-12-03T06:42:08Z
---

# viewID(type:)

**Instance Method**

The id of the view positioned in the scroll view if configured to be in that position or the user has scrolled past a view with an id of matching type.

## Declaration

```swift
func viewID<T>(type: T.Type) -> T? where T : Hashable, T : Sendable
```

