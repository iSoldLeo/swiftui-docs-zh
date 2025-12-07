--- 来源：https://developer.apple.com/documentation/SwiftUI/View/controlWidgetStatus(_:)

抓取时间：2025-11-30T21:08:34Z

---

# controlWidgetStatus(_:)

**实例方法**

返回由修改标签描述的控件的状态。

## 声明

```swift
@MainActor @preconcurrency func controlWidgetStatus(_ status: LocalizedStringResource) -> some View

```

## 参数

- **status**：要显示的本地化字符串资源。

## 说明

当控件状态更改时，此文本将显示在控制中心。您可以通过将此修饰符应用于控件的值标签来自定义文本：

```swift
// Status Text: "Do Not Disturb Until This Evening" / "Do Not Disturb Disabled"
ControlWidgetToggle("Do Not Disturb", ...) { isOn in
    Image(systemName: "moon")
        .controlWidgetStatus(isOn ? "Do Not Disturb Until This Evening" : "Do Not Disturb Disabled")
}
```

## 组合控件

- **ControlWidget**：控件的配置和内容，用于在系统空间（例如控制中心、锁屏界面和操作按钮）中显示。

- **ControlWidgetConfiguration**：描述控件内容的类型。

- **EmptyControlWidgetConfiguration**：空的控件配置。

- **ControlWidgetConfigurationBuilder**：用于构建控件主体的自定义属性。

- **ControlWidgetTemplate**：描述控件内容的类型。

- **EmptyControlWidgetTemplate**：空的控件模板。

- **ControlWidgetTemplateBuilder**：用于构建控件模板主体的自定义属性。

- **controlWidgetActionHint(_:)**：由修改后的标签描述的控件的操作提示。


---
source: https://developer.apple.com/documentation/SwiftUI/View/controlWidgetStatus(_:)
crawled: 2025-11-30T21:08:34Z
---

# controlWidgetStatus(_:)

**Instance Method**

The status of the control described by the modified label.

## Declaration

```swift
@MainActor @preconcurrency func controlWidgetStatus(_ status: LocalizedStringResource) -> some View

```

## Parameters

- **status**: The localized string resource to display.

## Discussion

This text appears in Control Center when your control’s state changes. You can customize the text by applying this modifier to the control’s value label:

```swift
// Status Text: "Do Not Disturb Until This Evening" / "Do Not Disturb Disabled"
ControlWidgetToggle("Do Not Disturb", ...) { isOn in
    Image(systemName: "moon")
        .controlWidgetStatus(isOn ? "Do Not Disturb Until This Evening" : "Do Not Disturb Disabled")
}
```

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.

