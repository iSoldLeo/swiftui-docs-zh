---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationOptions/alwaysAvailable
抓取时间： 2025-12-03T06:04:58Z
---

# 始终可用

**类型属性**

配置默认的可定制工具栏内容，使其始终出现在工具栏中。

## 声明

```swift
static var alwaysAvailable: ToolbarCustomizationOptions { get }
```

## 讨论

在 iOS 中，无论用户的定制状态如何，默认的可定制工具栏内容都可以在工具栏中使用。这些项目将始终位于工具栏的溢出菜单中。用户可以自定义这些项目是否作为控件出现在工具栏中，但如果将其从工具栏中移除，则仍可始终访问该项目。

对于用户应始终能够访问的项目，但其重要性可能不足以始终占据工具栏本身的空间时，可考虑使用此功能。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationOptions/alwaysAvailable
crawled: 2025-12-03T06:04:58Z
---

# alwaysAvailable

**Type Property**

Configures default customizable toolbar content to always be present in the toolbar.

## Declaration

```swift
static var alwaysAvailable: ToolbarCustomizationOptions { get }
```

## Discussion

In iOS, default customizable toolbar content have the option of always being available in the toolbar regardless of the customization status of the user. These items will always be in the overflow menu of the toolbar. Users can customize whether the items are present as controls in the toolbar itself but will still always be able to access the item if they remove it from the toolbar itself.

Consider using this for items that users should always be able to access, but may not be important enough to always occupy space in the toolbar itself.

