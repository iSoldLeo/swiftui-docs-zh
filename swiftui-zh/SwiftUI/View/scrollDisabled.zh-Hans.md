--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollDisabled(_:)

抓取时间：2025-12-02T17:40:41Z

---

# scrollDisabled(_:)

**实例方法**

禁用或启用可滚动视图的滚动。

## 声明

```swift
nonisolated func scrollDisabled(_ disabled: Bool) -> some View

```

## 参数

- **disabled**：一个布尔值，指示是否禁用滚动。

## 说明

使用此修饰符控制 [ScrollView](../ScrollView.zh-Hans.md) 是否可以滚动：

```swift
@State private var isScrollDisabled = false

var body: some View {
    ScrollView {
        VStack {
            Toggle("Disable", isOn: $isScrollDisabled)
            MyContent()
        }
    }
    .scrollDisabled(isScrollDisabled)
}
```

SwiftUI 会将 disabled 属性传递给环境变量，这意味着您可以使用此修饰符禁用视图层次结构中所有可滚动视图的滚动。在以下示例中，修饰符会影响两个滚动视图：

```swift
 ScrollView {
     ForEach(rows) { row in
         ScrollView(.horizontal) {
             RowContent(row)
         }
     }
 }
 .scrollDisabled(true)
```

您还可以使用此修饰符禁用其他类型可滚动视图的滚动，例如 [List](../List.zh-Hans.md) 或 [TextEditor](../TextEditor.zh-Hans.md)。

## 禁用滚动

- **isScrollEnabled**：一个布尔值，指示与此环境关联的任何滚动视图是否允许滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollDisabled(_:)
crawled: 2025-12-02T17:40:41Z
---

# scrollDisabled(_:)

**Instance Method**

Disables or enables scrolling in scrollable views.

## Declaration

```swift
nonisolated func scrollDisabled(_ disabled: Bool) -> some View

```

## Parameters

- **disabled**: A Boolean that indicates whether scrolling is disabled.

## Discussion

Use this modifier to control whether a [ScrollView](../ScrollView.zh-Hans.md) can scroll:

```swift
@State private var isScrollDisabled = false

var body: some View {
    ScrollView {
        VStack {
            Toggle("Disable", isOn: $isScrollDisabled)
            MyContent()
        }
    }
    .scrollDisabled(isScrollDisabled)
}
```

SwiftUI passes the disabled property through the environment, which means you can use this modifier to disable scrolling for all scroll views within a view hierarchy. In the following example, the modifier affects both scroll views:

```swift
 ScrollView {
     ForEach(rows) { row in
         ScrollView(.horizontal) {
             RowContent(row)
         }
     }
 }
 .scrollDisabled(true)
```

You can also use this modifier to disable scrolling for other kinds of scrollable views, like a [List](../List.zh-Hans.md) or a [TextEditor](../TextEditor.zh-Hans.md).

## Disabling scrolling

- **isScrollEnabled**: A Boolean value that indicates whether any scroll views associated with this environment allow scrolling to occur.

