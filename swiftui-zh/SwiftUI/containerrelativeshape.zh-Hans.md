--- 来源：https://developer.apple.com/documentation/swiftui/containerrelativeshape
抓取时间：2025-12-04T11:34:00Z

---

# ContainerRelativeShape

**Structure**

一种形状，会被替换为当前容器形状的内嵌版本。如果未定义容器形状，则会被替换为矩形。

## 声明

```swift
@frozen struct ContainerRelativeShape
```

## 创建形状

- **init()**

## 设置容器形状

- **containerShape(_:)**：设置此视图中任何容器相对形状或同心矩形所使用的容器形状。

- **InsettableShape**：一种能够内嵌自身以生成其他形状的形状类型。

## 符合以下特性

- 可动画

- 可按位复制

- 可复制

- 可插入形状

- 可发送

- 可发送元类型

- 形状

- 视图


---
source: https://developer.apple.com/documentation/swiftui/containerrelativeshape
crawled: 2025-12-04T11:34:00Z
---

# ContainerRelativeShape

**Structure**

A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.

## Declaration

```swift
@frozen struct ContainerRelativeShape
```

## Creating the shape

- **init()**

## Setting a container shape

- **containerShape(_:)**: Sets the container shape to use for any container relative shape or concentric rectangle within this view.
- **InsettableShape**: A shape type that is able to inset itself to produce another shape.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- InsettableShape
- Sendable
- SendableMetatype
- Shape
- View

