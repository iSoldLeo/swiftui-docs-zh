--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplateBuilder
抓取时间：2025-12-02T17:32:04Z

---

# ControlWidgetTemplateBuilder

**Structure**

一个用于构建控件模板主体的自定义属性。

## 声明

```swift
@resultBuilder struct ControlWidgetTemplateBuilder
```

## 概述

`@ControlWidgetTemplateBuilder` 属性允许控件模板的主体闭包在执行零个或多个其他语句后生成控件模板：

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        let kind = "com.yourcompany.GarageDoorOpener"

        StaticControlConfiguration(
            kind: kind
        ) {
            let isOpen = ...

            ControlWidgetToggle(
                "Garage Door",
                isOn: isOpen,
                action: ToggleGarageDoor()
            ) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ?
                        "door.garage.open" : "door.garage.closed"
                )
            }
        }
    }
}
```

## 类型方法

- **buildBlock(_:)**：传递一个作为子视图编写的单个控件模板，不做任何修改。

- **buildExpression(_:)**：在构建器中构建表达式。

## 控件组件的构成

- **ControlWidget**：用于在系统空间（例如控制中心、锁屏界面和操作按钮）中显示的控件组件的配置和内容。

- **ControlWidgetConfiguration**：描述控件组件内容的类型。

- **EmptyControlWidgetConfiguration**：空的控件组件配置。

- **ControlWidgetConfigurationBuilder**：用于构建控件组件主体的自定义属性。

- **ControlWidgetTemplate**：描述控件组件内容的类型。

- **EmptyControlWidgetTemplate**：空的控件组件模板。

- **controlWidgetActionHint(_:)**：由修改后的标签描述的控件的操作提示。

- **controlWidgetStatus(_:)**：由修改后的标签描述的控件的状态。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplateBuilder
crawled: 2025-12-02T17:32:04Z
---

# ControlWidgetTemplateBuilder

**Structure**

A custom attribute that constructs a control widget template’s body.

## Declaration

```swift
@resultBuilder struct ControlWidgetTemplateBuilder
```

## Overview

The `@ControlWidgetTemplateBuilder` attribute allows your control template’s body closure to produce a control template after zero or more other statements:

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        let kind = "com.yourcompany.GarageDoorOpener"

        StaticControlConfiguration(
            kind: kind
        ) {
            let isOpen = ...

            ControlWidgetToggle(
                "Garage Door",
                isOn: isOpen,
                action: ToggleGarageDoor()
            ) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ?
                        "door.garage.open" : "door.garage.closed"
                )
            }
        }
    }
}
```

## Type Methods

- **buildBlock(_:)**: Passes a single control widget template written as a child view through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

