--- 来源：https://developer.apple.com/documentation/SwiftUI/Landmarks-Displaying-custom-activity-badges

抓取时间：2025-12-02T15:45:37Z

---

# Landmarks：显示自定义活动徽章

**示例代码**

为用户提供一种方式，通过显示动画自定义活动徽章来标记他们的旅程。

## 概述

Landmarks 应用让用户在探索世界各地景点时记录他们的旅程。无论是家附近的国家公园，还是遥远的异国他乡，该应用都提供了一种方式，让用户标记他们的旅程，并在此过程中获得自定义活动徽章。

此示例以垂直视图显示徽章，并包含一个用于显示或隐藏徽章的切换按钮。Landmarks 应用包含一个自定义修饰符，使其他视图更容易采用徽章视图。通过将徽章配置为使用 Liquid Glass，徽章在显示或隐藏时可以应用变形动画效果。

## 添加修饰符以在其他视图中显示徽章

为了使徽章在其他视图（例如 `CollectionsView`）中可用，示例使用自定义修饰符 `ShowBadgesViewModifier` 作为 [ViewModifier](ViewModifier.zh-Hans.md)。该示例使用 [ZStack](ZStack.zh-Hans.md) 将徽章叠加在另一个视图之上，并将徽章视图定位在底部尾角：

```swift
private struct ShowsBadgesViewModifier: ViewModifier {
    func body(content: Content) -> some View {
        ZStack {
            content
            HStack {
                Spacer()
                VStack {
                    Spacer()
                    BadgesView()
                        .padding()
                }
            }
        }
    }
}
```

该示例通过添加 `showBadges` 修饰符来扩展 [View](View.zh-Hans.md)：

```swift
extension View {
    func showsBadges() -> some View {
        modifier(ShowsBadgesViewModifier())
    }
}
```

## 将 Liquid Glass 应用于切换按钮

为了创建切换按钮，该示例使用 `ToggleBadgesLabel` 配置 [Button](Button.zh-Hans.md)，其中 `ToggleBadgesLabel` 为“显示”和“隐藏”切换状态设置了不同的系统图像。要应用液态玻璃效果，请使用 [glass](PrimitiveButtonStyle/glass.zh-Hans.md) 修饰符设置按钮样式：

```swift
Button {
    //...
} label: {
    //...
}
.buttonStyle(.glass)

```

## 为徽章添加液态玻璃效果

要为每个徽章添加液态玻璃效果，示例使用了 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修饰符。要创建自定义玻璃视图外观，示例指定了一个带有圆角的矩形选项：

```swift
BadgeLabel(badge: $0)
    .glassEffect(.regular, in: .rect(cornerRadius: Constants.badgeCornerRadius))
```

## 使用变形效果为徽章添加动画

变形效果是液态玻璃视图的一种动画效果。在此动画过程中，切换按钮和每个徽章最初是一个组合视图。然后，按钮和徽章像液体一样改变形状，并分离移动。反向操作时，切换按钮和徽章改变形状并重新组合成一个视图。

为了实现液态玻璃变形效果，应用执行以下操作：

- 将徽章和切换按钮组织成一个 [GlassEffectContainer](GlassEffectContainer.zh-Hans.md)

- 为每个徽章添加 [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md)

- 为切换按钮添加 [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md)

- 将切换 `isExpanded` 属性的命令封装在 [withAnimation(_:_:)](withAnimation.zh-Hans.md)

```swift
// Organizes the badges and toggle button to animate together.
GlassEffectContainer(spacing: Constants.badgeGlassSpacing) {
    VStack(alignment: .center, spacing: Constants.badgeButtonTopSpacing) {
        if isExpanded {
            VStack(spacing: Constants.badgeSpacing) {
                ForEach(modelData.earnedBadges) {
                    BadgeLabel(badge: $0)
                        // Adds Liquid Glass to the badge.
                        .glassEffect(.regular, in: .rect(cornerRadius: Constants.badgeCornerRadius))
                        // Adds an identifier to the badge for animation.
                        .glassEffectID($0.id, in: namespace)
                }
            }
        }

        Button {
            // Animates this button and badges when `isExpanded` changes values.
            withAnimation {
                isExpanded.toggle()
            }
        } label: {
            ToggleBadgesLabel(isExpanded: isExpanded)
                .frame(width: Constants.badgeShowHideButtonWidth,
                       height: Constants.badgeShowHideButtonHeight)
        }
        // Adds Liquid Glass to the button.
        .buttonStyle(.glass)
        #if os(macOS)
        .tint(.clear)
        #endif
        // Adds an identifier to the button for animation.
        .glassEffectID("togglebutton", in: namespace)
    }
    .frame(width: Constants.badgeFrameWidth)
}
```

## 应用功能

- **地标：应用背景扩展效果**：配置图像以使其在侧边栏或检查器面板下模糊和扩展。

- **地标：扩展侧边栏或检查器面板下的水平滚动条**：通过在侧边栏或检查器面板下扩展水平滚动条来改善其外观。

- **重要改进：优化工具栏的液态玻璃效果**：将工具栏按相关类别分组，以提升其外观和实用性。


---
source: https://developer.apple.com/documentation/SwiftUI/Landmarks-Displaying-custom-activity-badges
crawled: 2025-12-02T15:45:37Z
---

# Landmarks: Displaying custom activity badges

**Sample Code**

Provide people with a way to mark their adventures by displaying animated custom activity badges.

## Overview

The Landmarks app lets people track their adventures as they explore sites around the world. Whether it’s a national park near their home or a far-flung location on a different continent, the app provides a way for people to mark their adventures and receive custom activity badges along the way.



This sample displays the badges in a vertical view that includes a toggle button for showing or hiding the badges. The Landmarks app includes a custom modifier that makes it easier for other views to adopt the badge view. By configuring the badges to use Liquid Glass, the badges gain the advantage of using the morphing animation when you show or hide the badges.

## Add a modifier to show badges in other views

To make the badges available in other views, like `CollectionsView`, the sample uses a custom modifier, `ShowBadgesViewModifier`, as a [ViewModifier](ViewModifier.zh-Hans.md). The sample layers the badges over another view using a [ZStack](ZStack.zh-Hans.md), and positions the badge view in the lower trailing corner:

```swift
private struct ShowsBadgesViewModifier: ViewModifier {
    func body(content: Content) -> some View {
        ZStack {
            content
            HStack {
                Spacer()
                VStack {
                    Spacer()
                    BadgesView()
                        .padding()
                }
            }
        }
    }
}
```

The sample extends [View](View.zh-Hans.md) by adding the `showBadges` modifier:

```swift
extension View {
    func showsBadges() -> some View {
        modifier(ShowsBadgesViewModifier())
    }
}
```

## Apply Liquid Glass to the toggle button

To create the toggle button, the sample configures a [Button](Button.zh-Hans.md) using `ToggleBadgesLabel` which has different system images for the Show and Hide toggle states. To apply Liquid Glass, style the button with the [glass](PrimitiveButtonStyle/glass.zh-Hans.md) modifier:

```swift
Button {
    //...
} label: {
    //...
}
.buttonStyle(.glass)

```

## Add Liquid Glass to the badges

To add Liquid Glass to each badge, the sample uses the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier. To make a custom glass view appearance, the sample specifies a rectangular option with a corner radius:

```swift
BadgeLabel(badge: $0)
    .glassEffect(.regular, in: .rect(cornerRadius: Constants.badgeCornerRadius))
```

## Animate the badges using the morph effect

The morph effect is an animation for Liquid Glass views. During this animation, the toggle button and each badge start as a combined view. Then, the button and badges change shape like a liquid as they separate and move from one location to another. In reverse, the toggle button and badges change shape and combine back into one view.

To achieve the Liquid Glass morph effect, the app:

- organizes the badges and toggle button into a [GlassEffectContainer](GlassEffectContainer.zh-Hans.md)
- adds [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md) to each badge
- adds [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md) to the toggle button
- wraps the command that toggles the `isExpanded` property in [withAnimation(_:_:)](withAnimation.zh-Hans.md)

```swift
// Organizes the badges and toggle button to animate together.
GlassEffectContainer(spacing: Constants.badgeGlassSpacing) {
    VStack(alignment: .center, spacing: Constants.badgeButtonTopSpacing) {
        if isExpanded {
            VStack(spacing: Constants.badgeSpacing) {
                ForEach(modelData.earnedBadges) {
                    BadgeLabel(badge: $0)
                        // Adds Liquid Glass to the badge.
                        .glassEffect(.regular, in: .rect(cornerRadius: Constants.badgeCornerRadius))
                        // Adds an identifier to the badge for animation.
                        .glassEffectID($0.id, in: namespace)
                }
            }
        }

        Button {
            // Animates this button and badges when `isExpanded` changes values.
            withAnimation {
                isExpanded.toggle()
            }
        } label: {
            ToggleBadgesLabel(isExpanded: isExpanded)
                .frame(width: Constants.badgeShowHideButtonWidth,
                       height: Constants.badgeShowHideButtonHeight)
        }
        // Adds Liquid Glass to the button.
        .buttonStyle(.glass)
        #if os(macOS)
        .tint(.clear)
        #endif
        // Adds an identifier to the button for animation.
        .glassEffectID("togglebutton", in: namespace)
    }
    .frame(width: Constants.badgeFrameWidth)
}
```

## App features

- **Landmarks: Applying a background extension effect**: Configure an image to blur and extend under a sidebar or inspector panel.
- **Landmarks: Extending horizontal scrolling under a sidebar or inspector**: Improve your horizontal scrollbar’s appearance by extending it under a sidebar or inspector.
- **Landmarks: Refining the system provided Liquid Glass effect in toolbars**: Organize toolbars into related groupings to improve their appearance and utility.

