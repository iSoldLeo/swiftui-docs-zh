--- 来源：https://developer.apple.com/documentation/SwiftUI/OutlineGroup

抓取时间：2025-12-02T17:02:57Z

---

# OutlineGroup

**Structure**

OutlineGroup 是一种结构，它能够根据底层树状结构化、已识别的数据集合按需计算视图和展开组。

## 声明

```swift
struct OutlineGroup<Data, ID, Parent, Leaf, Subgroup> where Data : RandomAccessCollection, ID : Hashable
```

## 概述

当您需要使用展开视图来表示数据层次结构时，可以使用 OutlineGroup。这样，用户就可以使用展开视图来展开和折叠分支，从而浏览树状结构。

在以下示例中，`FileItem` 数据的树状结构提供了一个简化的文件系统视图。传递此树的根节点及其子节点的键路径，即可快速创建文件系统的可视化表示。

```swift
struct FileItem: Hashable, Identifiable, CustomStringConvertible {
    var id: Self { self }
    var name: String
    var children: [FileItem]? = nil
    var description: String {
        switch children {
        case nil:
            return "📄 \(name)"
        case .some(let children):
            return children.isEmpty ? "📂 \(name)" : "📁 \(name)"
        }
    }
}

let data =
  FileItem(name: "users", children:
    [FileItem(name: "user1234", children:
      [FileItem(name: "Photos", children:
        [FileItem(name: "photo001.jpg"),
         FileItem(name: "photo002.jpg")]),
       FileItem(name: "Movies", children:
         [FileItem(name: "movie001.mp4")]),
          FileItem(name: "Documents", children: [])
      ]),
     FileItem(name: "newuser", children:
       [FileItem(name: "Documents", children: [])
       ])
    ])

OutlineGroup(data, children: \.children) { item in
    Text("\(item.description)")
}
```

### 类型参数

五个通用类型约束定义了一个特定的 `OutlineGroup` 实例：

- `Data`：包含树状数据中某个元素的子元素的集合的类型。

- `ID`：元素标识符的类型。

- `Parent`：children 属性为非 `nil` 的元素的视觉表示的类型。

- `Leaf`：children 属性为 `nil` 的元素的视觉表示的类型。

- `Subgroup`：一种视图类型，它将父视图和表示其子视图的视图组合在一起，通常包含显示和隐藏子视图的机制。

## 创建大纲组

- **init(_:children:)**：根据根数据元素集合和指向元素子元素的键路径创建大纲组。

- **init(_:children:content:)**：根据绑定到根数据元素集合和指向其子元素的键路径创建大纲组。

- **init(_:id:children:content:)**：根据绑定到根数据元素集合、指向数据元素标识符的键路径和指向其子元素的键路径创建大纲组。

## 支持的类型

- **OutlineSubgroupChildren**：表示大纲子组中子元素的类型擦除视图。

## 逐步披露信息

- **DisclosureGroup**：根据披露控件的状态显示或隐藏其他内容视图。

- **disclosureGroupStyle(_:)**：设置此视图中披露组的样式。

## 符合以下标准

- Copyable

- TableRowContent

- View


---
source: https://developer.apple.com/documentation/SwiftUI/OutlineGroup
crawled: 2025-12-02T17:02:57Z
---

# OutlineGroup

**Structure**

A structure that computes views and disclosure groups on demand from an underlying collection of tree-structured, identified data.

## Declaration

```swift
struct OutlineGroup<Data, ID, Parent, Leaf, Subgroup> where Data : RandomAccessCollection, ID : Hashable
```

## Overview

Use an outline group when you need a view that can represent a hierarchy of data by using disclosure views. This allows the user to navigate the tree structure by using the disclosure views to expand and collapse branches.

In the following example, a tree structure of `FileItem` data offers a simplified view of a file system. Passing the root of this tree and the key path of its children allows you to quickly create a visual representation of the file system.

```swift
struct FileItem: Hashable, Identifiable, CustomStringConvertible {
    var id: Self { self }
    var name: String
    var children: [FileItem]? = nil
    var description: String {
        switch children {
        case nil:
            return "📄 \(name)"
        case .some(let children):
            return children.isEmpty ? "📂 \(name)" : "📁 \(name)"
        }
    }
}

let data =
  FileItem(name: "users", children:
    [FileItem(name: "user1234", children:
      [FileItem(name: "Photos", children:
        [FileItem(name: "photo001.jpg"),
         FileItem(name: "photo002.jpg")]),
       FileItem(name: "Movies", children:
         [FileItem(name: "movie001.mp4")]),
          FileItem(name: "Documents", children: [])
      ]),
     FileItem(name: "newuser", children:
       [FileItem(name: "Documents", children: [])
       ])
    ])

OutlineGroup(data, children: \.children) { item in
    Text("\(item.description)")
}
```

### Type parameters

Five generic type constraints define a specific `OutlineGroup` instance:

- `Data`: The type of a collection containing the children of an element in the tree-shaped data.
- `ID`: The type of the identifier for an element.
- `Parent`: The type of the visual representation of an element whose children property is non-`nil`
- `Leaf`: The type of the visual representation of an element whose children property is `nil`.
- `Subgroup`: A type of a view that groups a parent view and a view representing its children, typically with some mechanism for showing and hiding the children

## Creating an outline group

- **init(_:children:)**: Creates an outline group from a collection of root data elements and a key path to element’s children.
- **init(_:children:content:)**: Creates an outline group from a binding to a collection of root data elements and a key path to its children.
- **init(_:id:children:content:)**: Creates an outline group from a binding to a collection of root data elements, the key path to a data element’s identifier, and a key path to its children.

## Supporting types

- **OutlineSubgroupChildren**: A type-erased view representing the children in an outline subgroup.

## Disclosing information progressively

- **DisclosureGroup**: A view that shows or hides another content view, based on the state of a disclosure control.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.

## Conforms To

- Copyable
- TableRowContent
- View

