--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabItem(_:)

抓取时间：2025-11-30T21:15:02Z

---

# tabItem(_:)

**实例方法**

设置与此视图关联的标签栏项。

## 声明

```swift
nonisolated func tabItem<V>(@ViewBuilder _ label: () -> V) -> some View where V : View

```

## 参数

- **label**：要与此视图关联的标签栏项。

## 说明

使用 `tabItem(_:)` 将视图配置为 [TabView](../TabView.zh-Hans.md) 中的标签栏项。以下示例在 [TabView](../TabView.zh-Hans.md) 中添加两个视图作为选项卡：

```swift
struct View1: View {
    var body: some View {
        Text("View 1")
    }
}

struct View2: View {
    var body: some View {
        Text("View 2")
    }
}

struct TabItem: View {
    var body: some View {
        TabView {
            View1()
                .tabItem {
                    Label("Menu", systemImage: "list.dash")
                }

            View2()
                .tabItem {
                    Label("Order", systemImage: "square.and.pencil")
                }
        }
    }
}
```

## 已弃用类型

- **NavigationView**：用于呈现视图堆栈的视图，该堆栈表示导航层次结构中的可见路径。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabItem(_:)
crawled: 2025-11-30T21:15:02Z
---

# tabItem(_:)

**Instance Method**

Sets the tab bar item associated with this view.

## Declaration

```swift
nonisolated func tabItem<V>(@ViewBuilder _ label: () -> V) -> some View where V : View

```

## Parameters

- **label**: The tab bar item to associate with this view.

## Discussion

Use `tabItem(_:)` to configure a view as a tab bar item in a [TabView](../TabView.zh-Hans.md). The example below adds two views as tabs in a [TabView](../TabView.zh-Hans.md):

```swift
struct View1: View {
    var body: some View {
        Text("View 1")
    }
}

struct View2: View {
    var body: some View {
        Text("View 2")
    }
}

struct TabItem: View {
    var body: some View {
        TabView {
            View1()
                .tabItem {
                    Label("Menu", systemImage: "list.dash")
                }

            View2()
                .tabItem {
                    Label("Order", systemImage: "square.and.pencil")
                }
        }
    }
}
```



## Deprecated Types

- **NavigationView**: A view for presenting a stack of views that represents a visible path in a navigation hierarchy.

