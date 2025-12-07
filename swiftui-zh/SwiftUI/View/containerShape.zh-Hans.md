--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerShape(_:)

抓取时间：2025-12-02T17:36:47Z

---

# containerShape(_:)

**实例方法**

设置此视图中任何容器相对形状或同心矩形所使用的容器形状。

## 声明

```swift
nonisolated func containerShape(_ shape: some RoundedRectangularShape) -> some View

```

## 说明

以下示例定义了一个视图，该视图使用圆角矩形背景和相同的容器形状来显示其内容。`content` 内的任何 [ContainerRelativeShape](../ContainerRelativeShape.zh-Hans.md) 都将根据此容器内边距匹配相应的圆角矩形形状。`content` 内的任何 [ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) 都将匹配与容器角同心的角。

```swift
struct PlatterContainer<Content: View> : View {
    @ViewBuilder var content: Content
    var body: some View {
        content
            .padding()
            .containerShape(shape)
            .background(shape.fill(.background))
    }
    var shape: RoundedRectangle { RoundedRectangle(cornerRadius: 20) }
}
```

## 设置容器形状

- **InsettableShape**：一种能够内嵌自身以生成其他形状的形状类型。

- **ContainerRelativeShape**：一种会被当前容器形状的内嵌版本替换的形状。如果未定义容器形状，则会被替换为矩形。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerShape(_:)
crawled: 2025-12-02T17:36:47Z
---

# containerShape(_:)

**Instance Method**

Sets the container shape to use for any container relative shape or concentric rectangle within this view.

## Declaration

```swift
nonisolated func containerShape(_ shape: some RoundedRectangularShape) -> some View

```

## Discussion

The example below defines a view that shows its content with a rounded rectangle background and the same container shape. Any [ContainerRelativeShape](../ContainerRelativeShape.zh-Hans.md) within the `content` matches the rounded rectangle shape from this container inset as appropriate. Any [ConcentricRectangle](../ConcentricRectangle.zh-Hans.md) within the `content` will match the corners to be concentric to the container corners.

```swift
struct PlatterContainer<Content: View> : View {
    @ViewBuilder var content: Content
    var body: some View {
        content
            .padding()
            .containerShape(shape)
            .background(shape.fill(.background))
    }
    var shape: RoundedRectangle { RoundedRectangle(cornerRadius: 20) }
}
```



## Setting a container shape

- **InsettableShape**: A shape type that is able to inset itself to produce another shape.
- **ContainerRelativeShape**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.

