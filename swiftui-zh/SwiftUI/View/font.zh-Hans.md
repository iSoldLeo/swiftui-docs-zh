--- 来源：https://developer.apple.com/documentation/SwiftUI/View/font(_:)

抓取时间：2025-12-02T17:34:40Z

---

# font(_:)

**实例方法**

设置此视图中文本的默认字体。

## 声明

```swift
nonisolated func font(_ font: Font?) -> some View

```

## 参数

- **font**：此视图中使用的默认字体。

## 返回值

一个默认字体设置为您提供的值的视图。

## 说明

使用 `font(_:)` 将特定字体应用于视图中的所有文本。

以下示例展示了将字体应用于单个视图和视图层次结构的效果。字体信息作为环境的一部分，沿着视图层级向下传递，除非在单个视图或视图容器级别进行覆盖，否则将一直有效。

这里，最外层的 [VStack](../VStack.zh-Hans.md) 将 16 磅系统字体作为默认字体应用于其 [VStack](../VStack.zh-Hans.md) 中包含的视图。在该堆栈内部，示例仅将 [largeTitle](../font/largeTitle.zh-Hans.md) 字体应用于第一个文本视图；这显式地覆盖了默认设置。其余堆栈及其包含的视图继续使用其包含视图设置的 16 磅系统字体：

```swift
VStack {
    Text("Font applied to a text view.")
        .font(.largeTitle)

    VStack {
        Text("These 2 text views have the same font")
        Text("applied to their parent hierarchy")
    }
}
.font(.system(size: 16, weight: .light, design: .default))
```

## 设置字体

- **将自定义字体应用于文本**：在应用中添加并使用可随动态类型缩放的字体。

- **fontDesign(_:)**：设置此视图中文本的字体样式。

- **fontWeight(_:)**：设置此视图中文本的字体粗细。

- **fontWidth(_:)**：设置此视图中文本的字体宽度。

- **font**：此环境的默认字体。

- **Font**：环境相关的字体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/font(_:)
crawled: 2025-12-02T17:34:40Z
---

# font(_:)

**Instance Method**

Sets the default font for text in this view.

## Declaration

```swift
nonisolated func font(_ font: Font?) -> some View

```

## Parameters

- **font**: The default font to use in this view.

## Return Value

A view with the default font set to the value you supply.

## Discussion

Use `font(_:)` to apply a specific font to all of the text in a view.

The example below shows the effects of applying fonts to individual views and to view hierarchies. Font information flows down the view hierarchy as part of the environment, and remains in effect unless overridden at the level of an individual view or view container.

Here, the outermost [VStack](../VStack.zh-Hans.md) applies a 16-point system font as a default font to views contained in that [VStack](../VStack.zh-Hans.md). Inside that stack, the example applies a [largeTitle](../font/largeTitle.zh-Hans.md) font to just the first text view; this explicitly overrides the default. The remaining stack and the views contained with it continue to use the 16-point system font set by their containing view:

```swift
VStack {
    Text("Font applied to a text view.")
        .font(.largeTitle)

    VStack {
        Text("These 2 text views have the same font")
        Text("applied to their parent hierarchy")
    }
}
.font(.system(size: 16, weight: .light, design: .default))
```



## Setting a font

- **Applying custom fonts to text**: Add and use a font in your app that scales with Dynamic Type.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.
- **Font**: An environment-dependent font.

