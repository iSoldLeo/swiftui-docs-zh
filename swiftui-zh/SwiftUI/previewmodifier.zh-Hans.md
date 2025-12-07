--- 来源：https://developer.apple.com/documentation/swiftui/previewmodifier
抓取时间：2025-12-04T13:58:27Z

---

# PreviewModifier

**Protocol**

定义预览显示环境的类型。

## 声明

```swift
@MainActor protocol PreviewModifier
```

## 概述

符合规范的类型可以定义共享上下文，这些上下文将被预览系统缓存，并在参与预览的视图之间重复使用。例如，您可以在此处创建一个模型容器，并填充示例数据；然后在您的 `body` 方法中，您可以使用 `.modelContainer` 视图修饰符将其应用到预览中。

```swift
struct SampleData: PreviewModifier {
    static func makeSharedContext() throws -> ModelContainer {
        let container = try ModelContainer(for: Snack.self)
        container.mainContext.insert(Snack.potatoChips)
        return container
    }

    func body(content: Content, context: ModelContainer) -> some View {
        content.modelContainer(context)
    }
 }
```

使用 `.modifier` 预览特性为预览附加修饰符。

```swift
#Preview(traits: .modifier(SampleData())) {
    @Previewable @Query var snacks: [Snack]
    return SnackView(snack: snacks.first!)
}
```

## 关联类型

- **Body**

- **Context**

## 实例方法

- **body(content:context:)**：通过应用共享上下文来修改预览。

## 类型别名

- **PreviewModifier.Content**：预览的已擦除类型的内容。

## 类型方法

- **makeSharedContext()**：创建要应用于预览的共享上下文。此处返回的上下文将被缓存，并传递给应用此类型修饰符的每个预览的 `body` 方法。

## 定义预览

- **Previewable()**：允许动态属性在预览中以内联方式显示的标签。

- **PreviewProvider**：在 Xcode 中生成视图预览的类型。

- **PreviewPlatform**：可以运行预览的平台。

- **previewDisplayName(_:)**：设置要在预览画布中显示的用户可见名称。

- **PreviewModifierContent**：预览中已擦除类型的内容。


---
source: https://developer.apple.com/documentation/swiftui/previewmodifier
crawled: 2025-12-04T13:58:27Z
---

# PreviewModifier

**Protocol**

A type that defines an environment in which previews can appear.

## Declaration

```swift
@MainActor protocol PreviewModifier
```

## Overview

Conforming types can define shared contexts that will be cached by the preview system, then reused across participating previews. For example, you might create a model container here and populate it with sample data; in your `body` method you would then apply it to the preview using the `.modelContainer` view modifier.

```swift
struct SampleData: PreviewModifier {
    static func makeSharedContext() throws -> ModelContainer {
        let container = try ModelContainer(for: Snack.self)
        container.mainContext.insert(Snack.potatoChips)
        return container
    }

    func body(content: Content, context: ModelContainer) -> some View {
        content.modelContainer(context)
    }
 }
```

Use the `.modifier` preview trait to attach modifiers to a preview.

```swift
#Preview(traits: .modifier(SampleData())) {
    @Previewable @Query var snacks: [Snack]
    return SnackView(snack: snacks.first!)
}
```

## Associated Types

- **Body**
- **Context**

## Instance Methods

- **body(content:context:)**: Modify a preview by applying the shared context.

## Type Aliases

- **PreviewModifier.Content**: The type-erased content of a preview.

## Type Methods

- **makeSharedContext()**: Create shared context to apply to previews. The context returned here will be cached and passed into the `body` method for every preview that applies a modifier of this type.

## Defining a preview

- **Previewable()**: Tag allowing a dynamic property to appear inline in a preview.
- **PreviewProvider**: A type that produces view previews in Xcode.
- **PreviewPlatform**: Platforms that can run the preview.
- **previewDisplayName(_:)**: Sets a user visible name to show in the canvas for a preview.
- **PreviewModifierContent**: The type-erased content of a preview.

