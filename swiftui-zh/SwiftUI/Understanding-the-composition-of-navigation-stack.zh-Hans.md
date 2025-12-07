--- 来源：https://developer.apple.com/documentation/SwiftUI/Understanding-the-composition-of-navigation-stack

抓取时间：2025-12-02T17:29:29Z

---

# 理解导航栈

**Article**

了解导航栈、链接以及如何在应用结构中管理导航类型。

## 概述

[NavigationStack](NavigationStack.zh-Hans.md) 是应用导航结构的容器。使用导航栈可以在根视图之上呈现一系列视图。

`NavigationStack` 通过其初始化器的路径参数将其状态暴露给应用。要创建可控制或跟踪导航堆栈中视图的路径的导航堆栈，请使用 [NavigationPath](NavigationPath.zh-Hans.md) 或 [Binding](Binding.zh-Hans.md) 连接到包含 [doc://com.apple.documentation/documentation/Swift/Hashable] 元素的 [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] 和 [doc://com.apple.documentation/documentation/Swift/RangeReplaceableCollection]。

`NavigationPath` 是一个类型擦除的集合，您可以在其中存储异构数据列表。对于同构数据，请改用 [doc://com.apple.documentation/documentation/Swift/Array]。由于 `NavigationPath` 是类型擦除的，因此它可以表示与导航堆栈中的视图对应的不同类型的数据。

导航堆栈的另一个元素是*导航目标*，它封装了用户可以在应用程序中导航到的视图。

您可以使用以下方法在 `NavigationStack` 上显示目的地：

### 显示视图-目的地链接

您可以使用 `NavigationLink(destination:label:)` 将视图推送到 `NavigationStack` 上。通过此初始化器，您可以同时指定标签（显示在链接本身上）和目的地（用户点击链接时显示）。

将 [NavigationLink](NavigationLink.zh-Hans.md) 包含在视图层次结构中更高层的导航结构中，例如父视图。如果未满足此条件，则链接通常会显示为禁用状态。

以下示例展示了 `NavigationStack` 中包含两个链接的情况：

```swift
struct DestinationView: View {
    var body: some View {
        NavigationStack {
            NavigationLink {
                ColorDetail(color: .mint, text: "Mint")
            } label: {
                Text("Mint")
            }
            
            NavigationLink {
                ColorDetail(color: .red, text: "Red")
            } label: {
                Text("Red")
            }
        }
    }
}

struct ColorDetail: View {
    var color: Color
    var text: String

    var body: some View {
        VStack {
            Text(text)
            color
         }
    }
}
```

在此示例中，点击名为“Mint”的标签会将 `ColorDetail(color: .mint, text: "Mint")` 视图推送到导航堆栈中。导航堆栈的内容包括深度为 `0` 的根视图（即 `NavigationLink` 本身）和深度为 `1` 的 `ColorDetail(color: .mint, text: "Mint")`。

使用 [init(destination:label:)](NavigationLink/init_destination_label.zh-Hans.md) 时，请注意：

- SwiftUI 会跟踪导航状态和导航路径的内容；但是，您的应用没有状态钩子来指示系统何时推送视图。

- 其状态无法通过编程方式恢复。

请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/Understanding-the-composition-of-navigation-stack#Manage-navigation-state-and-compose-links] 中描述的有状态导航技术来跟踪导航链接的触发时间，而不是使用 [onAppear(perform:)](View/onAppear_perform.zh-Hans.md) 或 [task(priority:_:)](View/task_priority.zh-Hans.md)。

使用 [navigationDestination(isPresented:destination:)](View/navigationDestination_isPresented_destination.zh-Hans.md) 修饰符，通过绑定到 `Boolean` 值，以编程方式进行导航。例如，您可以以编程方式将 `ColorDetail` 视图推入堆栈：

```swift
struct DestinationView: View { 
    @State private var showDetails = false
    var favoriteColor: Color
    
    NavigationStack {
        VStack {
            Circle()
                .fill(favoriteColor)
            Button("Show details") {
                showDetails = true
            }
        }
        .navigationDestination(isPresented: $showDetails) {
            ColorDetail(color: favoriteColor, text: color.description)
        }
    }
}
```

当您希望基于状态切换而非用户交互进行导航，或者当您的应用呈现的一次性目标与导航堆栈中同质路径的数据类型不同时，请使用此方法。

### 呈现值-目标链接

当您向导航路径添加数据时，SwiftUI 会将数据类型映射到视图，然后在用户点击链接时将其推入导航堆栈。要描述堆栈显示的视图，请在 `NavigationStack` 中使用 [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 视图修饰符。

以下示例将 `DestinationView` 实现为一系列导航链接：

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Red", value: Color.red)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color, text: color.description)
    }
}
```

在上面的示例中，SwiftUI 使用值类型（在本例中为 `Color`）来确定合适的导航目标。通过基于值的导航，您可以为单个堆栈定义多种可能的目标。当用户点击“Mint”时，SwiftUI 会将值 `.mint` 的视图 `ColorDetail` 推入堆栈。

基于值的导航在目标类型混合的场景中表现出色。除了颜色之外，您还可以扩展应用以处理与食谱相关的内容：

```swift
struct ValueView: View {
    private var recipes: [Recipe] = [.applePie, .chocolateCake]
    
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                ForEach(recipes) { recipe in
                    NavigationLink(recipe.description, value: recipe)
                }
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}

struct RecipeDetailView: View {
    var recipe: Recipe
    
    var body: some View {
        Text(recipe.description)
    }
}

enum Recipe: Identifiable, Hashable, Codable {
    case applePie
    case chocolateCake
    
    var id: Self { self }
    
    var description: String {
        switch self {
        case .applePie:
            return "Apple Pie"
        case .chocolateCake:
            return "Chocolate Cake"
        }
    }
}
```

在本例中，`NavigationStack` 支持两种目标类型：`Color` 用于颜色，`Recipe` 用于食谱。SwiftUI 会根据导航链接中值的数据类型确定正确的目标视图。

当需要根据项目是否存在导航到某个视图时，请使用 [navigationDestination(item:destination:)](View/navigationDestination_item_destination.zh-Hans.md)。当项目绑定不为 nil 时，SwiftUI 会将该值传递给目标闭包，并将视图压入堆栈。例如：

```swift
struct ContentView: View {
    private var recipes: [Recipe] = [.applePie, .chocolateCake]
    @State private var selectedRecipe: Recipe?
    
    var body: some View {
        NavigationStack {
            List(recipes, selection: $selectedRecipe) { recipe in
                NavigationLink(recipe.description, value: recipe)
            }
            .navigationDestination(item: $selectedRecipe) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```

当用户点击食谱时，`selectedRecipe` 值会更新，SwiftUI 会将 `RecipeDetailView(recipe: recipe)` 压入导航堆栈。您可以通过将 `selectedRecipe` 设置为 nil 来将视图从堆栈中弹出。

### 管理导航状态和组合链接

默认情况下，导航堆栈会管理状态以跟踪堆栈上的视图。但是，您的应用程序可以通过将堆栈绑定到您创建的数据值集合来共享状态控制权。

当您想要观察此堆栈的导航状态时，请使用 [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md)，它接受一个绑定到 `NavigationPath` 参数的函数。

`NavigationPath` 数据类型是一个异构集合类型，接受任何 `Hashable` 值。您可以通过调用 [append(_:)](NavigationPath/append.zh-Hans.md) 或当用户点击值目标链接（例如 [init(value:label:)](NavigationLink/init_value_label.zh-Hans.md)）时向路径添加内容。

当您使用 [init(_:value:)](NavigationLink/init___value.zh-Hans.md) 将值压入堆栈时，您会将该值追加到路径中，如下所示：

```swift
struct ContentView: View {
    @State private var path = NavigationPath()

    var body: some View {
        NavigationStack(path: $path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color)
            }
        }
    }
}
```

在本例中，当用户激活链接时，SwiftUI 会将相应的值（例如 `Color.mint`）添加到 `path`。SwiftUI 使用名为 `path` 的 [State](State.zh-Hans.md) 属性来管理导航堆栈的状态。

[init(path:root:)](NavigationStack/init_path_root.zh-Hans.md) 还提供了一个初始化器，其中路径参数接受一个 [Binding](Binding.zh-Hans.md) 到 `RandomAccessCollection` 和一个 `RangeReplaceableCollection` 参数。您可以将路径存储为使用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏数据类型的对象中的一个属性，并使用属性观察器（例如 `willSet` 和 `didSet`）或 [onChange(of:initial:_:)](View/onChange_of_initial.zh-Hans.md) 修饰符来响应值-目标链接触发时的变化。

在这种情况下，导航路径是一个同构集合类型，它接受标准类型（例如 `Array`）或自定义数据类型，如下所示：

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        willSet {
            print("will set to \(newValue)")
        }
        
        didSet {
            print("didSet to \(path)")
        }
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
        }
    }
}
```

在上面的示例中，属性观察器 `willSet` 和 `didSet` 会跟踪导航链接何时触发。

您还可以使用对 `path` 变量的引用来执行程序化导航。例如，您可以从堆栈中弹出视图：

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        willSet {
            print("will set to \(newValue)")
        }
        
        didSet {
            print("didSet to \(path)")
        }
    }
    
    @discardableResult
    func navigateBack() -> Color? {
        path.popLast()
    }
}
```

当堆栈显示的视图依赖于单一数据类型时，请使用标准类型；当需要在单个堆栈中呈现多种数据类型时，请使用 `NavigationPath`，如下例所示：

```swift
struct ValueView: View {
    @State private var path = NavigationPath()
    
    var body: some View {
        NavigationStack(path: $path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                NavigationLink("Apple Pie", value: Recipe.applePie)
                NavigationLink("Chocolate Cake", value: Recipe.chocolateCake)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```

导航 API 允许您根据实际情况灵活使用这两种链接样式。

例如，当用户点击“查看薄荷绿”链接时，SwiftUI 会将基于值的目标链接推入堆栈，然后是视图目标链接：

```swift
struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        RecipeDetailView(recipe: .applePie)
                    }
                }
        }
    }
}
```

此示例中的代码运行后，用户点击每个 `NavigationLink`，导航堆栈将构建三个视图：

SwiftUI 会跟踪整个导航路径。底层数据结构如下例所示：

```swift
Root → [Color.mint] → [RecipeDetailView]
```

从概念上讲，SwiftUI 会将基于视图的目标堆叠在基于值的目标之上，形成一个导航路径栈。例如，以下代码将上述示例中的 `RecipeDetailView` 替换为 `NavigationLink`：

```swift
struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        NavigationLink("Push another view", value: Color.pink)
                    }
                }
        }
    }
}
```

运行修改后的示例时，视图目标链接仍然位于栈顶。

如果在栈中使用异构或同构路径，您可能会观察到导航路径随时间发生变化，如下所示：

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        didSet {
            print("didSet to \(path)")
        }
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        RecipeDetailView(recipe: .applePie)
                    }
                }
        }
    }
}
```

当用户浏览应用时，会打印以下日志：

```swift
New path: []
New Path: [Color.mint]
```

之所以会打印日志，是因为视图目标导航链接不会引起应用可观察到的任何状态变化。如果在视图目标链接位于堆栈中时尝试推送值，SwiftUI 会弹出所有视图目标，并将该值的目标位置压入堆栈。

### 恢复导航路径的状态

恢复导航路径的状态允许您在后续启动时将界面恢复到之前的交互点，从而为用户提供应用体验的连续性。

在 iOS 中，状态恢复在窗口或场景级别尤为重要，因为窗口会频繁地出现和消失。因此，处理导航路径的状态恢复时，应与处理应用在窗口或场景级别的状态恢复方式相同。请参阅 [restoring-your-app-s-state-with-swiftui](restoring-your-app-s-state-with-swiftui.zh-Hans.md) 了解如何存储场景数据。

使用 `Codable`，您可以手动持久化和加载导航堆栈路径，具体方式取决于路径数据类型是同构的还是异构的。存储同构路径，如下例所示：

```swift
@Observable
class NavigationManager {
    var path: [Recipe] = [] {
        didSet {
            save()
        }
    }
    
    /// The URL for the JSON file that stores the navigation path.
    private static var dataURL: URL {
        .documentsDirectory.appending(path: "NavigationPath.json")
    }
    
    init() {
        do {
            // Load the data model from the 'NavigationPath' data file found in the Documents directory.
            let path = try load(url: NavigationManager.dataURL)
            self.path = path
        } catch {
            // Handle error.
        }
    }
    
    func save() {
        let encoder = JSONEncoder()
        do {
            let data = try encoder.encode(path)
            try data.write(to: NavigationManager.dataURL)
        } catch {
            // Handle error.
        }
    }
    
    /// Load the navigation path from a previously saved state.
    func load(url: URL) throws -> [Recipe] {
        let data = try Data(contentsOf: url, options: .mappedIfSafe)
        let decoder = JSONDecoder()
        return try decoder.decode([Recipe].self, from: data)
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                NavigationLink("Apple Pie", value: Recipe.applePie)
                NavigationLink("Chocolate Cake", value: Recipe.chocolateCake)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```

在上面的示例中，当 `path` 发生变化时，`didSet` 属性观察器会被触发，并调用 `save` 函数。该函数会将新路径保存到磁盘，以便应用程序在初始化 `NavigationManager` 时能够恢复该路径。

使用 `NavigationPath` 存储异构路径，如下例所示：

```swift
@Observable
class NavigationManager {
    var path = NavigationPath() {
        didSet {
            save()
        }
    }
    
    /// The URL for the JSON file that stores the navigation path.
    private static var dataURL: URL {
        .documentsDirectory.appending(path: "NavigationPath.json")
    }
    
    init() {
        do {
            // Load the data model from the 'NavigationPath' data file found in the Documents directory.
            let path = try load(url: NavigationManager.dataURL)
            self.path = path
        } catch {
            // Handle error
        }
    }
    
    func save() {
        guard let codableRepresentation = path.codable else { return }
        let encoder = JSONEncoder()
        do {
            let data = try encoder.encode(codableRepresentation)
            try data.write(to: NavigationManager.dataURL)
        } catch {
            //Handle error.
        }
    }
    
    /// Load the navigation path from a previously saved data.
    func load(url: URL) throws -> NavigationPath {
        let data = try Data(contentsOf: url, options: .mappedIfSafe)
        let decoder = JSONDecoder()
        let path = try decoder.decode(NavigationPath.CodableRepresentation.self, from: data)
        return NavigationPath(path)
    }
}

```

在上面的示例中，`save` 方法会检查 `path.codable` 是否为空。该值以可序列化的格式描述路径的内容。如果路径中任何类型擦除的元素不符合 `codable` 规范，则返回 `nil`。

执行此检查至关重要，因为 `NavigationPath` 不要求数据类型符合 `Codable` 规范。`NavigationPath` 仅要求类型符合 `Hashable` 规范，因此，您无法在编译时验证导航路径是否是 `Codable` 的有效表示。

要了解有关导航栈、链接和路径的更多信息，请参阅 [Bringing-robust-navigation-structure-to-your-swiftui-app](Bringing-robust-navigation-structure-to-your-swiftui-app.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Understanding-the-composition-of-navigation-stack
crawled: 2025-12-02T17:29:29Z
---

# Understanding the navigation stack

**Article**

Learn about the navigation stack, links, and how to manage navigation types in your app’s structure.

## Overview

A [NavigationStack](NavigationStack.zh-Hans.md) is a container for your app’s navigation structure. Use a navigation stack to present a stack of views over a root view.

A `NavigationStack` exposes its state to your app with the path parameter of its initializer. To create a navigation stack with a path that you can control or track views on the navigation stack, use a [NavigationPath](NavigationPath.zh-Hans.md) or a [Binding](Binding.zh-Hans.md) to a [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] and [doc://com.apple.documentation/documentation/Swift/RangeReplaceableCollection] that contains [doc://com.apple.documentation/documentation/Swift/Hashable] elements.

A `NavigationPath` is a type-erased collection on which you can store a heterogenous list of data. For homogenous data, use an [doc://com.apple.documentation/documentation/Swift/Array] instead. Because `NavigationPath` is type-erased, it can represent different types of data that correspond to a view in the navigation stack.



Another element of the navigation stack is the *navigation destination*, which encapsulates the views people can navigate to within your app.

You can present destinations on a `NavigationStack` using:





### Present view–destination links

You can push a view onto a `NavigationStack` using `NavigationLink(destination:label:)`. With this initializer, you specify both a label—displayed on the link itself—and a destination—displayed when someone taps the link.

Enclose a [NavigationLink](NavigationLink.zh-Hans.md) in a navigation structure higher up in the view-hierarchy—an ancestor view, for example. If this condition isn’t met, the link typically appears as disabled.

Below is an example with two links inside a `NavigationStack`:

```swift
struct DestinationView: View {
    var body: some View {
        NavigationStack {
            NavigationLink {
                ColorDetail(color: .mint, text: "Mint")
            } label: {
                Text("Mint")
            }
            
            NavigationLink {
                ColorDetail(color: .red, text: "Red")
            } label: {
                Text("Red")
            }
        }
    }
}

struct ColorDetail: View {
    var color: Color
    var text: String

    var body: some View {
        VStack {
            Text(text)
            color
         }
    }
}
```

In this example, tapping the label titled “Mint” pushes a `ColorDetail(color: .mint, text: "Mint")` view onto the navigation stack. The navigation stack contents are the root view (the `NavigationLink` itself) at depth `0`, and `ColorDetail(color: .mint, text: "Mint")`  at depth `1`.

When you use [init(destination:label:)](NavigationLink/init_destination_label.zh-Hans.md), note that:

- SwiftUI tracks the navigation state and the content of the navigation path; however, there are no stateful hooks for your app that indicate when the system pushes a view.
- Its state can’t be restored programmatically.

Use the stateful navigation techniques described in [doc://com.apple.SwiftUI/documentation/SwiftUI/Understanding-the-composition-of-navigation-stack#Manage-navigation-state-and-compose-links] to track when a navigation link triggers, instead of [onAppear(perform:)](View/onAppear_perform.zh-Hans.md) or [task(priority:_:)](View/task_priority.zh-Hans.md).

Use a [navigationDestination(isPresented:destination:)](View/navigationDestination_isPresented_destination.zh-Hans.md) modifier to navigate programmatically by providing a binding to a `Boolean` value. For example, you can programmatically push `ColorDetail` view onto the stack:

```swift
struct DestinationView: View { 
    @State private var showDetails = false
    var favoriteColor: Color
    
    NavigationStack {
        VStack {
            Circle()
                .fill(favoriteColor)
            Button("Show details") {
                showDetails = true
            }
        }
        .navigationDestination(isPresented: $showDetails) {
            ColorDetail(color: favoriteColor, text: color.description)
        }
    }
}
```

Use this approach when you want to navigate based on toggling state rather than by people’s interaction, or when your app presents a one-off destination with a different data type than the homogenous path of the navigation stack.

### Present value-destination links

When you add data to the navigation path, SwiftUI maps the data type to a view, then pushes it onto the navigation stack when someone taps the link. To describe the view the stack displays, use the [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) view modifier inside a `NavigationStack`.

The following example implements `DestinationView` as a series of navigation links:

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Red", value: Color.red)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color, text: color.description)
    }
}
```

In the example above, SwiftUI uses the value type—in this case, `Color`—to determine the appropriate navigation destination. With value-based navigation, you can define a variety of possible destinations for a single stack When someone taps “Mint”, SwiftUI pushes `ColorDetail` view with a value `.mint` onto the stack.

Value-based navigation shines in scenarios with mixed destination types. You can extend your app to handle recipe-related content in addition to colors:

```swift
struct ValueView: View {
    private var recipes: [Recipe] = [.applePie, .chocolateCake]
    
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                ForEach(recipes) { recipe in
                    NavigationLink(recipe.description, value: recipe)
                }
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}

struct RecipeDetailView: View {
    var recipe: Recipe
    
    var body: some View {
        Text(recipe.description)
    }
}

enum Recipe: Identifiable, Hashable, Codable {
    case applePie
    case chocolateCake
    
    var id: Self { self }
    
    var description: String {
        switch self {
        case .applePie:
            return "Apple Pie"
        case .chocolateCake:
            return "Chocolate Cake"
        }
    }
}
```

In this example, the `NavigationStack` supports two destination types: `Color` for colors, and `Recipe` for recipes. SwiftUI determines the correct destination view based on the data type of the value from the navigation link.

Use [navigationDestination(item:destination:)](View/navigationDestination_item_destination.zh-Hans.md) when you need to navigate to a view based on the presence of an item. When the item binding is non-nil, SwiftUI passes the value into the destination closure and pushes the view onto the stack. For example:

```swift
struct ContentView: View {
    private var recipes: [Recipe] = [.applePie, .chocolateCake]
    @State private var selectedRecipe: Recipe?
    
    var body: some View {
        NavigationStack {
            List(recipes, selection: $selectedRecipe) { recipe in
                NavigationLink(recipe.description, value: recipe)
            }
            .navigationDestination(item: $selectedRecipe) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```

When a person taps a recipe, `selectedRecipe` value updates and SwiftUI pushes `RecipeDetailView(recipe: recipe)` onto the navigation stack. You can pop the view off the stack by setting `selectedRecipe` back to nil.

### Manage navigation state and compose links

By default, a navigation stack manages state to keep track of the views on the stack. However, your app can share control of the state by initializing the stack with a binding to a collection of data values that you create.

Use [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md), which takes a binding to a `NavigationPath` argument, when you want to observe the navigation state for this stack.

The `NavigationPath` data type is a heterogeneous collection type that accepts any `Hashable` values. You can add to the path by calling [append(_:)](NavigationPath/append.zh-Hans.md) or when people tap value-destination links such as [init(value:label:)](NavigationLink/init_value_label.zh-Hans.md).

When you push a value onto the stack using [init(_:value:)](NavigationLink/init___value.zh-Hans.md), you append the value to the path, as shown below:

```swift
struct ContentView: View {
    @State private var path = NavigationPath()

    var body: some View {
        NavigationStack(path: $path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color)
            }
        }
    }
}
```

In this example, when someone activates a link, SwiftUI adds the corresponding value, such as `Color.mint`, to `path`. SwiftUI uses the [State](State.zh-Hans.md) property called `path` to mange the state of the navigation stack.

[init(path:root:)](NavigationStack/init_path_root.zh-Hans.md) also provides an initializer in which the path parameter takes a [Binding](Binding.zh-Hans.md) to a `RandomAccessCollection` and a `RangeReplaceableCollection` argument. You can store the path as a property in an object that leverages the [doc://com.apple.documentation/documentation/Observation/Observable()] macro data type, and use property observers such as `willSet` and `didSet` or the [onChange(of:initial:_:)](View/onChange_of_initial.zh-Hans.md) modifier to respond to changes when the value-destination link triggers.

In this case, the navigation path is a homogenous collection type that accepts a standard type, such as `Array`, or a custom data type as shown below:

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        willSet {
            print("will set to \(newValue)")
        }
        
        didSet {
            print("didSet to \(path)")
        }
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
        }
    }
}
```

In the example above, the `willSet` and `didSet` property observers track when a navigation link triggers.

You can also use the reference to `path` variable to perform programmatic navigation. For example, you can pop a view off the stack:

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        willSet {
            print("will set to \(newValue)")
        }
        
        didSet {
            print("didSet to \(path)")
        }
    }
    
    @discardableResult
    func navigateBack() -> Color? {
        path.popLast()
    }
}
```

Use a standard type when your stack displays views that rely on a single type of data, and `NavigationPath` when you need to present multiple data types in a single stack, as in the following example:

```swift
struct ValueView: View {
    @State private var path = NavigationPath()
    
    var body: some View {
        NavigationStack(path: $path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                NavigationLink("Apple Pie", value: Recipe.applePie)
                NavigationLink("Chocolate Cake", value: Recipe.chocolateCake)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```



When composed together, the navigation APIs allow you to use both styles of links, depending on what works best.

Here, when someone taps on the link “View Mint Color”, SwiftUI pushes the value-based destination link onto the stack, followed by a view-destination link:

```swift
struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        RecipeDetailView(recipe: .applePie)
                    }
                }
        }
    }
}
```

After the code in this example runs, and someone clicks each `NavigationLink`, the navigation stack builds up with three views:



SwiftUI keeps track of the entire navigation path. The underlying data structure looks like the following example:

```swift
Root → [Color.mint] → [RecipeDetailView]
```

Conceptually, SwiftUI stacks view-based destinations on top of the value-based destinations in the stack’s navigation path. For example, the code below replaces `RecipeDetailView` from the above example with a `NavigationLink`:

```swift
struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        NavigationLink("Push another view", value: Color.pink)
                    }
                }
        }
    }
}
```

When you run the revised example, the view-destination link is still on the top of the stack.

If you use a heterogenous or homogeneous path on the stack, you may observe changes to the navigation path over time, as shown below:

```swift
@Observable
class NavigationManager {
    var path: [Color] = [] {
        didSet {
            print("didSet to \(path)")
        }
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            NavigationLink("View Mint Color", value: Color.mint)
                .navigationDestination(for: Color.self) { color in
                    NavigationLink("Push Recipe View") {
                        RecipeDetailView(recipe: .applePie)
                    }
                }
        }
    }
}
```

When someone navigates through the app, it prints the following logs:

```swift
New path: []
New Path: [Color.mint]
```

The logs print because view-destination navigation links don’t cause any state changes that your app can observe. If you attempt to push a value while a view-destination link is on the stack, SwiftUI pops all view destinations and pushes the value’s destination onto the stack.

### Restore state for navigation paths

State restoration for a navigation path enables you restore your interface to the previous interaction point during a subsequent launch, providing continuity for people using your app.

In iOS, state restoration is especially important at the window or scene level, because windows come and go frequently. For this reason, it’s important to think about state restoration for navigation path in the same way you handle restoring your app’s state at the window or scene level. See [restoring-your-app-s-state-with-swiftui](restoring-your-app-s-state-with-swiftui.zh-Hans.md) to learn about storing scene data.

Using `Codable`, you can manually persist and load the navigation stack path in one of two ways, depending on whether the path data type is homogeneous or heterogeneous. Store a homogenous path as in the following example:

```swift
@Observable
class NavigationManager {
    var path: [Recipe] = [] {
        didSet {
            save()
        }
    }
    
    /// The URL for the JSON file that stores the navigation path.
    private static var dataURL: URL {
        .documentsDirectory.appending(path: "NavigationPath.json")
    }
    
    init() {
        do {
            // Load the data model from the 'NavigationPath' data file found in the Documents directory.
            let path = try load(url: NavigationManager.dataURL)
            self.path = path
        } catch {
            // Handle error.
        }
    }
    
    func save() {
        let encoder = JSONEncoder()
        do {
            let data = try encoder.encode(path)
            try data.write(to: NavigationManager.dataURL)
        } catch {
            // Handle error.
        }
    }
    
    /// Load the navigation path from a previously saved state.
    func load(url: URL) throws -> [Recipe] {
        let data = try Data(contentsOf: url, options: .mappedIfSafe)
        let decoder = JSONDecoder()
        return try decoder.decode([Recipe].self, from: data)
    }
}

struct ContentView: View {
    @State private var navigationManager = NavigationManager()

    var body: some View {
        NavigationStack(path: $navigationManager.path) {
            List {
                NavigationLink("Mint", value: Color.mint)
                NavigationLink("Red", value: Color.red)
                NavigationLink("Apple Pie", value: Recipe.applePie)
                NavigationLink("Chocolate Cake", value: Recipe.chocolateCake)
            }
            .navigationDestination(for: Color.self) { color in
                ColorDetail(color: color, text: color.description)
            }
            .navigationDestination(for: Recipe.self) { recipe in
                RecipeDetailView(recipe: recipe)
            }
        }
    }
}
```

In the above example, when the `path` changes, `didSet` property observer triggers and the `save` function is called. The function saves the new path to disk enabling the app to restore it when initializing `NavigationManager`.

Store a heterogeneous path using `NavigationPath`, as shown in the following example:

```swift
@Observable
class NavigationManager {
    var path = NavigationPath() {
        didSet {
            save()
        }
    }
    
    /// The URL for the JSON file that stores the navigation path.
    private static var dataURL: URL {
        .documentsDirectory.appending(path: "NavigationPath.json")
    }
    
    init() {
        do {
            // Load the data model from the 'NavigationPath' data file found in the Documents directory.
            let path = try load(url: NavigationManager.dataURL)
            self.path = path
        } catch {
            // Handle error
        }
    }
    
    func save() {
        guard let codableRepresentation = path.codable else { return }
        let encoder = JSONEncoder()
        do {
            let data = try encoder.encode(codableRepresentation)
            try data.write(to: NavigationManager.dataURL)
        } catch {
            //Handle error.
        }
    }
    
    /// Load the navigation path from a previously saved data.
    func load(url: URL) throws -> NavigationPath {
        let data = try Data(contentsOf: url, options: .mappedIfSafe)
        let decoder = JSONDecoder()
        let path = try decoder.decode(NavigationPath.CodableRepresentation.self, from: data)
        return NavigationPath(path)
    }
}

```

In the example above, the `save` method checks `path.codable` for nullability. This value describes the contents of the path in a serializable format. It returns `nil` if any of the type-erased elements of the path don’t conform to the `codable`.

It’s important to perform this check because `NavigationPath` doesn’t require the data types to conform to `Codable`. `NavigationPath` only needs the types to conform to `Hashable`, and as a result, you can’t verify that the navigation path is a valid representation of `Codable` at compile time.

To learn more about navigation stacks, links and paths, see [Bringing-robust-navigation-structure-to-your-swiftui-app](Bringing-robust-navigation-structure-to-your-swiftui-app.zh-Hans.md).

