--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(content:label:)

抓取时间：2025-12-03T05:31:20Z

---

# init(content:label:)

**Initializer**

创建一个菜单栏附加组件，该组件将显示在系统菜单栏中，并定义一个 `App` 的主场景。

## 声明

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **content**：一个 `View`，用于在用户选择该项时显示。

- **label**：一个 `View`，用作系统菜单栏中的标签。

## 讨论

当用户从系统菜单栏移除此项时，应用程序将自动退出。因此，它不应与 `App` 中的其他场景类型一起使用。

## 创建菜单栏附加项

- **init(_:content:)**：创建一个菜单栏附加项，其键用于指定本地化字符串作为标签。该附加项定义了 `App` 的主场景。

- **init(_:isInserted:content:)**：创建一个菜单栏附加项，其键用于指定本地化字符串作为标签。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏移除该项，则绑定将设置为 `false`。

- **init(isInserted:content:label:)**：创建一个菜单栏附加项。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(content:label:)
crawled: 2025-12-03T05:31:20Z
---

# init(content:label:)

**Initializer**

Creates a menu bar extra that will be displayed in the system menu bar, and defines the primary scene of an `App`.

## Declaration

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **content**: A `View` to display when the user selects the item.
- **label**: A `View` to use as the label in the system menu bar.

## Discussion

When this item is removed from the system menu bar by the user, the application will be automatically quit. As such, it should not be used in conjunction with other scene types in your `App`.

## Creating a menu bar extra

- **init(_:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The extra defines the primary scene of an `App`.
- **init(_:isInserted:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.
- **init(isInserted:content:label:)**: Creates a menu bar extra. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

