--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(trailing:)

抓取时间：2025-12-01T10:24:45Z

---

# navigationBarItems(trailing:)

**实例方法**

配置此视图的导航栏项目。

## 声明

```swift
nonisolated func navigationBarItems<T>(trailing: T) -> some View where T : View

```

## 参数

- **trailing**：显示在标题栏尾部的视图。

## 说明

使用 `navigationBarItems(trailing:)` 可将此视图的导航栏项目添加到导航栏的尾部。此修饰符仅在此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该视图中可见时生效。

以下示例在导航视图的按钮区域后缘添加按钮：

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
            .navigationBarItems(trailing:
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

- **navigationBarItems(leading:)**：设置此视图的导航栏项目。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarHidden(_:)**：隐藏此视图的导航栏。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarItems(trailing:)
crawled: 2025-12-01T10:24:45Z
---

# navigationBarItems(trailing:)

**Instance Method**

Configures the navigation bar items for this view.

## Declaration

```swift
nonisolated func navigationBarItems<T>(trailing: T) -> some View where T : View

```

## Parameters

- **trailing**: A view shown on the trailing edge of the title.

## Discussion

Use `navigationBarItems(trailing:)` to add navigation bar items to the trailing edge of the navigation bar for this view. This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

The example below adds buttons to the trailing edge of the button area of the navigation view:

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
            .navigationBarItems(trailing:
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
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

