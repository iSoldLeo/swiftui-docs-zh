--- 来源：https://developer.apple.com/documentation/SwiftUI/View/controlWidgetActionHint(_:)

抓取时间：2025-11-30T21:08:33Z

---

# controlWidgetActionHint(_:)

**实例方法**

用于描述由修改后的标签所定义的控件的操作提示。

## 声明

```swift
@MainActor @preconcurrency func controlWidgetActionHint(_ hint: LocalizedStringResource) -> some View

```

## 参数

- **hint**：要显示的本地化字符串资源。

## 说明

此文本将显示在操作按钮旁边，用于描述控件激活后将执行的操作。默认情况下，控件的操作提示由其显示名称、控件类型以及值文本（如果有）派生而来：

// 操作提示：“按住‘Ping My Watch’” struct PingMyWatchButton: Control { static let displayName: LocalizedStringResource = “Ping My Watch” … }

// 当此按钮的操作符合 `OpenIntent` 时：// 操作提示：“按住打开备忘录” struct NotesLauncher: Control { static let displayName: LocalizedStringResource = “备忘录” … }

// 操作提示：“按住开启‘静音模式’” / “按住关闭‘静音模式’” struct SilentModeToggle: Control { static let displayName: LocalizedStringResource = “静音模式” … }

// 操作提示：“按住静音” / “按住响铃” ControlWidgetToggle(…) { isOn in Label( isOn ? “Silent” : “Ring”，systemImage: isOn ? “bell.slash” : “bell” ) }

当默认操作提示不够清晰时，您可以通过将此修饰符应用于控件的标签来自定义提示。例如，我们可以将用户使用 `NotesLauncher` 控件执行的操作描述为“撰写笔记”，而不是默认的“按住打开笔记”提示，如下所示：

ControlWidgetButton(…) { Image(systemName: “note.text”) .controlWidgetActionHint(“撰写笔记”) }

## 编写控件

- **ControlWidget**：控件的配置和内容，用于在系统空间（例如控制中心、锁屏界面和操作按钮）中显示。

- **ControlWidgetConfiguration**：描述控件内容的类型。

- **EmptyControlWidgetConfiguration**：一个空的控件配置。

- **ControlWidgetConfigurationBuilder**：一个用于构建控件主体的自定义属性。

- **ControlWidgetTemplate**：一个用于描述控件内容的类型。

- **EmptyControlWidgetTemplate**：一个空的控件模板。

- **ControlWidgetTemplateBuilder**：一个用于构建控件模板主体的自定义属性。

- **controlWidgetStatus(_:)**：由“已修改”标签描述的控件状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/controlWidgetActionHint(_:)
crawled: 2025-11-30T21:08:33Z
---

# controlWidgetActionHint(_:)

**Instance Method**

The action hint of the control described by the modified label.

## Declaration

```swift
@MainActor @preconcurrency func controlWidgetActionHint(_ hint: LocalizedStringResource) -> some View

```

## Parameters

- **hint**: The localized string resource to display.

## Discussion

This text will appear next to the Action Button to describe what your control will do when activated. By default, a control’s action hint is derived from its display name, the type of control, and value text, if any:

// Action Hint: “Hold for ‘Ping My Watch’” struct PingMyWatchButton: Control { static let displayName: LocalizedStringResource = “Ping My Watch” … }

// When this button’s action conforms to `OpenIntent`: // Action Hint: “Hold to Open Notes” struct NotesLauncher: Control { static let displayName: LocalizedStringResource = “Notes” … }

// Action Hint: “Hold to Turn On ‘Silent Mode’” / “Hold to Turn Off ‘Silent Mode’” struct SilentModeToggle: Control { static let displayName: LocalizedStringResource = “Silent Mode” … }

// Action Hint: “Hold for Silent” / “Hold for Ring” ControlWidgetToggle(…) { isOn in Label( isOn ? “Silent” : “Ring”, systemImage: isOn ? “bell.slash” : “bell” ) }

When the default action hint is insufficiently descriptive, you can customize the hint by applying this modifier to the control’s label. For instance, we can describe what the user will use our `NotesLauncher` control to do, “Compose a Note”, instead of the default “Hold to Open Notes” hint, like this:

ControlWidgetButton(…) { Image(systemName: “note.text”) .controlWidgetActionHint(“Compose a Note”) }

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

