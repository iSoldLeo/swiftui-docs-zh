--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/hidden

抓取时间：2025-12-03T06:43:01Z

---

# hidden

**类型属性**

隐藏滚动指示器。

## 声明

```swift
static var hidden: ScrollIndicatorVisibility { get }
```

## 讨论

默认情况下，macOS 中的滚动视图会在鼠标连接时显示滚动指示器。使用 [never](never.zh-Hans.md) 可以指定更强的偏好设置，从而覆盖此默认行为。

## 获取可见性

- **automatic**：滚动指示器的可见性取决于接受可见性配置的组件的策略。

- **never**：滚动指示器永远不可见。

- **visible**：显示滚动指示器。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/hidden
crawled: 2025-12-03T06:43:01Z
---

# hidden

**Type Property**

Hide the scroll indicators.

## Declaration

```swift
static var hidden: ScrollIndicatorVisibility { get }
```

## Discussion

By default, scroll views in macOS show indicators when a mouse is connected. Use [never](never.zh-Hans.md) to indicate a stronger preference that can override this behavior.

## Getting visibilties

- **automatic**: Scroll indicator visibility depends on the policies of the component accepting the visibility configuration.
- **never**: Scroll indicators should never be visible.
- **visible**: Show the scroll indicators.

