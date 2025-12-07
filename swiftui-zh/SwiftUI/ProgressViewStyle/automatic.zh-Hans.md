--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/automatic

抓取时间：2025-12-03T06:10:16Z

---

# automatic

**Type 属性**

当前视图上下文中的默认进度视图样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: DefaultProgressViewStyle { get }
```

## 讨论

默认样式代表基于进度视图的原始初始化参数以及进度视图在视图层级结构中的上下文而推荐的样式。

## 获取内置进度视图样式

- **circular**：使用圆形仪表指示 Activity 部分完成情况的进度视图样式。

- **linear**：使用水平条直观地指示进度的进度视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/automatic
crawled: 2025-12-03T06:10:16Z
---

# automatic

**Type Property**

The default progress view style in the current context of the view being styled.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: DefaultProgressViewStyle { get }
```

## Discussion

The default style represents the recommended style based on the original initialization parameters of the progress view, and the progress view’s context within the view hierarchy.

## Getting built-in progress view styles

- **circular**: The style of a progress view that uses a circular gauge to indicate the partial completion of an activity.
- **linear**: A progress view that visually indicates its progress using a horizontal bar.

