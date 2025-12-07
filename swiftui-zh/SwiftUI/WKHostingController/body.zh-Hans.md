--- 来源：https://developer.apple.com/documentation/SwiftUI/WKHostingController/body
抓取时间：2025-12-03T07:01:19Z

---

# body

**实例属性**

用于界面控制器的视图层级结构的根视图。

## 声明

```swift
@MainActor @preconcurrency var body: Body { get }
```

## 讨论

重写此属性，并从您的实现中返回 SwiftUI 视图层级结构的根视图。如果您不重写此属性，访问默认实现将触发异常。


---
source: https://developer.apple.com/documentation/SwiftUI/WKHostingController/body
crawled: 2025-12-03T07:01:19Z
---

# body

**Instance Property**

The root view of the view hierarchy to display for your interface controller.

## Declaration

```swift
@MainActor @preconcurrency var body: Body { get }
```

## Discussion

Override this property and return the root view of your SwiftUI view hierarchy from your implementation. If you don’t override this property, accessing the default implementation triggers an exception.

