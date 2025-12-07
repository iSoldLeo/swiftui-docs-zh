---
来源：https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/makeBody(配置:)
抓取时间： 2025-12-03T06:09:31Z
---

# makeBody(configuration:)

**实例方法**

返回`DatePicker`的外观和交互内容。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 讨论

系统会为视图层次结构中的每个[DatePicker](../DatePicker.zh-Hans.md) 实例调用此方法，其中该样式是当前日期选择器样式。

## 创建自定义日期选择器样式

- **DatePickerStyleConfiguration**：`DatePicker`的属性。
- **DatePickerStyle.Configuration**：`DatePicker`属性的类型别名。
- **Body**：表示`DatePicker` 的外观和交互的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/makeBody(configuration:)
crawled: 2025-12-03T06:09:31Z
---

# makeBody(configuration:)

**Instance Method**

Returns the appearance and interaction content for a `DatePicker`.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Discussion

The system calls this method for each [DatePicker](../DatePicker.zh-Hans.md) instance in a view hierarchy where this style is the current date picker style.

## Creating custom date picker styles

- **DatePickerStyleConfiguration**: The properties of a `DatePicker`.
- **DatePickerStyle.Configuration**: A type alias for the properties of a `DatePicker`.
- **Body**: A view representing the appearance and interaction of a `DatePicker`.

