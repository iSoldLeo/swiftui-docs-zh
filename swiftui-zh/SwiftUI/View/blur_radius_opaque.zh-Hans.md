--- 来源：https://developer.apple.com/documentation/SwiftUI/View/blur(radius:opaque:)

抓取时间：2025-11-30T21:22:29Z

---

# blur(radius:opaque:)

**实例方法**

对当前视图应用高斯模糊。

## 声明

```swift
nonisolated func blur(radius: CGFloat, opaque: Bool = false) -> some View

```

## 参数

- **radius**：模糊的径向大小。半径越大，模糊效果越漫射。

- **opaque**：一个布尔值，指示模糊渲染器是否允许模糊输出具有透明度。设置为 `true` 创建不透明模糊，设置为 `false` 允许透明度。

## 讨论

使用 `blur(radius:opaque:)` 可对本视图的渲染应用高斯模糊效果。

以下示例展示了两个 [Text](../Text.zh-Hans.md) 视图，第一个视图未应用模糊效果，第二个视图应用了 `blur(radius:opaque:)`，并将 `radius` 的值设置为 `2`。半径越大，模糊效果越明显。

```swift
struct Blur: View {
    var body: some View {
        VStack {
            Text("This is some text.")
                .padding()
            Text("This is some blurry text.")
                .blur(radius: 2.0)
        }
    }
}
```

## 应用模糊和阴影

- **shadow(color:radius:x:y:)**：为本视图添加阴影。

- **ColorMatrix**：用于 RGBA 颜色变换的矩阵。


---
source: https://developer.apple.com/documentation/SwiftUI/View/blur(radius:opaque:)
crawled: 2025-11-30T21:22:29Z
---

# blur(radius:opaque:)

**Instance Method**

Applies a Gaussian blur to this view.

## Declaration

```swift
nonisolated func blur(radius: CGFloat, opaque: Bool = false) -> some View

```

## Parameters

- **radius**: The radial size of the blur. A blur is more diffuse when its radius is large.
- **opaque**: A Boolean value that indicates whether the blur renderer permits transparency in the blur output. Set to `true` to create an opaque blur, or set to `false` to permit transparency.

## Discussion

Use `blur(radius:opaque:)` to apply a gaussian blur effect to the rendering of this view.

The example below shows two [Text](../Text.zh-Hans.md) views, the first with no blur effects, the second with `blur(radius:opaque:)` applied with the `radius` set to `2`. The larger the radius, the more diffuse the effect.

```swift
struct Blur: View {
    var body: some View {
        VStack {
            Text("This is some text.")
                .padding()
            Text("This is some blurry text.")
                .blur(radius: 2.0)
        }
    }
}
```



## Applying blur and shadows

- **shadow(color:radius:x:y:)**: Adds a shadow to this view.
- **ColorMatrix**: A matrix to use in an RGBA color transformation.

