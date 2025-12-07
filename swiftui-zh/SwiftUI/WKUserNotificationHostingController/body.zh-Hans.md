---
来源： https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/body
抓取时间： 2025-12-03T07:01:22Z
---

# 正文

**实例属性**

通知界面要显示的视图层次结构的根视图。

## 声明

```swift
@MainActor @preconcurrency var body: Body { get }
```

## 讨论

重载此属性并从您的实现中返回 SwiftUI 视图层次结构的根视图。如果不重载此属性，访问默认实现会触发异常。


---
source: https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/body
crawled: 2025-12-03T07:01:22Z
---

# body

**Instance Property**

The root view of the view hierarchy to display for your notification interface.

## Declaration

```swift
@MainActor @preconcurrency var body: Body { get }
```

## Discussion

Override this property and return the root view of your SwiftUI view hierarchy from your implementation. If you don’t override this property, accessing the default implementation triggers an exception.

