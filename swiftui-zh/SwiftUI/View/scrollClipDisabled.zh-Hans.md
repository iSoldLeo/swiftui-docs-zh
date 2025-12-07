--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollClipDisabled(_:)

抓取时间：2025-12-02T16:23:38Z

---

# scrollClipDisabled(_:)

**实例方法**

设置滚动视图是否将其内容裁剪到边界内。

## 声明

```swift
nonisolated func scrollClipDisabled(_ disabled: Bool = true) -> some View

```

## 参数

- **disabled**：一个布尔值，用于指定是否禁用滚动视图裁剪。

## 返回值

一个用于禁用或启用滚动视图裁剪的视图。

## 说明

默认情况下，滚动视图会将其内容裁剪到边界内，但您可以使用此修饰符禁用此行为。例如，如果滚动视图内部的视图的阴影超出了滚动视图的边界，您可以使用以下修饰符来避免裁剪阴影：

```swift
struct ContentView: View {
    var disabled: Bool
    let colors: [Color] = [.red, .green, .blue, .mint, .teal]

    var body: some View {
        ScrollView(.horizontal) {
            HStack(spacing: 20) {
                ForEach(colors, id: \.self) { color in
                    Rectangle()
                        .frame(width: 100, height: 100)
                        .foregroundStyle(color)
                        .shadow(color: .primary, radius: 20)
                }
            }
        }
        .scrollClipDisabled(disabled)
    }
}
```

在上例中，当内容视图的 `disabled` 输入为 `false` 时，滚动视图会发生裁剪，就像您省略此修饰符时一样；但当输入为 `true` 时则不会。

虽然您可能希望避免裁剪超出滚动视图边界的视图部分（例如上例中的阴影），但通常您仍然希望滚动视图在某些位置进行裁剪。您可以使用 [clipShape(_:style:)](clipShape___style.zh-Hans.md) 修饰符添加不同的裁剪形状，从而创建自定义裁剪。以下代码禁用默认裁剪，然后添加超出滚动视图边界的矩形裁剪，裁剪范围为默认内边距量：

```swift
ScrollView(.horizontal) {
    // ...
}
.scrollClipDisabled()
.padding()
.clipShape(Rectangle())
```

## 管理内容可见性

- **scrollContentBackground(_:)**：指定此视图中可滚动视图的背景可见性。

- **ScrollContentOffsetAdjustmentBehavior**：定义滚动视图可以具有的不同内容偏移调整行为的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollClipDisabled(_:)
crawled: 2025-12-02T16:23:38Z
---

# scrollClipDisabled(_:)

**Instance Method**

Sets whether a scroll view clips its content to its bounds.

## Declaration

```swift
nonisolated func scrollClipDisabled(_ disabled: Bool = true) -> some View

```

## Parameters

- **disabled**: A Boolean value that specifies whether to disable scroll view clipping.

## Return Value

A view that disables or enables scroll view clipping.

## Discussion

By default, a scroll view clips its content to its bounds, but you can disable that behavior by using this modifier. For example, if the views inside the scroll view have shadows that extend beyond the bounds of the scroll view, you can use this modifier to avoid clipping the shadows:

```swift
struct ContentView: View {
    var disabled: Bool
    let colors: [Color] = [.red, .green, .blue, .mint, .teal]

    var body: some View {
        ScrollView(.horizontal) {
            HStack(spacing: 20) {
                ForEach(colors, id: \.self) { color in
                    Rectangle()
                        .frame(width: 100, height: 100)
                        .foregroundStyle(color)
                        .shadow(color: .primary, radius: 20)
                }
            }
        }
        .scrollClipDisabled(disabled)
    }
}
```

The scroll view in the above example clips when the content view’s `disabled` input is `false`, as it does if you omit the modifier, but not when the input is `true`:



While you might want to avoid clipping parts of views that exceed the bounds of the scroll view, like the shadows in the above example, you typically still want the scroll view to clip at some point. Create custom clipping by using the [clipShape(_:style:)](clipShape___style.zh-Hans.md) modifier to add a different clip shape. The following code disables the default clipping and then adds rectangular clipping that exceeds the bounds of the scroll view by the default padding amount:

```swift
ScrollView(.horizontal) {
    // ...
}
.scrollClipDisabled()
.padding()
.clipShape(Rectangle())
```

## Managing content visibility

- **scrollContentBackground(_:)**: Specifies the visibility of the background for scrollable views within this view.
- **ScrollContentOffsetAdjustmentBehavior**: A type that defines the different kinds of content offset adjusting behaviors a scroll view can have.

