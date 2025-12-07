--- 来源：https://developer.apple.com/documentation/SwiftUI/View/previewDisplayName(_:)

抓取时间：2025-12-02T17:45:59Z

---

# previewDisplayName(_:)

**实例方法**

设置预览在画布中显示的用户可见名称。

## 声明

```swift
nonisolated func previewDisplayName(_ value: String?) -> some View

```

## 参数

- **value**：预览的名称。

## 返回值

使用给定名称的预览。

## 说明

将此修饰符应用于您实现中的视图，以将显示名称与该视图的预览关联：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDisplayName("Circle")
    }
}
```

当画布中同时存在多个需要区分的预览时，添加名称。默认值为 `nil`，此时 Xcode 会显示一个默认字符串。

## 定义预览

- **Previewable()**：允许动态属性以内联方式显示在预览中的标签。

- **PreviewProvider**：用于在 Xcode 中生成视图预览的类型。

- **PreviewPlatform**：可以运行预览的平台。

- **PreviewModifier**：定义预览显示环境的类型。

- **PreviewModifierContent**：预览的已擦除类型信息的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/previewDisplayName(_:)
crawled: 2025-12-02T17:45:59Z
---

# previewDisplayName(_:)

**Instance Method**

Sets a user visible name to show in the canvas for a preview.

## Declaration

```swift
nonisolated func previewDisplayName(_ value: String?) -> some View

```

## Parameters

- **value**: A name for the preview.

## Return Value

A preview that uses the given name.

## Discussion

Apply this modifier to a view inside your [PreviewProvider](../PreviewProvider.zh-Hans.md) implementation to associate a display name with that view’s preview:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDisplayName("Circle")
    }
}
```



Add a name when you have multiple previews together in the canvas that you need to tell apart. The default value is `nil`, in which case Xcode displays a default string.

## Defining a preview

- **Previewable()**: Tag allowing a dynamic property to appear inline in a preview.
- **PreviewProvider**: A type that produces view previews in Xcode.
- **PreviewPlatform**: Platforms that can run the preview.
- **PreviewModifier**: A type that defines an environment in which previews can appear.
- **PreviewModifierContent**: The type-erased content of a preview.

