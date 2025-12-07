---
来源： https://developer.apple.com/documentation/SwiftUI/EditButton
抓取时间： 2025-12-02T17:26:59Z
---

# 编辑按钮

**Structure**

用于切换编辑模式环境值的按钮。

## 声明

```swift
struct EditButton
```

## 概览

对于支持编辑模式的容器中的内容，编辑按钮可切换环境的[editMode](EnvironmentValues/editMode.zh-Hans.md) 值。在下面的示例中，放置在[NavigationView](NavigationView.zh-Hans.md) 中的编辑按钮支持编辑[List](List.zh-Hans.md)：

```swift
@State private var fruits = [
    "Apple",
    "Banana",
    "Papaya",
    "Mango"
]

var body: some View {
    NavigationView {
        List {
            ForEach(fruits, id: \.self) { fruit in
                Text(fruit)
            }
            .onDelete { fruits.remove(atOffsets: $0) }
            .onMove { fruits.move(fromOffsets: $0, toOffset: $1) }
        }
        .navigationTitle("Fruits")
        .toolbar {
            EditButton()
        }
    }
}
```

由于上例中的[ForEach](ForEach.zh-Hans.md) 为[onDelete(perform:)](DynamicViewContent/onDelete_perform.zh-Hans.md) 和[onMove(perform:)](DynamicViewContent/onMove_perform.zh-Hans.md) 定义了行为，因此当用户点击编辑时，可编辑列表会显示删除和移动用户界面。请注意，当编辑模式激活时，"编辑 "按钮会显示标题 "完成"：



您还可以创建能对编辑模式状态变化作出反应的自定义视图，详见[EditMode](EditMode.zh-Hans.md)。

## 创建编辑按钮

- **init()**：创建编辑按钮实例。

## 创建特殊用途按钮

- **PasteButton**：系统按钮，用于从粘贴板读取项目并将其传送到闭合器。
- **RenameButton**：触发标准重命名操作的按钮。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/EditButton
crawled: 2025-12-02T17:26:59Z
---

# EditButton

**Structure**

A button that toggles the edit mode environment value.

## Declaration

```swift
struct EditButton
```

## Overview

An edit button toggles the environment’s [editMode](EnvironmentValues/editMode.zh-Hans.md) value for content within a container that supports edit mode. In the following example, an edit button placed inside a [NavigationView](NavigationView.zh-Hans.md) supports editing of a [List](List.zh-Hans.md):

```swift
@State private var fruits = [
    "Apple",
    "Banana",
    "Papaya",
    "Mango"
]

var body: some View {
    NavigationView {
        List {
            ForEach(fruits, id: \.self) { fruit in
                Text(fruit)
            }
            .onDelete { fruits.remove(atOffsets: $0) }
            .onMove { fruits.move(fromOffsets: $0, toOffset: $1) }
        }
        .navigationTitle("Fruits")
        .toolbar {
            EditButton()
        }
    }
}
```

Because the [ForEach](ForEach.zh-Hans.md) in the above example defines behaviors for [onDelete(perform:)](DynamicViewContent/onDelete_perform.zh-Hans.md) and [onMove(perform:)](DynamicViewContent/onMove_perform.zh-Hans.md), the editable list displays the delete and move UI when the user taps Edit. Notice that the Edit button displays the title “Done” while edit mode is active:



You can also create custom views that react to changes in the edit mode state, as described in [EditMode](EditMode.zh-Hans.md).

## Creating an edit button

- **init()**: Creates an Edit button instance.

## Creating special-purpose buttons

- **PasteButton**: A system button that reads items from the pasteboard and delivers it to a closure.
- **RenameButton**: A button that triggers a standard rename action.

## Conforms To

- View

