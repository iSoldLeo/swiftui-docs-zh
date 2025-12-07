---
来源： https://developer.apple.com/documentation/SwiftUI/MatchedGeometryProperties
抓取时间： 2025-12-02T17:34:16Z
---

# 匹配的几何属性

**Structure**

一组视图属性，可使用 `View.matchedGeometryEffect()` 函数在不同视图之间同步。

## 声明

```swift
@frozen struct MatchedGeometryProperties
```

## 匹配属性

- **frame**：`position` 和 `size` 属性。
- **position**：视图的位置，以窗口坐标表示。
- **size**：视图的大小，以本地坐标表示。

## 同步几何图形

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何图形的视图。
- **GeometryEffect**：一种改变视图视觉外观的效果，基本上不改变其祖先或后代。
- **Namespace**：一种动态属性类型，允许访问由包含该属性的对象（如视图）的持久标识所定义的命名空间。
- **geometryGroup()**：将视图的几何图形（如位置和大小）与其父视图隔离。

## 符合

- 比特可复制
- 可复制
- 等价
- 可表达数组原型
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/MatchedGeometryProperties
crawled: 2025-12-02T17:34:16Z
---

# MatchedGeometryProperties

**Structure**

A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.

## Declaration

```swift
@frozen struct MatchedGeometryProperties
```

## Matching properties

- **frame**: Both the `position` and `size` properties.
- **position**: The view’s position, in window coordinates.
- **size**: The view’s size, in local coordinates.

## Synchronizing geometries

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **GeometryEffect**: An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.
- **Namespace**: A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

