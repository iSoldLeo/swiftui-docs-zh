--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(leading:)

抓取时间：2025-12-03T05:35:35Z

---

# navigationBarItems(leading:)

**实例方法**

设置此视图的导航栏项目。

## 声明

```swift
nonisolated func navigationBarItems<L>(leading: L) -> some View where L : View

```

## 参数

- **leading**：显示在标题栏前缘的视图。

## 说明

使用 `navigationBarItems(leading:)` 可将此视图的导航栏项目添加到导航栏的前缘。

此修饰符仅在此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该视图中可见时生效。

在 iOS 14 及更高版本中，默认情况下，导航栏顶部的按钮会作为可见返回按钮的补充，而不是替换它。要隐藏返回按钮，请使用 [navigationBarBackButtonHidden(_:)](navigationBarBackButtonHidden.zh-Hans.md)。

以下示例在导航视图按钮区域的前缘添加按钮：

```swift
struct FlavorView: View {
    var body: some View {
        NavigationView {
            List {
                Text("Chocolate")
                Text("Vanilla")
                Text("Strawberry")
            }
            .navigationBarTitle(Text("Today's Flavors"))
            .navigationBarItems(leading:
                HStack {
                    Button("Hours") {
                        print("Hours tapped!")
                    }

                    Button("Help") {
                        print("Help tapped!")
                    }
                }
            )
        }
    }
}
```

## 辅助视图修饰符

- **navigationBarTitle(_:)**：设置此视图导航栏的标题。

- **navigationBarTitle(_:displayMode:)**：设置此视图导航栏的标题和显示模式。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项目。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(leading:)
crawled: 2025-12-03T05:35:35Z
---

# navigationBarItems(leading:)

**Instance Method**

Sets the navigation bar items for this view.

## Declaration

```swift
nonisolated func navigationBarItems<L>(leading: L) -> some View where L : View

```

## Parameters

- **leading**: A view that appears on the leading edge of the title.

## Discussion

Use `navigationBarItems(leading:)` to add navigation bar items to the leading edge of the navigation bar for this view.

This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

On iOS 14 and later, the leading item supplements a visible back button, instead of replacing it, by default. To hide the back button, use [navigationBarBackButtonHidden(_:)](navigationBarBackButtonHidden.zh-Hans.md).

The example below adds buttons to the leading edge of the button area of the navigation view:

```swift
struct FlavorView: View {
    var body: some View {
        NavigationView {
            List {
                Text("Chocolate")
                Text("Vanilla")
                Text("Strawberry")
            }
            .navigationBarTitle(Text("Today's Flavors"))
            .navigationBarItems(leading:
                HStack {
                    Button("Hours") {
                        print("Hours tapped!")
                    }

                    Button("Help") {
                        print("Help tapped!")
                    }
                }
            )
        }
    }
}
```

## Auxiliary view modifiers

- **navigationBarTitle(_:)**: Sets the title in the navigation bar for this view.
- **navigationBarTitle(_:displayMode:)**: Sets the title and display mode in the navigation bar for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

