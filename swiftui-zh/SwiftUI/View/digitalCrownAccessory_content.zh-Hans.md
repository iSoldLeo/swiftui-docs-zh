--- 来源：https://developer.apple.com/documentation/SwiftUI/View/digitalCrownAccessory(content:)

抓取时间：2025-12-02T17:42:20Z

---

# digitalCrownAccessory(content:)

**实例方法**

在 Apple Watch 的数码表冠旁边放置一个配件视图。

## 声明

```swift
nonisolated func digitalCrownAccessory<Content>(@ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## 参数

- **content**：用作数码表冠配件的视图。

## 说明

使用此方法在 Apple Watch 的数码表冠旁边放置一个自定义的 `View` 视图。使用 [digitalCrownAccessory(_:)](digitalCrownAccessory.zh-Hans.md) 指定自定义视图的可见性。

```swift
struct ZoomingMapView: View {
    // Width of the map displayed on screen in miles
    @State private var zoomLevel: Int = 1.0

    var body: some View {
        CustomMap(width: .miles(zoomLevel))
            .focusable()
            .digitalCrownRotation(value: $zoomLevel)
            .digitalCrownAccessory {
                Text("\(zoomLevel, specifier: "%.2f")MI")
                .background {
                    RoundedRectangle(cornerRadius: 5)
                        .fill(Color.gray)
                }
            }
    }
}
```

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：将数码表冠旋转至两个整数之间所需的角度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/digitalCrownAccessory(content:)
crawled: 2025-12-02T17:42:20Z
---

# digitalCrownAccessory(content:)

**Instance Method**

Places an accessory View next to the Digital Crown on Apple Watch.

## Declaration

```swift
nonisolated func digitalCrownAccessory<Content>(@ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## Parameters

- **content**: The view to be used as a Digital Crown Accessory.

## Discussion

Use this method to place a custom `View` next to the Digital Crown on Apple Watch. Use [digitalCrownAccessory(_:)](digitalCrownAccessory.zh-Hans.md) to specify the visibility of your custom view.

```swift
struct ZoomingMapView: View {
    // Width of the map displayed on screen in miles
    @State private var zoomLevel: Int = 1.0

    var body: some View {
        CustomMap(width: .miles(zoomLevel))
            .focusable()
            .digitalCrownRotation(value: $zoomLevel)
            .digitalCrownAccessory {
                Text("\(zoomLevel, specifier: "%.2f")MI")
                .background {
                    RoundedRectangle(cornerRadius: 5)
                        .fill(Color.gray)
                }
            }
    }
}
```

## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

