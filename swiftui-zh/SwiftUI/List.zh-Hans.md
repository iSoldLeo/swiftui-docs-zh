--- 来源：https://developer.apple.com/documentation/SwiftUI/List
抓取时间：2025-12-02T17:27:28Z

---

# 列表

**Structure**

列表是一个容器，用于以单列形式呈现数据行，并可选择是否提供选择一个或多个成员的功能。

## 声明

```swift
@MainActor @preconcurrency struct List<SelectionValue, Content> where SelectionValue : Hashable, Content : View
```

## 概述

最简单的列表会静态地创建其内容，如下例所示：`List`

```swift
var body: some View {
    List {
        Text("A List Item")
        Text("A Second List Item")
        Text("A Third List Item")
    }
}
```

更常见的情况是，列表会根据底层数据集合动态创建。以下示例展示了如何从符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 规范的 `Ocean` 类型数组创建简单列表：

```swift
struct Ocean: Identifiable {
    let name: String
    let id = UUID()
}

private var oceans = [
    Ocean(name: "Pacific"),
    Ocean(name: "Atlantic"),
    Ocean(name: "Indian"),
    Ocean(name: "Southern"),
    Ocean(name: "Arctic")
]

var body: some View {
    List(oceans) {
        Text($0.name)
    }
}
```

### 支持列表中的选择

要使列表中的成员可选中，请提供与选择变量的绑定。绑定到列表数据的 `Identifiable.ID` 类型的单个实例将创建一个单选列表。绑定到 [doc://com.apple.documentation/documentation/Swift/Set] 将创建一个支持多选的列表。以下示例展示了如何在前面的示例中添加多选功能：

```swift
struct Ocean: Identifiable, Hashable {
    let name: String
    let id = UUID()
}

private var oceans = [
    Ocean(name: "Pacific"),
    Ocean(name: "Atlantic"),
    Ocean(name: "Indian"),
    Ocean(name: "Southern"),
    Ocean(name: "Arctic")
]

@State private var multiSelection = Set<UUID>()

var body: some View {
    NavigationView {
        List(oceans, selection: $multiSelection) {
            Text($0.name)
        }
        .navigationTitle("Oceans")
        .toolbar { EditButton() }
    }
    Text("\(multiSelection.count) selections")
}
```

当用户通过点击或单击进行单选时，选中的单元格会改变其外观以指示已选中状态。要启用点击手势的多选功能，请通过修改 [editMode](EnvironmentValues/editMode.zh-Hans.md) 值或在应用界面中添加 [EditButton](EditButton.zh-Hans.md) 将列表置于编辑模式。列表进入编辑模式后，每个列表项旁边都会显示一个圆圈。用户选择相应项后，圆圈内会显示一个勾号。上面的示例使用了一个“编辑”按钮，该按钮在编辑模式下标题会变为“完成”。

在配备键盘、鼠标或触控板的设备（例如 Mac 和 iPad）上，用户无需进入编辑模式即可进行多选。

### 刷新列表内容

要使用标准刷新控件刷新列表内容，请使用 [refreshable(action:)](View/refreshable_action.zh-Hans.md) 修饰符。

以下示例展示了如何向列表添加标准刷新控件。当用户向下拖动列表顶部时，SwiftUI 会显示刷新控件并执行指定的操作。在闭包 `action` 中使用 `await` 表达式来刷新数据。刷新指示器会在等待操作期间保持可见。

```swift
struct Ocean: Identifiable, Hashable {
     let name: String
     let id = UUID()
     let stats: [String: String]
 }

 class OceanStore: ObservableObject {
     @Published var oceans = [Ocean]()
     func loadStats() async {}
 }

 @EnvironmentObject var store: OceanStore

 var body: some View {
     NavigationView {
         List(store.oceans) { ocean in
             HStack {
                 Text(ocean.name)
                 StatsSummary(stats: ocean.stats) // A custom view for showing statistics.
             }
         }
         .refreshable {
             await store.loadStats()
         }
         .navigationTitle("Oceans")
     }
 }
```

### 支持多维列表

要创建二维列表，请将项目分组到 [Section](Section.zh-Hans.md) 实例中。以下示例创建了以世界各大洋命名的章节，每个章节都包含以主要海域命名的 [Text](Text.zh-Hans.md) 视图。该示例还允许选择单个列表项，该列表项由示例 `Sea` 类型的 `id` 标识。

```swift
struct ContentView: View {
    struct Sea: Hashable, Identifiable {
        let name: String
        let id = UUID()
    }

    struct OceanRegion: Identifiable {
        let name: String
        let seas: [Sea]
        let id = UUID()
    }

    private let oceanRegions: [OceanRegion] = [
        OceanRegion(name: "Pacific",
                    seas: [Sea(name: "Australasian Mediterranean"),
                           Sea(name: "Philippine"),
                           Sea(name: "Coral"),
                           Sea(name: "South China")]),
        OceanRegion(name: "Atlantic",
                    seas: [Sea(name: "American Mediterranean"),
                           Sea(name: "Sargasso"),
                           Sea(name: "Caribbean")]),
        OceanRegion(name: "Indian",
                    seas: [Sea(name: "Bay of Bengal")]),
        OceanRegion(name: "Southern",
                    seas: [Sea(name: "Weddell")]),
        OceanRegion(name: "Arctic",
                    seas: [Sea(name: "Greenland")])
    ]

    @State private var singleSelection: UUID?

    var body: some View {
        NavigationView {
            List(selection: $singleSelection) {
                ForEach(oceanRegions) { region in
                    Section(header: Text("Major \(region.name) Ocean Seas")) {
                        ForEach(region.seas) { sea in
                            Text(sea.name)
                        }
                    }
                }
            }
            .navigationTitle("Oceans and Seas")
        }
    }
}
```

由于此示例使用单选，因此用户可以在所有平台上的非编辑模式下进行选择。

### 创建层级列表

您还可以通过提供树状结构数据和一个 `children` 参数来创建任意深度的层级列表。该参数提供一个键路径，用于获取任意级别的子节点。以下示例使用自定义 `FileItem` 类型的深度嵌套集合来模拟文件系统的内容。由此数据创建的列表使用可折叠单元格，使用户能够浏览树状结构。

```swift
struct ContentView: View {
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
    let fileHierarchyData: [FileItem] = [
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
        ]),
        FileItem(name: "private", children: nil)
    ]
    var body: some View {
        List(fileHierarchyData, children: \.children) { item in
            Text(item.description)
        }
    }
}
```

### 设置列表样式

SwiftUI 会根据平台和列表所在的视图类型选择列表的显示样式。使用 [listStyle(_:)](View/listStyle.zh-Hans.md) 修饰符可以为视图中的所有列表应用不同的 [ListStyle](ListStyle.zh-Hans.md) 样式。例如，在“创建多维列表”主题的示例中添加 `.listStyle(.plain)` 会应用 [plain](ListStyle/plain.zh-Hans.md) 样式，如下截图所示：

## 从一组视图创建列表

- **init(content:)**：创建具有给定内容的列表。

- **init(selection:content:)**：创建具有给定内容的列表，支持选择单行且无法取消选择。

## 从枚举数据创建列表

- **init(_:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行。

- **init(_:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，并可选择允许用户选择单行。

- **init(_:id:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行。

- **init(_:id:selection:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户选择性地选择单行。

## 从分层数据创建列表

- **init(_:children:rowContent:)**：创建一个分层列表，该列表根据与底层可识别数据集合的绑定按需计算其行。

- **init(_:children:selection:rowContent:)**：创建一个分层列表，该列表根据与底层可识别数据集合的绑定按需计算其行，并允许用户始终选择且仅选择一行。

- **init(_:id:children:rowContent:)**：创建一个层级列表，该列表基于指向底层数据标识符的键路径来标识其行。

- **init(_:id:children:selection:rowContent:)**：创建一个层级列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户始终选择且仅选择一行。

## 从可编辑数据创建列表

- **init(_:editActions:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，并允许编辑该集合。

- **init(_:editActions:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，允许编辑该集合，并且要求选择单行。

- **init(_:id:editActions:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算行，并允许编辑该集合。

- **init(_:id:editActions:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算行，允许编辑该集合，并且需要选择单行。

## 支持的类型

- **body**：列表的内容。

## 创建列表

- **在列表中显示数据**：以平台适用的外观可视化数据集合。

- **listStyle(_:)**：设置此视图中列表的样式。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/List
crawled: 2025-12-02T17:27:28Z
---

# List

**Structure**

A container that presents rows of data arranged in a single column, optionally providing the ability to select one or more members.

## Declaration

```swift
@MainActor @preconcurrency struct List<SelectionValue, Content> where SelectionValue : Hashable, Content : View
```

## Overview

In its simplest form, a `List` creates its contents statically, as shown in the following example:

```swift
var body: some View {
    List {
        Text("A List Item")
        Text("A Second List Item")
        Text("A Third List Item")
    }
}
```



More commonly, you create lists dynamically from an underlying collection of data. The following example shows how to create a simple list from an array of an `Ocean` type which conforms to [doc://com.apple.documentation/documentation/Swift/Identifiable]:

```swift
struct Ocean: Identifiable {
    let name: String
    let id = UUID()
}

private var oceans = [
    Ocean(name: "Pacific"),
    Ocean(name: "Atlantic"),
    Ocean(name: "Indian"),
    Ocean(name: "Southern"),
    Ocean(name: "Arctic")
]

var body: some View {
    List(oceans) {
        Text($0.name)
    }
}
```



### Supporting selection in lists

To make members of a list selectable, provide a binding to a selection variable. Binding to a single instance of the list data’s `Identifiable.ID` type creates a single-selection list. Binding to a [doc://com.apple.documentation/documentation/Swift/Set] creates a list that supports multiple selections. The following example shows how to add multiselect to the previous example:

```swift
struct Ocean: Identifiable, Hashable {
    let name: String
    let id = UUID()
}

private var oceans = [
    Ocean(name: "Pacific"),
    Ocean(name: "Atlantic"),
    Ocean(name: "Indian"),
    Ocean(name: "Southern"),
    Ocean(name: "Arctic")
]

@State private var multiSelection = Set<UUID>()

var body: some View {
    NavigationView {
        List(oceans, selection: $multiSelection) {
            Text($0.name)
        }
        .navigationTitle("Oceans")
        .toolbar { EditButton() }
    }
    Text("\(multiSelection.count) selections")
}
```

When people make a single selection by tapping or clicking, the selected cell changes its appearance to indicate the selection. To enable multiple selections with tap gestures, put the list into edit mode by either modifying the [editMode](EnvironmentValues/editMode.zh-Hans.md) value, or adding an [EditButton](EditButton.zh-Hans.md) to your app’s interface. When you put the list into edit mode, the list shows a circle next to each list item. The circle contains a checkmark when the user selects the associated item. The example above uses an Edit button, which changes its title to Done while in edit mode:



People can make multiple selections without needing to enter edit mode on devices that have a keyboard and mouse or trackpad, like Mac and iPad.

### Refreshing the list content

To make the content of the list refreshable using the standard refresh control, use the [refreshable(action:)](View/refreshable_action.zh-Hans.md) modifier.

The following example shows how to add a standard refresh control to a list. When the user drags the top of the list downward, SwiftUI reveals the refresh control and executes the specified action. Use an `await` expression inside the `action` closure to refresh your data. The refresh indicator remains visible for the duration of the awaited operation.

```swift
struct Ocean: Identifiable, Hashable {
     let name: String
     let id = UUID()
     let stats: [String: String]
 }

 class OceanStore: ObservableObject {
     @Published var oceans = [Ocean]()
     func loadStats() async {}
 }

 @EnvironmentObject var store: OceanStore

 var body: some View {
     NavigationView {
         List(store.oceans) { ocean in
             HStack {
                 Text(ocean.name)
                 StatsSummary(stats: ocean.stats) // A custom view for showing statistics.
             }
         }
         .refreshable {
             await store.loadStats()
         }
         .navigationTitle("Oceans")
     }
 }
```

### Supporting multidimensional lists

To create two-dimensional lists, group items inside [Section](Section.zh-Hans.md) instances. The following example creates sections named after the world’s oceans, each of which has [Text](Text.zh-Hans.md) views named for major seas attached to those oceans. The example also allows for selection of a single list item, identified by the `id` of the example’s `Sea` type.

```swift
struct ContentView: View {
    struct Sea: Hashable, Identifiable {
        let name: String
        let id = UUID()
    }

    struct OceanRegion: Identifiable {
        let name: String
        let seas: [Sea]
        let id = UUID()
    }

    private let oceanRegions: [OceanRegion] = [
        OceanRegion(name: "Pacific",
                    seas: [Sea(name: "Australasian Mediterranean"),
                           Sea(name: "Philippine"),
                           Sea(name: "Coral"),
                           Sea(name: "South China")]),
        OceanRegion(name: "Atlantic",
                    seas: [Sea(name: "American Mediterranean"),
                           Sea(name: "Sargasso"),
                           Sea(name: "Caribbean")]),
        OceanRegion(name: "Indian",
                    seas: [Sea(name: "Bay of Bengal")]),
        OceanRegion(name: "Southern",
                    seas: [Sea(name: "Weddell")]),
        OceanRegion(name: "Arctic",
                    seas: [Sea(name: "Greenland")])
    ]

    @State private var singleSelection: UUID?

    var body: some View {
        NavigationView {
            List(selection: $singleSelection) {
                ForEach(oceanRegions) { region in
                    Section(header: Text("Major \(region.name) Ocean Seas")) {
                        ForEach(region.seas) { sea in
                            Text(sea.name)
                        }
                    }
                }
            }
            .navigationTitle("Oceans and Seas")
        }
    }
}
```

Because this example uses single selection, people can make selections outside of edit mode on all platforms.





### Creating hierarchical lists

You can also create a hierarchical list of arbitrary depth by providing tree-structured data and a `children` parameter that provides a key path to get the child nodes at any level. The following example uses a deeply-nested collection of a custom `FileItem` type to simulate the contents of a file system. The list created from this data uses collapsing cells to allow the user to navigate the tree structure.

```swift
struct ContentView: View {
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
    let fileHierarchyData: [FileItem] = [
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
        ]),
        FileItem(name: "private", children: nil)
    ]
    var body: some View {
        List(fileHierarchyData, children: \.children) { item in
            Text(item.description)
        }
    }
}
```



### Styling lists

SwiftUI chooses a display style for a list based on the platform and the view type in which it appears. Use the [listStyle(_:)](View/listStyle.zh-Hans.md) modifier to apply a different [ListStyle](ListStyle.zh-Hans.md) to all lists within a view. For example, adding `.listStyle(.plain)` to the example shown in the “Creating Multidimensional Lists” topic applies the [plain](ListStyle/plain.zh-Hans.md) style, the following screenshot shows:



## Creating a list from a set of views

- **init(content:)**: Creates a list with the given content.
- **init(selection:content:)**: Creates a list with the given content that supports selecting a single row that cannot be deselected.

## Creating a list from enumerated data

- **init(_:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data.
- **init(_:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, optionally allowing users to select a single row.
- **init(_:id:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data.
- **init(_:id:selection:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data, optionally allowing users to select a single row.

## Creating a list from hierarchical data

- **init(_:children:rowContent:)**: Creates a hierarchical list that computes its rows on demand from a binding to an underlying collection of identifiable data.
- **init(_:children:selection:rowContent:)**: Creates a hierarchical list that computes its rows on demand from a binding to an underlying collection of identifiable data and allowing users to have exactly one row always selected.
- **init(_:id:children:rowContent:)**: Creates a hierarchical list that identifies its rows based on a key path to the identifier of the underlying data.
- **init(_:id:children:selection:rowContent:)**: Creates a hierarchical list that identifies its rows based on a key path to the identifier of the underlying data and allowing users to have exactly one row always selected.

## Creating a list from editable data

- **init(_:editActions:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data and enables editing the collection.
- **init(_:editActions:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, enables editing the collection, and requires a selection of a single row.
- **init(_:id:editActions:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data and enables editing the collection.
- **init(_:id:editActions:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, enables editing the collection, and requires a selection of a single row.

## Supporting types

- **body**: The content of the list.

## Creating a list

- **Displaying data in lists**: Visualize collections of data with platform-appropriate appearance.
- **listStyle(_:)**: Sets the style for lists within this view.

## Conforms To

- View

