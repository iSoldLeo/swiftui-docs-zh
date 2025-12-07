--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationStack

抓取时间：2025-12-02T16:24:11Z

---

# NavigationStack

**Structure**

一个用于显示根视图并允许在根视图上方显示其他视图的视图。

## 声明

```swift
@MainActor @preconcurrency struct NavigationStack<Data, Root> where Root : View
```

## 概述

使用导航堆栈可以在根视图上方显示一系列视图。用户可以通过点击或轻触 [NavigationLink](NavigationLink.zh-Hans.md) 将视图添加到堆栈顶部，并使用内置的、平台适用的控件（例如“返回”按钮或滑动操作）移除视图。堆栈始终显示最近添加且尚未移除的视图，并且不允许移除根视图。

要创建导航链接，请在堆栈的视图层次结构中添加 [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 修饰符，将视图与数据类型关联起来。然后初始化 [NavigationLink](NavigationLink.zh-Hans.md)，以呈现相同类型的数据实例。以下堆栈显示了 `ParkDetails` 视图，用于呈现 `Park` 类型的数据：

```swift
NavigationStack {
    List(parks) { park in
        NavigationLink(park.name, value: park)
    }
    .navigationDestination(for: Park.self) { park in
        ParkDetails(park: park)
    }
}
```

在本例中，[List](List.zh-Hans.md) 作为根视图，始终存在。从列表中选择一个导航链接会将 `ParkDetails` 视图添加到堆栈中，使其覆盖列表。返回上一级视图会移除详细信息视图，并再次显示列表。当堆栈为空且根视图（即列表）可见时，系统会禁用后向导航控件。

### 管理导航状态

默认情况下，导航堆栈会管理状态以跟踪堆栈中的视图。但是，您的代码可以通过将堆栈绑定到您创建的数据值集合来共享状态控制权。堆栈会在向堆栈中添加视图时向集合中添加项，并在移除视图时移除项。例如，您可以创建一个名为 [State](State.zh-Hans.md) 的属性来管理公园详情视图的导航：

```swift
@State private var presentedParks: [Park] = []
```

将状态初始化为空数组表示堆栈中没有任何视图。使用初始化器 [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md) 创建堆栈时，请使用美元符号 (`$`) 前缀为该状态属性提供 [Binding](Binding.zh-Hans.md)：

```swift
NavigationStack(path: $presentedParks) {
    List(parks) { park in
        NavigationLink(park.name, value: park)
    }
    .navigationDestination(for: Park.self) { park in
        ParkDetails(park: park)
    }
}
```

与之前一样，当用户点击或轻触公园的导航链接时，堆栈会使用关联的公园数据显示 `ParkDetails` 视图。但是，现在堆栈还会将公园数据放入 `presentedParks` 数组中。您的代码可以监听此数组以读取当前的堆栈状态。它还可以修改此数组以更改堆栈上的视图。例如，您可以创建一个方法，使用一组特定的公园配置堆栈：

```swift
func showParks() {
    presentedParks = [Park("Yosemite"), Park("Sequoia")]
}
```

`showParks` 方法会将堆栈的显示替换为一个视图，该视图显示 Sequoia 的详细信息，Sequoia 是新 `presentedParks` 数组中的最后一个项目。从该视图返回会将 Sequoia 从数组中移除，从而显示一个显示 Yosemite 详细信息的视图。使用路径可以支持深度链接、状态恢复或其他类型的程序化导航。

### 导航到不同的视图类型

要创建一个可以显示多种视图的堆栈，您可以在堆栈的视图层次结构中添加多个 [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 修饰符，每个修饰符表示不同的数据类型。堆栈会根据各自的数据类型将导航链接与导航目标进行匹配。

要创建包含多种数据类型的程序化导航路径，可以使用 [NavigationPath](NavigationPath.zh-Hans.md) 实例作为路径。

## 创建导航堆栈

- **init(root:)**：创建一个管理自身导航状态的导航堆栈。

## 创建带有路径的导航堆栈

- **init(path:root:)**：创建一个具有可控同构导航状态的导航堆栈。

## 将视图堆叠在一列中

- **NavigationPath**：表示导航堆栈内容的已去除类型标记的数据列表。

- **navigationDestination(for:destination:)**：将目标视图与导航堆栈中显示的数据类型关联起来。

- **navigationDestination(isPresented:destination:)**：将目标视图与一个绑定关联起来，该绑定可用于将视图推送到 [NavigationStack](NavigationStack.zh-Hans.md)。

- **navigationDestination(item:destination:)**：将目标视图与一个绑定值关联起来，以便在导航堆栈或导航拆分视图中使用。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationStack
crawled: 2025-12-02T16:24:11Z
---

# NavigationStack

**Structure**

A view that displays a root view and enables you to present additional views over the root view.

## Declaration

```swift
@MainActor @preconcurrency struct NavigationStack<Data, Root> where Root : View
```

## Overview

Use a navigation stack to present a stack of views over a root view. People can add views to the top of the stack by clicking or tapping a [NavigationLink](NavigationLink.zh-Hans.md), and remove views using built-in, platform-appropriate controls, like a Back button or a swipe gesture. The stack always displays the most recently added view that hasn’t been removed, and doesn’t allow the root view to be removed.

To create navigation links, associate a view with a data type by adding a [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) modifier inside the stack’s view hierarchy. Then initialize a [NavigationLink](NavigationLink.zh-Hans.md) that presents an instance of the same kind of data. The following stack displays a `ParkDetails` view for navigation links that present data of type `Park`:

```swift
NavigationStack {
    List(parks) { park in
        NavigationLink(park.name, value: park)
    }
    .navigationDestination(for: Park.self) { park in
        ParkDetails(park: park)
    }
}
```

In this example, the [List](List.zh-Hans.md) acts as the root view and is always present. Selecting a navigation link from the list adds a `ParkDetails` view to the stack, so that it covers the list. Navigating back removes the detail view and reveals the list again. The system disables backward navigation controls when the stack is empty and the root view, namely the list, is visible.

### Manage navigation state

By default, a navigation stack manages state to keep track of the views on the stack. However, your code can share control of the state by initializing the stack with a binding to a collection of data values that you create. The stack adds items to the collection as it adds views to the stack and removes items when it removes views. For example, you can create a [State](State.zh-Hans.md) property to manage the navigation for the park detail view:

```swift
@State private var presentedParks: [Park] = []
```

Initializing the state as an empty array indicates a stack with no views. Provide a [Binding](Binding.zh-Hans.md) to this state property using the dollar sign (`$`) prefix when you create a stack using the [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md) initializer:

```swift
NavigationStack(path: $presentedParks) {
    List(parks) { park in
        NavigationLink(park.name, value: park)
    }
    .navigationDestination(for: Park.self) { park in
        ParkDetails(park: park)
    }
}
```

Like before, when someone taps or clicks the navigation link for a park, the stack displays the `ParkDetails` view using the associated park data. However, now the stack also puts the park data in the `presentedParks` array. Your code can observe this array to read the current stack state. It can also modify the array to change the views on the stack. For example, you can create a method that configures the stack with a specific set of parks:

```swift
func showParks() {
    presentedParks = [Park("Yosemite"), Park("Sequoia")]
}
```

The `showParks` method replaces the stack’s display with a view that shows details for Sequoia, the last item in the new `presentedParks` array. Navigating back from that view removes Sequoia from the array, which reveals a view that shows details for Yosemite. Use a path to support deep links, state restoration, or other kinds of programmatic navigation.

### Navigate to different view types

To create a stack that can present more than one kind of view, you can add multiple [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) modifiers inside the stack’s view hierarchy, with each modifier presenting a different data type. The stack matches navigation links with navigation destinations based on their respective data types.

To create a path for programmatic navigation that contains more than one kind of data, you can use a [NavigationPath](NavigationPath.zh-Hans.md) instance as the path.

## Creating a navigation stack

- **init(root:)**: Creates a navigation stack that manages its own navigation state.

## Creating a navigation stack with a path

- **init(path:root:)**: Creates a navigation stack with homogeneous navigation state that you can control.

## Stacking views in one column

- **NavigationPath**: A type-erased list of data representing the content of a navigation stack.
- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](NavigationStack.zh-Hans.md).
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view

## Conforms To

- View

