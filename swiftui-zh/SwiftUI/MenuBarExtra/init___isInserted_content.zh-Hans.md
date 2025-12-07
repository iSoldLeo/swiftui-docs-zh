--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:isInserted:content:)

抓取时间：2025-12-03T05:31:21Z

---

# init(_:isInserted:content:)

**Initializer**

创建一个菜单栏附加项，其标签为本地化字符串。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：用于该项标签的标题键。

- **isInserted**：菜单项是否插入菜单栏。菜单项是否可见取决于菜单项的数量。

- **content**：用户选择菜单项时显示的 `View`。

## 创建菜单栏附加项

- **init(_:content:)**：创建一个菜单栏附加项，其键值是一个本地化字符串，用作标签。该附加项定义了 `App` 的主场景。

- **init(content:label:)**：创建一个将显示在系统菜单栏中的菜单栏附加项，并定义了 `App` 的主场景。

- **init(isInserted:content:label:)**：创建一个菜单栏附加项。当指定的绑定设置为`true`时，该项目将显示在系统菜单栏中。如果用户从菜单栏中移除该项目，则绑定将设置为`false`。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:isInserted:content:)
crawled: 2025-12-03T05:31:21Z
---

# init(_:isInserted:content:)

**Initializer**

Creates a menu bar extra with a key for a localized string to use as the label. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isInserted: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The title key to use for the label of the item.
- **isInserted**: Whether the item is inserted in the menu bar. The item may or may not be visible, depending on the number of items present.
- **content**: A `View` to display when the user selects the item.

## Creating a menu bar extra

- **init(_:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The extra defines the primary scene of an `App`.
- **init(content:label:)**: Creates a menu bar extra that will be displayed in the system menu bar, and defines the primary scene of an `App`.
- **init(isInserted:content:label:)**: Creates a menu bar extra. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

