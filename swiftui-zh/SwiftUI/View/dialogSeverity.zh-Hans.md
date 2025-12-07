--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dialogSeverity(_:)

抓取时间：2025-12-02T17:30:39Z

---

# dialogSeverity(_:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ dialogSeverity(_:) ](/documentation/SwiftUI/View/dialogSeverity(_:))

- [ View ](/documentation/swiftui/view)

- dialogSeverity(_:) 

实例方法 # dialogSeverity(_:)

macOS 13.0+ 和 watchOS 10.0+

```
nonisolated
func dialogSeverity(_ severity: DialogSeverity) -> some View

```

## [ 参数 ](/documentation/SwiftUI/View/dialogSeverity(_:)#parameters)

`severity`用于确认对话框和警告的严重性级别。

## [另请参阅](/documentation/SwiftUI/View/dialogSeverity(_:)#see-also)

### [配置对话框](/documentation/SwiftUI/View/dialogSeverity(_:)#Configuring-a-dialog)

[`func dialogIcon(Image?) -> some View`](/documentation/swiftui/view/dialogicon(_:))配置此视图中对话框使用的图标。[`func dialogIcon(Image?) -> some Scene`](/documentation/swiftui/scene/dialogicon(_:))配置警报使用的图标。[`func dialogSeverity(DialogSeverity) -> some Scene`](/documentation/swiftui/scene/dialogseverity(_:))设置警报的严重级别。[`func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some View`](/documentation/swiftui/view/dialogsuppressiontoggle(issuppressed:))启用用户屏蔽在 `self` 中显示的对话框和警报，macOS 上会显示默认屏蔽消息。在其他平台上未使用。[`func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some Scene`](/documentation/swiftui/scene/dialogsuppressiontoggle(issuppressed:))允许用户使用自定义抑制消息抑制警报。[`func dialogSuppressionToggle(_:isSuppressed:)`](/documentation/swiftui/view/dialogsuppressiontoggle(_:issuppressed:))允许用户在 macOS 上使用自定义抑制消息抑制 `self` 中显示的对话框和警报。在其他平台上未使用。[`func dialogSuppressionToggle(_:isSuppressed:)`](/documentation/swiftui/scene/dialogsuppressiontoggle(_:issuppressed:))允许用户使用自定义抑制消息抑制警报。

---
source: https://developer.apple.com/documentation/SwiftUI/View/dialogSeverity(_:)
crawled: 2025-12-02T17:30:39Z
---

# dialogSeverity(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ dialogSeverity(_:) ](/documentation/SwiftUI/View/dialogSeverity(_:))

- [ View ](/documentation/swiftui/view)

-  dialogSeverity(_:) 

Instance Method# dialogSeverity(_:)

macOS 13.0+watchOS 10.0+

```
nonisolated
func dialogSeverity(_ severity: DialogSeverity) -> some View

```

## [ Parameters ](/documentation/SwiftUI/View/dialogSeverity(_:)#parameters)

`severity`The severity to use for confirmation dialogs and alerts.

## [See Also](/documentation/SwiftUI/View/dialogSeverity(_:)#see-also)

### [Configuring a dialog](/documentation/SwiftUI/View/dialogSeverity(_:)#Configuring-a-dialog)

[`func dialogIcon(Image?) -> some View`](/documentation/swiftui/view/dialogicon(_:))Configures the icon used by dialogs within this view.[`func dialogIcon(Image?) -> some Scene`](/documentation/swiftui/scene/dialogicon(_:))Configures the icon used by alerts.[`func dialogSeverity(DialogSeverity) -> some Scene`](/documentation/swiftui/scene/dialogseverity(_:))Sets the severity for alerts.[`func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some View`](/documentation/swiftui/view/dialogsuppressiontoggle(issuppressed:))Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.[`func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some Scene`](/documentation/swiftui/scene/dialogsuppressiontoggle(issuppressed:))Enables user suppression of an alert with a custom suppression message.[`func dialogSuppressionToggle(_:isSuppressed:)`](/documentation/swiftui/view/dialogsuppressiontoggle(_:issuppressed:))Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.[`func dialogSuppressionToggle(_:isSuppressed:)`](/documentation/swiftui/scene/dialogsuppressiontoggle(_:issuppressed:))Enables user suppression of an alert with a custom suppression message.