--- 来源：https://developer.apple.com/documentation/SwiftUI/Populating-SwiftUI-menus-with-adaptive-controls

抓取时间：2025-12-02T17:02:03Z

---

# 使用自适应控件填充 SwiftUI 菜单

**Article**

通过在菜单中填充控件并以直观的方式组织内容，改进您的应用。

## 概述

菜单是功能强大的组件，您可以自适应地填充控件，并使用它们来组织应用中的命令、操作或项目。

在布局紧凑或设备尺寸较小的情况下，菜单可以通过按需显示选项来优化空间。当操作可以进行逻辑分组时，可以使用菜单来隐藏复杂的界面选项。您可以配置菜单，使用各种控件，例如 [Button](Button.zh-Hans.md)、[Toggle](Toggle.zh-Hans.md)、[Slider](Slider.zh-Hans.md)、[Divider](Divider.zh-Hans.md) 等等。这种灵活性确保您的菜单既能保持简洁，又能支持复杂的使用场景。

### 规划菜单结构

让您的菜单简洁灵活，能够适应各种界面，例如 iOS 和 iPadOS 上的常规尺寸和紧凑尺寸，以及 macOS、tvOS 和 visionOS 上的各种尺寸。

菜单由三个组件构成：

- 标签：描述菜单用途的视图。

- 内容：使用 [ViewBuilder](ViewBuilder.zh-Hans.md) 定义菜单项的闭包。

- 主要操作：一个可选的闭包，用于在用户点击或轻触菜单时执行操作，而不是默认的打开菜单的主要操作。如果提供了菜单，则打开菜单的操作将成为辅助操作，例如，长按手势即可打开菜单，而不是点击。

有关设计指南，请参阅人机界面指南 > [https://developer.apple.com/design/human-interface-guidelines/menus]。

### 填充菜单

一个定义良好的 SwiftUI [Menu](Menu.zh-Hans.md) 能够展现其最终渲染效果：菜单内容会根据每个元素的用途进行视觉调整。例如，在菜单的闭合部分插入 `Button` 会渲染一个可操作的菜单项，而插入 `Menu` 则会创建一个子菜单项。

要渲染执行特定操作闭包的菜单项，请使用 `Button` 控件：

```swift
Menu("Actions") {
    Button("Duplicate") {
        // Duplicate action.
    }
    Button("Rename") {
        // Rename action.
    }
    Button("Delete…") {
        // Delete action.
    }
}
```

要在菜单项标题旁边显示符号，请使用 [init(_:systemImage:action:)](Button/init___systemImage_action.zh-Hans.md) 初始化器：

```swift
Menu("Actions") {
    Button("Duplicate", systemImage: "doc.on.doc") {
        // Duplicate action.
    }
    Button("Rename", systemImage: "pencil") {
        // Rename action.
    }
    Button("Delete…", systemImage: "trash") {
        // Delete action.
    }
}
```

您还可以通过在 `Button` 上添加标签闭包初始化器来构建菜单操作。此方法为您的字幕提供了更大的灵活性。

要向菜单项添加标题和副标题，请使用两个 [Text](Text.zh-Hans.md) 视图填充控件的标签闭包，其中第一个文本表示标题，第二个文本表示副标题。以下示例展示了如何将此层级样式应用于视图：

```swift
Menu("Actions") {
    Button {
        // Duplicate action.
    } label: {
        Text("Duplicate")
        Text("Duplicate the component")
    }
    Button {
        // Rename action.
    } label: {
        Text("Rename")
        Text("Rename the component")
    }
    Button {
        // Delete action.
    } label: {
        Text("Delete…")
        Text("Delete the component")
    }
}
```

您可以通过将第一个 `Text` 替换为 [Label](Label.zh-Hans.md) 来插入图标：

```swift
Menu("Actions") {
    Button {
        // Duplicate action.
    } label: {
        Label("Duplicate", systemImage: "doc.on.doc")
        Text("Duplicate the component")
    }
    Button {
        // Rename action.
    } label: {
        Label("Rename", systemImage: "pencil")
        Text("Rename the component")
    }
    Button {
        // Delete action.
    } label: {
        Label("Delete…", systemImage: "trash")
        Text("Delete the component")
    }
}
```

为本质上具有破坏性的菜单项添加视觉警告提示。为 `Button` 添加 [destructive](ButtonRole/destructive.zh-Hans.md) 角色，使菜单项显示为红色。仅对需要谨慎操作的操作使用 `destructive`。

```swift
Menu("Actions") {
    // ...

    Button("Delete…", systemImage: "trash", role: .destructive) {
        // Delete action.
    }
}
```

在 macOS 上，使用 `Label` 构建的菜单项默认情况下不显示图标。使用 [titleAndIcon](LabelStyle/titleAndIcon.zh-Hans.md) 样式可以覆盖系统行为，并为菜单项显式渲染图标。

```swift
Menu("Actions") {
    // ...
}
.labelStyle(.titleAndIcon)
```

菜单也非常适合表示可切换的选项。要渲染一个可切换的菜单项，您可以向菜单内容添加一个 `Toggle`。

由于 SwiftUI 控件会根据上下文进行调整，菜单中的 `Toggle` 会自动显示一个勾号，指示其开启或关闭状态。

```swift
Menu("Actions") {
    // ...

    Toggle(
        "Favorite",
        systemImage: "suit.heart",
        isOn: $isFavorite)
}
```

与 `Button` 类似，使用标签闭包初始化 `Toggle` 可以提高灵活性。

```swift
Menu("Actions") {
    // ...

    Toggle(isOn: $isFavorite) {
        Label("Favorite", systemImage: "suit.heart")
        Text("Adds the component to the favorites list")
    }
}
```

在菜单中使用 [Picker](Picker.zh-Hans.md) 可以让用户从选项列表中进行选择：

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate

var body: some View {
    Picker("Flavor", selection: $selectedFlavor) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
                .tag(flavor)
        }
    }
}
```

此示例在菜单中嵌入了一个选择器，显示多个可选选项。虽然您可以选择多个选项，但任何时候都只有一个选项处于激活状态。选中的选项会显示一个勾号，表明当前选择。

在菜单中添加选择器比使用多个单独的开关更方便、更个性化。选择器提供了一个统一的界面来管理多个选项，确保用户一次只能选择一个选项。如果您的内容不需要互斥，则使用多个开关可能更合适。

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order") {
        Button("Special request") {
            // Create a special request.
        }

        Toggle("Include toppings", isOn: $includesToppings)

        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue.capitalized)
                    .tag(flavor)
            }
        }
    }
}
```

您可以选择选择器样式，例如 [inline](PickerStyle/inline.zh-Hans.md)、[menu](PickerStyle/menu.zh-Hans.md) 和 [palette](PickerStyle/palette.zh-Hans.md)。

### 为菜单选择器应用样式

默认情况下，菜单中的选择器选项以内联方式显示。SwiftUI 会隐式应用 `inline` 样式，允许您在不离开当前视图的情况下选择选项。内联样式非常适合需要立即显示上下文的设置或配置。

当您将 `menu` 样式应用于菜单中的选择器时，它会转换为子菜单，以层级方式呈现选项。此样式有助于组织具有分类选项的复杂菜单。

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order") {
        Button("Special request") {
            // Create a special request.
        }

        Toggle("Include toppings", isOn: $includesToppings)

        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue.capitalized)
                    .tag(flavor)
            }
        }
        .pickerStyle(.menu)
    }
}
```

调色板选择器最适合紧凑的场景，用户可以从一组符号中进行选择。调色板选择器会最小化图标，并在空间有限时转换为水平滚动条。

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order 3") {
        Button("Special request") {
            // Create a special request.
        }
        Toggle("Include toppings", isOn: $includesToppings)
        Picker("Flavor", selection: $selectedFlavor) {
            Text("🟤")
                .tag(Flavor.chocolate)
            Text("⚪️")
                .tag(Flavor.vanilla)
            Text("🔴")
                .tag(Flavor.strawberry)
        }
        .pickerStyle(.palette)
    }
}
```

菜单还可以使用滑块和步进器处理数值。

```swift
@State private var quantity: Int = 1

Menu("Actions") {
    // ...

    Stepper(value: $quantity) {
        Text("Quantity: \(quantity)")
    }
}
```

### 菜单项分组

SwiftUI 提供了多种对菜单中的项目进行分组的方法，包括子菜单、分区和分隔符。

子菜单以层级方式对项目进行分组，并在需要时才显示内容。子菜单可以保持主菜单的简洁，并在需要时提供其他选项：

```swift
Menu("General Settings") {
    // The General Settings submenu.
    Button("Wi-Fi") { openWiFiSettings() }
    Button("Bluetooth") { openBluetoothSettings() }
    Button("Notifications") { openNotificationSettings() }
    
    // The Account Settings submenu.
    Menu("Account Settings") {
        Button("Profile") { openProfileSettings() }
        Button("Security") { openSecuritySettings() }
        Button("Privacy") { openPrivacySettings() }
    }
    
    // The Advanced Settings submenu.
    Menu("Advanced Settings") {
        Button("Developer Options") { openDeveloperOptions() }
        Button("System Update") { openSystemUpdate() }
        Button("Backup & Restore") { openBackupRestore() }
    }
}
```

在上面的示例中，“设置”菜单包含两个子菜单，分别用于分组相关的、不太常用的设置操作。

您还可以使用“分区”来组织项目。[Section](Section.zh-Hans.md) 视图将项目分组，同时保持所有元素可见，通常还会添加分区标题以清晰区分。这种样式适用于在根级菜单中组织相关项目，为每个组提供清晰的分隔和上下文。

```swift
Menu("Settings") {
    // The General Settings submenu.
    Section("General Settings") {
        Button("Wi-Fi") { openWiFiSettings() }
        Button("Bluetooth") { openBluetoothSettings() }
        Button("Notifications") { openNotificationSettings() }
    }
    
    // The Account Settings submenu.
    Section("Account Settings") {
        Button("Profile") { openProfileSettings() }
        Button("Security") { openSecuritySettings() }
        Button("Privacy") { openPrivacySettings() }
    }
    
    // The Advanced Settings submenu.
    Section("Advanced Settings") {
        Button("Developer Options") { openDeveloperOptions() }
        Button("System Update") { openSystemUpdate() }
        Button("Backup & Restore") { openBackupRestore() }
    }
}
```

### 显示紧凑的菜单项

如果您想在菜单中的一行显示几个相关的操作，请考虑使用 [ControlGroup](ControlGroup.zh-Hans.md)。这种方法可以以紧凑的水平分组布局显示最多四个项目。

```swift
Menu("Edit") {
    ControlGroup {
        Button {
            // Undo action
        } label: {
            Label("Undo", systemImage: "arrow.uturn.backward")
        }
        
        Button {
            // Redo action
        } label: {
            Label("Redo", systemImage: "arrow.uturn.forward")
        }
        
        Button {
            // Copy action
        } label: {
            Label("Copy", systemImage: "doc.on.doc")
        }
    }
    
    Divider()
    
    // Additional menu items here...
}
```

子菜单和分区是用于分组项目的容器，而 `Divider` 视图则提供了一种简单的方法来在视觉上分隔菜单中的项目。与 `Section` 不同，`Divider` 并非容器，而是作为一种视觉分隔符，用于分隔项目组，以便组织和分组类似的命令，从而提高可用性并增强应用程序之间的一致性。

### 修改内容行为

除了填充菜单内容之外，SwiftUI 还提供了一组 API 来修改菜单项的默认行为。

SwiftUI 提供了一组 API 来修改菜单项的默认行为。在 iOS 和 iPadOS 上，系统默认会重新排列菜单项，使菜单中的第一个项目最靠近用户的交互点。要覆盖此默认行为并保持项目按您定义的顺序排列，请使用 [menuOrder(_:)](View/menuOrder.zh-Hans.md) 修饰符：

```swift
Menu("Settings", systemImage: "ellipsis.circle") {
    Button("Select") {
        // Select folders
    }
    Button("New Folder") {
        // Create folder
    }
    Picker("Appearance", selection: $appearance) {
        Label("Icons", systemImage: "square.grid.2x2").tag(Appearance.icons)
        Label("List", systemImage: "list.bullet").tag(Appearance.list)
    }
}
.menuOrder(.fixed)
```

默认情况下，用户点击或轻触项目后，菜单会立即关闭。如果您希望用户进行多项选择或重复操作而无需重新打开菜单，请使用 [menuActionDismissBehavior(_:)](View/menuActionDismissBehavior.zh-Hans.md) 修饰符覆盖特定项目的默认行为。

以下代码演示了：

- 增加和减少操作，禁用菜单关闭功能，允许用户反复点击或轻触以调整字体大小，而无需每次都重新打开菜单。

- 重置操作，将字体恢复为默认大小。由于此操作不会禁用菜单关闭功能，因此重置后菜单会关闭。

```swift
Menu("Font size") {
    Button(action: increase) {
        Label("Increase", systemImage: "plus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
    Button("Reset", action: reset)
    Button(action: decrease) {
        Label("Decrease", systemImage: "minus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
}
```

## 创建菜单

- **Menu**：用于显示操作菜单的控件。

- **menuStyle(_:)**：设置此视图中菜单的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Populating-SwiftUI-menus-with-adaptive-controls
crawled: 2025-12-02T17:02:03Z
---

# Populating SwiftUI menus with adaptive controls

**Article**

Improve your app by populating menus with controls and organizing your content intuitively.

## Overview

Menus are versatile components you can populate adaptively and use to organize commands, actions, or items in your app.

In tight layouts or smaller devices, menus optimize space by displaying options on demand. Use menus to conceal complex interface options when actions can be logically grouped. You have options for configuring your menus, with various controls like [Button](Button.zh-Hans.md), [Toggle](Toggle.zh-Hans.md), [Slider](Slider.zh-Hans.md), [Divider](Divider.zh-Hans.md), and more. This adaptability ensures that your menus remain flexible and succinct while supporting complex use cases.



### Plan the structure of your menus

Make your menus simple and flexible, able to adapt to various interfaces, such as regular and compact size classes on iOS and iPadOS and across macOS, tvOS, and visionOS.

A menu consists of three components:

- Label: A view that describes the purpose of the menu.
- Content: A closure that uses a [ViewBuilder](ViewBuilder.zh-Hans.md) to define the items inside the menu.
- Primary action: An optional closure that performs an action when someone clicks or taps the menu, instead of the default primary action of opening the menu. When provided, opening the menu becomes the secondary action, such as opening after a long press gesture instead of a tap.

For design guidance, see Human Interface Guidelines > [https://developer.apple.com/design/human-interface-guidelines/menus].

### Populate your menus

A well-declared SwiftUI [Menu](Menu.zh-Hans.md) resembles its ultimate rendered appearance: the contents of the menu visually adapt to the purpose of each element. For example, inserting a `Button` in the menu’s closure renders an actionable menu item, while inserting a `Menu` creates a submenu item.

To render a menu item that performs a given action closure, use the `Button` control:

```swift
Menu("Actions") {
    Button("Duplicate") {
        // Duplicate action.
    }
    Button("Rename") {
        // Rename action.
    }
    Button("Delete…") {
        // Delete action.
    }
}
```





To show a symbol next to the menu item title, use the [init(_:systemImage:action:)](Button/init___systemImage_action.zh-Hans.md) initializer:

```swift
Menu("Actions") {
    Button("Duplicate", systemImage: "doc.on.doc") {
        // Duplicate action.
    }
    Button("Rename", systemImage: "pencil") {
        // Rename action.
    }
    Button("Delete…", systemImage: "trash") {
        // Delete action.
    }
}
```



You can also construct menu actions by adding the label closure initializers on `Button`. This method provides more flexibility for your subtitles.

To add a title and subtitle to a menu item, populate the control’s label closure with two [Text](Text.zh-Hans.md) views, in which the first text represents the title, and the second represents the subtitle. The following example shows this hierarchical style applied to the views:

```swift
Menu("Actions") {
    Button {
        // Duplicate action.
    } label: {
        Text("Duplicate")
        Text("Duplicate the component")
    }
    Button {
        // Rename action.
    } label: {
        Text("Rename")
        Text("Rename the component")
    }
    Button {
        // Delete action.
    } label: {
        Text("Delete…")
        Text("Delete the component")
    }
}
```



You can insert an icon by replacing the first `Text` with a [Label](Label.zh-Hans.md):

```swift
Menu("Actions") {
    Button {
        // Duplicate action.
    } label: {
        Label("Duplicate", systemImage: "doc.on.doc")
        Text("Duplicate the component")
    }
    Button {
        // Rename action.
    } label: {
        Label("Rename", systemImage: "pencil")
        Text("Rename the component")
    }
    Button {
        // Delete action.
    } label: {
        Label("Delete…", systemImage: "trash")
        Text("Delete the component")
    }
}
```



Add a visual warning cue to menu items that are destructive by nature. Add a [destructive](ButtonRole/destructive.zh-Hans.md) role to `Button` to tint the menu item red. Use `destructive` only for actions that require caution.

```swift
Menu("Actions") {
    // ...

    Button("Delete…", systemImage: "trash", role: .destructive) {
        // Delete action.
    }
}
```



On macOS, menu items constructed with a `Label` render without an icon by default. Use the [titleAndIcon](LabelStyle/titleAndIcon.zh-Hans.md) style to override the system behavior and explicitly render an icon for the menu items.

```swift
Menu("Actions") {
    // ...
}
.labelStyle(.titleAndIcon)
```

Menus are also great for representing toggled items. To render a toggled menu item, you can add a `Toggle` to the menu’s content.

Because SwiftUI controls adapt to their context, a `Toggle` in a menu automatically appears with a checkmark indicating its on or off state.

```swift
Menu("Actions") {
    // ...

    Toggle(
        "Favorite",
        systemImage: "suit.heart",
        isOn: $isFavorite)
}
```



Just like `Button`, initialize a `Toggle` with a label closure for more flexibility.

```swift
Menu("Actions") {
    // ...

    Toggle(isOn: $isFavorite) {
        Label("Favorite", systemImage: "suit.heart")
        Text("Adds the component to the favorites list")
    }
}
```



Use a [Picker](Picker.zh-Hans.md) within a menu to let people choose from a list of options:

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate

var body: some View {
    Picker("Flavor", selection: $selectedFlavor) {
        ForEach(Flavor.allCases) { flavor in
            Text(flavor.rawValue.capitalized)
                .tag(flavor)
        }
    }
}
```



This example embeds a picker within a menu, displaying multiple selectable items. Although you can select several options, only one item is active at any given time. The selected item, identified with a checkmark, indicates the current selection.

Adding a picker to a menu creates a more convenient and customized layout than several individual toggles. A picker provides a single interface to manage multiple options, ensuring a person can only select one item at a time. Multiple toggles might be more appropriate when your content doesn’t require mutual exclusivity.

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order") {
        Button("Special request") {
            // Create a special request.
        }

        Toggle("Include toppings", isOn: $includesToppings)

        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue.capitalized)
                    .tag(flavor)
            }
        }
    }
}
```



You can choose picker styles such as [inline](PickerStyle/inline.zh-Hans.md), [menu](PickerStyle/menu.zh-Hans.md), and [palette](PickerStyle/palette.zh-Hans.md).

### Apply style to menu pickers

By default, picker options in menus appear inline. SwiftUI implicitly applies the `inline` style, allowing you to select options without navigating away from the current view. The inline style works well for settings or configurations that require immediate context.

When you apply the `menu` style to a picker within a menu, it transforms into a submenu, presenting options in a hierarchical manner. This style helps organize complex menus with categorized options.

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order") {
        Button("Special request") {
            // Create a special request.
        }

        Toggle("Include toppings", isOn: $includesToppings)

        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue.capitalized)
                    .tag(flavor)
            }
        }
        .pickerStyle(.menu)
    }
}
```



Palette pickers work best in compact scenarios in which someone chooses from a set of symbols. Palette pickers minimize icons, and turn into a horizontal scroll if there’s limited space.

```swift
enum Flavor: String, CaseIterable, Identifiable {
    case chocolate, vanilla, strawberry
    var id: Self { self }
}

@State private var selectedFlavor: Flavor = .chocolate
@State private var includesToppings: Bool = false

var body: some View {
    Menu("Ice Cream Order 3") {
        Button("Special request") {
            // Create a special request.
        }
        Toggle("Include toppings", isOn: $includesToppings)
        Picker("Flavor", selection: $selectedFlavor) {
            Text("🟤")
                .tag(Flavor.chocolate)
            Text("⚪️")
                .tag(Flavor.vanilla)
            Text("🔴")
                .tag(Flavor.strawberry)
        }
        .pickerStyle(.palette)
    }
}
```



Menus can also handle numerical values with sliders and steppers.

```swift
@State private var quantity: Int = 1

Menu("Actions") {
    // ...

    Stepper(value: $quantity) {
        Text("Quantity: \(quantity)")
    }
}
```



### Group menu items

SwiftUI provides multiple ways to group items within menus, including submenus, sections, and dividers.

Submenus group items hierarchically, hiding content until needed. A submenu keeps the main menu uncluttered, while providing access to additional options when necessary:

```swift
Menu("General Settings") {
    // The General Settings submenu.
    Button("Wi-Fi") { openWiFiSettings() }
    Button("Bluetooth") { openBluetoothSettings() }
    Button("Notifications") { openNotificationSettings() }
    
    // The Account Settings submenu.
    Menu("Account Settings") {
        Button("Profile") { openProfileSettings() }
        Button("Security") { openSecuritySettings() }
        Button("Privacy") { openPrivacySettings() }
    }
    
    // The Advanced Settings submenu.
    Menu("Advanced Settings") {
        Button("Developer Options") { openDeveloperOptions() }
        Button("System Update") { openSystemUpdate() }
        Button("Backup & Restore") { openBackupRestore() }
    }
}
```



In the example above, the Settings menu populates with two submenus, grouping related and less-prominent settings actions.

You can also organize items with sections. The [Section](Section.zh-Hans.md) view groups items while keeping all elements visible, often with section headers for clarity. This style is useful for organizing related items within the root-level menu, providing clear separation and context for each group.

```swift
Menu("Settings") {
    // The General Settings submenu.
    Section("General Settings") {
        Button("Wi-Fi") { openWiFiSettings() }
        Button("Bluetooth") { openBluetoothSettings() }
        Button("Notifications") { openNotificationSettings() }
    }
    
    // The Account Settings submenu.
    Section("Account Settings") {
        Button("Profile") { openProfileSettings() }
        Button("Security") { openSecuritySettings() }
        Button("Privacy") { openPrivacySettings() }
    }
    
    // The Advanced Settings submenu.
    Section("Advanced Settings") {
        Button("Developer Options") { openDeveloperOptions() }
        Button("System Update") { openSystemUpdate() }
        Button("Backup & Restore") { openBackupRestore() }
    }
}
```



### Display compact menu items

When you want to display a few related actions in a single row within a menu, consider using a [ControlGroup](ControlGroup.zh-Hans.md). This method provides a compact, horizontally-grouped layout of up to four items.

```swift
Menu("Edit") {
    ControlGroup {
        Button {
            // Undo action
        } label: {
            Label("Undo", systemImage: "arrow.uturn.backward")
        }
        
        Button {
            // Redo action
        } label: {
            Label("Redo", systemImage: "arrow.uturn.forward")
        }
        
        Button {
            // Copy action
        } label: {
            Label("Copy", systemImage: "doc.on.doc")
        }
    }
    
    Divider()
    
    // Additional menu items here...
}
```

While submenus and sections are containers that group items, the `Divider` view provides a simple way to visually separate items within a menu. Unlike `Section`, `Divider` isn’t a container, but serves as a visual break that divides groups of items to organize and group like-commands for improved usability and uniformity across apps.

### Modify content behavior

Beyond populating a menu’s content, SwiftUI also offers a set of APIs to modify the default behavior of menu items.

SwiftUI offers a set of APIs to modify the default behavior of menu items. On iOS and iPadOS, the system rearranges menu items by default so the first items in a menu appear closest to the viewer’s point of interaction. To override this behavior and keep items in the order you define, use the [menuOrder(_:)](View/menuOrder.zh-Hans.md) modifier:

```swift
Menu("Settings", systemImage: "ellipsis.circle") {
    Button("Select") {
        // Select folders
    }
    Button("New Folder") {
        // Create folder
    }
    Picker("Appearance", selection: $appearance) {
        Label("Icons", systemImage: "square.grid.2x2").tag(Appearance.icons)
        Label("List", systemImage: "list.bullet").tag(Appearance.list)
    }
}
.menuOrder(.fixed)
```



By default, menus dismiss as soon as someone clicks or taps an item. If you want the person to make multiple selections, or repeat an action without reopening the menu, override this behavior with the [menuActionDismissBehavior(_:)](View/menuActionDismissBehavior.zh-Hans.md) modifier on specific items.

The following code demonstrates:

- Increase and decrease actions that disable menu dismissal, letting someone click or tap them repeatedly to adjust the font size without re-opening the menu each time.
- A reset action that reverts the font to a default size. Because the action doesn’t disable the dismissal, the menu closes after resetting.

```swift
Menu("Font size") {
    Button(action: increase) {
        Label("Increase", systemImage: "plus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
    Button("Reset", action: reset)
    Button(action: decrease) {
        Label("Decrease", systemImage: "minus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
}
```

## Creating a menu

- **Menu**: A control for presenting a menu of actions.
- **menuStyle(_:)**: Sets the style for menus within this view.

