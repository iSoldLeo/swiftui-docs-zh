---
来源： https://developer.apple.com/documentation/swiftui/font
抓取时间： 2025-12-05T22:21:37Z
---

# 字体

**Structure**

取决于环境的字体。

## 声明

```swift
@frozen struct Font
```

## 概览

由于[Font](Font.zh-Hans.md) 是一个较晚绑定的标记，因此系统会在特定环境中使用字体时解析该字体的值。

## 获取标准字体

- **extraLargeTitle2**：创建具有二级特大标题文本样式的字体。
- **extraLargeTitle**：创建具有超大标题文本样式的字体。
- **largeTitle**：具有大标题文本样式的字体。
- **title**：具有标题文本样式的字体。
- **title2**：为二级分层标题创建字体。
- **title3**：为三级分层标题创建字体。
- **headline**：具有标题文本样式的字体。
- **subheadline**：具有副标题文本样式的字体。
- **body**：具有正文文本样式的字体。
- **callout**：具有呼出文本样式的字体。
- **caption**：具有标题文本样式的字体。
- **caption2**：创建具有备用标题文本样式的字体。
- **footnote**：具有脚注文本样式的字体。

## 获取系统字体

- **system(_:design:weight:)**：获取使用指定样式、设计和权重的系统字体。
- **system(size:weight:design:)**：指定要使用的系统字体，以及要应用到文本中的样式、权重和任何设计参数。
- **Font.Design**：用于字体的设计。
- **Font.TextStyle**：用于字体的动态文本样式。
- **Font.Weight**：用于字体的权重。

## 创建自定义字体

- **custom(_:fixedSize:)**：使用给定的`name` 和固定的`size` 创建自定义字体，该字体不会随动态字体缩放。
- **custom(_:size:relativeTo:)**：使用给定的`name` 和`size` 创建自定义字体，该字体相对于给定的`textStyle` 缩放。
- **custom(_:size:)**：使用给定的`name` 和`size` 创建自定义字体，该字体可与正文文本样式一起缩放。

## 从其他字体获取字体

- **init(_:)**：从平台字体实例创建自定义字体。

## 创建字体样式

- **bold()**：为字体添加粗体或加粗样式。
- **italic()**：为字体添加斜体。
- **monospaced()**：返回与基本字体同族的固定宽度字体。
- **monospacedDigit()**：返回修改后的字体，该字体使用固定宽度的数字，其他字符按比例间隔。
- **smallCaps()**：调整字体以启用所有小写字母。
- **lowercaseSmallCaps()**：调整字体以启用小写字母。
- **uppercaseSmallCaps()**：调整字体以启用小写大写字母。
- **weight(_:)**：设置字体的重量。
- **width(_:)**：设置字体的宽度。
- **Font.Width**：字体有多种宽度时使用的宽度。
- **leading(_:)**：调整字体的行距。
- **Font.Leading**：可应用于字体的行距调整。

## 过时的符号

- **system(_:design:)**：获取具有给定文本样式和设计的系统字体。
- **system(size:weight:design:)**：指定要使用的系统字体，以及要应用到文本中的样式、权重和任何设计参数。

### 结构

- **Font.Context**：用于解析字体的信息。
- **Font.Resolved**：具体的字体值。

### 实例方法

- **bold(_:)**：添加或删除字体的粗体或强调样式。
- **italic(_:)**：在字体上添加/删除斜体。
- **lowercaseSmallCaps(_:)**：调整字体以启用/禁用小写字母。
- **monospaced(_:)**：返回添加或删除与基本字体同族的固定宽度设计的字体。
- **pointSize(_:)**：明确设置字体的点大小。
- **resolve(in:)**：根据当前上下文将此字体评估为已解析字体。
- **scaled(by:)**：缩放字体的点大小。
- **smallCaps(_:)**：调整字体以启用/禁用所有小写字母。
- **uppercaseSmallCaps(_:)**：调整字体以启用/禁用大写小写字母。

### 类型属性

- **default**：在任何给定环境中使用的有效 SwiftUI 字体。

### 类型方法

- **system(size:weight:design:)**：指定要使用的系统字体，以及样式、重量和您希望应用于文本的任何设计参数。

## 设置字体

- 在文本中应用自定义字体**：在应用程序中添加并使用可与动态字体一起缩放的字体。
- **font(_:)**：设置此视图中文本的默认字体。
- **fontDesign(_:)**：设置此视图中文本的字体设计。
- **fontWeight(_:)**：设置此视图中文本的字体重量。
- **fontWidth(_:)**：设置此视图中文本的字体宽度。
- **font**：此环境的默认字体。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/font
crawled: 2025-12-05T22:21:37Z
---

# Font

**Structure**

An environment-dependent font.

## Declaration

```swift
@frozen struct Font
```

## Overview

The system resolves a font’s value at the time it uses the font in a given environment because [Font](Font.zh-Hans.md) is a late-binding token.

## Getting standard fonts

- **extraLargeTitle2**: Create a font with the second level extra large title text style.
- **extraLargeTitle**: Create a font with the extra large title text style.
- **largeTitle**: A font with the large title text style.
- **title**: A font with the title text style.
- **title2**: Create a font for second level hierarchical headings.
- **title3**: Create a font for third level hierarchical headings.
- **headline**: A font with the headline text style.
- **subheadline**: A font with the subheadline text style.
- **body**: A font with the body text style.
- **callout**: A font with the callout text style.
- **caption**: A font with the caption text style.
- **caption2**: Create a font with the alternate caption text style.
- **footnote**: A font with the footnote text style.

## Getting system fonts

- **system(_:design:weight:)**: Gets a system font that uses the specified style, design, and weight.
- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.
- **Font.Design**: A design to use for fonts.
- **Font.TextStyle**: A dynamic text style to use for fonts.
- **Font.Weight**: A weight to use for fonts.

## Creating custom fonts

- **custom(_:fixedSize:)**: Create a custom font with the given `name` and a fixed `size` that does not scale with Dynamic Type.
- **custom(_:size:relativeTo:)**: Create a custom font with the given `name` and `size` that scales relative to the given `textStyle`.
- **custom(_:size:)**: Create a custom font with the given `name` and `size` that scales with the body text style.

## Getting a font from another font

- **init(_:)**: Creates a custom font from a platform font instance.

## Styling a font

- **bold()**: Adds bold or emphasized styling to the font.
- **italic()**: Adds italics to the font.
- **monospaced()**: Returns a fixed-width font from the same family as the base font.
- **monospacedDigit()**: Returns a modified font that uses fixed-width digits, while leaving other characters proportionally spaced.
- **smallCaps()**: Adjusts the font to enable all small capitals.
- **lowercaseSmallCaps()**: Adjusts the font to enable lowercase small capitals.
- **uppercaseSmallCaps()**: Adjusts the font to enable uppercase small capitals.
- **weight(_:)**: Sets the weight of the font.
- **width(_:)**: Sets the width of the font.
- **Font.Width**: A width to use for fonts that have multiple widths.
- **leading(_:)**: Adjusts the line spacing of a font.
- **Font.Leading**: A line spacing adjustment that you can apply to a font.

## Deprecated symbols

- **system(_:design:)**: Gets a system font with the given text style and design.
- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.

## Structures

- **Font.Context**: Information used to resolve a font.
- **Font.Resolved**: A concrete font value.

## Instance Methods

- **bold(_:)**: Adds or removes bold or emphasized styling on the font.
- **italic(_:)**: Adds/removes italics on the font.
- **lowercaseSmallCaps(_:)**: Adjusts the font to enable/disable lowercase small capitals.
- **monospaced(_:)**: Returns a font adding or removing fixed-width design from the same family as the base font.
- **pointSize(_:)**: Sets the point size of the font explicitly.
- **resolve(in:)**: Evaluates this font to a resolved font given the current context.
- **scaled(by:)**: Scales the point size of the font.
- **smallCaps(_:)**: Adjusts the font to enable/disable all small capitals.
- **uppercaseSmallCaps(_:)**: Adjusts the font to enable/disable uppercase small capitals.

## Type Properties

- **default**: The effective SwiftUI font used in any given environment.

## Type Methods

- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.

## Setting a font

- **Applying custom fonts to text**: Add and use a font in your app that scales with Dynamic Type.
- **font(_:)**: Sets the default font for text in this view.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

