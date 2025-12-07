--- 来源：https://developer.apple.com/documentation/SwiftUI/View/backgroundStyle(_:)

抓取时间：2025-11-30T21:21:56Z

---

# backgroundStyle(_:)

**实例方法**

设置指定的样式以渲染视图中的背景。

## 声明

```swift
nonisolated func backgroundStyle<S>(_ style: S) -> some View where S : ShapeStyle

```

## 说明

以下示例使用此修饰符将 [backgroundStyle](../EnvironmentValues/backgroundStyle.zh-Hans.md) 环境值设置为包含细微的 [blue](../ShapeStyle/blue.zh-Hans.md) 颜色。 SwiftUI 会使用以下样式填充作为背景元素的 [Circle](../Circle.zh-Hans.md) 形状：

```swift
Image(systemName: "swift")
    .padding()
    .background(in: Circle())
    .backgroundStyle(.blue.gradient)
```

要恢复默认背景样式，请使用 [environment(_:_:)](environment.zh-Hans.md) 修饰符将 [backgroundStyle](../EnvironmentValues/backgroundStyle.zh-Hans.md) 环境值设置为 `nil`：

```swift
.environment(\.backgroundStyle, nil)
```

## 设置内容样式

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。

- **foregroundStyle(_:)**：设置视图的前景色元素使用给定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的主级别和次级别。

- **foregroundStyle(_:_:_:)**：设置前景样式的主色、次色和三级色。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **ShapeStyle**：渲染形状时使用的颜色或图案。

- **AnyShapeStyle**：已擦除的 ShapeStyle 值。

- **Gradient**：颜色渐变，表示为颜色停止点数组，每个停止点都有一个参数化的位置值。

- **MeshGradient**：由二维定位颜色网格定义的二维渐变。

- **AnyGradient**：颜色渐变。

- **ShadowStyle**：渲染阴影时使用的样式。

- **Glass**：定义液态玻璃材料结构的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/View/backgroundStyle(_:)
crawled: 2025-11-30T21:21:56Z
---

# backgroundStyle(_:)

**Instance Method**

Sets the specified style to render backgrounds within the view.

## Declaration

```swift
nonisolated func backgroundStyle<S>(_ style: S) -> some View where S : ShapeStyle

```

## Discussion

The following example uses this modifier to set the [backgroundStyle](../EnvironmentValues/backgroundStyle.zh-Hans.md) environment value to a [blue](../ShapeStyle/blue.zh-Hans.md) color that includes a subtle [gradient](../Color/gradient.zh-Hans.md). SwiftUI fills the [Circle](../Circle.zh-Hans.md) shape that acts as a background element with this style:

```swift
Image(systemName: "swift")
    .padding()
    .background(in: Circle())
    .backgroundStyle(.blue.gradient)
```



To restore the default background style, set the [backgroundStyle](../EnvironmentValues/backgroundStyle.zh-Hans.md) environment value to `nil` using the [environment(_:_:)](environment.zh-Hans.md) modifer:

```swift
.environment(\.backgroundStyle, nil)
```

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

