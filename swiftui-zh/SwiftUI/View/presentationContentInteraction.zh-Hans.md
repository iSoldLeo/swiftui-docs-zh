--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationContentInteraction(_:)

抓取时间：2025-12-02T17:30:16Z

---

# presentationContentInteraction(_:)

**实例方法**

配置演示文稿中滑动操作的行为。

## 声明

```swift
nonisolated func presentationContentInteraction(_ behavior: PresentationContentInteraction) -> some View

```

## 参数

- **behavior**：请求的行为。

## 说明

默认情况下，当用户在可调整大小的演示文稿中向上滑动滚动视图时，演示文稿会扩展到下一个刻度。嵌入在演示文稿中的滚动视图只有在演示文稿达到最大尺寸后才会滚动。使用此修饰符可以控制哪个操作优先。

例如，您可以请求滑动操作先滚动内容，待滚动到页面底部后再调整工作表大小，方法是将 [scrolls](../PresentationContentInteraction/scrolls.zh-Hans.md) 值传递给以下修饰符：

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
                .presentationContentInteraction(.scrolls)
        }
    }
}
```

用户始终可以使用拖动指示器调整演示文稿的大小。

## 配置工作表高度

- **presentationDetents(_:)**：设置包含工作表的可用位置。

- **presentationDetents(_:selection:)**：设置包含工作表的可用位置，允许您以编程方式控制当前选定的位置。

- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。

- **PresentationDetent**：表示工作表自然放置高度的类型。

- **CustomPresentationDetent**：自定义定位点的定义，可计算其高度。

- **PresentationContentInteraction**：可用于控制演示文稿对滑动操作响应方式的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationContentInteraction(_:)
crawled: 2025-12-02T17:30:16Z
---

# presentationContentInteraction(_:)

**Instance Method**

Configures the behavior of swipe gestures on a presentation.

## Declaration

```swift
nonisolated func presentationContentInteraction(_ behavior: PresentationContentInteraction) -> some View

```

## Parameters

- **behavior**: The requested behavior.

## Discussion

By default, when a person swipes up on a scroll view in a resizable presentation, the presentation grows to the next detent. A scroll view embedded in the presentation only scrolls after the presentation reaches its largest size. Use this modifier to control which action takes precedence.

For example, you can request that swipe gestures scroll content first, resizing the sheet only after hitting the end of the scroll view, by passing the [scrolls](../PresentationContentInteraction/scrolls.zh-Hans.md) value to this modifier:

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
                .presentationContentInteraction(.scrolls)
        }
    }
}
```

People can always resize your presentation using the drag indicator.

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

