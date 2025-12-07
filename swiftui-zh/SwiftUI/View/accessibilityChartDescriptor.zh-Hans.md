--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityChartDescriptor(_:)

抓取时间：2025-12-02T17:44:19Z

---

# accessibilityChartDescriptor(_:)

**实例方法**

向表示图表的视图添加描述符，使图表内容对所有用户都可访问。

## 声明

```swift
nonisolated func accessibilityChartDescriptor<R>(_ representable: R) -> some View where R : AXChartDescriptorRepresentable

```

## 说明

使用此方法提供有关图表视图的信息，以便 VoiceOver 和其他辅助技术用户能够感知图表及其数据并与之交互。

此方法可应用于任何表示图表的视图，包括图像视图和自定义渲染的图表视图。

`accessibilityChartDescriptor` 修饰符可应用于任何表示图表的视图，最简单的情况是仅包含图表图像的视图。视图的具体实现细节并不重要，重要的是它代表一个图表，并且提供的图表描述符能够准确地描述图表的内容。

使用示例：

首先定义您的 `AXChartDescriptorRepresentable` 类型。

```swift
struct MyChartDescriptorRepresentable:
AXChartDescriptorRepresentable {
    func makeChartDescriptor() -> AXChartDescriptor {
        // Build and return your `AXChartDescriptor` here.
    }

    func updateChartDescriptor(_ descriptor: AXChartDescriptor) {
        // Update your chart descriptor with any new values, or
        // don't override if your chart doesn't have changing
        // values.
    }
}
```

然后使用 `accessibilityChartDescriptor` 修饰符，将您的 `AXChartDescriptorRepresentable` 类型的实例提供给代表图表的视图：

```swift
SomeChartView()
    .accessibilityChartDescriptor(MyChartDescriptorRepresentable())
```

## 描述图表

- **AXChartDescriptorRepresentable**：用于生成 `AXChartDescriptor` 对象的类型，您可以使用该对象提供有关图表及其数据的信息，以便在 VoiceOver 或其他辅助技术中获得无障碍体验。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityChartDescriptor(_:)
crawled: 2025-12-02T17:44:19Z
---

# accessibilityChartDescriptor(_:)

**Instance Method**

Adds a descriptor to a View that represents a chart to make the chart’s contents accessible to all users.

## Declaration

```swift
nonisolated func accessibilityChartDescriptor<R>(_ representable: R) -> some View where R : AXChartDescriptorRepresentable

```

## Discussion

Use this method to provide information about your chart view to allow VoiceOver and other assistive technology users to perceive and interact with your chart and its data.

This may be applied to any View that represents a chart, including Image and custom-rendered chart views.

The `accessibilityChartDescriptor` modifier can be applied to -any- view representing a chart, the simplest case being just an image of a chart. The implementation details of the view aren’t important, only the fact that it represents a chart, and that the provided chart descriptor accurately describes the content of the chart.

Example usage:

First define your `AXChartDescriptorRepresentable` type.

```swift
struct MyChartDescriptorRepresentable:
AXChartDescriptorRepresentable {
    func makeChartDescriptor() -> AXChartDescriptor {
        // Build and return your `AXChartDescriptor` here.
    }

    func updateChartDescriptor(_ descriptor: AXChartDescriptor) {
        // Update your chart descriptor with any new values, or
        // don't override if your chart doesn't have changing
        // values.
    }
}
```

Then use the `accessibilityChartDescriptor` modifier to provide an instance of your `AXChartDescriptorRepresentable` type to the view representing your chart:

```swift
SomeChartView()
    .accessibilityChartDescriptor(MyChartDescriptorRepresentable())
```

## Describing charts

- **AXChartDescriptorRepresentable**: A type to generate an `AXChartDescriptor` object that you use to provide information about a chart and its data for an accessible experience in VoiceOver or other assistive technologies.

