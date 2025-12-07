---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportedActivityFamilies
抓取时间： 2025-12-03T06:08:15Z
---

# supportedActivityFamilies

**实例属性**

表示实时活动潜在呈现族的环境值。

## 声明

```swift
var supportedActivityFamilies: Set<ActivityFamily> { get set }
```

## 讨论

要检测当前渲染的活动族大小，请使用 [doc://com.apple.documentation/documentation/SwiftUI/EnvironmentValues/activityFamily] 环境变量。`supportedActivityFamilies`环境变量可能只有在 Swift 软件包中提供实时活动视图时才有用。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportedActivityFamilies
crawled: 2025-12-03T06:08:15Z
---

# supportedActivityFamilies

**Instance Property**

An environment value that that indicates potential rendered family for a Live Activity.

## Declaration

```swift
var supportedActivityFamilies: Set<ActivityFamily> { get set }
```

## Discussion

To detect the currently rendered activity family size, use the [doc://com.apple.documentation/documentation/SwiftUI/EnvironmentValues/activityFamily] environment variable. The `supportedActivityFamilies` environment value might only be useful if your make you make your Live Activity views available in a Swift package.

