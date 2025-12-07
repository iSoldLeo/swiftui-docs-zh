--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(leading:trailing:)

抓取时间：2025-12-03T05:35:36Z

---

# navigationBarItems(leading:trailing:)

**实例方法**

设置此视图的导航栏项目。

## 声明

```swift
nonisolated func navigationBarItems<L, T>(leading: L, trailing: T) -> some View where L : View, T : View

```

## 参数

- **leading**：显示在标题栏前缘的视图。

- **trailing**：显示在标题栏后缘的视图。

## 说明

使用 `navigationBarItems(leading:trailing:)` 可将此视图的导航栏项目添加到导航栏的前缘和后缘。

此修饰符仅在此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且可见时生效。

在 iOS 14 及更高版本中，默认情况下，前导项会补充可见的返回按钮，而不是替换它。要隐藏返回按钮，请使用 [navigationBarBackButtonHidden(_:)](navigationBarBackButtonHidden.zh-Hans.md)。

以下示例在导航视图按钮区域的前缘和后缘添加按钮：

```swift
struct FlavorView: View {
    var body: some View {
        NavigationView {
            List {
                Text("Chocolate")
                Text("Vanilla")
                Text("Strawberry")
            }
            .navigationBarTitle(Text("Today‘s Flavors"))
            .navigationBarItems(leading:
                HStack {
                    Button("Hours") {
                        print("Hours tapped!")
                    }
                }, trailing:
                HStack {
                    Button("Favorites") {
                        print("Favorites tapped!")
                    }

                    Button("Specials") {
                        print("Specials tapped!")
                    }
                }
            )
        }
    }
}
```

## 辅助视图修饰符

- **navigationBarTitle(_:)**：设置此视图在导航栏中的标题。

- **navigationBarTitle(_:displayMode:)**：设置此视图在导航栏中的标题和显示模式。

- **navigationBarItems(leading:)**：设置此视图的导航栏项。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(leading:trailing:)
crawled: 2025-12-03T05:35:36Z
---

# navigationBarItems(leading:trailing:)

**Instance Method**

Sets the navigation bar items for this view.

## Declaration

```swift
nonisolated func navigationBarItems<L, T>(leading: L, trailing: T) -> some View where L : View, T : View

```

## Parameters

- **leading**: A view that appears on the leading edge of the title.
- **trailing**: A view that appears on the trailing edge of the title.

## Discussion

Use `navigationBarItems(leading:trailing:)` to add navigation bar items to the leading and trailing edges of the navigation bar for this view.

This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

On iOS 14 and later, the leading item supplements a visible back button, instead of replacing it, by default. To hide the back button, use [navigationBarBackButtonHidden(_:)](navigationBarBackButtonHidden.zh-Hans.md).

The example below adds buttons to the leading and trailing edges of the button area of the navigation view:

```swift
struct FlavorView: View {
    var body: some View {
        NavigationView {
            List {
                Text("Chocolate")
                Text("Vanilla")
                Text("Strawberry")
            }
            .navigationBarTitle(Text("Today‘s Flavors"))
            .navigationBarItems(leading:
                HStack {
                    Button("Hours") {
                        print("Hours tapped!")
                    }
                }, trailing:
                HStack {
                    Button("Favorites") {
                        print("Favorites tapped!")
                    }

                    Button("Specials") {
                        print("Specials tapped!")
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
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

