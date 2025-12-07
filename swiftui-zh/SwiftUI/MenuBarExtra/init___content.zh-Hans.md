--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:content:)

抓取时间：2025-12-01T10:20:25Z

---

# init(_:content:)

**Initializer**

创建一个菜单栏附加组件，其标签为本地化字符串。该附加组件定义了 `App` 的主场景。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：用于菜单项标签的标题键。

- **content**：用户选择菜单项时显示的 `View`。

## 讨论

当用户从系统菜单栏移除此项时，应用程序将自动退出。因此，它不应与 `App` 中的其他场景类型一起使用。

## 创建菜单栏附加项

- **init(content:label:)**：创建一个将显示在系统菜单栏中的菜单栏附加项，并定义 `App` 的主场景。

- **init(_:isInserted:content:)**：创建一个菜单栏附加项，其标签为本地化字符串。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。

- **init(isInserted:content:label:)**：创建一个菜单栏附加项。当指定的绑定设置为`true`时，该项目将显示在系统菜单栏中。如果用户从菜单栏中移除该项目，则绑定将设置为`false`。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra/init(_:content:)
crawled: 2025-12-01T10:20:25Z
---

# init(_:content:)

**Initializer**

Creates a menu bar extra with a key for a localized string to use as the label. The extra defines the primary scene of an `App`.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The title key to use for the label of the item.
- **content**: A `View` to display when the user selects the item.

## Discussion

When this item is removed from the system menu bar by the user, the application will be automatically quit. As such, it should not be used in conjunction with other scene types in your `App`.

## Creating a menu bar extra

- **init(content:label:)**: Creates a menu bar extra that will be displayed in the system menu bar, and defines the primary scene of an `App`.
- **init(_:isInserted:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.
- **init(isInserted:content:label:)**: Creates a menu bar extra. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

