---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityLargeContentViewerEnabled
抓取时间： 2025-12-02T17:43:40Z
---

# 无障碍大型内容浏览器已启用

**实例属性**

大型内容查看器是否已启用。

## 声明

```swift
var accessibilityLargeContentViewerEnabled: Bool { get }
```

## 讨论

系统可以通过 [accessibilityShowsLargeContentViewer()](../View/accessibilityShowsLargeContentViewer.zh-Hans.md) 自动提供大型内容视图，您也可以通过 [accessibilityShowsLargeContentViewer(_:)](../View/accessibilityShowsLargeContentViewer.zh-Hans.md) 提供自己的视图。

虽然在添加大型内容视图之前没有必要检查该值，但如果需要调整手势的行为，该值可能会有所帮助。例如，带有长按处理程序的按钮可能会增加其长按持续时间，以便用户可以先阅读大内容查看器中的文本。

## 放大内容

- **accessibilityShowsLargeContentViewer()**：添加默认大内容视图，由大内容查看器显示。
- **accessibilityShowsLargeContentViewer(_:)**：添加自定义大型内容查看器显示的大型内容视图。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityLargeContentViewerEnabled
crawled: 2025-12-02T17:43:40Z
---

# accessibilityLargeContentViewerEnabled

**Instance Property**

Whether the Large Content Viewer is enabled.

## Declaration

```swift
var accessibilityLargeContentViewerEnabled: Bool { get }
```

## Discussion

The system can automatically provide a large content view with [accessibilityShowsLargeContentViewer()](../View/accessibilityShowsLargeContentViewer.zh-Hans.md) or you can provide your own with [accessibilityShowsLargeContentViewer(_:)](../View/accessibilityShowsLargeContentViewer.zh-Hans.md).

While it is not necessary to check this value before adding a large content view, it may be helpful if you need to adjust the behavior of a gesture. For example, a button with a long press handler might increase its long press duration so the user can read the text in the large content viewer first.

## Enlarging content

- **accessibilityShowsLargeContentViewer()**: Adds a default large content view to be shown by the large content viewer.
- **accessibilityShowsLargeContentViewer(_:)**: Adds a custom large content view to be shown by the large content viewer.

