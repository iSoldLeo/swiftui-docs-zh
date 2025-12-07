--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationCompactAdaptation(_:)

抓取时间：2025-11-30T21:15:09Z

---

# presentationCompactAdaptation(_:)

**实例方法**

指定如何将演示文稿适配到紧凑尺寸类别。

## 声明

```swift
nonisolated func presentationCompactAdaptation(_ adaptation: PresentationAdaptation) -> some View

```

## 参数

- **adaptation**：用于水平或垂直紧凑尺寸类别的适配方式。

## 说明

某些演示文稿会根据上下文调整其外观。例如，在垂直紧凑视图上显示的表格演示文稿默认使用全屏覆盖外观。使用此修饰符可以指定自定义的适配偏好。例如，以下代码使用演示调整值 [none](../PresentationAdaptation/none.zh-Hans.md) 来请求系统不要在紧凑尺寸类别中调整工作表：

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
                .presentationCompactAdaptation(.none)
        }
    }
}
```

如果要为每个维度指定不同的调整，请改用 [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) 方法。

## 调整演示尺寸

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示调整为水平和垂直的紧凑尺寸类别。

- **PresentationAdaptation**：将演示调整为不同尺寸类别的策略。

- **presentationSizing(_:)**：设置包含演示的大小。

- **PresentationSizing**：定义演示内容的大小以及演示大小如何根据其内容大小的变化进行调整的类型。

- **PresentationSizingRoot**：为演示文稿提供的视图代理，该视图具有已定义的演示文稿大小。

- **PresentationSizingContext**：关于演示文稿的上下文信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationCompactAdaptation(_:)
crawled: 2025-11-30T21:15:09Z
---

# presentationCompactAdaptation(_:)

**Instance Method**

Specifies how to adapt a presentation to compact size classes.

## Declaration

```swift
nonisolated func presentationCompactAdaptation(_ adaptation: PresentationAdaptation) -> some View

```

## Parameters

- **adaptation**: The adaptation to use in either a horizontally or vertically compact size class.

## Discussion

Some presentations adapt their appearance depending on the context. For example, a sheet presentation over a vertically-compact view uses a full-screen-cover appearance by default. Use this modifier to indicate a custom adaptation preference. For example, the following code uses a presentation adaptation value of [none](../PresentationAdaptation/none.zh-Hans.md) to request that the system not adapt the sheet in compact size classes:

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
                .presentationCompactAdaptation(.none)
        }
    }
}
```

If you want to specify different adaptations for each dimension, use the [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) method instead.

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

