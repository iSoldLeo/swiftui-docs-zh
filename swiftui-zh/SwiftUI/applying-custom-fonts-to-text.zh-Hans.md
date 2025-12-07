--- 来源：https://developer.apple.com/documentation/swiftui/applying-custom-fonts-to-text

抓取时间：2025-12-04T13:23:11Z

---

# 将自定义字体应用于文本

**Article**

在应用中添加并使用可随动态字体缩放的字体。

## 概述

SwiftUI 支持使用内置字体设置文本视图的样式，默认使用系统字体。除了使用系统提供的字体外，您还可以通过在 Xcode 项目中包含字体文件来使用自定义字体。要使用自定义字体，请将包含您已授权字体的字体文件添加到您的应用中，然后将该字体应用于文本视图或将其设置为容器视图中的默认字体。SwiftUI 的自适应文本显示功能会使用动态字体自动缩放字体。

动态字体允许用户选择屏幕上显示的文本内容的大小。它能帮助需要更大字体以获得更好阅读体验的用户，同时也能满足阅读较小字体的用户的需求，从而在屏幕上显示更多信息。

### 将字体文件添加到项目

要将字体文件添加到 Xcode 项目，请执行以下操作：

1. 在 Xcode 中，选择“项目导航器”。

2. 将字体文件从 Finder 窗口拖到项目中。这会将字体复制到项目中。

3. 选择字体或包含字体的文件夹，并确认这些文件已勾选其在应用目标中的成员资格。

### 确定要包含在应用包中的字体文件

对于 iOS、watchOS、tvOS 或 Mac Catalyst 目标，请将 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIAppFonts] 键添加到应用的 `Info.plist` 文件中。该键的值是一个字符串数组，其中包含所有已添加字体文件的相对路径。对于 macOS 应用目标，请在目标的 `Info.plist` 文件中使用 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/ATSApplicationFontsPath] 键，并将存放字体的文件夹名称作为该键的值。

在以下示例中，字体文件位于 `project_fonts` 目录中，因此您需要在 `Info.plist` 文件中使用 `project_fonts/MyFont.ttf` 作为字符串值。

### 应用支持动态大小的字体

使用 [custom(_:size:)](font/custom___size.zh-Hans.md) 方法检索字体实例，并使用 [font(_:)](Text/font.zh-Hans.md) 修饰符将其应用于文本视图。使用 [custom(_:size:)](font/custom___size.zh-Hans.md) 检索字体时，请确保字体名称与字体的 PostScript 名称匹配。您可以通过“字体册”应用打开字体并选择“字体信息”选项卡来查找字体的 PostScript 名称。如果 SwiftUI 无法检索并应用您的字体，则会使用默认系统字体渲染文本视图。

以下示例将字体 `MyFont` 应用于文本视图：

```swift
Text("Hello, world!")
    .font(Font.custom("MyFont", size: 18))
```

字体会根据提供的大小自适应缩放，以与默认文本样式 [body](font/body.zh-Hans.md) 对齐。使用 `relativeTo` 参数可以指定除默认样式 `body` 之外的其他缩放样式。例如，要将字体大小设置为 `32` 磅，并根据 [title](font/title.zh-Hans.md) 的文本样式进行自适应缩放：

```swift
Text("Hello, world!")
    .font(Font.custom("MyFont", size: 32, relativeTo: .title))
```

SwiftUI 不会自动合成粗体或斜体字体样式。如果字体支持加粗或斜体变体，您可以使用 [weight(_:)](Font/weight.zh-Hans.md) 或 [italic()](Font/italic.zh-Hans.md) 修饰符来自定义文本视图的排版。

有关如何在目标平台上选择字体以增强应用体验的设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography]。

### 使用缩放度量缩放内边距

视图属性上的 [ScaledMetric](ScaledMetric.zh-Hans.md) 属性包装器提供了一个缩放值，该值会随辅助功能设置自动更改。使用自适应字体时，您可以使用此属性包装器缩放文本之间或周围的间距，以改善视觉设计。

以下示例使用 `@ScaledMetric` 相对于 `body` 文本样式缩放文本视图周围的内边距值，并添加蓝色边框以标识内边距增加的间距：

```swift
struct ContentView: View {
    @ScaledMetric(relativeTo: .body) var scaledPadding: CGFloat = 10

    var body: some View {
        Text("The quick brown fox jumps over the lazy dog.")
            .font(Font.custom("MyFont", size: 18))
            .padding(scaledPadding)
            .border(Color.blue)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

预览显示以下图像，未启用任何辅助功能设置：

使用 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符将预览中的辅助功能大小类别设置为 [accessibilityLarge](ContentSizeCategory/accessibilityLarge.zh-Hans.md)：

```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .environment(\.sizeCategory, .accessibilityLarge)
    }
}
```

预览随后显示以下图像，反映了增加的辅助功能大小和缩放后的内边距：

## 设置字体

- **font(_:)**：设置此视图中文本的默认字体。

- **fontDesign(_:)**：设置此视图中文本的字体样式。

- **fontWeight(_:)**：设置此视图中文本的字体粗细。

- **fontWidth(_:)**：设置此视图中文本的字体宽度。

- **font**：此环境的默认字体。

- **Font**：环境相关的字体。


---
source: https://developer.apple.com/documentation/swiftui/applying-custom-fonts-to-text
crawled: 2025-12-04T13:23:11Z
---

# Applying custom fonts to text

**Article**

Add and use a font in your app that scales with Dynamic Type.

## Overview

SwiftUI supports styling text views using the built-in fonts, and uses a system font by default. Rather than using a system-provided font, you can use custom fonts by including the font files in your Xcode project. To use a custom font, add the font file that contains your licensed font to your app, and then apply the font to a text view or set it as a default font within a container view. SwiftUI’s adaptive text display scales the font automatically using Dynamic Type.

Dynamic Type allows users to choose the size of textual content displayed onscreen. It helps users who need larger text for better readability and accommodates those who can read smaller text, allowing more information to appear onscreen.

### Add the font files to the project

To add the font files to your Xcode project:

1. In Xcode, select the Project navigator.
2. Drag your fonts from a Finder window into your project. This copies the fonts to your project.
3. Select the font or folder with the fonts, and verify that the files show their target membership checked for your app’s targets.



### Identify the font files to include in the app bundle

For iOS, watchOS, tvOS, or Mac Catalyst targets, add the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIAppFonts] key to your app’s `Info.plist` file. For the key’s value, provide an array of strings containing the relative paths to any added font files. For a macOS app target, use the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/ATSApplicationFontsPath] key in your target’s `Info.plist` file, and provide the name of the folder that holds the fonts as the value for that key.

In the following example, the font file is inside the `project_fonts` directory, so you use `project_fonts/MyFont.ttf` as the string value in the `Info.plist` file.



### Apply a font supporting dynamic sizing

Use the [custom(_:size:)](font/custom___size.zh-Hans.md) method to retrieve an instance of your font and apply it to a text view with the [font(_:)](Text/font.zh-Hans.md) modifier. When retrieving the font with [custom(_:size:)](font/custom___size.zh-Hans.md), match the name of the font with the font’s PostScript name. You can find the postscript name of a font by opening it with the Font Book app and selecting the Font Info tab. If SwiftUI can’t retrieve and apply your font, it renders the text view with the default system font instead.

The following example applies the font `MyFont` to a text view:

```swift
Text("Hello, world!")
    .font(Font.custom("MyFont", size: 18))
```

The font scales adaptively from the size provided to align with the default text style of [body](font/body.zh-Hans.md). Use the `relativeTo` parameter to specify a text style to scale with other than the default of `body`. For example, to set the font size to `32` points and adaptively scale relative to the text style of [title](font/title.zh-Hans.md):

```swift
Text("Hello, world!")
    .font(Font.custom("MyFont", size: 32, relativeTo: .title))
```

SwiftUI doesn’t synthesize bold or italic styling for fonts. If the font supports weighted or italic variants, you can customize the typography of the text view by styling the font using the [weight(_:)](Font/weight.zh-Hans.md) or [italic()](Font/italic.zh-Hans.md) modifiers.

For design guidance on choosing fonts to enhance your app on your target platform, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography] in the Human Interface Guidelines.

### Scale padding using scaled metric

The [ScaledMetric](ScaledMetric.zh-Hans.md) property wrapper on a view property provides a scaled value that changes automatically with accessibility settings. When working with adaptively sized fonts, you can scale the spacing between or around the text to improve the visual design with this property wrapper.

The following example uses `@ScaledMetric` to scale the padding value surrounding a text view relative to the `body` text style, with a blue border added to identify the spacing that padding adds:

```swift
struct ContentView: View {
    @ScaledMetric(relativeTo: .body) var scaledPadding: CGFloat = 10

    var body: some View {
        Text("The quick brown fox jumps over the lazy dog.")
            .font(Font.custom("MyFont", size: 18))
            .padding(scaledPadding)
            .border(Color.blue)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

The preview shows the following image without any accessibility settings turned on:



Use the [environment(_:_:)](View/environment.zh-Hans.md) modifier to set the accessibility size category on the preview to [accessibilityLarge](ContentSizeCategory/accessibilityLarge.zh-Hans.md):

```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .environment(\.sizeCategory, .accessibilityLarge)
    }
}
```

The preview then shows the following image that reflects the increased accessibility size and the scaled padding:



## Setting a font

- **font(_:)**: Sets the default font for text in this view.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.
- **Font**: An environment-dependent font.

