---
来源：https://developer.apple.com/documentation/SwiftUI/GaugeStyle/makeBody(配置:)
抓取时间：2025-12-01T10:59:08Z
---

# makeBody(configuration:)

**实例方法**

创建代表仪表主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：要应用于仪器实例的属性。

## 讨论

系统会在视图层次结构中的每个 gauge 实例上调用此修改器，其中此样式是当前的 gauge 样式。

## 创建自定义仪表盘样式

- **GaugeStyle.Configuration**：仪表盘实例的属性。
- **Body**：表示仪器主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyle/makeBody(configuration:)
crawled: 2025-12-01T10:59:08Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view representing the body of a gauge.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties to apply to the gauge instance.

## Discussion

The system calls this modifier on each instance of gauge within a view hierarchy where this style is the current gauge style.

## Creating custom gauge styles

- **GaugeStyle.Configuration**: The properties of a gauge instance.
- **Body**: A view representing the body of a gauge.

