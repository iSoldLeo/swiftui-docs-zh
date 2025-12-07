---
来源： https://developer.apple.com/documentation/SwiftUI/PreviewProvider/previews-swift.type.property
抓取时间： 2025-12-03T07:07:12Z
---

# 预览

**类型属性**

要预览的视图集合。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency static var previews: Self.Previews { get }
```

## 讨论

实现一个计算的 `previews` 属性，以指示要预览的内容。Xcode 会为您列出的每个视图生成一个预览。您可以向视图应用[View](../View.zh-Hans.md)修饰符，就像创建自定义视图时一样。对于预览，您还可以使用各种特定于预览的修饰符来自定义预览。例如，通过添加[previewDevice(_:)](../View/previewDevice.zh-Hans.md)修饰符，可以为预览选择特定的设备：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

有关预览专用修饰符的完整列表，请参见 [Previews-in-Xcode](../Previews-in-Xcode.zh-Hans.md)。

## 创建预览

- **Previews**：要预览的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewProvider/previews-swift.type.property
crawled: 2025-12-03T07:07:12Z
---

# previews

**Type Property**

A collection of views to preview.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency static var previews: Self.Previews { get }
```

## Discussion

Implement a computed `previews` property to indicate the content to preview. Xcode generates a preview for each view that you list. You can apply [View](../View.zh-Hans.md) modifiers to the views, like you do when creating a custom view. For a preview, you can also use various preview-specific modifiers that customize the preview. For example, you can choose a specific device for the preview by adding the [previewDevice(_:)](../View/previewDevice.zh-Hans.md) modifier:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

For the full list of preview-specific modifiers, see [Previews-in-Xcode](../Previews-in-Xcode.zh-Hans.md).

## Creating a preview

- **Previews**: The type to preview.

