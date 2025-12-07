--- 来源：https://developer.apple.com/documentation/SwiftUI/View/labelStyle(_:)

抓取时间：2025-11-30T21:18:26Z

---

# labelStyle(_:)

**实例方法**

设置此视图中标签的样式。

## 声明

```swift
nonisolated func labelStyle<S>(_ style: S) -> some View where S : LabelStyle

```

## 说明

使用此修饰符可为视图中的所有标签设置特定样式：

```swift
VStack {
    Label("Fire", systemImage: "flame.fill")
    Label("Lightning", systemImage: "bolt.fill")
}
.labelStyle(MyCustomLabelStyle())
```

## 显示文本

- **Text**：显示一行或多行只读文本的视图。

- **Label**：用户界面项的标准标签，由图标和标题组成。


---
source: https://developer.apple.com/documentation/SwiftUI/View/labelStyle(_:)
crawled: 2025-11-30T21:18:26Z
---

# labelStyle(_:)

**Instance Method**

Sets the style for labels within this view.

## Declaration

```swift
nonisolated func labelStyle<S>(_ style: S) -> some View where S : LabelStyle

```

## Discussion

Use this modifier to set a specific style for all labels within a view:

```swift
VStack {
    Label("Fire", systemImage: "flame.fill")
    Label("Lightning", systemImage: "bolt.fill")
}
.labelStyle(MyCustomLabelStyle())
```

## Displaying text

- **Text**: A view that displays one or more lines of read-only text.
- **Label**: A standard label for user interface items, consisting of an icon with a title.

