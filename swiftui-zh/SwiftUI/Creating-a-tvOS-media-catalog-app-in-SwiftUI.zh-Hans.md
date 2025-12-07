--- 来源：https://developer.apple.com/documentation/SwiftUI/Creating-a-tvOS-media-catalog-app-in-SwiftUI
抓取时间：2025-12-02T15:50:59Z

---

# 使用 SwiftUI 创建 tvOS 媒体目录应用

**示例代码**

为您的 tvOS 应用构建标准的内容锁和内容架行。

## 概述

此示例代码项目展示了如何为 tvOS 创建标准的内容锁，并提供了构建内容架行的最佳实践。它还包含产品页面、搜索视图和标签视图的示例，包括为 tvOS 提供侧边栏的全新自适应标签视图样式。

示例项目包含以下示例：

- `StackView` 实现了一个内容目录应用的示例首页，定义了多个内容架，并在其上方添加了展示或首页横幅区域。它还提供了一个首屏和首屏切换动画的示例。

- `ButtonsView` 展示了 tvOS 中各种可用的按钮样式。

- `DescriptionView` 提供了一个示例，说明如何构建类似于 Apple TV 应用中的产品页面，并带有自定义 Material 模糊效果。

- `SearchView` 展示了一个使用 [searchable(text:placement:prompt:)-18a8f](View/searchable_text_placement_prompt_-18a8f.zh-Hans.md) 和 [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) 修饰符的简单搜索页面示例。

- `SidebarContentView` 展示了如何使用 tvOS 18 中的新标签栏 API 创建分段式侧边栏。

- `HeroHeaderView` 提供了一个示例，说明如何创建 Material 渐变来模糊特定区域的内容，并将其淡入到清晰的内容中。

### 创建内容锁定

按钮样式 [borderless](PrimitiveButtonStyle/borderless.zh-Hans.md) 提供您在 tvOS 中使用的主要锁定样式，包括所有焦点交互和悬停效果。按钮的标题和任何附近的章节标题会在按钮图像放大并获得焦点时自动移开。

在按钮的标签闭合中提供单独的 [Image](Image.zh-Hans.md) 和 [Text](Text.zh-Hans.md) 视图，以确保正确的垂直外观。使用 [Label](Label.zh-Hans.md) 通常会导致水平布局，并且根据当前标签样式，可能无法达到您预期的外观效果。

```swift
Button { /* action */ } label: {
    Image("discovery_portrait")
        .resizable()
        .frame(width: 250, height: 375)
    Text("Borderless Portrait")
}
```

默认情况下，按钮样式会定位按钮标签内的第一个 `Image` 元素，并为其附加 [highlight](HoverEffect/highlight.zh-Hans.md) 悬停效果，从而实现悬停、镜面高光和万向节运动效果。

为了确保悬停效果应用于正确的视图，您可以使用 [hoverEffect(_:)](View/hoverEffect.zh-Hans.md) 修改器将其手动附加到按钮标签的特定子视图。例如，要确保 SF Symbols 图像与其背景一起悬停，请执行以下操作：

```swift
Button { /* action */ } label: {
    Image(systemName: "person.circle")
        .font(.title)
        .background(Color.blue.grayscale(0.7))
        .hoverEffect(.highlight)
    Text("Shaped")
}
.buttonBorderShape(.circle)
```

您还可以将悬停效果附加到自定义视图。

```swift
Button { /* action */ } label: {
    CodeSampleArtwork(size: .appIconSize)
        .frame(width: 400, height: 240)
        .hoverEffect(.highlight)
    Text("Custom Icon View")
}
```

### 显示信息密集型按钮

对于信息更密集的按钮，可以考虑使用 [card](PrimitiveButtonStyle/card.zh-Hans.md) 按钮样式，该样式提供面板效果，并在聚焦时呈现更柔和的动态效果。将带有内边距的容器作为按钮标签，可以实现类似于 Apple TV 应用搜索结果按钮的效果。

```swift
Button { /* action */ } label: {
    HStack(alignment: .top, spacing: 10) {
        Image( . . . )
            .resizable()
            .aspectRatio(contentMode: .fit)
            .clipShape(RoundedRectangle(cornerRadius: 12))

        VStack(alignment: .leading) {
            Text(asset.title)
                .font(.body)
            Text("Subtitle text goes here, limited to two lines.")
                .font(.caption2)
                .foregroundStyle(.secondary)
                .lineLimit(2)
            Spacer(minLength: 0)
            HStack(spacing: 4) {
                ForEach(1..<4) { _ in
                    Image(systemName: "ellipsis.rectangle.fill")
                }
            }
            .foregroundStyle(.secondary)
        }
    }
    .padding(12)
}
```

您还可以使用自定义的 [LabelStyle](LabelStyle.zh-Hans.md) 来创建标准的卡片式按钮外观，同时保持按钮在使用时的声明简洁。

```swift
struct CardOverlayLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
        ZStack(alignment: .bottomLeading) {
            configuration.icon
                .resizable()
                .aspectRatio(400/240, contentMode: .fit)
                .overlay {
                    LinearGradient(
                        stops: [
                            .init(color: .black.opacity(0.6), location: 0.1),
                            .init(color: .black.opacity(0.2), location: 0.25),
                            .init(color: .black.opacity(0), location: 0.4)
                        ],
                        startPoint: .bottom, endPoint: .top
                    )
                }
                .overlay {
                    RoundedRectangle(cornerRadius: 12)
                        .stroke(lineWidth: 2)
                        .foregroundStyle(.quaternary)
                }

            configuration.title
                .font(.caption.bold())
                .foregroundStyle(.secondary)
                .padding(6)
        }
        .frame(maxWidth: 400)
    }
}

Button { /* action */ } label: {
    Label("Title at the bottom", image: "discovery_landscape")
}
```

### 显示内容架

内容架通常是滚动视图中的水平堆叠。

必须禁用滚动裁剪，才能使聚焦效果放大并提升每个按钮。内容架通常只包含一种按钮样式，因此请将按钮样式放置在内容架容器的外部。

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 40) {
        ForEach(Asset.allCases) { asset in
            // . . .
        }
    }
}
.scrollClipDisabled()
.buttonStyle(.borderless)
```

为了更好地排列您的组件，请使用 [containerRelativeFrame(_:count:span:spacing:alignment:)](View/containerRelativeFrame___count_span_spacing_alignment.zh-Hans.md) 修饰符，让 SwiftUI 为每个组件确定最佳尺寸。您可以指定屏幕上要显示的组件数量，以及堆栈视图提供的间距。然后，SwiftUI 会排列内容，使首尾项目的边缘与其容器的首尾安全区域内边距对齐。

对于无边框按钮，您可以将修饰符附加到按钮标签闭包内的 `Image` 实例，使图像成为框架计算和对齐的来源。

```swift
asset.portraitImage
    .resizable()
    .aspectRatio(250 / 375, contentMode: .fit)
    .containerRelativeFrame(.horizontal, count: 6, spacing: 40)
Text(asset.title)
```

### 显示首屏上方和下方的内容

对于落地页，您可以通过结合使用 [ScrollTargetBehavior](ScrollTargetBehavior.zh-Hans.md) 和带有渐变蒙版的背景视图来实现首屏上方和下方的显示效果。

将您的展示或页眉部分定义为一个带有容器相对框架的堆栈，使其占据可用空间的特定百分比。同时，为该堆栈添加一个 [focusSection()](View/focusSection.zh-Hans.md) 修饰符，使其整个宽度可以作为焦点移动的目标，并将焦点重定向到其内容。否则，从下方货架右侧向上移动焦点可能会失败，或者直接跳到标签栏，因为焦点引擎会沿着当前焦点项的直线搜索最近的可聚焦视图。

```swift
VStack(alignment: .leading) {
    // Header content.
}
.frame(maxWidth: .infinity, alignment: .leading)
.focusSection()
.containerRelativeFrame(.vertical, alignment: .topLeading) {
    length, _ in length * 0.8
}
```

以上代码是首屏部分。要检测焦点何时移动到首屏下方，请使用 [onScrollVisibilityChange(threshold:_:)](View/onScrollVisibilityChange_threshold.zh-Hans.md) 来检测页眉视图何时移动到屏幕一半以上之外。

```swift
.onScrollVisibilityChange { visible in
    // When the header scrolls more than 50% offscreen, toggle
    // to the below-the-fold state.
    withAnimation {
        belowFold = !visible
    }
}
```

您可以使用带有材质叠加层的全屏图像来定义着陆页的背景。然后，您可以使用 [LinearGradient](LinearGradient.zh-Hans.md) 蒙版将材质转换为渐变，并根据视图的首屏或首屏状态调整渐变色块的不透明度。

```swift
Image("beach_landscape")
    .resizable()
    .aspectRatio(contentMode: .fill)
    .overlay {
        // Build the gradient material by filling an area with a material, and
        // then masking that area using a linear gradient.
        Rectangle()
            .fill(.regularMaterial)
            .mask {
                LinearGradient(
                    stops: [
                        .init(color: .black, location: 0.25),
                        .init(color: .black.opacity(belowFold ? 1 : 0.3), location: 0.375),
                        .init(color: .black.opacity(belowFold ? 1 : 0), location: 0.5)
                    ],
                    startPoint: .bottom, endPoint: .top
                )
            }
    }
    .ignoresSafeArea()
```

通过调整渐变色块的不透明度，而不是更换蒙版视图，您可以实现首屏显示效果和首屏下显示效果之间的平滑动画过渡。首屏显示效果是指材质在一定高度以上逐渐淡出，露出其后的图像；而首屏下显示效果是指整个图像模糊。

### 折叠点对齐

您可以实现自定义的 [ScrollTargetBehavior](ScrollTargetBehavior.zh-Hans.md) 来创建折叠点对齐效果。然后添加一个检查，以确定滚动事件的目标是否跨越了折叠阈值，并将该目标更新为页面顶部（如果向上滚动）或第一个内容架的顶部（如果向下滚动）。由于您的视图已经跟踪了首屏/首屏状态，它可以将该信息传递给行为，以指示要检查哪个操作。

```swift
ScrollView {
    // . . .
}
.scrollTargetBehavior(
    FoldSnappingScrollTargetBehavior(
        aboveFold: !belowFold, showcaseHeight: showcaseHeight))

struct FoldSnappingScrollTargetBehavior: ScrollTargetBehavior {
    var aboveFold: Bool
    var showcaseHeight: CGFloat

    func updateTarget(_ target: inout ScrollTarget, context: TargetContext) {
        // The view is above the fold and not moving far enough down, so make no
        // change.
        if aboveFold && target.rect.minY < showcaseHeight * 0.3 {
            return
        }

        // The view is below the fold, and the header isn't coming onscreen, so
        // make no change.
        if !aboveFold && target.rect.minY > showcaseHeight {
            return
        }

        // Upward movement: Require revealing over 30% of the header, or don't let
        // the scroll go upward.
        let showcaseRevealThreshold = showcaseHeight * 0.7
        let snapToHideRange = showcaseRevealThreshold...showcaseHeight

        if aboveFold || snapToHideRange.contains(target.rect.origin.y) {
            // Snap to align the first content shelf at the top of the screen.
            target.rect.origin.y = showcaseHeight
        }
        else {
            // Snap upward to reveal the header.
            target.rect.origin.y = 0
        }
    }
}
```

### 提供产品亮点页面

产品页面通常会使用 Material Design 的渐变外观，并启用首屏/首屏对齐功能。您可能需要对渐变进行一些调整，以适应屏幕底部较高的内容栏，但通常情况下，您希望保留内容的展示图片，并适当模糊处理，作为向下滚动时视图的背景。

这使得每个产品的页面都独一无二，其标志性的图片会为内容着色。这与 Apple TV 的根屏幕使用的效果相同——系统会模糊最近显示的顶部图片，并将其用作 tvOS 主屏幕的背景。

在您的描述视图中，您可能需要显示一组带边框的按钮，并将每个按钮拉伸到相同的宽度。 SwiftUI 通过为按钮标签添加背景来实现带边框的按钮，因此增大按钮视图的大小并不一定会导致背景区域也随之增大。实际上，你需要指定*标签内容*可以扩展，这样它的背景也会随之扩展。将 [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) 修饰符添加到按钮的标签内容即可实现这一点。

```swift
VStack(spacing: 12) {
    Button { /* action */ } label: {
        Text("Sign Up")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }

    Button { /* action */ } label: {
        Text("Buy or Rent")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }

    Button { /* action */ } label: {
        Label("Add to Up Next", systemImage: "plus")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }
}
```

在显示内容描述时，允许其在页面上被截断，并使用 `.plain` 样式将其放置在 [Button](Button.zh-Hans.md) 中。这样，用户可以选择该描述，然后你可以使用带有 [fullScreenCover(isPresented:onDismiss:content:)](View/fullScreenCover_isPresented_onDismiss_content.zh-Hans.md) 修饰符的叠加视图来显示完整的描述。

```swift
.fullScreenCover(isPresented: $showDescription) {
    VStack(alignment: .center) {
        Text(loremIpsum)
            .frame(maxWidth: 600)
    }
}
```

### 搜索内容

对于搜索页面，建议使用 [LazyVGrid](LazyVGrid.zh-Hans.md) 来显示搜索结果，并采用横向布局。这样可以同时在屏幕上显示更多内容，每行显示三到五个结果。较高的内容容器区域可以更清晰地显示搜索词更改后的效果。

搜索功能的实现基于简单的视图修饰符，这些修饰符在所有 Apple 平台上的功能都相同。[searchable(text:placement:prompt:)-18a8f](View/searchable_text_placement_prompt_-18a8f.zh-Hans.md) 修饰符提供完整的搜索界面，并将搜索字段绑定到提供的文本。通过附加 [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) 修饰符，您可以显示可能的搜索关键字补全列表。这些补全项通常是 `Text` 实例，但 `Button` 和 [Label](Label.zh-Hans.md) 也适用。

请务必对搜索结果进行排序，以确保表格内容稳定且易于预测。

```swift
ScrollView(.vertical) {
    LazyVGrid(
        columns: Array(repeating: .init(.flexible(), spacing: 40), count: 4), 
        spacing: 40
    ) {
        ForEach(/* matching assets, sorted */) { asset in
            Button { /* action */ } label: {
                asset.landscapeImage
                    .resizable()
                    .aspectRatio(16 / 9, contentMode: .fit)
                Text(asset.title)
            }
        }
    }
    .buttonStyle(.borderless)
}
.scrollClipDisabled()
.searchable(text: $searchTerm)
.searchSuggestions {
    ForEach(/* keywords matching search term */, id: \.self) { suggestion in
        Text(suggestion)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Creating-a-tvOS-media-catalog-app-in-SwiftUI
crawled: 2025-12-02T15:50:59Z
---

# Creating a tvOS media catalog app in SwiftUI

**Sample Code**

Build standard content lockups and rows of content shelves for your tvOS app.

## Overview

This sample code project shows how to create the standard content lockups for tvOS, and provides best practices for building out rows of content shelves. It also includes examples for product pages, search views, and tab views, including the new sidebar adaptive tab view style that provides a sidebar in tvOS.



The sample project contains the following examples:

- `StackView` implements an example landing page for a content catalog app, defining several shelves with a showcase or hero header area above them. It also gives an example of an above- and below-the-fold switching animation.
- `ButtonsView` provides a showcase of the various button styles available in tvOS.
- `DescriptionView` provides an example of how to build a product page similar to those you see on the Apple TV app, with a custom material blur.
- `SearchView` shows an example of a simple search page using the [searchable(text:placement:prompt:)-18a8f](View/searchable_text_placement_prompt_-18a8f.zh-Hans.md) and [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) modifiers.
- `SidebarContentView` shows how to make a sectioned sidebar using the new tab bar APIs in tvOS 18.
- `HeroHeaderView` gives an example of creating a material gradient to blur content in a certain area, fading it into unblurred content.

### Create content lockups

The [borderless](PrimitiveButtonStyle/borderless.zh-Hans.md) button style provides the primary lockup style you use in tvOS, including all the focus interactions and hover effects. The button’s title and any nearby section titles automatically move out of the way of the button’s image as it scales up on focus.



Provide a separate [Image](Image.zh-Hans.md) and [Text](Text.zh-Hans.md) view in the button’s label closure to ensure the correct vertical appearance. Using a [Label](Label.zh-Hans.md) usually results in a horizontal layout, and, depending on the current label style, may not give you the appearance you expect.

```swift
Button { /* action */ } label: {
    Image("discovery_portrait")
        .resizable()
        .frame(width: 250, height: 375)
    Text("Borderless Portrait")
}
```

By default, the button style locates the first `Image` within the button’s label and attaches a [highlight](HoverEffect/highlight.zh-Hans.md) hover effect to it, providing lift, a specular highlight, and gimbal motion effects.

To ensure the hover effect applies to exactly the right view, you can manually attach it to a particular subview of the button’s label using the [hoverEffect(_:)](View/hoverEffect.zh-Hans.md) modifier. For instance, to ensure an SF Symbols image hovers along with its background, do the following:

```swift
Button { /* action */ } label: {
    Image(systemName: "person.circle")
        .font(.title)
        .background(Color.blue.grayscale(0.7))
        .hoverEffect(.highlight)
    Text("Shaped")
}
.buttonBorderShape(.circle)
```

You can also attach the hover effect to a custom view.

```swift
Button { /* action */ } label: {
    CodeSampleArtwork(size: .appIconSize)
        .frame(width: 400, height: 240)
        .hoverEffect(.highlight)
    Text("Custom Icon View")
}
```

### Show information-dense lockups

For lockups with more dense information, consider using the [card](PrimitiveButtonStyle/card.zh-Hans.md) button style, which provides a platter and a more subtle motion effect on focus. Providing containers with padding as the button’s label gives you something similar to the search result lockups on the Apple TV app.



```swift
Button { /* action */ } label: {
    HStack(alignment: .top, spacing: 10) {
        Image( . . . )
            .resizable()
            .aspectRatio(contentMode: .fit)
            .clipShape(RoundedRectangle(cornerRadius: 12))

        VStack(alignment: .leading) {
            Text(asset.title)
                .font(.body)
            Text("Subtitle text goes here, limited to two lines.")
                .font(.caption2)
                .foregroundStyle(.secondary)
                .lineLimit(2)
            Spacer(minLength: 0)
            HStack(spacing: 4) {
                ForEach(1..<4) { _ in
                    Image(systemName: "ellipsis.rectangle.fill")
                }
            }
            .foregroundStyle(.secondary)
        }
    }
    .padding(12)
}
```

You can also use a custom [LabelStyle](LabelStyle.zh-Hans.md) to create a standard card-based lockup appearance while keeping your button’s declarations clean at the point of use.

```swift
struct CardOverlayLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
        ZStack(alignment: .bottomLeading) {
            configuration.icon
                .resizable()
                .aspectRatio(400/240, contentMode: .fit)
                .overlay {
                    LinearGradient(
                        stops: [
                            .init(color: .black.opacity(0.6), location: 0.1),
                            .init(color: .black.opacity(0.2), location: 0.25),
                            .init(color: .black.opacity(0), location: 0.4)
                        ],
                        startPoint: .bottom, endPoint: .top
                    )
                }
                .overlay {
                    RoundedRectangle(cornerRadius: 12)
                        .stroke(lineWidth: 2)
                        .foregroundStyle(.quaternary)
                }

            configuration.title
                .font(.caption.bold())
                .foregroundStyle(.secondary)
                .padding(6)
        }
        .frame(maxWidth: 400)
    }
}

Button { /* action */ } label: {
    Label("Title at the bottom", image: "discovery_landscape")
}
```

### Display content shelves

Content shelves are usually horizontal stacks in scroll views.



Disabling scroll clipping is necessary to allow the focus effects to scale up and lift each lockup. Shelves typically contain only a single style of lockup, so assign your button style on the outside of the shelf container.

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 40) {
        ForEach(Asset.allCases) { asset in
            // . . .
        }
    }
}
.scrollClipDisabled()
.buttonStyle(.borderless)
```

To arrange your lockups nicely, use the [containerRelativeFrame(_:count:span:spacing:alignment:)](View/containerRelativeFrame___count_span_spacing_alignment.zh-Hans.md) modifier to let SwiftUI determine the best size for each. You can specify how many lockups you want on the screen, and the amount of spacing your stack view provides. Then SwiftUI arranges the content so that the edges of the leading and trailing items align with the leading and trailing safe area insets of its container.

For borderless buttons, you can attach the modifier to the `Image` instance within the button’s label closure to make the image the source of the frame calculations and alignments.

```swift
asset.portraitImage
    .resizable()
    .aspectRatio(250 / 375, contentMode: .fit)
    .containerRelativeFrame(.horizontal, count: 6, spacing: 40)
Text(asset.title)
```

### Show content above and below the fold

For a landing page you can implement above- and below-the-fold appearances through a combination of [ScrollTargetBehavior](ScrollTargetBehavior.zh-Hans.md) and a background view with a gradient mask.



Define your showcase or header section as a stack with a container relative frame to make it take up a particular percentage of the available space. Attach a [focusSection()](View/focusSection.zh-Hans.md) modifier to the stack as well, so that its full width can act as a target for focus movement, which it then diverts to its content. Otherwise, moving focus up from the right side of the shelves below might fail, or might jump all the way to the tab bar because the focus engine searches for the nearest focusable view along a straight line from the currently focused item.

```swift
VStack(alignment: .leading) {
    // Header content.
}
.frame(maxWidth: .infinity, alignment: .leading)
.focusSection()
.containerRelativeFrame(.vertical, alignment: .topLeading) {
    length, _ in length * 0.8
}
```

The code above is the above-the-fold section. To detect when focus moves below the fold, use [onScrollVisibilityChange(threshold:_:)](View/onScrollVisibilityChange_threshold.zh-Hans.md) to detect when the header view moves more than halfway off the screen.

```swift
.onScrollVisibilityChange { visible in
    // When the header scrolls more than 50% offscreen, toggle
    // to the below-the-fold state.
    withAnimation {
        belowFold = !visible
    }
}
```

You can define the background of your landing page using a full-screen image with a material in an overlay. Then you can turn the material into a gradient by masking it with a [LinearGradient](LinearGradient.zh-Hans.md), and you can adjust the opacity of that gradient’s stops according to the view’s above- or below-the-fold status.

```swift
Image("beach_landscape")
    .resizable()
    .aspectRatio(contentMode: .fill)
    .overlay {
        // Build the gradient material by filling an area with a material, and
        // then masking that area using a linear gradient.
        Rectangle()
            .fill(.regularMaterial)
            .mask {
                LinearGradient(
                    stops: [
                        .init(color: .black, location: 0.25),
                        .init(color: .black.opacity(belowFold ? 1 : 0.3), location: 0.375),
                        .init(color: .black.opacity(belowFold ? 1 : 0), location: 0.5)
                    ],
                    startPoint: .bottom, endPoint: .top
                )
            }
    }
    .ignoresSafeArea()
```

By adjusting the opacity of the gradient stops, rather than swapping out the mask view, you achieve a smooth animation between the above-the-fold appearance, where the material fades out above a certain height to reveal the image behind, and the below-the-fold appearance where the entire image blurs.

### Snap at the fold point

You can implement a custom [ScrollTargetBehavior](ScrollTargetBehavior.zh-Hans.md) to create a fold-snapping effect. Then add a check to determine whether the target of a scroll event is crossing a fold threshold, and update that target to either the top of the page (if moving upward) or to the top of your first content shelf (if moving downward). With your view already tracking the above/below fold state, it can pass that information into the behavior to indicate which operation to check for.

```swift
ScrollView {
    // . . .
}
.scrollTargetBehavior(
    FoldSnappingScrollTargetBehavior(
        aboveFold: !belowFold, showcaseHeight: showcaseHeight))

struct FoldSnappingScrollTargetBehavior: ScrollTargetBehavior {
    var aboveFold: Bool
    var showcaseHeight: CGFloat

    func updateTarget(_ target: inout ScrollTarget, context: TargetContext) {
        // The view is above the fold and not moving far enough down, so make no
        // change.
        if aboveFold && target.rect.minY < showcaseHeight * 0.3 {
            return
        }

        // The view is below the fold, and the header isn't coming onscreen, so
        // make no change.
        if !aboveFold && target.rect.minY > showcaseHeight {
            return
        }

        // Upward movement: Require revealing over 30% of the header, or don't let
        // the scroll go upward.
        let showcaseRevealThreshold = showcaseHeight * 0.7
        let snapToHideRange = showcaseRevealThreshold...showcaseHeight

        if aboveFold || snapToHideRange.contains(target.rect.origin.y) {
            // Snap to align the first content shelf at the top of the screen.
            target.rect.origin.y = showcaseHeight
        }
        else {
            // Snap upward to reveal the header.
            target.rect.origin.y = 0
        }
    }
}
```

### Provide product highlight pages

It’s common for product pages to use a material gradient appearance with above- and below-the-fold snapping. You most likely need to tune the gradient a little differently to account for a taller bar of content at the bottom of the screen, but you typically want to keep the content’s showcase image, with a suitable blur, as a background for the view when scrolling below.



This makes each product’s page unique, with its defining artwork tinting the content. This is the same effect that root screen on the Apple TV uses — the system blurs the most recently displayed top-shelf image and uses it as the background of the tvOS home screen.

In your description view, you may want to display a stack of bordered buttons, and stretch each to the same width. SwiftUI implements bordered buttons by attaching a background to their labels, so increasing the size of the button view isn’t necessarily going to cause the background platter to grow. Instead, you need to specify that the *label content* is able to expand, and its background then expands as well. Attaching a [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) modifier to the button’s label content achieves this for you.

```swift
VStack(spacing: 12) {
    Button { /* action */ } label: {
        Text("Sign Up")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }

    Button { /* action */ } label: {
        Text("Buy or Rent")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }

    Button { /* action */ } label: {
        Label("Add to Up Next", systemImage: "plus")
            .font(.body.bold())
            .frame(maxWidth: .infinity)
    }
}
```

When displaying your content’s description, allow it to truncate on the page, and place it within a [Button](Button.zh-Hans.md) using the `.plain` style. People can then select it, and you can present the full description using an overlay view that you attach with the [fullScreenCover(isPresented:onDismiss:content:)](View/fullScreenCover_isPresented_onDismiss_content.zh-Hans.md) modifier.

```swift
.fullScreenCover(isPresented: $showDescription) {
    VStack(alignment: .center) {
        Text(loremIpsum)
            .frame(maxWidth: 600)
    }
}
```

### Search for content

For your search page, prefer using a [LazyVGrid](LazyVGrid.zh-Hans.md) to contain your results, and a landscape orientation for the lockups themselves. This allows more content to appear onscreen at one time, with several rows of three to five items per row. A tall content container area makes it much easier to see the effects of changes to your search term.



The search implementation consists of simple view modifiers that function identically on each Apple platform. The [searchable(text:placement:prompt:)-18a8f](View/searchable_text_placement_prompt_-18a8f.zh-Hans.md) modifier provides the entire search UI for you, binding the search field to the provided text. By attaching a [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) modifier, you can present a list of potential search keyword completions. These are commonly `Text` instances, but `Button` and [Label](Label.zh-Hans.md) also work.

Be sure to sort your search results so that the content of your grid is stable and predictable.

```swift
ScrollView(.vertical) {
    LazyVGrid(
        columns: Array(repeating: .init(.flexible(), spacing: 40), count: 4), 
        spacing: 40
    ) {
        ForEach(/* matching assets, sorted */) { asset in
            Button { /* action */ } label: {
                asset.landscapeImage
                    .resizable()
                    .aspectRatio(16 / 9, contentMode: .fit)
                Text(asset.title)
            }
        }
    }
    .buttonStyle(.borderless)
}
.scrollClipDisabled()
.searchable(text: $searchTerm)
.searchSuggestions {
    ForEach(/* keywords matching search term */, id: \.self) { suggestion in
        Text(suggestion)
    }
}
```

