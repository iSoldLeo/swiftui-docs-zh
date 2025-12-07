--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollContentBackground(_:)

抓取时间：2025-11-30T21:25:44Z

---

# scrollContentBackground(_:)

**实例方法**

指定此视图中可滚动视图的背景可见性。

## 声明

```swift
nonisolated func scrollContentBackground(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：用于背景的可见性。

## 说明

以下示例隐藏了列表的标准系统背景。

```swift
List {
    Text("One")
    Text("Two")
    Text("Three")
}
.scrollContentBackground(.hidden)
```

在 macOS 15.0 及更高版本中，滚动背景的可见性有助于实现填充窗口内容视图或面板完整宽度和高度的滚动视图的无缝窗口/标题栏外观。 `List` 和 `Form` 默认呈现无缝外观，可通过隐藏滚动背景进行配置。`ScrollView` 可通过显示背景实现无缝效果。

## 管理内容可见性

- **scrollClipDisabled(_:)**：设置滚动视图是否将其内容裁剪到边界内。

- **ScrollContentOffsetAdjustmentBehavior**：定义滚动视图可以具有的不同内容偏移调整行为的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollContentBackground(_:)
crawled: 2025-11-30T21:25:44Z
---

# scrollContentBackground(_:)

**Instance Method**

Specifies the visibility of the background for scrollable views within this view.

## Declaration

```swift
nonisolated func scrollContentBackground(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The visibility to use for the background.

## Discussion

The following example hides the standard system background of the List.

```swift
List {
    Text("One")
    Text("Two")
    Text("Three")
}
.scrollContentBackground(.hidden)
```

On macOS 15.0 and later, the visibility of the scroll background helps achieve the seamless window/titlebar appearance for scroll views that fill the window’s content view, or a pane’s full width and height. `List` and `Form` have the seamless appearance by default, configurable by hiding the scroll background. `ScrollView` can become seamless by making the background visible.

## Managing content visibility

- **scrollClipDisabled(_:)**: Sets whether a scroll view clips its content to its bounds.
- **ScrollContentOffsetAdjustmentBehavior**: A type that defines the different kinds of content offset adjusting behaviors a scroll view can have.

