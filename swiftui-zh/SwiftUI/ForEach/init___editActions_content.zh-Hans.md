---
来源：https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:editActions:content:)
抓取时间： 2025-12-01T00:43:52Z
---

# init(_:editActions:content:)

**Initializer**

创建一个实例，根据底层数据的身份在更新时唯一标识和创建视图。

## 声明

```swift
init<C, R>(_ data: Binding<C>, editActions: EditActions<C>, @ViewBuilder content: @escaping (Binding<C.Element>) -> R) where Data == IndexedIdentifierCollection<C, ID>, ID == C.Element.ID, Content == EditableCollectionContent<R, C>, C : MutableCollection, C : RandomAccessCollection, R : View, C.Element : Identifiable, C.Index : Hashable
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建视图并可由用户编辑的标识数据。
- **editActions**：在 `data` 上合成的编辑操作。
- **content**：动态创建视图的视图生成器。

## 讨论

重要的是，数据元素的`id` 不能改变，除非用具有新标识的新数据元素替换该数据元素。如果数据元素的`id` 发生变化，由该数据元素生成的内容视图将丢失任何当前状态和动画。

当数据元素放置在`List` 中时，编辑操作（如删除或移动）可通过指定适当的`EditActions` 自动合成。

下面的示例显示了一个食谱列表，其中的元素可以删除和重新排序：

```swift
List {
    ForEach($recipes, editActions: [.delete, .move]) { $recipe in
        RecipeCell($recipe)
    }
}
```

使用[deleteDisabled(_:)](../View/deleteDisabled.zh-Hans.md) 和 [moveDisabled(_:)](../View/moveDisabled.zh-Hans.md)分别禁用按行删除或移动操作。

下面的示例显示了一个配方列表，其中的元素只有满足条件才能删除：

```swift
List {
    ForEach($recipes, editActions: .delete) { $recipe in
        RecipeCell($recipe)
            .deleteDisabled(recipe.isFromMom)
    }
}
```

明确的`DynamicViewContent.onDelete(perform:)`、`DynamicViewContent.onMove(perform:)` 或 `View.swipeActions(edge:allowsFullSwipe:content:)` 修改器将覆盖任何合成操作。如果需要对如何将突变应用于驱动`ForEach` 的数据进行精细控制，请使用此修改器。例如，需要执行副作用或调用现有模型代码时。

## 创建可编辑的集合

- **init(_:id:editActions:content:)**：创建一个唯一标识的实例，并根据底层数据的标识创建跨更新的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:editActions:content:)
crawled: 2025-12-01T00:43:52Z
---

# init(_:editActions:content:)

**Initializer**

Creates an instance that uniquely identifies and creates views across updates based on the identity of the underlying data.

## Declaration

```swift
init<C, R>(_ data: Binding<C>, editActions: EditActions<C>, @ViewBuilder content: @escaping (Binding<C.Element>) -> R) where Data == IndexedIdentifierCollection<C, ID>, ID == C.Element.ID, Content == EditableCollectionContent<R, C>, C : MutableCollection, C : RandomAccessCollection, R : View, C.Element : Identifiable, C.Index : Hashable
```

## Parameters

- **data**: The identified data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create views dynamically and can be edited by the user.
- **editActions**: The edit actions that are synthesized on `data`.
- **content**: The view builder that creates views dynamically.

## Discussion

It’s important that the `id` of a data element doesn’t change unless you replace the data element with a new data element that has a new identity. If the `id` of a data element changes, the content view generated from that data element loses any current state and animations.

When placed inside a `List` the edit actions (like delete or move) can be automatically synthesized by specifying an appropriate `EditActions`.

The following example shows a list of recipes whose elements can be deleted and reordered:

```swift
List {
    ForEach($recipes, editActions: [.delete, .move]) { $recipe in
        RecipeCell($recipe)
    }
}
```

Use [deleteDisabled(_:)](../View/deleteDisabled.zh-Hans.md) and [moveDisabled(_:)](../View/moveDisabled.zh-Hans.md) to disable respectively delete or move actions on a per-row basis.

The following example shows a list of recipes whose elements can be deleted only if they satisfy a condition:

```swift
List {
    ForEach($recipes, editActions: .delete) { $recipe in
        RecipeCell($recipe)
            .deleteDisabled(recipe.isFromMom)
    }
}
```

Explicit `DynamicViewContent.onDelete(perform:)`, `DynamicViewContent.onMove(perform:)`, or `View.swipeActions(edge:allowsFullSwipe:content:)` modifiers will override any synthesized actions. Use this modifier if you need fine-grain control on how mutations are applied to the data driving the `ForEach`. For example, if you need to execute side effects or call into your existing model code.

## Creating an editable collection

- **init(_:id:editActions:content:)**: Creates an instance that uniquely identifies and creates views across updates based on the identity of the underlying data.

