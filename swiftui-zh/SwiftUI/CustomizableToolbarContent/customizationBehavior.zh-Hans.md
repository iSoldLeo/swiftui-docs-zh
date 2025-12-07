--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/customizationBehavior(_:)

抓取时间：2025-12-01T10:53:50Z

---

# customizationBehavior(_:)

**实例方法**

配置可自定义工具栏内容的自定义行为。

## 声明

```swift
nonisolated func customizationBehavior(_ behavior: ToolbarCustomizationBehavior) -> some CustomizableToolbarContent

```

## 参数

- **behavior**：可自定义工具栏内容的自定义行为。

## 说明

可自定义工具栏项目支持以下几种自定义方式：

- 用户可以添加工具栏中不存在的项目。

- 用户可以删除工具栏中的项目。

- 用户可以移动工具栏中的项目。

根据工具栏项目的自定义行为，将支持不同的编辑方式。

使用此修饰符可以控制用户对工具栏项的自定义行为。在以下示例中，可自定义的工具栏项支持所有类型的工具栏自定义，并且位于工具栏的起始位置。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
    }
```

您可以通过向此修饰符传递值 [disabled](../ToolbarCustomizationBehavior/disabled.zh-Hans.md) 来创建一个无法从工具栏中移除或在工具栏内移动的项。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .customizationBehavior(.disabled)
    }
```

您可以通过传递值 [reorderable](../ToolbarCustomizationBehavior/reorderable.zh-Hans.md) 来创建一个无法从工具栏中移除但可以移动的项。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .customizationBehavior(.reorderable)
    }
```


---
source: https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/customizationBehavior(_:)
crawled: 2025-12-01T10:53:50Z
---

# customizationBehavior(_:)

**Instance Method**

Configures the customization behavior of customizable toolbar content.

## Declaration

```swift
nonisolated func customizationBehavior(_ behavior: ToolbarCustomizationBehavior) -> some CustomizableToolbarContent

```

## Parameters

- **behavior**: The customization behavior of the customizable toolbar content.

## Discussion

Customizable toolbar items support different kinds of customization:

- A user can add an item that is not in the toolbar.
- A user can remove an item that is in the toolbar.
- A user can move an item within the toolbar.

Based on the customization behavior of the toolbar items, different edits will be supported.

Use this modifier to the customization behavior a user can perform on your toolbar items. In the following example, the customizable toolbar item supports all of the different kinds of toolbar customizations and starts in the toolbar.

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
    }
```

You can create an item that can not be removed from the toolbar or moved within the toolbar  by passing a value of [disabled](../ToolbarCustomizationBehavior/disabled.zh-Hans.md) to this modifier.

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .customizationBehavior(.disabled)
    }
```

You can create an item that can not be removed from the toolbar, but can be moved by passing a value of [reorderable](../ToolbarCustomizationBehavior/reorderable.zh-Hans.md).

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "new") {
            // new button here
        }
        .customizationBehavior(.reorderable)
    }
```

