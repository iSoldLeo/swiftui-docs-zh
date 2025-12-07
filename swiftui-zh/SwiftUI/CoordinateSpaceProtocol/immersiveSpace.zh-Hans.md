---
来源： https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/immersiveSpace
抓取时间： 2025-12-03T06:33:45Z
---

# 沉浸式空间

**类型属性**

已命名的坐标空间，代表当前打开的[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景。如果当前没有打开沉浸式空间，该坐标空间将提供与`.global`坐标空间相同的行为。

### 声明

```swift
static var immersiveSpace: NamedCoordinateSpace { get }
```

## 讨论

使用此功能可将变换从窗口转换到沉浸式空间。下面的示例将 Model3D 视图的顶端向后原点转换为沉浸式空间中的坐标。

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
    .onGeometryChange3D(for: AffineTransform3D.self) { proxy in
        // Convert the view's transform to the immersive space
        return proxy.transform(in: .immersiveSpace) ?? .identity
    } action: { transform in
        appModel.immersiveSpaceFromCuboid = transform
    }
}
```

然后，将其应用于沉浸式空间中的相应 Model3D。

```swift
if let transform = appModel.immersiveSpaceFromRobot {
    Model3D(url: URL(string: "https://example.com/robot.usdz")!)
        // Align the origin of this Model3D to its top-leading-back
        .visualEffect3D({ effect, proxy in
            effect
                .offset(x: proxy.size.width/2, y: proxy.size.height/2)
                .offset(z: proxy.size.depth/2)
        })
        // Apply the transform in SRT order
       .scaleEffect(transform.scale)
       .rotation3DEffect(transform.rotation ?? .identity)
       .transform3DEffect(AffineTransform3D(
           translation: transform.translation))
}
```

要应用相对于视图原点的缩放和旋转，不要同时使用 [transform3DEffect(_:)](../View/transform3deffect.zh-Hans.md) 设置它们。相反，请使用 [scaleEffect(_:anchor:)](../View/scaleEffect___anchor.zh-Hans.md) 和 [rotation3DEffect(_:anchor:)](../View/rotation3DEffect___anchor.zh-Hans.md) 分别设置它们。



## 获取内置坐标空间

- **global**：位于视图层次结构根部的全局坐标空间。
- **local**：当前视图的局部坐标空间。
- **named(_:)**：当前视图的局部坐标空间：使用给定值创建命名坐标空间。
- **scrollView**：系统为包含滚动视图的最内层添加的已命名坐标空间。
- **scrollView(axis:)**：系统为包含滚动视图的最内层添加的已命名坐标空间，允许沿提供的轴滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol/immersiveSpace
crawled: 2025-12-03T06:33:45Z
---

# immersiveSpace

**Type Property**

The named coordinate space that represents the currently opened [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene. If no immersive space is currently opened, this CoordinateSpace provides the same behavior as the `.global` coordinate space.

## Declaration

```swift
static var immersiveSpace: NamedCoordinateSpace { get }
```

## Discussion

Use this to convert transforms from a window to an immersive space. The following sample converts the top-leading-back origin of a Model3D view to coordinates in the immersive space.

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
    .onGeometryChange3D(for: AffineTransform3D.self) { proxy in
        // Convert the view's transform to the immersive space
        return proxy.transform(in: .immersiveSpace) ?? .identity
    } action: { transform in
        appModel.immersiveSpaceFromCuboid = transform
    }
}
```

Then, apply it to a corresponding Model3D in the immersive space.

```swift
if let transform = appModel.immersiveSpaceFromRobot {
    Model3D(url: URL(string: "https://example.com/robot.usdz")!)
        // Align the origin of this Model3D to its top-leading-back
        .visualEffect3D({ effect, proxy in
            effect
                .offset(x: proxy.size.width/2, y: proxy.size.height/2)
                .offset(z: proxy.size.depth/2)
        })
        // Apply the transform in SRT order
       .scaleEffect(transform.scale)
       .rotation3DEffect(transform.rotation ?? .identity)
       .transform3DEffect(AffineTransform3D(
           translation: transform.translation))
}
```

To apply scale and rotation relative to a view’s origin, don’t set them at the same time using [transform3DEffect(_:)](../View/transform3deffect.zh-Hans.md). Instead, set them separately using [scaleEffect(_:anchor:)](../View/scaleEffect___anchor.zh-Hans.md) together with [rotation3DEffect(_:anchor:)](../View/rotation3DEffect___anchor.zh-Hans.md).



## Getting built-in coordinate spaces

- **global**: The global coordinate space at the root of the view hierarchy.
- **local**: The local coordinate space of the current view.
- **named(_:)**: Creates a named coordinate space using the given value.
- **scrollView**: The named coordinate space that is added by the system for the innermost containing scroll view.
- **scrollView(axis:)**: The named coordinate space that is added by the system for the innermost containing scroll view that allows scrolling along the provided axis.

