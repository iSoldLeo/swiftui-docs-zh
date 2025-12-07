--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contextMenu(_:)

抓取时间：2025-12-01T10:24:47Z

---

# contextMenu(_:)

**实例方法**

向视图添加上下文菜单。

## 声明

```swift
nonisolated func contextMenu<MenuItems>(_ contextMenu: ContextMenu<MenuItems>?) -> some View where MenuItems : View

```

## 参数

- **contextMenu**：用于将视图作为菜单项显示在上下文菜单中的上下文菜单容器。

## 返回值

一个可以显示上下文菜单的视图。

## 说明

使用此方法将指定的上下文菜单附加到视图。您可以通过有条件地将 `nil` 作为 `contextMenu` 的值来禁用上下文菜单。

以下示例创建了一个包含两个项目的 [ContextMenu](../ContextMenu.zh-Hans.md)，并将它们传递给修饰符。布尔值 `shouldShowMenu`（默认值为 `true`）控制上下文菜单的可用性：

```swift
private let menuItems = ContextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
    Button {
        // Open Maps and center it on this item.
    } label: {
        Label("Show in Maps", systemImage: "mappin")
    }
}

private struct ContextMenuMenuItems: View {
    @State private var shouldShowMenu = true

    var body: some View {
        Text("Turtle Rock")
            .contextMenu(shouldShowMenu ? menuItems : nil)
    }
}
```

## 辅助视图修饰符

- **navigationBarTitle(_:)**：设置此视图导航栏中的标题。

- **navigationBarTitle(_:displayMode:)**：设置此视图导航栏中的标题和显示模式。

- **navigationBarItems(leading:)**：设置此视图的导航栏项目。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项目。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contextMenu(_:)
crawled: 2025-12-01T10:24:47Z
---

# contextMenu(_:)

**Instance Method**

Adds a context menu to the view.

## Declaration

```swift
nonisolated func contextMenu<MenuItems>(_ contextMenu: ContextMenu<MenuItems>?) -> some View where MenuItems : View

```

## Parameters

- **contextMenu**: A context menu container for views that you present as menu items in a context menu.

## Return Value

A view that can show a context menu.

## Discussion

Use this method to attach a specified context menu to a view. You can make the context menu unavailable by conditionally passing `nil` as the value for the `contextMenu`.

The example below creates a [ContextMenu](../ContextMenu.zh-Hans.md) that contains two items and passes them into the modifier. The Boolean value `shouldShowMenu`, which defaults to `true`, controls the context menu availability:

```swift
private let menuItems = ContextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
    Button {
        // Open Maps and center it on this item.
    } label: {
        Label("Show in Maps", systemImage: "mappin")
    }
}

private struct ContextMenuMenuItems: View {
    @State private var shouldShowMenu = true

    var body: some View {
        Text("Turtle Rock")
            .contextMenu(shouldShowMenu ? menuItems : nil)
    }
}
```



## Auxiliary view modifiers

- **navigationBarTitle(_:)**: Sets the title in the navigation bar for this view.
- **navigationBarTitle(_:displayMode:)**: Sets the title and display mode in the navigation bar for this view.
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.

