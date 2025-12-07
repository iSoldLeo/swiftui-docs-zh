---
来源：https://developer.apple.com/documentation/swiftui/emptycontrolwidgettemplate
抓取时间： 2025-12-04T13:10:22Z
---

# EmptyControlWidgetTemplate

**Structure**

空控件部件模板。

### 声明

```swift
@MainActor @frozen @preconcurrency struct EmptyControlWidgetTemplate
```

## Initializers

- **init()**

## 组成控件部件

- **ControlWidget**：控制中心、锁屏和操作按钮等系统空间中显示的控制 widget 的配置和内容。
- **ControlWidgetConfiguration**：描述控制 widget 内容的类型。
- **EmptyControlWidgetConfiguration**：一个空的控件部件配置。
- **ControlWidgetConfigurationBuilder**：用于构建控件 widget 主体的自定义属性。
- **ControlWidgetTemplate**：描述控件 widget 内容的类型。
- **ControlWidgetTemplateBuilder**：用于构建控件 widget 模板主体的自定义属性。
- **controlWidgetActionHint(_:)**：修改后的标签所描述的控件的操作提示。
- **controlWidgetStatus(_:)**：被修改标签描述的控件的状态。

## 符合

- 比特可复制
- 控件部件模板
- 可复制


---
source: https://developer.apple.com/documentation/swiftui/emptycontrolwidgettemplate
crawled: 2025-12-04T13:10:22Z
---

# EmptyControlWidgetTemplate

**Structure**

An empty control widget template.

## Declaration

```swift
@MainActor @frozen @preconcurrency struct EmptyControlWidgetTemplate
```

## Initializers

- **init()**

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

## Conforms To

- BitwiseCopyable
- ControlWidgetTemplate
- Copyable

