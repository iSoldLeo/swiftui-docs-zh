--- 来源：https://developer.apple.com/documentation/SwiftUI/Displaying-Data-in-Lists

抓取时间：2025-12-02T17:39:27Z

---

# 在列表中显示数据

**Article**

以平台适配的外观可视化数据集合。

## 概述

在许多应用中，以垂直列表形式显示数据集合是一个常见需求。无论是联系人列表、事件日程表、类别索引还是购物清单，您通常都会用到 [List](List.zh-Hans.md)。

列表视图垂直显示项目集合，根据需要加载行，并在行数超过屏幕显示范围时添加滚动条，使其非常适合显示大型数据集合。

默认情况下，列表视图还会为其元素应用平台适配的样式。例如，在 iOS 系统中，列表的默认配置是在每行之间显示分隔线，并在项目旁边添加展开/展开指示器，以触发导航操作。

本文中的代码展示了如何使用列表视图来显示公司员工名录。每个部分都通过添加自定义单元格、将列表拆分为多个部分以及使用列表选择导航到详细信息视图来增强列表的实用性。

### 准备迭代数据

[List](List.zh-Hans.md) 最常见的用途是表示数据模型中的信息集合。以下示例将 `Person` 定义为 [doc://com.apple.documentation/documentation/Swift/Identifiable] 类型，并具有属性 `name` 和 `phoneNumber`。名为 `staff` 的数组包含此类型的两个实例。

```swift
struct Person: Identifiable {
     let id = UUID()
     var name: String
     var phoneNumber: String
 }

var staff = [
    Person(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
    Person(name: "Mei Chen", phoneNumber: "(919) 555-2481")
]
```

为了将数组内容呈现为列表，示例创建了一个 `List` 实例。列表的内容构建器使用 [ForEach](ForEach.zh-Hans.md) 来遍历 `staff` 数组。对于数组中的每个成员，列表会通过实例化一个新的 [Text](Text.zh-Hans.md) 来创建一个行视图，该视图包含 `Person` 的名称。

```swift
struct StaffList: View {
    var body: some View {
        List {
            ForEach(staff) { person in
                Text(person.name)
            }
        }
    }
}
```

列表的成员必须彼此唯一标识。唯一标识符使 SwiftUI 能够自动为底层数据的更改（例如插入、删除和移动）生成动画。识别列表成员的方法有两种：一是使用符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 规范的类型（如 `Person` 所示）；二是提供一个 `id` 参数，该参数包含指向该类型唯一属性的键路径。填充上述列表的 `ForEach` 依赖于此行为，接受 [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] 成员进行迭代的 `List` 初始化器也依赖于此行为。

### 在行中显示数据

[List](List.zh-Hans.md) 中的每一行都必须是 SwiftUI [View](View.zh-Hans.md)。您或许可以使用单个视图（例如 [Image](Image.zh-Hans.md) 或 [Text](Text.zh-Hans.md) 视图）来表示您的数据，或者您可能需要定义自定义视图，将多个视图组合成更复杂的视图。

随着行视图变得越来越复杂，请将视图重构为单独的视图结构，并将行需要渲染的数据传递给这些结构。以下示例定义了一个 `PersonRowView`，用于为 `Person` 创建一个两行视图，并使用字体、颜色和系统“电话”图标图像来设置数据的视觉样式。

```swift
struct PersonRowView: View {
    var person: Person

    var body: some View {
        VStack(alignment: .leading, spacing: 3) {
            Text(person.name)
                .foregroundColor(.primary)
                .font(.headline)
            HStack(spacing: 3) {
                Label(person.phoneNumber, systemImage: "phone")
            }
            .foregroundColor(.secondary)
            .font(.subheadline)
        }
    }
}

struct StaffList: View {
    var body: some View {
        List {
            ForEach(staff) { person in
                PersonRowView(person: person)
            }
        }
    }
}
```

有关组合列表行中常用视图类型的更多信息，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

### 使用节表示数据层次结构

视图还可以显示具有层次结构的数据，将关联数据分组到不同的节中。

考虑一个扩展的数据模型，该模型表示一个包含多个部门的整个公司。每个 `Department` 都有一个名称和一个 `Person` 实例数组，而公司本身则有一个 `Department` 类型的数组。

```swift
struct Department: Identifiable {
    let id = UUID()
    var name: String
    var staff: [Person]
}

struct Company {
    var departments: [Department]
}

var company = Company(departments: [
    Department(name: "Sales", staff: [
        Person(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
        Person(name: "Mei Chen", phoneNumber: "(919) 555-2481"),
        // ...
    ]),
    Department(name: "Engineering", staff: [
        Person(name: "Bill James", phoneNumber: "(408) 555-4450"),
        Person(name: "Anne Johnson", phoneNumber: "(417) 555-9311"),
        // ...
    ]),
    // ...
])
```

使用视图为 `List` 中的数据赋予层次结构。首先创建 `List`，使用 [ForEach](ForEach.zh-Hans.md) 遍历 `company.departments` 数组，然后为每个部门创建 `Section` 视图。在章节的视图构建器中，使用 `ForEach` 遍历部门的 `staff`，并为每个 `Person` 返回一个自定义视图。

```swift
List {
     ForEach(company.departments) { department in
         Section(header: Text(department.name)) {
             ForEach(department.staff) { person in
                PersonRowView(person: person)
             }
         }
     }
 }
```

## 使用列表进行导航

在 [NavigationView](NavigationView.zh-Hans.md) 内嵌套 [List](List.zh-Hans.md) 并使用 [NavigationLink](NavigationLink.zh-Hans.md)，可以添加平台适用的视觉样式，在某些情况下，还可以添加额外的容器视图，为导航提供结构。 SwiftUI 根据运行时环境使用两种视觉呈现方式之一：

- 带有展开/展开指示器的列表，当用户选择列表项时，会执行动画导航到目标场景。SwiftUI 在 watchOS、tvOS 和大多数 iOS 设备上使用此呈现方式，但下文另有说明。

- 双面板拆分视图，左侧以列表形式显示顶级数据，右侧显示详细信息。要使用此呈现方式，还需要在列表后提供一个占位符视图；此占位符会填充详细信息面板，直到用户进行选择。SwiftUI 在 macOS、iPadOS 和具有足够水平空间的 iOS 设备上使用此双面板方式，水平空间由 [horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) 环境值指示。

以下示例通过将列表包裹在导航视图中来设置基于导航的 UI。 `NavigationLink` 实例会包裹列表行，以便在用户点击行时提供 `destination` 视图进行导航。如果平台支持分屏导航，则右侧面板最初会显示“未选择”占位符视图，当用户进行选择时，导航视图会将其替换为目标视图。

```swift
NavigationView {
    List {
        ForEach(company.departments) { department in
            Section(header: Text(department.name)) {
                ForEach(department.staff) { person in
                    NavigationLink(destination: PersonDetailView(person: person)) {
                        PersonRowView(person: person)
                    }
                }
            }
        }
    }
    .navigationTitle("Staff Directory")

    // Placeholder
    Text("No Selection")
        .font(.headline)
}
```

在本例中，作为 `destination` 传入的视图是 `PersonDetailView`，它重复了列表中的信息。在更复杂的应用程序中，此详细信息视图可以显示比列表行所能容纳的更多的关于 `Person` 的信息。

```swift
struct PersonDetailView: View {
    var person: Person

    var body: some View {
        VStack {
            Text(person.name)
                .foregroundColor(.primary)
                .font(.title)
                .padding()
            HStack {
                Label(person.phoneNumber, systemImage: "phone")
            }
            .foregroundColor(.secondary)
        }
    }
}
```

在大多数 iOS 设备（横向尺寸为紧凑型的设备）上，列表会以独立视图的形式显示，点击某一行会触发动画过渡效果，跳转到目标视图。下图展示了列表视图以及用户选择后出现的目标视图：

另一方面，iPadOS 和 macOS 会将列表视图和详情视图合并显示为多列视图。下图展示了 macOS 上在进行选择之前的示例，这意味着“未选择”占位符视图仍然显示在详情列中。

您可以使用 [navigationViewStyle(_:)](View/navigationViewStyle.zh-Hans.md) 视图修饰符来更改 `NavigationView` 的默认行为。例如，在 iOS 上，即使在 iPad 横屏模式下，[StackNavigationViewStyle](StackNavigationViewStyle.zh-Hans.md) 也会强制使用单列模式。

## 创建列表

- **List**：用于以单列形式呈现数据行的容器，可选择是否允许选择一个或多个成员。

- **listStyle(_:)**：设置此视图中列表的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Displaying-Data-in-Lists
crawled: 2025-12-02T17:39:27Z
---

# Displaying data in lists

**Article**

Visualize collections of data with platform-appropriate appearance.

## Overview

Displaying a collection of data in a vertical list is a common requirement in many apps. Whether it’s a list of contacts, a schedule of events, an index of categories, or a shopping list, you’ll often find a use for a [List](List.zh-Hans.md).

List views display collections of items vertically, load rows as needed, and add scrolling when the rows don’t fit on the screen, making them suitable for displaying large collections of data.

By default, list views also apply platform-appropriate styling to their elements. For example, on iOS, the default configuration of a list displays a separator line between each row, and adds disclosure indicators next to items that initiate navigation actions.



The code in this article shows the use of list views to display a company’s staff directory. Each section enhances the usefulness of the list, by adding custom cells, splitting the list into sections, and using the list selection to navigate to a detail view.

### Prepare your data for iteration

The most common use of [List](List.zh-Hans.md) is for representing collections of information in your data model. The following example defines a `Person` as an [doc://com.apple.documentation/documentation/Swift/Identifiable] type with the properties `name` and `phoneNumber`. An array called `staff` contains two instances of this type.

```swift
struct Person: Identifiable {
     let id = UUID()
     var name: String
     var phoneNumber: String
 }

var staff = [
    Person(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
    Person(name: "Mei Chen", phoneNumber: "(919) 555-2481")
]
```

To present the contents of the array as a list, the example creates a `List` instance. The list’s content builder uses a [ForEach](ForEach.zh-Hans.md) to iterate over the `staff` array. For each member of the array, the listing creates a row view by instantiating a new [Text](Text.zh-Hans.md) that contains the name of the `Person`.

```swift
struct StaffList: View {
    var body: some View {
        List {
            ForEach(staff) { person in
                Text(person.name)
            }
        }
    }
}
```



Members of a list must be uniquely identifiable from one another. Unique identifiers allow SwiftUI to automatically generate animations for changes in the underlying data, like inserts, deletions, and moves. Identify list members either by using a type that conforms to [doc://com.apple.documentation/documentation/Swift/Identifiable], as `Person` does, or by providing an `id` parameter with the key path to a unique property of the type. The `ForEach` that populates the list above depends on this behavior, as do the `List` initializers that take a [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] of members to iterate over.



### Display data inside a row

Each row inside a [List](List.zh-Hans.md) must be a SwiftUI [View](View.zh-Hans.md). You may be able to represent your data with a single view such as an [Image](Image.zh-Hans.md) or [Text](Text.zh-Hans.md) view, or you may need to define a custom view to compose several views into something more complex.

As your row views get more sophisticated, refactor the views into separate view structures, passing in the data that the row needs to render. The following example defines a `PersonRowView` to create a two-line view for a `Person`, using fonts, colors, and the system “phone” icon image to visually style the data.

```swift
struct PersonRowView: View {
    var person: Person

    var body: some View {
        VStack(alignment: .leading, spacing: 3) {
            Text(person.name)
                .foregroundColor(.primary)
                .font(.headline)
            HStack(spacing: 3) {
                Label(person.phoneNumber, systemImage: "phone")
            }
            .foregroundColor(.secondary)
            .font(.subheadline)
        }
    }
}

struct StaffList: View {
    var body: some View {
        List {
            ForEach(staff) { person in
                PersonRowView(person: person)
            }
        }
    }
}
```



For more information on composing the types of views commonly used inside list rows, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Represent data hierarchy with sections

[List](List.zh-Hans.md) views can also display data with a level of hierarchy, grouping associated data into sections.

Consider an expanded data model that represents an entire company, including multiple departments. Each `Department` has a name and an array of `Person` instances, and the company has an array of the `Department` type.

```swift
struct Department: Identifiable {
    let id = UUID()
    var name: String
    var staff: [Person]
}

struct Company {
    var departments: [Department]
}

var company = Company(departments: [
    Department(name: "Sales", staff: [
        Person(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
        Person(name: "Mei Chen", phoneNumber: "(919) 555-2481"),
        // ...
    ]),
    Department(name: "Engineering", staff: [
        Person(name: "Bill James", phoneNumber: "(408) 555-4450"),
        Person(name: "Anne Johnson", phoneNumber: "(417) 555-9311"),
        // ...
    ]),
    // ...
])
```

Use [Section](Section.zh-Hans.md) views to give the data inside a `List` a level of hierarchy. Start by creating the `List`, using a [ForEach](ForEach.zh-Hans.md) to iterate over the `company.departments` array, and then create `Section` views for each department. Within the section’s view builder, use a `ForEach` to iterate over the department’s `staff`, and return a customized view for each `Person`.

```swift
List {
     ForEach(company.departments) { department in
         Section(header: Text(department.name)) {
             ForEach(department.staff) { person in
                PersonRowView(person: person)
             }
         }
     }
 }
```





## Use Lists for Navigation

Using a [NavigationLink](NavigationLink.zh-Hans.md) within a [List](List.zh-Hans.md) contained inside a [NavigationView](NavigationView.zh-Hans.md) adds platform-appropriate visual styling, and in some cases, additional container views that provide the structure for navigation. SwiftUI uses one of two visual presentations, based on the runtime environment:

- A list with disclosure indicators, which performs an animated navigation to a destination scene when the user chooses a list item. SwiftUI uses this presentation on watchOS, tvOS, and on most iOS devices except as described below.
- A two-panel split view, with the top-level data as a list on the left side and the detail on the right. To get this presentation, you also need to provide a placeholder view after the list; this placeholder fills the detail pane until the user makes a selection. SwiftUI uses this two-panel approach on macOS, iPadOS, and on iOS devices with sufficient horizontal space, as indicated by the [horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) environment value.

The following example sets up a navigation-based UI by wrapping the list with a navigation view. Instances of `NavigationLink` wrap the list’s rows to provide a `destination` view to navigate to when the user taps the row. If a split view navigation is appropriate for the platform, the right panel initially contains the “No Selection” placeholder view, which the navigation view replaces with the destination view when the user makes a selection.

```swift
NavigationView {
    List {
        ForEach(company.departments) { department in
            Section(header: Text(department.name)) {
                ForEach(department.staff) { person in
                    NavigationLink(destination: PersonDetailView(person: person)) {
                        PersonRowView(person: person)
                    }
                }
            }
        }
    }
    .navigationTitle("Staff Directory")

    // Placeholder
    Text("No Selection")
        .font(.headline)
}
```

In this example, the view passed in as the `destination` is a `PersonDetailView`, which repeats the information from the list. In a more complex app, this detail view could show more information about a `Person` than would fit inside the list row.

```swift
struct PersonDetailView: View {
    var person: Person

    var body: some View {
        VStack {
            Text(person.name)
                .foregroundColor(.primary)
                .font(.title)
                .padding()
            HStack {
                Label(person.phoneNumber, systemImage: "phone")
            }
            .foregroundColor(.secondary)
        }
    }
}
```

On most iOS devices (those with a compact horizontal size class), the list appears as a view by itself, and tapping a row performs an animated transition to the destination view. The following figure shows both the list view and the destination view that appears when the user makes a selection:



On the other hand, iPadOS and macOS show the list and the detail view together as a multi-column view. The following figure shows what this example looks like on macOS prior to making a selection, which means the “No selection” placeholder view is still in the detail column.



You can use the [navigationViewStyle(_:)](View/navigationViewStyle.zh-Hans.md) view modifier to change the default behavior of a `NavigationView`. For example, on iOS, the [StackNavigationViewStyle](StackNavigationViewStyle.zh-Hans.md) forces single-column mode, even on an iPad in landscape orientation.

## Creating a list

- **List**: A container that presents rows of data arranged in a single column, optionally providing the ability to select one or more members.
- **listStyle(_:)**: Sets the style for lists within this view.

