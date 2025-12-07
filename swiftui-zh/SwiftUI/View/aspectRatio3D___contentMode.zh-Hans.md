--- 来源：https://developer.apple.com/documentation/SwiftUI/View/aspectRatio3D(_:contentMode:)

抓取时间：2025-11-30T21:07:35Z

---

# aspectRatio3D(_:contentMode:)

**实例方法**

将此视图的尺寸限制为指定的 3D 纵横比。

## 声明

```swift
nonisolated func aspectRatio3D(_ aspectRatio: Size3D? = nil, contentMode: ContentMode) -> some View

```

## 参数

- **aspectRatio**：用于生成视图的宽度、高度和深度的比率。如果 `aspectRatio` 为 `nil`，则生成的视图将保持此视图的纵横比。

- **contentMode**：一个标志，指示此视图应适应父上下文还是填充父上下文。

## 返回值

返回一个视图，该视图的尺寸被限制在 `aspectRatio` 范围内，并使用 `contentMode` 作为缩放算法。

## 说明

如果此视图可调整大小，则生成的视图的纵横比将为 `aspectRatio`。在本例中，Model3D 的宽高比为 2:3:1，并缩放以适应其框架：

```swift
Model3D(named: "Sphere") { resolved in
    let ratio3D = Size3D(width: 2, height: 3, depth: 1)
    resolved
        .resizable()
        .aspectRatio3D(ratio3D, contentMode: .fit)
} placeholder: {
    ProgressView()
}
.frame(width: 200, height: 200)
.frame(depth: 200)
.border(Color(white: 0.75))
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/aspectRatio3D(_:contentMode:)
crawled: 2025-11-30T21:07:35Z
---

# aspectRatio3D(_:contentMode:)

**Instance Method**

Constrains this view’s dimensions to the specified 3D aspect ratio.

## Declaration

```swift
nonisolated func aspectRatio3D(_ aspectRatio: Size3D? = nil, contentMode: ContentMode) -> some View

```

## Parameters

- **aspectRatio**: The ratio of width to height to depth to use for the resulting view. If `aspectRatio` is `nil`, the resulting view maintains this view’s aspect ratio.
- **contentMode**: A flag indicating whether this view should fit or fill the parent context.

## Return Value

A view that constrains this view’s dimensions to `aspectRatio`, using `contentMode` as its scaling algorithm.

## Discussion

If this view is resizable, the resulting view will have `aspectRatio` as its aspect ratio. In this example, the Model3D has a 2 : 3 : 1 width to height to depth ratio, and scales to fit its frame:

```swift
Model3D(named: "Sphere") { resolved in
    let ratio3D = Size3D(width: 2, height: 3, depth: 1)
    resolved
        .resizable()
        .aspectRatio3D(ratio3D, contentMode: .fit)
} placeholder: {
    ProgressView()
}
.frame(width: 200, height: 200)
.frame(depth: 200)
.border(Color(white: 0.75))
```

