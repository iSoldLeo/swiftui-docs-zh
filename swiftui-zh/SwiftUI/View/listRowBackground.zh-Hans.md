--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowBackground(_:)

抓取时间：2025-11-30T21:24:44Z

---

# listRowBackground(_:)

**实例方法**

在列表行项后放置自定义背景视图。

## 声明

```swift
nonisolated func listRowBackground<V>(_ view: V?) -> some View where V : View

```

## 参数

- **view**：用作列表行视图背景的 [View](../View.zh-Hans.md)。

## 返回值

一个以 `view` 为背景视图的列表行视图。

## 说明

使用 `listRowBackground(_:)` 在列表行项后放置自定义背景视图。

在以下示例中，枚举 `Flavor` 为列表项提供内容。SwiftUI 的 [ForEach](../ForEach.zh-Hans.md) 结构会为枚举 `Flavor` 的每个元素计算视图，并提取每个元素的原始值，然后使用生成的文本创建每个列表行项。`listRowBackground(_:)` 修饰符随后会将您提供的视图放置在每个列表行项的后面：

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
                    .listRowBackground(Ellipse()
                                        .background(Color.clear)
                                        .foregroundColor(.purple)
                                        .opacity(0.3)
                    )
            }
        }
    }
}
```

## 配置背景

- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替行背景。

- **AlternatingRowBackgroundBehavior**：视图相对于交替行背景的样式。

- **backgroundProminence**：与此环境关联的视图下方背景的突出显示程度。

- **BackgroundProminence**：背景在其他视图下方的突出程度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowBackground(_:)
crawled: 2025-11-30T21:24:44Z
---

# listRowBackground(_:)

**Instance Method**

Places a custom background view behind a list row item.

## Declaration

```swift
nonisolated func listRowBackground<V>(_ view: V?) -> some View where V : View

```

## Parameters

- **view**: The [View](../View.zh-Hans.md) to use as the background behind the list row view.

## Return Value

A list row view with `view` as its background view.

## Discussion

Use `listRowBackground(_:)` to place a custom background view behind a list row item.

In the example below, the `Flavor` enumeration provides content for list items. The SwiftUI [ForEach](../ForEach.zh-Hans.md) structure computes views for each element of the `Flavor` enumeration and extracts the raw value of each of its elements using the resulting text to create each list row item. The `listRowBackground(_:)` modifier then places the view you supply behind each of the list row items:

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
                    .listRowBackground(Ellipse()
                                        .background(Color.clear)
                                        .foregroundColor(.purple)
                                        .opacity(0.3)
                    )
            }
        }
    }
}
```



## Configuring backgrounds

- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **AlternatingRowBackgroundBehavior**: The styling of views with respect to alternating row backgrounds.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **BackgroundProminence**: The prominence of backgrounds underneath other views.

