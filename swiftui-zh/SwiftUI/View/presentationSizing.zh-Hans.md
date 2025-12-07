--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationSizing(_:)

抓取时间：2025-12-02T17:30:11Z

---

# presentationSizing(_:)

**实例方法**

设置包含的演示文稿的大小。

## 声明

```swift
nonisolated func presentationSizing(_ sizing: some PresentationSizing) -> some View

```

## 参数

- **sizing**：一个值，用于指定建议给演示文稿内容的大小，以及演示文稿如何响应内容大小的变化。

## 说明

使用此修饰符可以将 [PresentationSizing](../PresentationSizing.zh-Hans.md) 应用于类似 [sheet(isPresented:onDismiss:content:)](sheet_isPresented_onDismiss_content.zh-Hans.md) 的演示文稿。`sizing` 参数定义了建议给内容的大小，演示文稿会采用返回的大小。默认值为 `automatic`。

可以根据内容调整尺寸，并可选择设置垂直固定。

例如，包含花卉知识的演示文稿可能更适合使用 `.page` 尺寸，因为其内容主要以信息为主。由于用户可以从选择器中选择不同的花卉，每种花卉的信息长度也不同，因此尺寸会垂直调整以适应文本内容，并设置垂直固定以防止演示文稿在用户更改选择时频繁改变尺寸。

```swift
struct ContentView: View {
    @State private var presentInfo = true

    var body: some View {
        ContentView.sheet(isPresented: $presentInfo) {
            VStack {
                Picker("Flower Species", selection: $flower) {
                    ForEach(Flower.allCases) {
                        Text($0.rawValue.uppercased()).tag($0)
                    }
                }
                Text(flower.emoji).font(.largeTitle)
                Text(flower.informationalText)
            }
            .frame(maxHeight: .infinity, alignment: .top)
            .padding()
            .presentationSizing(
                .page
                    .fitted(horizontal: false, vertical: true)
                    .sticky(horizontal: false, vertical: true))
        }
    }
}
```

## 调整演示文稿尺寸

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸类别。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类别。

- **PresentationAdaptation**：用于将演示文稿调整为不同尺寸类别的策略。

- **PresentationSizing**：定义演示文稿内容大小以及演示文稿大小如何随内容大小变化而调整的类型。

- **PresentationSizingRoot**：为演示文稿提供的具有已定义演示文稿大小的视图代理。

- **PresentationSizingContext**：关于演示文稿的上下文信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationSizing(_:)
crawled: 2025-12-02T17:30:11Z
---

# presentationSizing(_:)

**Instance Method**

Sets the sizing of the containing presentation.

## Declaration

```swift
nonisolated func presentationSizing(_ sizing: some PresentationSizing) -> some View

```

## Parameters

- **sizing**: A value dictating size to propose to presentation content and how the presentation responds to changes in content size.

## Discussion

Use this modifier to apply a [PresentationSizing](../PresentationSizing.zh-Hans.md) to a presentation like [sheet(isPresented:onDismiss:content:)](sheet_isPresented_onDismiss_content.zh-Hans.md). The `sizing` parameter defines the size proposed to the content, and the presentation adopts the returned size. The default value is `automatic`.

Sizings can be modified to fix their dimensions based on the content, and optionally be sticky.





For example, a presentation with facts about flowers could prefer `.page` sizing because its content is primarily informational. Since the user can choose different flowers from the picker, each with different lengths of information, the size is fitted vertically to size the sheet to the textual content, and vertically sticky is specified to prevent the presentation from changing size too frequently as the user changes selection.

```swift
struct ContentView: View {
    @State private var presentInfo = true

    var body: some View {
        ContentView.sheet(isPresented: $presentInfo) {
            VStack {
                Picker("Flower Species", selection: $flower) {
                    ForEach(Flower.allCases) {
                        Text($0.rawValue.uppercased()).tag($0)
                    }
                }
                Text(flower.emoji).font(.largeTitle)
                Text(flower.informationalText)
            }
            .frame(maxHeight: .infinity, alignment: .top)
            .padding()
            .presentationSizing(
                .page
                    .fitted(horizontal: false, vertical: true)
                    .sticky(horizontal: false, vertical: true))
        }
    }
}
```

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

