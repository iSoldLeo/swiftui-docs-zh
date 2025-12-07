---
来源：https://developer.apple.com/documentation/swiftui/geometryproxy
抓取时间： 2025-12-04T11:34:20Z
---

# 几何代理

**Structure**

用于访问容器视图的尺寸和坐标空间（锚点分辨率）的代理。

## 声明

```swift
struct GeometryProxy
```

## 访问几何特征

- **bounds(of:)**：返回指定坐标空间的边界矩形，并转换为本地坐标空间。
- **frame(in:)**：返回容器视图的边界矩形，并转换为已定义的坐标空间。
- **size**：容器视图的大小。
- **safeAreaInsets**：容器视图的安全区域嵌入。
- **subscript(_:)**：确定容器视图中锚点的值。
- **transform(in:)**：将容器视图的 3D 变换转换到定义的坐标空间。

### 实例属性

- **containerCornerInsets**：返回容器视图的边角嵌入值。使用此值可根据容器视图的重叠角嵌入调整视图的几何形状。角嵌入可能包括系统 UI 部件以及窗口和演示文稿的角半径。

## 测量视图

- **GeometryReader**：容器视图，将其内容定义为自身大小和坐标空间的函数。
- **GeometryReader3D**：将其内容定义为其自身大小和坐标空间函数的容器视图。
- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。
- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以对相对于命名空间的点和尺寸等维度进行操作。
- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。
- **CoordinateSpaceProtocol**：布局系统中的参照基准。
- **PhysicalMetric**：以点为单位访问与指定物理测量值相对应的值。
- **PhysicalMetricsConverter**：物理度量转换器以物理长度度量的形式，提供点值与其在三维空间中的范围之间的转换。


---
source: https://developer.apple.com/documentation/swiftui/geometryproxy
crawled: 2025-12-04T11:34:20Z
---

# GeometryProxy

**Structure**

A proxy for access to the size and coordinate space (for anchor resolution) of the container view.

## Declaration

```swift
struct GeometryProxy
```

## Accessing geometry characteristics

- **bounds(of:)**: Returns the given coordinate space’s bounds rectangle, converted to the local coordinate space.
- **frame(in:)**: Returns the container view’s bounds rectangle, converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

## Instance Properties

- **containerCornerInsets**: Returns the corner insets of the container view. Use this value to adjust the geometry of a view based on the overlapping corner insets of the container view. Corner insets may include pieces of system UI as well as the corner radii for windows and presentations.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

