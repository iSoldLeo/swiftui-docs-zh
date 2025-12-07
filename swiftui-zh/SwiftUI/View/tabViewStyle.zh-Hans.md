--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabViewStyle(_:)

抓取时间：2025-11-30T21:14:45Z

---

# tabViewStyle(_:)

**实例方法**

设置当前环境中标签视图的样式。

## 声明

```swift
nonisolated func tabViewStyle<S>(_ style: S) -> some View where S : TabViewStyle

```

## 参数

- **style**：要应用于此标签视图的样式。

## 在标签页中呈现视图

- **使用标签导航增强应用内容**：将应用内容置于中心位置，同时使用标签栏快速访问导航。

- **TabView**：使用交互式用户界面元素在多个子视图之间切换的视图。

- **Tab**：选项卡视图中选项卡及其关联选项卡项的内容。

- **TabRole**：定义选项卡用途的值。

- **TabSection**：可用于在选项卡视图中添加层级结构的容器。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabViewStyle(_:)
crawled: 2025-11-30T21:14:45Z
---

# tabViewStyle(_:)

**Instance Method**

Sets the style for the tab view within the current environment.

## Declaration

```swift
nonisolated func tabViewStyle<S>(_ style: S) -> some View where S : TabViewStyle

```

## Parameters

- **style**: The style to apply to this tab view.

## Presenting views in tabs

- **Enhancing your app’s content with tab navigation**: Keep your app content front and center while providing quick access to navigation using the tab bar.
- **TabView**: A view that switches between multiple child views using interactive user interface elements.
- **Tab**: The content for a tab and the tab’s associated tab item in a tab view.
- **TabRole**: A value that defines the purpose of the tab.
- **TabSection**: A container that you can use to add hierarchy within a tab view.

