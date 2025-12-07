--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scaledToFit3D()

抓取时间：2025-12-02T17:25:16Z

---

# scaledToFit3D()

**实例方法**

缩放此视图以适应其父视图。

## 声明

```swift
nonisolated func scaledToFit3D() -> some View

```

## 返回值

返回一个缩放此视图以适应其父视图的视图，并保持此视图的纵横比。

## 说明

此视图的 3D 纵横比在缩放过程中保持不变。此方法等效于调用 `aspectRatio3D(nil, contentMode: .fit)`。

```swift
Model3D(named: "Plane") { resolved in
    resolved
        .resizable()
        .scaledToFit3D()
} placeholder: {
    ProgressView()
}
.frame(width: 400, height: 400)
.frame(depth: 200)
.border(Color(white: 0.75))
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/scaledToFit3D()
crawled: 2025-12-02T17:25:16Z
---

# scaledToFit3D()

**Instance Method**

Scales this view to fit its parent.

## Declaration

```swift
nonisolated func scaledToFit3D() -> some View

```

## Return Value

A view that scales this view to fit its parent, maintaining this view’s aspect ratio.

## Discussion

This view’s 3D aspect ratio is maintained as the view scales. This method is equivalent to calling `aspectRatio3D(nil, contentMode: .fit)`.

```swift
Model3D(named: "Plane") { resolved in
    resolved
        .resizable()
        .scaledToFit3D()
} placeholder: {
    ProgressView()
}
.frame(width: 400, height: 400)
.frame(depth: 200)
.border(Color(white: 0.75))
```

