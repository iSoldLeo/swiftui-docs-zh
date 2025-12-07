---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/editMode
抓取时间： 2025-12-02T17:39:50Z
---

# 编辑模式

**实例属性**

用户是否可以编辑与此环境相关联的视图内容的指示。

## 声明

```swift
var editMode: Binding<EditMode>? { get set }
```

## 讨论

读取此环境值可接收编辑模式状态的可选绑定。该绑定包含一个 [EditMode](../EditMode.zh-Hans.md) 值，表示编辑模式是否处于活动状态，您可以用它来更改模式。要了解如何读取环境值，请参阅 [EnvironmentValues](../EnvironmentValues.zh-Hans.md)。

某些内置视图在编辑模式下会自动改变外观和行为。例如，使用[onDelete(perform:)](../DynamicViewContent/onDelete_perform.zh-Hans.md)或[onMove(perform:)](../DynamicViewContent/onMove_perform.zh-Hans.md)修饰符配置的[List](../List.zh-Hans.md)和[ForEach](../ForEach.zh-Hans.md)，可在编辑模式下提供删除或移动列表项的控制。在没有连接键盘和鼠标或触控板的设备上，只有当编辑模式激活时，用户才能在列表中进行多个选择。

您还可以自定义自己的视图，以便对编辑模式做出反应。下面的示例将只读[Text](../Text.zh-Hans.md) 视图替换为可编辑[TextField](../TextField.zh-Hans.md) 视图，通过测试封装值的[isEditing](../EditMode/isEditing.zh-Hans.md) 属性来检查编辑模式：

```swift
@Environment(\.editMode) private var editMode
@State private var name = "Maria Ruiz"

var body: some View {
    Form {
        if editMode?.wrappedValue.isEditing == true {
            TextField("Name", text: $name)
        } else {
            Text(name)
        }
    }
    .animation(nil, value: editMode?.wrappedValue)
    .toolbar { // Assumes embedding this view in a NavigationView.
        EditButton()
    }
}
```

您可以通过绑定设置编辑模式，也可以依靠[EditButton](../EditButton.zh-Hans.md) 属性来设置，如上例所示。当用户点击 "编辑 "按钮时，该按钮会激活编辑模式；当用户点击 "完成 "时，该按钮会关闭编辑模式。

## 编辑列表

- **moveDisabled(_:)**：添加视图的视图层次结构是否可移动的条件。
- **deleteDisabled(_:)**：添加视图的视图层次结构是否可删除的条件。
- **EditMode**：表示用户是否可以编辑视图内容的模式。
- **EditActions**：视图可向用户提供的一组数据集合编辑操作。
- **EditableCollectionContent**：不透明封装视图，可为列表中的一行添加编辑功能。
- **IndexedIdentifierCollection**：一个集合包装器，可遍历集合的索引和标识符。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/editMode
crawled: 2025-12-02T17:39:50Z
---

# editMode

**Instance Property**

An indication of whether the user can edit the contents of a view associated with this environment.

## Declaration

```swift
var editMode: Binding<EditMode>? { get set }
```

## Discussion

Read this environment value to receive a optional binding to the edit mode state. The binding contains an [EditMode](../EditMode.zh-Hans.md) value that indicates whether edit mode is active, and that you can use to change the mode. To learn how to read an environment value, see [EnvironmentValues](../EnvironmentValues.zh-Hans.md).

Certain built-in views automatically alter their appearance and behavior in edit mode. For example, a [List](../List.zh-Hans.md) with a [ForEach](../ForEach.zh-Hans.md) that’s configured with the [onDelete(perform:)](../DynamicViewContent/onDelete_perform.zh-Hans.md) or [onMove(perform:)](../DynamicViewContent/onMove_perform.zh-Hans.md) modifier provides controls to delete or move list items while in edit mode. On devices without an attached keyboard and mouse or trackpad, people can make multiple selections in lists only when edit mode is active.

You can also customize your own views to react to edit mode. The following example replaces a read-only [Text](../Text.zh-Hans.md) view with an editable [TextField](../TextField.zh-Hans.md), checking for edit mode by testing the wrapped value’s [isEditing](../EditMode/isEditing.zh-Hans.md) property:

```swift
@Environment(\.editMode) private var editMode
@State private var name = "Maria Ruiz"

var body: some View {
    Form {
        if editMode?.wrappedValue.isEditing == true {
            TextField("Name", text: $name)
        } else {
            Text(name)
        }
    }
    .animation(nil, value: editMode?.wrappedValue)
    .toolbar { // Assumes embedding this view in a NavigationView.
        EditButton()
    }
}
```

You can set the edit mode through the binding, or you can rely on an [EditButton](../EditButton.zh-Hans.md) to do that for you, as the example above demonstrates. The button activates edit mode when the user taps the Edit button, and disables editing mode when the user taps Done.

## Editing a list

- **moveDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is movable.
- **deleteDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is deletable.
- **EditMode**: A mode that indicates whether the user can edit a view’s content.
- **EditActions**: A set of edit actions on a collection of data that a view can offer to a user.
- **EditableCollectionContent**: An opaque wrapper view that adds editing capabilities to a row in a list.
- **IndexedIdentifierCollection**: A collection wrapper that iterates over the indices and identifiers of a collection together.

