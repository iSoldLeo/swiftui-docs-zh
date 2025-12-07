---
来源： https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable
抓取时间： 2025-12-02T17:44:20Z
---

# AXChartDescriptorRepresentable

**Protocol**

用于生成`AXChartDescriptor` 对象的类型，您可使用该对象提供有关图表及其数据的信息，以便在 VoiceOver 或其他辅助技术中获得无障碍体验。

### 声明

```swift
protocol AXChartDescriptorRepresentable
```

## 概览

请注意，您可能会在`AXChartDescriptorRepresentable` 的实现中使用`@Environment` 属性包装器，在这种情况下，您应该实现`updateChartDescriptor`，当`Environment` 发生变化时，它将被调用。

例如，要为表示图表的视图提供可访问性，首先要声明图表描述符的可表示类型：

```swift
struct MyChartDescriptorRepresentable: AXChartDescriptorRepresentable {
    func makeChartDescriptor() -> AXChartDescriptor {
        // Build and return your `AXChartDescriptor` here.
    }

    func updateChartDescriptor(_ descriptor: AXChartDescriptor) {
        // Update your chart descriptor with any new values.
    }
}
```

然后，使用`AXChartDescriptorRepresentable`修饰符为视图提供`accessibilityChartDescriptor` 类型的实例：

```swift
var body: some View {
    MyChartView()
        .accessibilityChartDescriptor(MyChartDescriptorRepresentable())
}
```

## 管理描述符

- **makeChartDescriptor()**：为该视图创建`AXChartDescriptor`，并将其返回。
- **updateChartDescriptor(_:)**：根据视图或`Environment` 中的更改，更新视图的现有`AXChartDescriptor`。

## 描述图表

- **accessibilityChartDescriptor(_:)**：为表示图表的 View 添加描述符，使所有用户都能访问图表的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable
crawled: 2025-12-02T17:44:20Z
---

# AXChartDescriptorRepresentable

**Protocol**

A type to generate an `AXChartDescriptor` object that you use to provide information about a chart and its data for an accessible experience in VoiceOver or other assistive technologies.

## Declaration

```swift
protocol AXChartDescriptorRepresentable
```

## Overview

Note that you may use the `@Environment` property wrapper inside the implementation of your `AXChartDescriptorRepresentable`, in which case you should implement `updateChartDescriptor`, which will be called when the `Environment` changes.

For example, to provide accessibility for a view that represents a chart, you would first declare your chart descriptor representable type:

```swift
struct MyChartDescriptorRepresentable: AXChartDescriptorRepresentable {
    func makeChartDescriptor() -> AXChartDescriptor {
        // Build and return your `AXChartDescriptor` here.
    }

    func updateChartDescriptor(_ descriptor: AXChartDescriptor) {
        // Update your chart descriptor with any new values.
    }
}
```

Then, provide an instance of your `AXChartDescriptorRepresentable` type to your view using the `accessibilityChartDescriptor` modifier:

```swift
var body: some View {
    MyChartView()
        .accessibilityChartDescriptor(MyChartDescriptorRepresentable())
}
```

## Managing a descriptor

- **makeChartDescriptor()**: Create the `AXChartDescriptor` for this view, and return it.
- **updateChartDescriptor(_:)**: Update the existing `AXChartDescriptor` for your view, based on changes in your view or in the `Environment`.

## Describing charts

- **accessibilityChartDescriptor(_:)**: Adds a descriptor to a View that represents a chart to make the chart’s contents accessible to all users.

