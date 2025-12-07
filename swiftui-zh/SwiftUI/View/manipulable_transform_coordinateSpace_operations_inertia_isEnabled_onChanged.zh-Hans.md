--- 来源：https://developer.apple.com/documentation/SwiftUI/View/manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)

抓取时间：2025-11-30T21:09:36Z

---

# manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)

**实例方法**

将给定的 3D 仿射变换应用于视图，并允许使用常见的手势对其进行操作。

## 声明

```swift
nonisolated func manipulable(transform: Binding<AffineTransform3D>, coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## 参数

- **transform**：绑定到应用于视图的 3D 仿射变换，并在用户操作此视图时更新。

- **coordinateSpace**：操作手势事件位置的坐标空间。

- **operations**：用户操作此视图时可执行的操作集合。

- **inertia**：此视图的惯性，定义了其抵抗操作的程度。

- **isEnabled**：布尔值，指示此视图修改器添加的操作手势是否已启用。

- **onChanged**：每次发生新的操作手势事件时要执行的操作。

## 返回值

应用了 3D 仿射变换且可以使用常用手势进行操作的视图。

## 说明

当用户结束操作手势时，视图将保持其变换状态，但您也可以在手势处于非活动状态时以编程方式修改它。

在以下示例中，当用户停止操作视图时，视图将淡出，然后以未修改的变换淡入到其原始位置：

```swift
struct FadeOutOnReleaseView: View {
    @State private var transform: AffineTransform3D = .identity
    @State private var opacity: CGFloat = 1

    var body: some View {
        Circle()
            .manipulable(transform: $transform) { event in
                switch event.phase {
                case .ended(let value):
                    withAnimation {
                        opacity = 0
                    } completion: {
                        transform = .identity
                        withAnimation { opacity = 1 }
                    }
                default:
                    break
                }
            }
            .opacity(opacity)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)
crawled: 2025-11-30T21:09:36Z
---

# manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)

**Instance Method**

Applies the given 3D affine transform to the view and allows it to be manipulated using common hand gestures.

## Declaration

```swift
nonisolated func manipulable(transform: Binding<AffineTransform3D>, coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## Parameters

- **transform**: The binding to a 3D affine transform applied to the view and updated when a person is manipulating this view.
- **coordinateSpace**: The coordinate space of the manipulation gesture event locations.
- **operations**: The set of allowed operations that can be applied when a person manipulates this view.
- **inertia**: The inertia of this view that defines how much it resists being manipulated.
- **isEnabled**: The Boolean value that indicates whether the manipulation gesture added by this view modifier is enabled or not.
- **onChanged**: The action to perform with each new manipulation gesture event.

## Return Value

A view with a 3D affine transform applied and that can be manipulated using common hand gestures.

## Discussion

When a person ends the manipulation gesture, the view will maintain its transform but you may also modify it programmatically when the gesture is inactive.

In the following example, when a person ends manipulating the view, it will fade out and fade in again in its original location and unmodified transform:

```swift
struct FadeOutOnReleaseView: View {
    @State private var transform: AffineTransform3D = .identity
    @State private var opacity: CGFloat = 1

    var body: some View {
        Circle()
            .manipulable(transform: $transform) { event in
                switch event.phase {
                case .ended(let value):
                    withAnimation {
                        opacity = 0
                    } completion: {
                        transform = .identity
                        withAnimation { opacity = 1 }
                    }
                default:
                    break
                }
            }
            .opacity(opacity)
        }
    }
}
```

