---
来源： https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/named(_:)
抓取时间： 2025-12-03T06:33:47Z
---

# named(_:)

**类型方法**

使用给定值创建一个已命名的坐标空间。

## 声明

```swift
static func named(_ name: some Hashable) -> NamedCoordinateSpace
```

## 参数

- **name**：标识坐标空间的唯一值。

## 返回值

由给定值标识的已命名坐标空间。

## 讨论

使用`coordinateSpace(_:)`修饰符为父视图的本地坐标空间指定名称。子视图可以使用 `.named(_:)` 引用该坐标空间。

## 获取内置坐标空间

- **immersiveSpace**：已命名的坐标空间，代表当前打开的[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景。如果当前没有打开沉浸式空间，该坐标空间将提供与`.global`坐标空间相同的行为。
- **global**：位于视图层次结构根部的全局坐标空间。
- **local**：当前视图的局部坐标空间：当前视图的局部坐标空间。
- **scrollView**：当前视图的局部坐标空间：系统为包含滚动视图的最内层添加的已命名坐标空间。
- **scrollView(axis:)**：系统为包含滚动视图的最内层添加的已命名坐标空间，允许沿提供的轴滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/named(_:)
crawled: 2025-12-03T06:33:47Z
---

# named(_:)

**Type Method**

Creates a named coordinate space using the given value.

## Declaration

```swift
static func named(_ name: some Hashable) -> NamedCoordinateSpace
```

## Parameters

- **name**: A unique value that identifies the coordinate space.

## Return Value

A named coordinate space identified by the given value.

## Discussion

Use the `coordinateSpace(_:)` modifier to assign a name to the local coordinate space of a  parent view. Child views can then refer to that coordinate space using `.named(_:)`.

## Getting built-in coordinate spaces

- **immersiveSpace**: The named coordinate space that represents the currently opened [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene. If no immersive space is currently opened, this CoordinateSpace provides the same behavior as the `.global` coordinate space.
- **global**: The global coordinate space at the root of the view hierarchy.
- **local**: The local coordinate space of the current view.
- **scrollView**: The named coordinate space that is added by the system for the innermost containing scroll view.
- **scrollView(axis:)**: The named coordinate space that is added by the system for the innermost containing scroll view that allows scrolling along the provided axis.

