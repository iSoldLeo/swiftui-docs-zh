--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationCompactAdaptation(horizontal:vertical:)

抓取时间：2025-11-30T21:15:08Z

---

# presentationCompactAdaptation(horizontal:vertical:)

**实例方法**

指定如何使演示文稿适应水平和垂直方向的紧凑尺寸。

## 声明

```swift
nonisolated func presentationCompactAdaptation(horizontal horizontalAdaptation: PresentationAdaptation, vertical verticalAdaptation: PresentationAdaptation) -> some View

```

## 参数

- **horizontalAdaptation**：用于水平紧凑尺寸的调整值。

- **verticalAdaptation**：用于垂直紧凑尺寸的调整值。对于同时具有水平和垂直紧凑尺寸的页面，SwiftUI 使用 `verticalAdaptation` 值。

## 讨论

某些演示文稿会根据上下文调整其外观。例如，在水平紧凑视图上弹出的演示文稿默认使用工作表外观。使用此修饰符可以指定自定义的调整首选项。

```swift
struct ContentView: View {
    @State private var showInfo = false

    var body: some View {
        Button("View Info") {
            showInfo = true
        }
        .popover(isPresented: $showInfo) {
            InfoView()
                .presentationCompactAdaptation(
                    horizontal: .popover,
                    vertical: .sheet)
        }
    }
}
```

如果要为两个维度指定相同的调整，请改用 [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) 方法。

## 调整演示文稿大小

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类别。

- **PresentationAdaptation**：将演示文稿调整为不同尺寸类别的策略。

- **presentationSizing(_:)**：设置包含演示文稿的大小。

- **PresentationSizing**：定义演示文稿内容的大小以及演示文稿大小如何根据其内容大小的变化进行调整的类型。

- **PresentationSizingRoot**：为演示文稿提供的视图代理，该视图具有已定义的演示文稿大小。

- **PresentationSizingContext**：关于演示文稿的上下文信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationCompactAdaptation(horizontal:vertical:)
crawled: 2025-11-30T21:15:08Z
---

# presentationCompactAdaptation(horizontal:vertical:)

**Instance Method**

Specifies how to adapt a presentation to horizontally and vertically compact size classes.

## Declaration

```swift
nonisolated func presentationCompactAdaptation(horizontal horizontalAdaptation: PresentationAdaptation, vertical verticalAdaptation: PresentationAdaptation) -> some View

```

## Parameters

- **horizontalAdaptation**: The adaptation to use in a horizontally compact size class.
- **verticalAdaptation**: The adaptation to use in a vertically compact size class. In a size class that is both horizontally and vertically compact, SwiftUI uses the `verticalAdaptation` value.

## Discussion

Some presentations adapt their appearance depending on the context. For example, a popover presentation over a horizontally-compact view uses a sheet appearance by default. Use this modifier to indicate a custom adaptation preference.

```swift
struct ContentView: View {
    @State private var showInfo = false

    var body: some View {
        Button("View Info") {
            showInfo = true
        }
        .popover(isPresented: $showInfo) {
            InfoView()
                .presentationCompactAdaptation(
                    horizontal: .popover,
                    vertical: .sheet)
        }
    }
}
```

If you want to specify the same adaptation for both dimensions, use the [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) method instead.

## Adapting a presentation size

- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

