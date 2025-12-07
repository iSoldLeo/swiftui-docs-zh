--- 来源：https://developer.apple.com/documentation/SwiftUI/Previewable()

抓取时间：2025-12-02T17:45:56Z

---

# Previewable()

**Macro**

允许动态属性在预览中以内联方式显示的标签。

## 声明

```swift
@attached(peer) macro Previewable()
```

## 概述

在根作用域的 SwiftUI 代码体中使用 `@Previewable` 标签声明变量，即可在预览中以内联方式使用动态属性。`#Preview` 宏会生成一个嵌入式 SwiftUI 视图；被标记的声明会成为该视图的属性，其余语句构成视图的主体。

```swift
#Preview("toggle") {
    @Previewable @State var toggled = true
    return Toggle("Loud Noises", isOn: $toggled)
}
```

在 `#Preview` 主体闭包之外使用 `@Previewable` 是错误的。

## 定义预览

- **PreviewProvider**：一种在 Xcode 中生成视图预览的类型。

- **PreviewPlatform**：可以运行预览的平台。

- **previewDisplayName(_:)**：设置预览画布中显示的用户可见名称。

- **PreviewModifier**：一种定义预览可以显示的环境的类型。

- **PreviewModifierContent**：预览的已擦除类型信息的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Previewable()
crawled: 2025-12-02T17:45:56Z
---

# Previewable()

**Macro**

Tag allowing a dynamic property to appear inline in a preview.

## Declaration

```swift
@attached(peer) macro Previewable()
```

## Overview

Tagging a variable declaration at root scope in your `#Preview` body with ‘@Previewable’ allows you to use dynamic properties inline in previews. The `#Preview` macro will generate an embedded SwiftUI view; tagged declarations become properties on the view, and all remaining statements form the view’s body.

```swift
#Preview("toggle") {
    @Previewable @State var toggled = true
    return Toggle("Loud Noises", isOn: $toggled)
}
```

It is an error to use `@Previewable` outside of a `#Preview` body closure.

## Defining a preview

- **PreviewProvider**: A type that produces view previews in Xcode.
- **PreviewPlatform**: Platforms that can run the preview.
- **previewDisplayName(_:)**: Sets a user visible name to show in the canvas for a preview.
- **PreviewModifier**: A type that defines an environment in which previews can appear.
- **PreviewModifierContent**: The type-erased content of a preview.

