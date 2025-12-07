---
来源： https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/scrollView(axis:)
抓取时间：2025-12-01T11:22:58Z
---

# scrollView(axis:)

**类型方法**

系统为最内层的滚动视图添加的指定坐标空间，该视图允许沿提供的轴滚动。

## 声明

```swift
static func scrollView(axis: Axis) -> Self
```

## 获取内置坐标空间

- **immersiveSpace**：已命名的坐标空间，代表当前打开的[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景。如果当前没有打开沉浸式空间，该坐标空间将提供与 `.global` 坐标空间相同的行为。
- **global**：位于视图层次结构根部的全局坐标空间。
- **local**：当前视图的局部坐标空间：当前视图的局部坐标空间。
- **named(_:)**：当前视图的局部坐标空间：使用给定值创建命名坐标空间。
- **scrollView**：系统为包含滚动视图的最内层添加的已命名坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/scrollView(axis:)
crawled: 2025-12-01T11:22:58Z
---

# scrollView(axis:)

**Type Method**

The named coordinate space that is added by the system for the innermost containing scroll view that allows scrolling along the provided axis.

## Declaration

```swift
static func scrollView(axis: Axis) -> Self
```

## Getting built-in coordinate spaces

- **immersiveSpace**: The named coordinate space that represents the currently opened [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene. If no immersive space is currently opened, this CoordinateSpace provides the same behavior as the `.global` coordinate space.
- **global**: The global coordinate space at the root of the view hierarchy.
- **local**: The local coordinate space of the current view.
- **named(_:)**: Creates a named coordinate space using the given value.
- **scrollView**: The named coordinate space that is added by the system for the innermost containing scroll view.

