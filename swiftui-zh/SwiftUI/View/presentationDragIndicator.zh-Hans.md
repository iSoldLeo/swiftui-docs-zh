--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationDragIndicator(_:)

抓取时间：2025-11-30T21:15:15Z

---

# presentationDragIndicator(_:)

**实例方法**

设置工作表顶部拖拽指示器的可见性。

## 声明

```swift
nonisolated func presentationDragIndicator(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：拖拽指示器的首选可见性。

## 说明

当工作表的大小调整不明显，或者无法以交互方式关闭时，可以显示拖拽指示器。

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents([.medium, .large])
                .presentationDragIndicator(.visible)
        }
    }
}
```

## 配置工作表的高度

- **presentationDetents(_:)**：设置包含工作表的可用刻度。

- **presentationDetents(_:selection:)**：设置外层纸张的可用定位点，使您可以通过编程方式控制当前选定的定位点。

- **presentationContentInteraction(_:)**：配置演示文稿中滑动操作的行为。

- **PresentationDetent**：表示纸张自然放置高度的类型。

- **CustomPresentationDetent**：定义具有计算高度的自定义定位点。

- **PresentationContentInteraction**：可用于影响演示文稿对滑动操作响应方式的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationDragIndicator(_:)
crawled: 2025-11-30T21:15:15Z
---

# presentationDragIndicator(_:)

**Instance Method**

Sets the visibility of the drag indicator on top of a sheet.

## Declaration

```swift
nonisolated func presentationDragIndicator(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The preferred visibility of the drag indicator.

## Discussion

You can show a drag indicator when it isn’t apparent that a sheet can resize or when the sheet can’t dismiss interactively.

```swift
struct ContentView: View {
    @State private var showSettings = false

    var body: some View {
        Button("View Settings") {
            showSettings = true
        }
        .sheet(isPresented: $showSettings) {
            SettingsView()
                .presentationDetents([.medium, .large])
                .presentationDragIndicator(.visible)
        }
    }
}
```

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

