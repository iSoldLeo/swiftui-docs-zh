---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/contextMenu(menuItems:)
抓取时间： 2025-12-01T10:50:45Z
---

# contextMenu(menuItems:)

**实例方法**

为标签页添加上下文菜单。

## 声明

```swift
nonisolated func contextMenu<M>(@ViewBuilder menuItems: () -> M) -> some TabContent<Self.TabValue> where M : View

```

## 参数

- **menuItems**：产生菜单内容的闭包。如果闭包不返回任何内容，则可以停用上下文菜单。

### 返回值

可以显示上下文菜单的一行。

## 讨论

使用此修改器可在标签页侧边栏中添加上下文菜单。通过返回[Button](../Button.zh-Hans.md)、[Toggle](../Toggle.zh-Hans.md) 和[Picker](../Picker.zh-Hans.md) 等控件来组成菜单。您还可以使用 [Menu](../Menu.zh-Hans.md) 定义子菜单，或使用 [Section](../Section.zh-Hans.md) 对项目进行分组。

下面的示例增加了固定标签页或与朋友共享标签页书籍的功能。

```swift
Tab("Currently Reading", systemImage: "book") {
    CurrentBooksList()
}
.contextMenu {
    Button {
        // Pin this tab.
    } label: {
        Label("Pin", systemImage: "pin")
    }
    Button {
        // Open a share sheet to share
    } label: {
        Label("Share", systemImage: "square.and.arrow.up")
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/contextMenu(menuItems:)
crawled: 2025-12-01T10:50:45Z
---

# contextMenu(menuItems:)

**Instance Method**

Adds a context menu to a tab.

## Declaration

```swift
nonisolated func contextMenu<M>(@ViewBuilder menuItems: () -> M) -> some TabContent<Self.TabValue> where M : View

```

## Parameters

- **menuItems**: A closure that produces the menu’s contents. You can deactivate the context menu by returning nothing from the closure.

## Return Value

A row that can display a context menu.

## Discussion

Use this modifier to add a context menu to a tab’s sidebar representation. Compose the menu by returning controls like [Button](../Button.zh-Hans.md), [Toggle](../Toggle.zh-Hans.md) and [Picker](../Picker.zh-Hans.md) from the `menuItems` closure. You can also use [Menu](../Menu.zh-Hans.md) to define submenus, or [Section](../Section.zh-Hans.md) to group items.

The following example adds the ability to pin the tab or share the tab’s books with a friend.

```swift
Tab("Currently Reading", systemImage: "book") {
    CurrentBooksList()
}
.contextMenu {
    Button {
        // Pin this tab.
    } label: {
        Label("Pin", systemImage: "pin")
    }
    Button {
        // Open a share sheet to share
    } label: {
        Label("Share", systemImage: "square.and.arrow.up")
    }
}
```

