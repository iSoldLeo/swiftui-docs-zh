---
来源： https://developer.apple.com/documentation/SwiftUI/PhysicalMetric
抓取时间： 2025-12-02T17:37:45Z
---

# 物理量

**Structure**

以点为单位访问与指定物理量值相对应的值。

### 声明

```swift
@propertyWrapper @frozen struct PhysicalMetric<Value>
```

## 概览

在[View](View.zh-Hans.md) 或继承`View` 环境的类型（如[ViewModifier](ViewModifier.zh-Hans.md)）中使用此属性包装器。它的值将等同于您指定的长度物理量的点数。

例如，如果想让一个变量包含与一米相对应的点数，可以这样做：

```swift
struct MyView: View {
    @PhysicalMetric(from: .meters)
    var twoAndAHalfMeters = 2.5
    …
}
```

对于与场景视图内容无关的属性类型，如[App](App.zh-Hans.md) 或[Scene](Scene.zh-Hans.md)，不支持使用此包装器。

## 补偿世界缩放

从根据 visionOS 2.0 SDK 构建的应用程序开始，`PhysicalMetric` 的默认行为是通过缩放其返回值以匹配当前场景的世界缩放比例，生成与同一场景中的`RealityView` 所使用的距离相匹配的值。在此之前，这些值是没有缩放的，它们适用于在任何场景之外测量用户周围环境中的距离和长度。如果与场景中的`RealityView`一起使用，未缩放的值可能会产生意想不到的行为。

要修改`PhysicalMetric` 的行为并获得无缩放值，请使用[transformEnvironment(_:transform:)](View/transformEnvironment___transform.zh-Hans.md) 修改器，转换[physicalMetrics](EnvironmentValues/physicalMetrics.zh-Hans.md) 关键路径、在修改后的视图中编辑`PhysicalMetric` 使用的转换器，以使用新的[WorldScalingCompensation](WorldScalingCompensation.zh-Hans.md) 模式。例如

```swift
struct RulerView: View {
    @PhysicalMetric(from: .meters)
    var oneMeter = 1

    var body: some View {
        /* implement a size-accurate ruler */
    }
}

struct ContentView: View {
    var body: some View {
        RulerView()
            .transformEnvironment(\.physicalMetrics) { metrics in
                metrics = metrics.worldScalingCompensation(.unscaled)
            }
    }
}
```





## 创建度量

- **init(wrappedValue:from:)**：创建一个值，将指定点（其尺寸以给定单位的物理长度测量值指定）映射到相关场景中点的相应值。

## 获取值

- **wrappedValue**：相关场景坐标系中的点值。

## 测量视图

- **GeometryReader**：容器视图，将其内容定义为自身大小和坐标空间的函数。
- **GeometryReader3D**：将其内容定义为其自身大小和坐标空间函数的容器视图。
- **GeometryProxy**：用于访问容器视图的大小和坐标空间（锚点分辨率）的代理。
- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。
- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以对相对于命名空间的点和尺寸等维度进行操作。
- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。
- **CoordinateSpaceProtocol**：布局系统中的参照基准。
- **PhysicalMetricsConverter**：物理度量转换器以物理长度测量的形式，提供点值与其在三维空间中的范围之间的转换。

## 符合

- 动态属性


---
source: https://developer.apple.com/documentation/SwiftUI/PhysicalMetric
crawled: 2025-12-02T17:37:45Z
---

# PhysicalMetric

**Structure**

Provides access to a value in points that corresponds to the specified physical measurement.

## Declaration

```swift
@propertyWrapper @frozen struct PhysicalMetric<Value>
```

## Overview

Use this property wrapper inside a [View](View.zh-Hans.md) or a type that inherits a `View`’s environment, like a [ViewModifier](ViewModifier.zh-Hans.md). Its value will be the equivalent in points of the physical measurement of length you specify.

For example, to have a variable that contains the amount of points corresponding to one meter, you can do the following:

```swift
struct MyView: View {
    @PhysicalMetric(from: .meters)
    var twoAndAHalfMeters = 2.5
    …
}
```

Using this wrapper for a property of a type not associated with a scene’s view contents, like an  [App](App.zh-Hans.md) or a [Scene](Scene.zh-Hans.md), is unsupported.

## Compensating for World Scaling

Starting with apps built against the visionOS 2.0 SDK, the default behavior of `PhysicalMetric` is to produce values that match the distances used by `RealityView`s in the same scene, by scaling its returned values to match the world scaling of the current scene. Previously, the values were not scaled, and they were suitable for measuring distances and lengths within the user’s surroundings, outside of any scene. Unscaled values could produce unexpected behavior if used in conjunction with `RealityView`s within the scene.

To modify the behavior of `PhysicalMetric` and obtain unscaled values, use the [transformEnvironment(_:transform:)](View/transformEnvironment___transform.zh-Hans.md) modifier, transforming the [physicalMetrics](EnvironmentValues/physicalMetrics.zh-Hans.md) key path, to edit the converter used by `PhysicalMetric` within the modified views to use a new [WorldScalingCompensation](WorldScalingCompensation.zh-Hans.md) mode. For example:

```swift
struct RulerView: View {
    @PhysicalMetric(from: .meters)
    var oneMeter = 1

    var body: some View {
        /* implement a size-accurate ruler */
    }
}

struct ContentView: View {
    var body: some View {
        RulerView()
            .transformEnvironment(\.physicalMetrics) { metrics in
                metrics = metrics.worldScalingCompensation(.unscaled)
            }
    }
}
```





## Creating a metric

- **init(wrappedValue:from:)**: Creates a value that maps the specified point, whose dimensions are specified in physical length measurements in the given unit, to the corresponding value in points in the associated scene.

## Getting the value

- **wrappedValue**: A value in points in the coordinate system of the associated scene.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Conforms To

- DynamicProperty

