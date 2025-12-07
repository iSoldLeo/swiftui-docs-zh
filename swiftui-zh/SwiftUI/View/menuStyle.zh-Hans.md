--- 来源：https://developer.apple.com/documentation/SwiftUI/View/menuStyle(_:)

抓取时间：2025-12-02T17:33:07Z

---

# menuStyle(_:)

**实例方法**

设置此视图中菜单的样式。

## 声明

```swift
nonisolated func menuStyle<S>(_ style: S) -> some View where S : MenuStyle

```

## 讨论

要为视图中的所有菜单实例设置特定样式，请使用 `menuStyle(_:)` 修饰符：

```swift
Menu("PDF") {
    Button("Open in Preview", action: openInPreview)
    Button("Save as PDF", action: saveAsPDF)
}
.menuStyle(ButtonMenuStyle())
```

## 创建菜单

- **使用自适应控件填充 SwiftUI 菜单**：通过在菜单中填充控件并以直观的方式组织内容来改进您的应用。

- **Menu**：用于显示操作菜单的控件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/menuStyle(_:)
crawled: 2025-12-02T17:33:07Z
---

# menuStyle(_:)

**Instance Method**

Sets the style for menus within this view.

## Declaration

```swift
nonisolated func menuStyle<S>(_ style: S) -> some View where S : MenuStyle

```

## Discussion

To set a specific style for all menu instances within a view, use the `menuStyle(_:)` modifier:

```swift
Menu("PDF") {
    Button("Open in Preview", action: openInPreview)
    Button("Save as PDF", action: saveAsPDF)
}
.menuStyle(ButtonMenuStyle())
```

## Creating a menu

- **Populating SwiftUI menus with adaptive controls**: Improve your app by populating menus with controls and organizing your content intuitively.
- **Menu**: A control for presenting a menu of actions.

