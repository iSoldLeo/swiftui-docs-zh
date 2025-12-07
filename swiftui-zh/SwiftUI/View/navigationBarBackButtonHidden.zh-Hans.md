--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationBarBackButtonHidden(_:)

抓取时间：2025-11-30T21:14:40Z

---

# navigationBarBackButtonHidden(_:)

**实例方法**

隐藏视图的导航栏返回按钮。

## 声明

```swift
nonisolated func navigationBarBackButtonHidden(_ hidesBackButton: Bool = true) -> some View

```

## 参数

- **hidesBackButton**：一个布尔值，指示是否隐藏返回按钮。默认值为 `true`。

## 说明

使用 `navigationBarBackButtonHidden(_:)` 隐藏此视图的返回按钮。

此修饰符仅在此视图位于 [NavigationView](../NavigationView.zh-Hans.md) 内且在该 [NavigationView](../NavigationView.zh-Hans.md) 内可见时生效。

## 配置导航栏

- **navigationBarTitleDisplayMode(_:)**：配置此视图的标题显示模式。

- **NavigationBarItem**：用于配置位于导航堆栈顶部的视图的导航栏。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationBarBackButtonHidden(_:)
crawled: 2025-11-30T21:14:40Z
---

# navigationBarBackButtonHidden(_:)

**Instance Method**

Hides the navigation bar back button for the view.

## Declaration

```swift
nonisolated func navigationBarBackButtonHidden(_ hidesBackButton: Bool = true) -> some View

```

## Parameters

- **hidesBackButton**: A Boolean value that indicates whether to hide the back button. The default value is `true`.

## Discussion

Use `navigationBarBackButtonHidden(_:)` to hide the back button for this view.

This modifier only takes effect when this view is inside of and visible within a [NavigationView](../NavigationView.zh-Hans.md).

## Configuring the navigation bar

- **navigationBarTitleDisplayMode(_:)**: Configures the title display mode for this view.
- **NavigationBarItem**: A configuration for a navigation bar that represents a view at the top of a navigation stack.

