--- 来源：https://developer.apple.com/documentation/SwiftUI/View/safeAreaPadding(_:)

抓取时间：2025-12-02T17:38:58Z

---

# safeAreaPadding(_:)

**实例方法**

将提供的内边距添加到此视图的安全区域。

## 声明

```swift
nonisolated func safeAreaPadding(_ insets: EdgeInsets) -> some View

```

## 说明

当您希望向视图的安全区域添加固定大小的空间时，请使用此修饰符。

```swift
ScrollView(.horizontal) {
    HStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
}
.safeAreaPadding(.horizontal, 20.0)
```

请参阅 `View/safeAreaInset(edge:alignment:spacing:content)` 修饰符，了解如何根据视图的大小向安全区域添加空间。

## 保持在安全区域内

- **ignoresSafeArea(_:edges:)**：扩展视图的安全区域。

- **safeAreaInset(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容。

- **safeAreaPadding(_:_:)**：将提供的内边距添加到此视图的安全区域。

- **SafeAreaRegions**：一组符号安全区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/safeAreaPadding(_:)
crawled: 2025-12-02T17:38:58Z
---

# safeAreaPadding(_:)

**Instance Method**

Adds the provided insets into the safe area of this view.

## Declaration

```swift
nonisolated func safeAreaPadding(_ insets: EdgeInsets) -> some View

```

## Discussion

Use this modifier when you would like to add a fixed amount of space to the safe area a view sees.

```swift
ScrollView(.horizontal) {
    HStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
}
.safeAreaPadding(.horizontal, 20.0)
```

See the `View/safeAreaInset(edge:alignment:spacing:content)` modifier for adding to the safe area based on the size of a view.

## Staying in the safe areas

- **ignoresSafeArea(_:edges:)**: Expands the safe area of a view.
- **safeAreaInset(edge:alignment:spacing:content:)**: Shows the specified content beside the modified view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.
- **SafeAreaRegions**: A set of symbolic safe area regions.

