--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:image:isInserted:content:)

抓取时间：2025-12-01T10:20:29Z

---

# init(_:image:isInserted:content:)

**Initializer**

创建一个菜单栏附加组件，并使用图片作为项目标签。提供的标题将由辅助功能系统使用。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：用于项目辅助功能标签的本地化字符串键。

- **image**：用作标签的图片资源。

- **isInserted**：项目是否插入到菜单栏中。根据现有项目数量，该项目可能可见，也可能不可见。

- **content**：用户选择该项目时显示的 `View`。

## 讨论

当指定的绑定设置为 `true` 时，该项目将显示在系统菜单栏中。如果用户从菜单栏中移除该项目，则绑定将设置为 `false`。

## 创建带有图像的菜单栏附加项

- **init(_:image:content:)**：创建一个带有图像的菜单栏附加项，该图像将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:content:)**：创建一个带有系统图像的菜单栏附加项，该图像将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:isInserted:content:)**：创建一个菜单栏附加组件，并使用系统图像作为项目标签。提供的标题将由辅助功能系统使用。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:image:isInserted:content:)
crawled: 2025-12-01T10:20:29Z
---

# init(_:image:isInserted:content:)

**Initializer**

Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The localized string key to use for the accessibility label of the item.
- **image**: The image resource to use as the label.
- **isInserted**: Whether the item is inserted in the menu bar. The item may or may not be visible, depending on the number of items present.
- **content**: A `View` to display when the user selects the item.

## Discussion

The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

## Creating a menu bar extra with an image

- **init(_:image:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:isInserted:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.

