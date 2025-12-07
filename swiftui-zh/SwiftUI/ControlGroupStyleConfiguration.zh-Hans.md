---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroupStyleConfiguration
抓取时间： 2025-12-02T17:33:30Z
---

# ControlGroupStyleConfiguration

**Structure**

控制组的属性。

## 声明

```swift
struct ControlGroupStyleConfiguration
```

## 配置标签

- **label**：提供[ControlGroup](ControlGroup.zh-Hans.md)的可选标签的视图。
- **ControlGroupStyleConfiguration.Label**：[ControlGroup](ControlGroup.zh-Hans.md)的类型迭代标签。

## 配置内容

- **content**：表示`ControlGroup`内容的视图。
- **ControlGroupStyleConfiguration.Content**：`ControlGroup`的类型化内容。

## 造型组

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。
- **ControlGroupStyle**：定义视图层次结构中所有控制组的实现。
- **formStyle(_:)**：为视图层次结构中的窗体设置样式。
- **FormStyle**：表单的外观和行为。
- **FormStyleConfiguration**：表单实例的属性。
- **groupBoxStyle(_:)**：表单实例的属性：为该视图中的组框设置样式。
- **GroupBoxStyle**：指定视图层次结构中所有组框的外观和交互的类型。
- **GroupBoxStyleConfiguration**：组框实例的属性。
- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。
- **IndexViewStyle**：定义视图层次结构中所有`IndexView` 实例的实现。
- **labeledContentStyle(_:)**：为标签内容设置样式。
- **LabeledContentStyle**：标注内容实例的外观和行为。
- **LabeledContentStyleConfiguration**: 标签内容实例的外观和行为：标注内容实例的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyleConfiguration
crawled: 2025-12-02T17:33:30Z
---

# ControlGroupStyleConfiguration

**Structure**

The properties of a control group.

## Declaration

```swift
struct ControlGroupStyleConfiguration
```

## Configuring the label

- **label**: A view that provides the optional label of the [ControlGroup](ControlGroup.zh-Hans.md).
- **ControlGroupStyleConfiguration.Label**: A type-erased label of a [ControlGroup](ControlGroup.zh-Hans.md).

## Configuring the content

- **content**: A view that represents the content of the `ControlGroup`.
- **ControlGroupStyleConfiguration.Content**: A type-erased content of a `ControlGroup`.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyle**: The appearance and behavior of a form.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyle**: A type that specifies the appearance and interaction of all group boxes within a view hierarchy.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

