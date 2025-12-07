--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarHidden(_:)

抓取时间：2025-12-03T05:35:38Z

---

# navigationBarHidden(_:)

**实例方法**

隐藏此视图的导航栏。

## 声明

```swift
nonisolated func navigationBarHidden(_ hidden: Bool) -> some View

```

## 参数

- **hidden**：一个布尔值，指示是否隐藏导航栏。

## 说明

使用此方法隐藏导航栏。此修饰符仅在被修改的视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该 [NavigationView](../NavigationView.zh-Hans.md) 内可见时生效。

## 辅助视图修饰符

- **navigationBarTitle(_:)**：设置此视图导航栏的标题。

- **navigationBarTitle(_:displayMode:)**：设置此视图导航栏的标题和显示模式。

- **navigationBarItems(leading:)**：设置此视图的导航栏项目。

- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目。

- **navigationBarItems(trailing:)**：配置此视图的导航栏项目。

- **statusBar(hidden:)**：设置状态栏的可见性。

- **contextMenu(_:)**：向视图添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarHidden(_:)
crawled: 2025-12-03T05:35:38Z
---

# navigationBarHidden(_:)

**Instance Method**

Hides the navigation bar for this view.

## Declaration

```swift
nonisolated func navigationBarHidden(_ hidden: Bool) -> some View

```

## Parameters

- **hidden**: A Boolean value that indicates whether to hide the navigation bar.

## Discussion

Use this method to hide the navigation bar. This modifier only takes effect when the modified view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

## Auxiliary view modifiers

- **navigationBarTitle(_:)**: Sets the title in the navigation bar for this view.
- **navigationBarTitle(_:displayMode:)**: Sets the title and display mode in the navigation bar for this view.
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

