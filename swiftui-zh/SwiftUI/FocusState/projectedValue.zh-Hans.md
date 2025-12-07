--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusState/projectedValue
抓取时间：2025-12-03T04:53:40Z

---

# projectedValue

**实例属性**

焦点状态值的投影，返回一个绑定。

## 声明

```swift
var projectedValue: FocusState<Value>.Binding { get }
```

## 说明

当焦点位于绑定到此状态的任何视图之外时，对于可选类型的状态，其投影值为 `nil`；对于布尔类型的状态，其投影值为 `false`。

在以下简单的导航侧边栏示例中，当用户按下“筛选侧边栏内容”按钮时，焦点会移动到侧边栏的筛选文本字段。相反，如果用户手动将焦点移动到侧边栏的筛选器，则 `isFiltering` 的值会自动变为 `true`，并且侧边栏视图会更新。

```swift
struct Sidebar: View {
    @State private var filterText = ""
    @FocusState private var isFiltering: Bool

    var body: some View {
        VStack {
            Button("Filter Sidebar Contents") {
                isFiltering = true
            }

            TextField("Filter", text: $filterText)
                .focused($isFiltering)
        }
    }
}
```

## 检查焦点状态

- **FocusState.Binding**：一种属性包装类型，可以读取和写入指示当前焦点位置的值。

- **wrappedValue**：当前状态值，其中考虑了由于当前焦点位置而可能生效的任何绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusState/projectedValue
crawled: 2025-12-03T04:53:40Z
---

# projectedValue

**Instance Property**

A projection of the focus state value that returns a binding.

## Declaration

```swift
var projectedValue: FocusState<Value>.Binding { get }
```

## Discussion

When focus is outside any view that is bound to this state, the wrapped value is `nil` for optional-typed state or `false` for Boolean state.

In the following example of a simple navigation sidebar, when the user presses the Filter Sidebar Contents button, focus moves to the sidebar’s filter text field. Conversely, if the user moves focus to the sidebar’s filter manually, then the value of `isFiltering` automatically becomes `true`, and the sidebar view updates.

```swift
struct Sidebar: View {
    @State private var filterText = ""
    @FocusState private var isFiltering: Bool

    var body: some View {
        VStack {
            Button("Filter Sidebar Contents") {
                isFiltering = true
            }

            TextField("Filter", text: $filterText)
                .focused($isFiltering)
        }
    }
}
```

## Inspecting the focus state

- **FocusState.Binding**: A property wrapper type that can read and write a value that indicates the current focus location.
- **wrappedValue**: The current state value, taking into account whatever bindings might be in effect due to the current location of focus.

