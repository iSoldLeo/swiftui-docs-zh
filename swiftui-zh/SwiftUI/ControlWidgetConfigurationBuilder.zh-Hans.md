---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfigurationBuilder
抓取时间： 2025-12-02T17:32:02Z
---

# ControlWidgetConfigurationBuilder

**Structure**

自定义属性，用于构建控制 widget 的主体。

### 声明

```swift
@resultBuilder struct ControlWidgetConfigurationBuilder
```

## 概览

`@ControlWidgetConfigurationBuilder`属性允许控制 widget 的主体闭包在零个或多个其他语句后生成控制 widget 配置：

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        let kind = "com.yourcompany.GarageDoorOpener"

        StaticControlConfiguration(
            kind: kind
        ) {
            ...
        }
    }
}
```

## 类型方法

- **buildBlock(_:)**：将作为子控件写入的单个控件部件配置原封不动地传递。
- **buildExpression(_:)**：在构建器中构建表达式。

## 组合控件部件

- **ControlWidget**：控制中心、锁屏和操作按钮等系统空间中显示的控制 widget 的配置和内容。
- **ControlWidgetConfiguration**：描述控制 widget 内容的类型。
- **EmptyControlWidgetConfiguration**：一个空的控件部件配置。
- **ControlWidgetTemplate**：描述控制 widget 内容的类型。
- **EmptyControlWidgetTemplate**：一个空的控件部件模板。
- **ControlWidgetTemplateBuilder**：用于构建控件 widget 模板主体的自定义属性。
- **controlWidgetActionHint(_:)**：修改后的标签所描述的控件的操作提示。
- **controlWidgetStatus(_:)**：被修改标签描述的控件的状态。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfigurationBuilder
crawled: 2025-12-02T17:32:02Z
---

# ControlWidgetConfigurationBuilder

**Structure**

A custom attribute that constructs a control widget’s body.

## Declaration

```swift
@resultBuilder struct ControlWidgetConfigurationBuilder
```

## Overview

The `@ControlWidgetConfigurationBuilder` attribute allows your control widget’s body closure to produce a control widget configuration after zero or more other statements:

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        let kind = "com.yourcompany.GarageDoorOpener"

        StaticControlConfiguration(
            kind: kind
        ) {
            ...
        }
    }
}
```

## Type Methods

- **buildBlock(_:)**: Passes a single control widget configuration written as a child control through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

