---

来源：https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter
抓取时间：2025-12-02T17:37:46Z

---

# PhysicalMetricsConverter

**Structure**

物理度量转换器提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。

## 声明

```swift
@MainActor @preconcurrency struct PhysicalMetricsConverter
```

## 概述

转换器可在 `View` 或其他继承自 `View` 环境的类型环境中使用，并与包含该环境的场景关联。转换过程接收（或输出）场景坐标系中的点值，并将其转换为（或从转换而来）用户或场景参考系中的长度测量值。

要获取转换器，请使用 [physicalMetrics](EnvironmentValues/physicalMetrics.zh-Hans.md) 键：

```swift
struct MyView: View {
    @Environment(\.physicalMetrics) var physicalMetrics
    …
}
```

当用户操作修改场景导致测量值发生变化时（例如，通过更改其缩放比例），系统将重新评估访问该环境键的视图及其层级结构。

不支持尝试在与场景内容无关的类型中获取转换器（例如，从 [App](App.zh-Hans.md) 或 [Scene](Scene.zh-Hans.md) 的环境获取）。

## 补偿世界缩放

默认情况下，在链接到 visionOS 2.0 SDK 或更高版本的应用程序中，这些转换与场景的坐标系相匹配，包括系统对其应用的任何缩放比例。如果您使用米作为单位，这将与同一场景中未缩放的 `RealityView` 中的米概念相匹配。

为了获得与用户环境相符的精确测量结果，请使用 [worldScalingCompensation(_:)](PhysicalMetricsConverter/worldScalingCompensation.zh-Hans.md) 方法启用合适的比例尺补偿模式。

## 单位长度转换

- **convert(_:from:)**：将指定单位的长度转换为适用于此转换器关联环境的点长度。

- **convert(_:to:)**：将点的坐标转换为指定单位的物理长度测量值。

## 实例属性

- **worldScalingCompensation**：提供此转换器的当前世界比例尺补偿。

## 实例方法

- **worldScalingCompensation(_:)**：获取具有不同世界比例尺补偿行为的新转换器。

## 测量视图

- **GeometryReader**：容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryReader3D**：一个容器视图，其内容根据自身的大小和坐标空间定义。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和大小等尺寸。

- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。

- **CoordinateSpaceProtocol**：布局系统中的一个参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter
crawled: 2025-12-02T17:37:46Z
---

# PhysicalMetricsConverter

**Structure**

A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Declaration

```swift
@MainActor @preconcurrency struct PhysicalMetricsConverter
```

## Overview

Converters are available from the environment of a `View` or other type that inherits a `View`‘s environments, and are associated with the scene that contains that environment. The conversions expect (or emit) values in points in that scene’s coordinate system, and convert these to (or from) measurements of length in the user’s or scene’s reference frame.

To obtain a converter, use the [physicalMetrics](EnvironmentValues/physicalMetrics.zh-Hans.md) key:

```swift
struct MyView: View {
    @Environment(\.physicalMetrics) var physicalMetrics
    …
}
```

When user action modifies a scene so that measurements have changed (e.g., by changing its scale), the view that accessed that environment key and its hierarchy will be reevaluated.

Attempting to obtain a converter inside a type not associated with a scene’s contents (for example, from an [App](App.zh-Hans.md) or [Scene](Scene.zh-Hans.md)’s environment) is not supported.

## Compensating for World Scaling

By default in apps linked against the visionOS 2.0 SDK or later, these conversions match the scene’s coordinate system, including any scale applied to it by the system. If you’re using meters as the unit, this will match the notion of meters in an unscaled `RealityView` in the same scene.

To obtain measurements that are accurate to the user’s surroundings, use the [worldScalingCompensation(_:)](PhysicalMetricsConverter/worldScalingCompensation.zh-Hans.md) method to enable an appropriate compensation mode for the scale.

## Converting a unit length

- **convert(_:from:)**: Converts a length in the specified unit to a length in points suitable for use in the environment this converter is associated with.
- **convert(_:to:)**: Converts a point’s coordinates to physical length measurements in the specified unit.

## Instance Properties

- **worldScalingCompensation**: Provides the current world scale compensation of this converter.

## Instance Methods

- **worldScalingCompensation(_:)**: Obtains a new converter with a different world scale compensation behavior.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

