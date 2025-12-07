--- 来源：https://developer.apple.com/documentation/swiftui/datepickerstyleconfiguration
抓取时间：2025-12-05T22:21:08Z

---

# DatePickerStyleConfiguration

**Structure**

`DatePicker` 的属性。

## 声明

```swift
struct DatePickerStyleConfiguration
```

## 设置日期范围

- **minimumDate**：最早的可选日期。

- **maximumDate**：最近的可选日期。

## 为日期选择器添加标签

- **label**：`DatePicker` 的描述。

- **DatePickerStyleConfiguration.Label**：`DatePicker` 的已擦除类型标签。

- **displayedComponents**：用户可以查看和编辑的日期组件。

## 选择日期

- **selection**：正在显示和选择的日期值。

- **$selection**

## 创建自定义日期选择器样式

- **makeBody(configuration:)**：返回 `DatePicker` 的外观和交互内容。

- **DatePickerStyle.Configuration**：`DatePicker` 属性的类型别名。

- **Body**：展示 `DatePicker` 的外观和交互方式。


---
source: https://developer.apple.com/documentation/swiftui/datepickerstyleconfiguration
crawled: 2025-12-05T22:21:08Z
---

# DatePickerStyleConfiguration

**Structure**

The properties of a `DatePicker`.

## Declaration

```swift
struct DatePickerStyleConfiguration
```

## Establishing the date range

- **minimumDate**: The oldest selectable date.
- **maximumDate**: The most recent selectable date.

## Labeling the date picker

- **label**: A description of the `DatePicker`.
- **DatePickerStyleConfiguration.Label**: A type-erased label of a `DatePicker`.
- **displayedComponents**: The date components that the user is able to view and edit.

## Selecting the date

- **selection**: The date value being displayed and selected.
- **$selection**

## Creating custom date picker styles

- **makeBody(configuration:)**: Returns the appearance and interaction content for a `DatePicker`.
- **DatePickerStyle.Configuration**: A type alias for the properties of a `DatePicker`.
- **Body**: A view representing the appearance and interaction of a `DatePicker`.

