--- 来源：https://developer.apple.com/documentation/SwiftUI/PreviewProvider
抓取时间：2025-12-02T17:45:56Z

---

# PreviewProvider

**Protocol**

一种用于在 Xcode 中生成视图预览的类型。

## 声明

```swift
@MainActor @preconcurrency protocol PreviewProvider : _PreviewProvider
```

## 概述

您可以通过声明一个符合 `PreviewProvider` 协议的结构来创建 Xcode 预览。实现所需的 [previews-swift.type.property](PreviewProvider/previews-swift_type_property.zh-Hans.md) 计算属性，并返回要显示的视图：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }
}
```

Xcode 会静态地发现项目中的预览提供程序，并为源代码编辑器中当前打开的任何提供程序生成预览。Xcode 会使用当前运行目标作为提示，确定要显示的设备。例如，如果您选择在 iPhone 12 Pro Max 模拟器上运行 iOS 目标，Xcode 将显示以下预览：

当您创建新文件（文件 > 新建 > 文件）并选择 SwiftUI 视图模板时，Xcode 会自动在文件底部插入一个可配置的预览结构。您也可以通过选择“编辑器”>“创建预览”在现有的 SwiftUI 视图文件中创建新的预览结构。

您可以像构建自定义视图时一样，通过添加视图修饰符来自定义预览的外观。这包括预览特有的修饰符，可用于控制预览的各个方面，例如设备方向：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeLeft)
    }
}
```

有关预览自定义项的完整列表，请参阅 [Previews-in-Xcode](Previews-in-Xcode.zh-Hans.md)。

Xcode 会为预览中的每个视图创建不同的预览，以便您可以并排查看不同的视图。例如，您可能希望同时查看视图的浅色和深色外观：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
        CircleImage()
            .preferredColorScheme(.dark)
    }
}
```

如果您希望保持不同的预览效果，但对所有预览应用同一个修饰符，请使用 [Group](Group.zh-Hans.md)：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        Group {
            CircleImage()
            CircleImage()
                .preferredColorScheme(.dark)
        }
        .previewLayout(.sizeThatFits)
    }
}
```

## 创建预览

- **previews**：要预览的视图集合。

- **Previews**：要预览的类型。

## 指定平台

- **platform**：运行提供程序的平台。

## 定义预览

- **Previewable()**：允许动态属性以内联方式显示在预览中的标签。

- **PreviewPlatform**：可以运行预览的平台。

- **previewDisplayName(_:)**：设置预览画布上显示的用户可见名称。

- **PreviewModifier**：定义预览显示环境的类型。

- **PreviewModifierContent**：预览中已擦除文字的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewProvider
crawled: 2025-12-02T17:45:56Z
---

# PreviewProvider

**Protocol**

A type that produces view previews in Xcode.

## Declaration

```swift
@MainActor @preconcurrency protocol PreviewProvider : _PreviewProvider
```

## Overview



You can create an Xcode preview by declaring a structure that conforms to the `PreviewProvider` protocol. Implement the required [previews-swift.type.property](PreviewProvider/previews-swift_type_property.zh-Hans.md) computed property, and return the view to display:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }
}
```

Xcode statically discovers preview providers in your project and generates previews for any providers currently open in the source editor. Xcode generates the preview using the current run destination as a hint for which device to display. For example, Xcode shows the following preview if you’ve selected an iOS target to run on the iPhone 12 Pro Max simulator:



When you create a new file (File > New > File) and choose the SwiftUI view template, Xcode automatically inserts a preview structure at the bottom of the file that you can configure. You can also create new preview structures in an existing SwiftUI view file by choosing Editor > Create Preview.

Customize the preview’s appearance by adding view modifiers, just like you do when building a custom [View](View.zh-Hans.md). This includes preview-specific modifiers that let you control aspects of the preview, like the device orientation:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeLeft)
    }
}
```



For the complete list of preview customizations, see [Previews-in-Xcode](Previews-in-Xcode.zh-Hans.md).

Xcode creates different previews for each view in your preview, so you can see variations side by side. For example, you might want to see a view’s light and dark appearances simultaneously:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
        CircleImage()
            .preferredColorScheme(.dark)
    }
}
```

Use a [Group](Group.zh-Hans.md) when you want to maintain different previews, but apply a single modifier to all of them:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        Group {
            CircleImage()
            CircleImage()
                .preferredColorScheme(.dark)
        }
        .previewLayout(.sizeThatFits)
    }
}
```



## Creating a preview

- **previews**: A collection of views to preview.
- **Previews**: The type to preview.

## Specifying the platform

- **platform**: The platform on which to run the provider.

## Defining a preview

- **Previewable()**: Tag allowing a dynamic property to appear inline in a preview.
- **PreviewPlatform**: Platforms that can run the preview.
- **previewDisplayName(_:)**: Sets a user visible name to show in the canvas for a preview.
- **PreviewModifier**: A type that defines an environment in which previews can appear.
- **PreviewModifierContent**: The type-erased content of a preview.

