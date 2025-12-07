--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/defaultCustomization(_:options:)

抓取时间：2025-12-01T10:53:49Z

---

# defaultCustomization(_:options:)

**实例方法**

配置具有默认行为的可自定义工具栏项的行为方式。

## 声明

```swift
func defaultCustomization(_ defaultVisibility: Visibility = .automatic, options: ToolbarCustomizationOptions = []) -> some CustomizableToolbarContent

```

## 参数

- **defaultVisibility**：具有默认自定义行为的工具栏内容的默认可见性。

- **options**：用于配置具有默认自定义行为的工具栏内容行为的自定义选项。

## 说明

默认的可自定义项支持用户进行多种编辑。

- 用户可以添加工具栏中不存在的项。

- 用户可以删除工具栏中的项。

- 用户可以移动工具栏中的项目。

默认情况下，所有默认可自定义项目都会显示在工具栏中。将此修饰符的值设置为 [hidden](../Visibility/hidden.zh-Hans.md)，即可指定项目初始状态对用户隐藏，并要求用户根据需要将其添加到工具栏。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .defaultCustomization(.hidden)
    }
```

您可以确保用户始终可以使用具有默认自定义功能的项目，即使该项目已从可自定义工具栏中移除。为此，请使用 [alwaysAvailable](../ToolbarCustomizationOptions/alwaysAvailable.zh-Hans.md) 选项。如果用户从工具栏中移除这些项目，它们将保留在溢出列表中。

将此修饰符的 options 参数的值设置为 [alwaysAvailable](../ToolbarCustomizationOptions/alwaysAvailable.zh-Hans.md) 即可实现此行为。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .defaultCustomization(options: .alwaysAvailable)
    }
```

## 使用默认选项

- **defaultCustomization()**：配置可自定义工具栏内容的默认可见性和选项。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/defaultCustomization(_:options:)
crawled: 2025-12-01T10:53:49Z
---

# defaultCustomization(_:options:)

**Instance Method**

Configures the way customizable toolbar items with the default behavior behave.

## Declaration

```swift
func defaultCustomization(_ defaultVisibility: Visibility = .automatic, options: ToolbarCustomizationOptions = []) -> some CustomizableToolbarContent

```

## Parameters

- **defaultVisibility**: The default visibility of toolbar content with the default customization behavior.
- **options**: The customization options to configure the behavior of toolbar content with the default customization behavior.

## Discussion

Default customizable items support a variety of edits by the user.

- A user can add an item that is not in the toolbar.
- A user can remove an item that is in the toolbar.
- A user can move an item within the toolbar.

By default, all default customizable items will be initially present in the toolbar. Provide a value of [hidden](../Visibility/hidden.zh-Hans.md) to this modifier to specify that items should initially be hidden from the user, and require them to add those items to the toolbar if desired.

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .defaultCustomization(.hidden)
    }
```

You can ensure that the user can always use an item with default customizability, even if it’s removed from the customizable toolbar. To do this, provide the [alwaysAvailable](../ToolbarCustomizationOptions/alwaysAvailable.zh-Hans.md) option. These items will remain in the overflow if the user removes them from the toolbar.

Provide a value of [alwaysAvailable](../ToolbarCustomizationOptions/alwaysAvailable.zh-Hans.md) to the options parameter of this modifier to receive this behavior.

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .defaultCustomization(options: .alwaysAvailable)
    }
```

## Using default options

- **defaultCustomization()**: Configures customizable toolbar content with the default visibility and options.

