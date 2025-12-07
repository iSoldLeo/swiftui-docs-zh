---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/labelsVisibility
抓取时间： 2025-12-02T17:32:37Z
---

# 标签可见性

**实例属性**

由 [labelsVisibility(_:)](../View/labelsVisibility.zh-Hans.md) 设置的标签可见性。

## 声明

```swift
var labelsVisibility: Visibility { get set }
```

## 讨论

从视图中读取此环境值，可获得层级中标签的首选可见性。如果您想动态隐藏自定义视图的标签，请确保通过[accessibilityLabel(content:)](../View/accessibilityLabel_content.zh-Hans.md)修饰符包含一个可访问性标签，如下图所示：

```swift
@Environment(\.labelsVisibility)
private var labelsVisibility

var body: some View {
    VStack {
        QuizCardView()
        if labelsVisibility != .hidden {
            label
        }
    }
    .accessibilityLabel {
        label
    }
}

private var label: some View {
    Text("Quiz Card")
}
```

## 隐藏系统元素

- **labelsHidden()**：隐藏此视图中包含的任何控件的标签。
- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。
- **menuIndicator(_:)**：设置该视图中控件的菜单指示符可见性。
- **statusBarHidden(_:)**：设置状态栏的可见性。
- **persistentSystemOverlays(_:)**：设置状态栏的可见性：设置覆盖应用程序的非临时系统视图的首选可见性。
- **Visibility**：用户界面元素的可见性，根据平台、当前上下文和其他因素自动选择。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/labelsVisibility
crawled: 2025-12-02T17:32:37Z
---

# labelsVisibility

**Instance Property**

The labels visibility set by [labelsVisibility(_:)](../View/labelsVisibility.zh-Hans.md).

## Declaration

```swift
var labelsVisibility: Visibility { get set }
```

## Discussion

Read this environment value from within a view to obtain the preferred visibility for labels within the hierarchy. If you would like to dynamically hide the label of your custom view, make sure to include an accessibility label via the [accessibilityLabel(content:)](../View/accessibilityLabel_content.zh-Hans.md) modifier as illustrated below:

```swift
@Environment(\.labelsVisibility)
private var labelsVisibility

var body: some View {
    VStack {
        QuizCardView()
        if labelsVisibility != .hidden {
            label
        }
    }
    .accessibilityLabel {
        label
    }
}

private var label: some View {
    Text("Quiz Card")
}
```

## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

