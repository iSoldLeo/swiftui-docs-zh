--- 来源：https://developer.apple.com/documentation/swiftui/namespace
抓取时间：2025-12-04T13:16:07Z

---

# 命名空间

**Structure**

一种动态属性类型，允许访问由包含该属性的对象（例如视图）的持久标识定义的命名空间。

## 声明

```swift
@frozen @propertyWrapper struct Namespace
```

## 创建命名空间

- **init()**

## 获取命名空间

- **wrappedValue**

- **Namespace.ID**：由动态属性的持久标识定义的命名空间。`@Namespace`

## 同步几何体

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何体的视图。

- **MatchedGeometryProperties**：一组视图属性，可以使用 `View.matchedGeometryEffect()` 函数在视图之间同步这些属性。

- **GeometryEffect**：一种改变视图视觉外观的效果，基本不会改变其父视图或子视图。

- **geometryGroup()**：将视图的几何体（例如位置和大小）与其父视图隔离。

## 符合以下规范

- BitwiseCopyable

- Copyable

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/namespace
crawled: 2025-12-04T13:16:07Z
---

# Namespace

**Structure**

A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).

## Declaration

```swift
@frozen @propertyWrapper struct Namespace
```

## Creating a namespace

- **init()**

## Getting the namespace

- **wrappedValue**
- **Namespace.ID**: A namespace defined by the persistent identity of an `@Namespace` dynamic property.

## Synchronizing geometries

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **MatchedGeometryProperties**: A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.
- **GeometryEffect**: An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

## Conforms To

- BitwiseCopyable
- Copyable
- DynamicProperty
- Sendable
- SendableMetatype

