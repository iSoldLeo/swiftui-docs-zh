---
来源：https://developer.apple.com/documentation/SwiftUI/DefaultToolbarItem/init(kind:place:)
抓取时间：2025-12-03T06:04:50Z
---

# init(kind:placement:)

**Initializer**

在给定的`ToolbarDefaultItemKind`处从`placement`创建一个系统定义的工具栏项。

## 声明

```swift
init(kind: ToolbarDefaultItemKind, placement: ToolbarItemPlacement = .automatic)
```

## 返回值

内容由 `kind` 提供的`ToolbarItem`。

## 讨论

`kind`和`placement`的组合可能在某些平台上有效，但在其他平台上无效。如果系统已经在工具栏中放置了匹配项`kind`，那么使用此初始化程序创建的有效`DefaultToolbarItem` 将隐式替换默认放置的实例。您可以使用它将默认项目类型移动到其他[ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md)，或相对于其他工具栏内容重新定位默认项目类型。例如，下面的代码会将`.search` 项目重新定位到底部工具栏的其他项目之间。搜索项目默认为最前面的项目：

```swift
NavigationSplitView {
    AllCalendarsView()
} detail: {
    SelectedCalendarView()
        .searchable($query)
        .toolbar {
            ToolbarItem(placement: .bottomBar) {
                CalendarPicker()
            }
            ToolbarItem(placement: .bottomBar) {
                Invites()
            }
            DefaultToolbarItem(kind: .search, placement: .bottomBar)
            ToolbarSpacer(placement: .bottomBar)
            ToolbarItem(placement: .bottomBar) { NewEventButton() }
        }
}
```

### 指定搜索栏

当 [NavigationSplitView](../NavigationSplitView.zh-Hans.md) 折叠时，`DefaultToolbarItem` 也可用于确定哪一列应负责搜索。将`DefaultToolbarItem`与`.search`同类，放置在应显示紧凑搜索字段的列中。在下面的示例中，侧边栏显示紧凑型搜索：

```swift
NavigationSplitView {
    SidebarView()
        .toolbar {
            DefaultToolbarItem(kind: .search, placement: .bottomBar)
        }
} content: {
    ContentView()
} detail: {
    DetailView()
}
.searchable(text: $text)
```

请注意，这只适用于搜索修饰符放在 `NavigationSplitView`上的情况。


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultToolbarItem/init(kind:placement:)
crawled: 2025-12-03T06:04:50Z
---

# init(kind:placement:)

**Initializer**

Creates a system-defined toolbar item from a `ToolbarDefaultItemKind` at the given `placement`.

## Declaration

```swift
init(kind: ToolbarDefaultItemKind, placement: ToolbarItemPlacement = .automatic)
```

## Return Value

A `ToolbarItem` with content provided by the `kind`.

## Discussion

Combinations of `kind` and `placement` may be valid on some platforms, but not on others. If the system has already placed a matching item `kind` in the toolbar, using a valid `DefaultToolbarItem` created by this initializer will implicitly replace the default-placed instance. You can use this to move default item kinds to other [ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md)s, or to reposition default item kinds relative to other toolbar content. For example, the below code repositions the `.search` item in between other items in the bottom bar. The search item is the leading-most item by default:

```swift
NavigationSplitView {
    AllCalendarsView()
} detail: {
    SelectedCalendarView()
        .searchable($query)
        .toolbar {
            ToolbarItem(placement: .bottomBar) {
                CalendarPicker()
            }
            ToolbarItem(placement: .bottomBar) {
                Invites()
            }
            DefaultToolbarItem(kind: .search, placement: .bottomBar)
            ToolbarSpacer(placement: .bottomBar)
            ToolbarItem(placement: .bottomBar) { NewEventButton() }
        }
}
```

### Specifying the Search Column

`DefaultToolbarItem` also can be used to identify which column should be responsible for search when a [NavigationSplitView](../NavigationSplitView.zh-Hans.md) is collapsed. Place the `DefaultToolbarItem` with the kind of `.search` in the column that should display the search field in compact. In the example below, the sidebar shows search in compact:

```swift
NavigationSplitView {
    SidebarView()
        .toolbar {
            DefaultToolbarItem(kind: .search, placement: .bottomBar)
        }
} content: {
    ContentView()
} detail: {
    DetailView()
}
.searchable(text: $text)
```

Note that this only applies when the search modifier is placed on the `NavigationSplitView`.

