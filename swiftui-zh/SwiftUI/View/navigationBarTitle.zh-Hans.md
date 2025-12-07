--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarTitle(_:)

抓取时间：2025-12-03T05:35:34Z

---

# navigationBarTitle(_:)

**实例方法**

设置此视图在导航栏中的标题。

## 声明

```swift
nonisolated func navigationBarTitle(_ title: Text) -> some View

```

## 参数

- **title**：要在导航栏中显示的此视图的描述。

## 说明

使用 `navigationBarTitle(_:)` 设置导航栏的标题。此修饰符仅在此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该视图可见时生效。

以下示例展示了如何使用 [Text](../Text.zh-Hans.md) 视图设置导航栏标题：

```swift
struct FlavorView: View {
    let items = ["Chocolate", "Vanilla", "Strawberry", "Mint Chip",
                 "Pistachio"]
    var body: some View {
        NavigationView {
            List(items, id: \.self) {
                Text($0)
            }
            .navigationBarTitle(Text("Today's Flavors"))
        }
    }
}
```

## 辅助视图修饰符

- **navigationBarTitle(_:displayMode:)**：设置此视图导航栏的标题和显示模式。

- **navigationBarItems(leading:)**：设置此视图的导航栏项目。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项目。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarTitle(_:)
crawled: 2025-12-03T05:35:34Z
---

# navigationBarTitle(_:)

**Instance Method**

Sets the title in the navigation bar for this view.

## Declaration

```swift
nonisolated func navigationBarTitle(_ title: Text) -> some View

```

## Parameters

- **title**: A description of this view to display in the navigation bar.

## Discussion

Use `navigationBarTitle(_:)` to set the title of the navigation bar. This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

The example below shows setting the title of the navigation bar using a [Text](../Text.zh-Hans.md) view:

```swift
struct FlavorView: View {
    let items = ["Chocolate", "Vanilla", "Strawberry", "Mint Chip",
                 "Pistachio"]
    var body: some View {
        NavigationView {
            List(items, id: \.self) {
                Text($0)
            }
            .navigationBarTitle(Text("Today's Flavors"))
        }
    }
}
```



## Auxiliary view modifiers

- **navigationBarTitle(_:displayMode:)**: Sets the title and display mode in the navigation bar for this view.
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

