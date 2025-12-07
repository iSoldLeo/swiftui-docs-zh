--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowLayoutRoot/sizeThatFits(_:)

抓取时间：2025-12-03T05:32:13Z

---

# sizeThatFits(_:)

**实例方法**

询问窗口内容的大小。

## 声明

```swift
func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## 参数

- **proposal**：子视图建议的大小。在 SwiftUI 中，视图会自行选择大小，但可以参考其父视图建议的大小。

## 返回值

内容根据其容器视图建议的大小而选择的实际大小。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowLayoutRoot/sizeThatFits(_:)
crawled: 2025-12-03T05:32:13Z
---

# sizeThatFits(_:)

**Instance Method**

Asks the window’s content for its size.

## Declaration

```swift
func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## Parameters

- **proposal**: A proposed size for the subview. In SwiftUI, views choose their own size, but can take a size proposal from their parent view into account when doing so.

## Return Value

The size that the content chooses for itself, given the proposal from its container view.

