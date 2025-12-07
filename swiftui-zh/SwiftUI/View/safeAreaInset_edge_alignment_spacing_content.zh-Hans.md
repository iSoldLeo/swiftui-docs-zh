--- 来源：https://developer.apple.com/documentation/SwiftUI/View/safeAreaInset(edge:alignment:spacing:content:)

抓取时间：2025-11-30T21:24:02Z

---

# safeAreaInset(edge:alignment:spacing:content:)

**实例方法**

在修改后的视图旁边显示指定内容。

## 声明

```swift
nonisolated func safeAreaInset<V>(edge: HorizontalEdge, alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **edge**：要内移 `content` 宽度的视图水平边缘，以便为 `content` 腾出空间。

- **alignment**：用于垂直定位 `content` 的对齐参考线。

- **spacing**：两个视图之间的额外距离，如果设置为 nil 则使用默认间距。

- **content**：视图构建器函数，用于提供要在修改视图的内嵌空间中显示的视图。

## 返回值

一个新视图，显示在修改视图旁边，`content`，通过水平内嵌修改视图，为 `content` 视图腾出空间。

## 说明

`content` 视图锚定到父视图中指定的水平边缘，并将其垂直轴与指定的对齐参考线对齐。修改视图从 `edge` 内嵌 `content` 的宽度，其安全区域也增加相同的宽度。

```swift
struct ScrollableViewWithSideBar: View {
    var body: some View {
        ScrollView {
            ScrolledContent()
        }
        .safeAreaInset(edge: .leading, spacing: 0) {
            SideBarContent()
        }
    }
}
```

## 保持在安全区域内

- **ignoresSafeArea(_:edges:)**：扩展视图的安全区域。

- **safeAreaPadding(_:)**：将提供的内边距添加到此视图的安全区域。

- **safeAreaPadding(_:_:)**：将提供的内边距添加到此视图的安全区域。

- **SafeAreaRegions**：一组符号安全区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/safeAreaInset(edge:alignment:spacing:content:)
crawled: 2025-11-30T21:24:02Z
---

# safeAreaInset(edge:alignment:spacing:content:)

**Instance Method**

Shows the specified content beside the modified view.

## Declaration

```swift
nonisolated func safeAreaInset<V>(edge: HorizontalEdge, alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **edge**: The horizontal edge of the view to inset by the width of `content`, to make space for `content`.
- **alignment**: The alignment guide used to position `content` vertically.
- **spacing**: Extra distance placed between the two views, or nil to use the default amount of spacing.
- **content**: A view builder function providing the view to display in the inset space of the modified view.

## Return Value

A new view that displays `content` beside the modified view, making space for the `content` view by horizontally insetting the modified view.

## Discussion

The `content` view is anchored to the specified horizontal edge in the parent view, aligning its vertical axis to the specified alignment guide. The modified view is inset by the width of `content`, from `edge`, with its safe area increased by the same amount.

```swift
struct ScrollableViewWithSideBar: View {
    var body: some View {
        ScrollView {
            ScrolledContent()
        }
        .safeAreaInset(edge: .leading, spacing: 0) {
            SideBarContent()
        }
    }
}
```

## Staying in the safe areas

- **ignoresSafeArea(_:edges:)**: Expands the safe area of a view.
- **safeAreaPadding(_:)**: Adds the provided insets into the safe area of this view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.
- **SafeAreaRegions**: A set of symbolic safe area regions.

