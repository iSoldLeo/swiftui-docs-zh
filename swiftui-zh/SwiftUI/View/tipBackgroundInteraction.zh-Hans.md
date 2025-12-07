--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tipBackgroundInteraction(_:)

抓取时间：2025-12-02T17:26:08Z

---

# tipBackgroundInteraction(_:)

**实例方法**

控制用户是否可以与弹出提示背后的视图进行交互。

## 声明

```swift
nonisolated func tipBackgroundInteraction(_ interaction: PresentationBackgroundInteraction) -> some View

```

## 参数

- **interaction**：指定用户如何与弹出提示背后的视图进行交互。

### 讨论

在许多平台上，SwiftUI 会自动禁用弹出提示背后的视图，因此用户在关闭提示之前无法与该视图进行交互。如果您希望启用交互，请使用此修饰符。

以下示例允许用户与 `popoverTip` 背后的视图进行交互。

```swift
struct LandmarkDetail: View {
    let landmark: Landmark

    var body: some View {
        ScrollView {
            MapView(coordinate: landmark.locationCoordinate)
                .popoverTip(CampsiteTip())
                .tipBackgroundInteraction(.enabled)

            HStack {
                Text(landmark.name)
                Text(landmark.park)
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/tipBackgroundInteraction(_:)
crawled: 2025-12-02T17:26:08Z
---

# tipBackgroundInteraction(_:)

**Instance Method**

Controls whether people can interact with the view behind a presented tip.

## Declaration

```swift
nonisolated func tipBackgroundInteraction(_ interaction: PresentationBackgroundInteraction) -> some View

```

## Parameters

- **interaction**: A specification of how people can interact with the view behind a presented tip.

### Discussion

On many platforms, SwiftUI automatically disables the view behind a popover tip that you present, so that people can’t interact with the backing view until they dismiss the tip. Use this modifier if you want to enable interaction.

The following example enables people to interact with the view behind a `popoverTip`.

```swift
struct LandmarkDetail: View {
    let landmark: Landmark

    var body: some View {
        ScrollView {
            MapView(coordinate: landmark.locationCoordinate)
                .popoverTip(CampsiteTip())
                .tipBackgroundInteraction(.enabled)

            HStack {
                Text(landmark.name)
                Text(landmark.park)
            }
        }
    }
}
```

