--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationDetents(_:selection:)

抓取时间：2025-12-02T17:30:15Z

---

# presentationDetents(_:selection:)

**实例方法**

设置包含视图的可用定位点，使您可以通过编程方式控制当前选中的定位点。

## 声明

```swift
nonisolated func presentationDetents(_ detents: Set<PresentationDetent>, selection: Binding<PresentationDetent>) -> some View

```

## 参数

- **detents**：视图支持的定位点集合。如果您提供多个定位点，用户可以拖动视图来调整其大小。

- **selection**：指向当前选中定位点的 [Binding](../Binding.zh-Hans.md)。请确保该值与您为 `detents` 参数提供的某个定位点相匹配。

## 讨论

默认情况下，工作表支持 [large](../PresentationDetent/large.zh-Hans.md) 定位点。

```swift
struct ContentView: View {
    @State private var showSettings = false
    @State private var settingsDetent = PresentationDetent.medium

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents(
                    [.medium, .large],
                    selection: $settingsDetent
                 )
        }
    }
}
```

## 配置工作表高度

- **presentationDetents(_:)**：设置包含工作表的可用定位点。

- **presentationContentInteraction(_:)**：配置演示文稿中滑动操作的行为。

- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。

- **PresentationDetent**：表示工作表自然放置高度的类型。

- **CustomPresentationDetent**：定义具有计算高度的自定义定位点。 - **PresentationContentInteraction**：一种可用于控制演示文稿对滑动操作响应方式的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationDetents(_:selection:)
crawled: 2025-12-02T17:30:15Z
---

# presentationDetents(_:selection:)

**Instance Method**

Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.

## Declaration

```swift
nonisolated func presentationDetents(_ detents: Set<PresentationDetent>, selection: Binding<PresentationDetent>) -> some View

```

## Parameters

- **detents**: A set of supported detents for the sheet. If you provide more that one detent, people can drag the sheet to resize it.
- **selection**: A [Binding](../Binding.zh-Hans.md) to the currently selected detent. Ensure that the value matches one of the detents that you provide for the `detents` parameter.

## Discussion

By default, sheets support the [large](../PresentationDetent/large.zh-Hans.md) detent.

```swift
struct ContentView: View {
    @State private var showSettings = false
    @State private var settingsDetent = PresentationDetent.medium

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents(
                    [.medium, .large],
                    selection: $settingsDetent
                 )
        }
    }
}
```

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

