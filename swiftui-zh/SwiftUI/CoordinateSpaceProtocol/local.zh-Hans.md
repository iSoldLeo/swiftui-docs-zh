---
来源： https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/local
抓取时间： 2025-12-03T06:33:47Z
---

# 本地

**类型属性**

当前视图的本地坐标空间。

## 声明

```swift
static var local: LocalCoordinateSpace { get }
```

## 获取内置坐标空间

- **immersiveSpace**：已命名的坐标空间，代表当前打开的[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景。如果当前没有打开沉浸式空间，该坐标空间将提供与 `.global` 坐标空间相同的行为。
- **global**：位于视图层次结构根部的全局坐标空间。
- **named(_:)**：使用给定值创建命名坐标空间。
- **scrollView**：系统为包含滚动视图的最内层添加的已命名坐标空间。
- **scrollView(axis:)**：系统为包含滚动视图的最内层添加的已命名坐标空间，允许沿提供的轴滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/local
crawled: 2025-12-03T06:33:47Z
---

# local

**Type Property**

The local coordinate space of the current view.

## Declaration

```swift
static var local: LocalCoordinateSpace { get }
```

## Getting built-in coordinate spaces

- **immersiveSpace**: The named coordinate space that represents the currently opened [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene. If no immersive space is currently opened, this CoordinateSpace provides the same behavior as the `.global` coordinate space.
- **global**: The global coordinate space at the root of the view hierarchy.
- **named(_:)**: Creates a named coordinate space using the given value.
- **scrollView**: The named coordinate space that is added by the system for the innermost containing scroll view.
- **scrollView(axis:)**: The named coordinate space that is added by the system for the innermost containing scroll view that allows scrolling along the provided axis.

