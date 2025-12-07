---
来源： https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable/updateChartDescriptor(_:)
抓取时间： 2025-12-01T11:38:51Z
---

# updateChartDescriptor(_:)

**实例方法**

根据视图或`Environment` 中的更改，更新视图的现有`AXChartDescriptor`。

### 声明

```swift
func updateChartDescriptor(_ descriptor: AXChartDescriptor)
```

## 讨论

当辅助功能需要您的 `AXChartDescriptor` 用于 VoiceOver 时，将根据需要调用该功能。只有当您的视图输入或`Environment` 的相关部分发生变化时，才会调用它。

## 管理描述符

- **makeChartDescriptor()**：为该视图创建`AXChartDescriptor`，并将其返回。


---
source: https://developer.apple.com/documentation/SwiftUI/AXChartDescriptorRepresentable/updateChartDescriptor(_:)
crawled: 2025-12-01T11:38:51Z
---

# updateChartDescriptor(_:)

**Instance Method**

Update the existing `AXChartDescriptor` for your view, based on changes in your view or in the `Environment`.

## Declaration

```swift
func updateChartDescriptor(_ descriptor: AXChartDescriptor)
```

## Discussion

This will be called as needed, when accessibility needs your `AXChartDescriptor` for VoiceOver. It will only be called if the inputs to your views, or a relevant part of the `Environment`, have changed.

## Managing a descriptor

- **makeChartDescriptor()**: Create the `AXChartDescriptor` for this view, and return it.

