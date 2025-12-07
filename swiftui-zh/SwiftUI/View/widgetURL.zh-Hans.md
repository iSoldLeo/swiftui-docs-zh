--- 来源：https://developer.apple.com/documentation/SwiftUI/View/widgetURL(_:)

抓取时间：2025-12-03T05:35:12Z

---

# widgetURL(_:)

**实例方法**

设置用户点击小部件时，在包含该小部件的应用程序中打开的 URL。

## 声明

```swift
@MainActor @preconcurrency func widgetURL(_ url: URL?) -> some View

```

## 参数

- **url**：要在包含该小部件的应用程序中打开的 URL。

## 返回值

一个视图，当用户点击小部件时，该视图会打开指定的 URL。

## 说明

小部件在其视图层次结构中仅支持一个 `widgetURL` 修饰符。如果多个视图具有 `widgetURL` 修饰符，则行为未定义。

## URL

- **onOpenURL(perform:)**：注册一个处理程序，用于响应应用接收到的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/View/widgetURL(_:)
crawled: 2025-12-03T05:35:12Z
---

# widgetURL(_:)

**Instance Method**

Sets the URL to open in the containing app when the user clicks the widget.

## Declaration

```swift
@MainActor @preconcurrency func widgetURL(_ url: URL?) -> some View

```

## Parameters

- **url**: The URL to open in the containing app.

## Return Value

A view that opens the specified URL when the user clicks the widget.

## Discussion

Widgets support one `widgetURL` modifier in their view hierarchy. If multiple views have `widgetURL` modifiers, the behavior is undefined.

## URLs

- **onOpenURL(perform:)**: Registers a handler to invoke in response to a URL that your app receives.

