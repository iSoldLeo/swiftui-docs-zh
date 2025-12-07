---
来源：https://developer.apple.com/documentation/SwiftUI/LabelStyle/makeBody(配置：)
抓取时间： 2025-12-03T06:10:27Z
---

# makeBody(configuration:)

**实例方法**

创建表示标签主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：标签的属性。

## 讨论

系统会为视图层次结构中的每个[Label](../Label.zh-Hans.md) 实例调用此方法，其中该样式是当前的标签样式。

## 创建自定义标签样式

- **LabelStyle.Configuration**：标签的属性。
- **Body**：表示标签主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/LabelStyle/makeBody(configuration:)
crawled: 2025-12-03T06:10:27Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a label.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the label.

## Discussion

The system calls this method for each [Label](../Label.zh-Hans.md) instance in a view hierarchy where this style is the current label style.

## Creating custom label styles

- **LabelStyle.Configuration**: The properties of a label.
- **Body**: A view that represents the body of a label.

