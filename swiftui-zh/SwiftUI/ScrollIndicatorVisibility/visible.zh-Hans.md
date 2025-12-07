--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/visible

抓取时间：2025-12-03T06:43:02Z

---

# visible

**类型属性**

显示滚动指示器。

## 声明

```swift
static var visible: ScrollIndicatorVisibility { get }
```

## 讨论

指示器的实际可见性取决于平台约定，例如 iOS 中的自动隐藏行为或 macOS 中的用户偏好设置。

## 获取可见性

- **automatic**：滚动指示器的可见性取决于接受可见性配置的组件的策略。

- **hidden**：隐藏滚动指示器。

- **never**：滚动指示器永远不应该可见。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/visible
crawled: 2025-12-03T06:43:02Z
---

# visible

**Type Property**

Show the scroll indicators.

## Declaration

```swift
static var visible: ScrollIndicatorVisibility { get }
```

## Discussion

The actual visibility of the indicators depends on platform conventions like auto-hiding behaviors in iOS or user preference behaviors in macOS.

## Getting visibilties

- **automatic**: Scroll indicator visibility depends on the policies of the component accepting the visibility configuration.
- **hidden**: Hide the scroll indicators.
- **never**: Scroll indicators should never be visible.

