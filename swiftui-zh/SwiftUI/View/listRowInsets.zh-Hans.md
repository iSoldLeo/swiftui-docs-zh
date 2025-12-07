--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowInsets(_:)

抓取时间：2025-12-02T17:39:27Z

---

# listRowInsets(_:)

**实例方法**

为列表中的行应用内边距。

## 声明

```swift
nonisolated func listRowInsets(_ insets: EdgeInsets?) -> some View

```

## 参数

- **insets**：要应用于视图边缘的 [EdgeInsets](../EdgeInsets.zh-Hans.md)。

## 返回值

一个使用给定内边距的视图，当用作列表单元格时。

## 说明

使用 `listRowInsets(_:)` 更改列表项内容的默认内边距。

在以下示例中，枚举类型 `Flavor` 为列表项提供内容。SwiftUI 结构 [ForEach](../ForEach.zh-Hans.md) 计算枚举类型 `Flavor` 中每个元素的视图，并提取每个元素的原始值，使用生成的文本创建每个列表行项。然后，修饰符 `listRowInsets(_:)` 根据提供的 [EdgeInsets](../EdgeInsets.zh-Hans.md) 更改列表每一行的边缘内边距：

```swift
struct ContentView: View {
    enum Flavor: String, CaseIterable, Identifiable {
        var id: String { self.rawValue }
        case vanilla, chocolate, strawberry
    }

    var body: some View {
        List {
            ForEach(Flavor.allCases) {
                Text($0.rawValue)
                    .listRowInsets(.init(top: 0,
                                         leading: 25,
                                         bottom: 0,
                                         trailing: 0))
            }
        }
    }
}
```

## 配置列表布局

- **defaultMinListRowHeight**：列表中行的默认最小高度。

- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **listSectionSpacing(_:)**：将 [List](../List.zh-Hans.md) 中相邻节之间的间距设置为自定义值。

- **ListSectionSpacing**：列表中相邻节之间的间距选项。

- **listSectionMargins(_:_:)**：设置特定边缘的节边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowInsets(_:)
crawled: 2025-12-02T17:39:27Z
---

# listRowInsets(_:)

**Instance Method**

Applies an inset to the rows in a list.

## Declaration

```swift
nonisolated func listRowInsets(_ insets: EdgeInsets?) -> some View

```

## Parameters

- **insets**: The [EdgeInsets](../EdgeInsets.zh-Hans.md) to apply to the edges of the view.

## Return Value

A view that uses the given edge insets when used as a list cell.

## Discussion

Use `listRowInsets(_:)` to change the default padding of the content of list items.

In the example below, the `Flavor` enumeration provides content for list items. The SwiftUI [ForEach](../ForEach.zh-Hans.md) structure computes views for each element of the `Flavor` enumeration and extracts the raw value of each of its elements using the resulting text to create each list row item. The `listRowInsets(_:)` modifier then changes the edge insets of each row of the list according to the [EdgeInsets](../EdgeInsets.zh-Hans.md) provided:

```swift
struct ContentView: View {
    enum Flavor: String, CaseIterable, Identifiable {
        var id: String { self.rawValue }
        case vanilla, chocolate, strawberry
    }

    var body: some View {
        List {
            ForEach(Flavor.allCases) {
                Text($0.rawValue)
                    .listRowInsets(.init(top: 0,
                                         leading: 25,
                                         bottom: 0,
                                         trailing: 0))
            }
        }
    }
}
```





## Configuring a list’s layout

- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

