---
来源： https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable/makeChartDescriptor()
抓取时间： 2025-12-01T11:38:50Z
---

# makeChartDescriptor()

**实例方法**

为该视图创建`AXChartDescriptor` 并返回。

## 声明

```swift
func makeChartDescriptor() -> AXChartDescriptor
```

## 讨论

您的`View` 的每个标识将调用一次。除非您的`View` 的身份发生变化，否则不会再次运行。如果您需要根据您的`View`或`Environment`中的变化更新`AXChartDescriptor`，请执行`updateChartDescriptor`。只有在辅助功能需要您视图中的`AXChartDescriptor`时，才会调用此方法。

## 管理描述符

- **updateChartDescriptor(_:)**：根据视图或`Environment`中的更改，更新视图的现有`AXChartDescriptor`。


---
source: https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable/makeChartDescriptor()
crawled: 2025-12-01T11:38:50Z
---

# makeChartDescriptor()

**Instance Method**

Create the `AXChartDescriptor` for this view, and return it.

## Declaration

```swift
func makeChartDescriptor() -> AXChartDescriptor
```

## Discussion

This will be called once per identity of your `View`. It will not be run again unless the identity of your `View` changes. If you need to update the `AXChartDescriptor` based on changes in your `View`, or in the `Environment`, implement `updateChartDescriptor`. This method will only be called if / when accessibility needs the `AXChartDescriptor` of your view, for VoiceOver.

## Managing a descriptor

- **updateChartDescriptor(_:)**: Update the existing `AXChartDescriptor` for your view, based on changes in your view or in the `Environment`.

