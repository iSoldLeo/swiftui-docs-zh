--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(isInserted:content:label:)

抓取时间：2025-12-03T05:31:22Z
---

# init(isInserted:content:label:)

**Initializer**

创建一个菜单栏附加项。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。

## 声明

```swift
init(isInserted: Binding<Bool>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **isInserted**：该项是否插入到菜单栏中。该项是否可见取决于菜单栏中已有的菜单项数量。

- **content**：用户选择项目时显示的 `View`。

- **label**：用作系统菜单栏标签的 `View`。

## 创建菜单栏附加项

- **init(_:content:)**：创建一个菜单栏附加项，其中包含一个用于本地化字符串的键，该字符串将用作标签。此附加项定义了 `App` 的主场景。

- **init(content:label:)**：创建一个将显示在系统菜单栏中的菜单栏附加项，并定义了 `App` 的主场景。

- **init(_:isInserted:content:)**：创建一个菜单栏附加项，其中包含一个用于本地化字符串的键，该字符串将用作标签。当指定的绑定设置为`true`时，该项目将显示在系统菜单栏中。如果用户从菜单栏中移除该项目，则绑定将设置为`false`。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(isInserted:content:label:)
crawled: 2025-12-03T05:31:22Z
---

# init(isInserted:content:label:)

**Initializer**

Creates a menu bar extra. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

## Declaration

```swift
init(isInserted: Binding<Bool>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **isInserted**: Whether the item is inserted in the menu bar. The item may or may not be visible, depending on the number of items present.
- **content**: A `View` to display when the user selects the item.
- **label**: A `View` to use as the label in the system menu bar.

## Creating a menu bar extra

- **init(_:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The extra defines the primary scene of an `App`.
- **init(content:label:)**: Creates a menu bar extra that will be displayed in the system menu bar, and defines the primary scene of an `App`.
- **init(_:isInserted:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

