--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:systemImage:isInserted:content:)

抓取时间：2025-12-01T10:20:31Z

---

# init(_:systemImage:isInserted:content:)

**Initializer**

创建一个菜单栏附加组件，并使用系统图像作为项目标签。提供的标题将由辅助功能系统使用。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：用于项目辅助功能标签的本地化字符串键。

- **systemImage**：要用作标签的系统图像的名称。

- **isInserted**：菜单项是否插入菜单栏。菜单项是否可见取决于菜单项的数量。

- **content**：用户选择菜单项时显示的 `View`。

## 讨论

当指定的绑定设置为 `true` 时，菜单项将显示在系统菜单栏中。如果用户从菜单栏中移除菜单项，则绑定将设置为 `false`。

## 创建带有图像的菜单栏附加项

- **init(_:image:content:)**：创建一个带有图像的菜单栏附加项，该图像将用作菜单项的标签。提供的标题将由辅助功能系统使用。

- **init(_:image:isInserted:content:)**：创建一个带有图像的菜单栏附加项，该图像将用作菜单项的标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:content:)**：创建一个带有系统图像的菜单栏附加项，用作项目标签。提供的标题将由辅助功能系统使用。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:systemImage:isInserted:content:)
crawled: 2025-12-01T10:20:31Z
---

# init(_:systemImage:isInserted:content:)

**Initializer**

Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The localized string key to use for the accessibility label of the item.
- **systemImage**: The name of a system image to use as the label.
- **isInserted**: Whether the item is inserted in the menu bar. The item may or may not be visible, depending on the number of items present.
- **content**: A `View` to display when the user selects the item.

## Discussion

The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

## Creating a menu bar extra with an image

- **init(_:image:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:image:isInserted:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.

