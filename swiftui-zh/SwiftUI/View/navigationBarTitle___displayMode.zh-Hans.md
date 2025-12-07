--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarTitle(_:displayMode:)

抓取时间：2025-12-03T05:35:34Z

---

# navigationBarTitle(_:displayMode:)

**实例方法**

设置此视图导航栏的标题和显示模式。

## 声明

```swift
nonisolated func navigationBarTitle(_ title: Text, displayMode: NavigationBarItem.TitleDisplayMode) -> some View

```

## 参数

- **title**：此视图在导航栏中显示的标题。

- **displayMode**：用于显示导航栏标题的样式。

## 说明

使用 `navigationBarTitle(_:displayMode:)` 设置此视图的导航栏标题，并从 [TitleDisplayMode](../NavigationBarItem/TitleDisplayMode.zh-Hans.md) 样式中指定标题的显示模式。此修饰符仅当此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该视图中可见时生效。

在下面的示例中，导航栏标题的文本由 [Text](../Text.zh-Hans.md) 视图提供。导航栏标题的 [TitleDisplayMode](../NavigationBarItem/TitleDisplayMode.zh-Hans.md) 设置为 `.inline`，这会将导航栏标题放置在导航栏的边界内。

```swift
struct FlavorView: View {
   let items = ["Chocolate", "Vanilla", "Strawberry", "Mint Chip",
                "Pistachio"]
   var body: some View {
        NavigationView {
            List(items, id: \.self) {
                Text($0)
            }
            .navigationBarTitle(Text("Today's Flavors", displayMode: .inline))
        }
    }
}
```

## 辅助视图修饰符

- **navigationBarTitle(_:)**：设置此视图的导航栏标题。

- **navigationBarItems(leading:)**：设置此视图的导航栏项目。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项目。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarTitle(_:displayMode:)
crawled: 2025-12-03T05:35:34Z
---

# navigationBarTitle(_:displayMode:)

**Instance Method**

Sets the title and display mode in the navigation bar for this view.

## Declaration

```swift
nonisolated func navigationBarTitle(_ title: Text, displayMode: NavigationBarItem.TitleDisplayMode) -> some View

```

## Parameters

- **title**: A title for this view to display in the navigation bar.
- **displayMode**: The style to use for displaying the navigation bar title.

## Discussion

Use `navigationBarTitle(_:displayMode:)` to set the title of the navigation bar for this view and specify a display mode for the title from one of the [TitleDisplayMode](../NavigationBarItem/TitleDisplayMode.zh-Hans.md) styles. This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

In the example below, text for the navigation bar title is provided using a [Text](../Text.zh-Hans.md) view. The navigation bar title’s [TitleDisplayMode](../NavigationBarItem/TitleDisplayMode.zh-Hans.md) is set to `.inline` which places the navigation bar title in the bounds of the navigation bar.

```swift
struct FlavorView: View {
   let items = ["Chocolate", "Vanilla", "Strawberry", "Mint Chip",
                "Pistachio"]
   var body: some View {
        NavigationView {
            List(items, id: \.self) {
                Text($0)
            }
            .navigationBarTitle(Text("Today's Flavors", displayMode: .inline))
        }
    }
}
```

## Auxiliary view modifiers

- **navigationBarTitle(_:)**: Sets the title in the navigation bar for this view.
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

