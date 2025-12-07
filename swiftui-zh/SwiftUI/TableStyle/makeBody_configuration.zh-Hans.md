---
来源：https://developer.apple.com/documentation/SwiftUI/TableStyle/makeBody(配置：)
抓取时间：2025-12-01T11:00:03Z
---

# makeBody(configuration:)

**实例方法**

创建表示表主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：表格的属性。

## 讨论

系统会为视图层次结构中的每个[Table](../Table.zh-Hans.md) 实例调用此方法，其中该样式是当前的表格样式。

## 创建自定义表格样式

- **TableStyle.Configuration**：表格的属性。
- **Body**：表示表主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/TableStyle/makeBody(configuration:)
crawled: 2025-12-01T11:00:03Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a table.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the table.

## Discussion

The system calls this method for each [Table](../Table.zh-Hans.md) instance in a view hierarchy where this style is the current table style.

## Creating custom table styles

- **TableStyle.Configuration**: The properties of a table.
- **Body**: A view that represents the body of a table.

