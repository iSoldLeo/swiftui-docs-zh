--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowPlatterColor(_:)

抓取时间：2025-12-01T10:24:35Z

---

# listRowPlatterColor(_:)

**实例方法**

设置当此视图放置在列表中时，系统应用于行背景的颜色。

## 声明

```swift
nonisolated func listRowPlatterColor(_ color: Color?) -> some View

```

## 参数

- **color**：要应用于系统单元格的 [Color](../Color.zh-Hans.md)。

## 返回值

应用了指定 `color` 的视图。

## 说明

使用 `listRowPlatterColor(_:)` 设置列表中的底层行背景颜色。

在下面的示例中，枚举类型 `Flavor` 为列表项提供内容。SwiftUI 构建器 [List](../List.zh-Hans.md) 遍历枚举类型 `Flavor` 并提取每个元素的原始值，使用生成的文本创建每个列表行项。列表构建器完成后，修饰符 `listRowPlatterColor(_:)` 将底层行背景颜色设置为您指定的 [Color](../Color.zh-Hans.md) 值。

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
                    .listRowPlatterColor(.green)
            }
        }
    }
}
```

## 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。

- **background(_:alignment:)**：将给定视图置于此视图下方。

- **overlay(_:alignment:)**：将辅助视图置于此视图上方。

- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。

- **complicationForeground()**：将此视图在复杂视图中提升为前景。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowPlatterColor(_:)
crawled: 2025-12-01T10:24:35Z
---

# listRowPlatterColor(_:)

**Instance Method**

Sets the color that the system applies to the row background when this view is placed in a list.

## Declaration

```swift
nonisolated func listRowPlatterColor(_ color: Color?) -> some View

```

## Parameters

- **color**: The [Color](../Color.zh-Hans.md) to apply to the system cell.

## Return Value

A view with the specified `color` applied to the system cell.

## Discussion

Use `listRowPlatterColor(_:)` to set the underlying row background color in a list.

In the example below, the `Flavor` enumeration provides content for list items. The SwiftUI [List](../List.zh-Hans.md) builder iterates over the `Flavor` enumeration and extracts the raw value of each of its elements using the resulting text to create each list row item. After the list builder finishes, the `listRowPlatterColor(_:)` modifier sets the underlying row background color to the [Color](../Color.zh-Hans.md) you specify.

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
                    .listRowPlatterColor(.green)
            }
        }
    }
}
```

## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **background(_:alignment:)**: Layers the given view behind this view.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

