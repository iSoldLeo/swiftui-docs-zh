---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/ignore
抓取时间： 2025-12-03T03:39:21Z
---

# 忽略

**类型属性**

任何可访问性子元素都会被隐藏。

## 声明

```swift
static let ignore: AccessibilityChildBehavior
```

## 讨论

当您想用一个辅助元素代表一个视图时，请使用此行为。新的辅助元素没有初始属性。因此，您需要使用其他辅助功能修饰符（如 [accessibilityLabel(_:)](../View/accessibilityLabel.zh-Hans.md)）来开始使其具有辅助功能。

```swift
var body: some View {
    VStack {
        Button("Previous Page", action: goBack)
        Text("\(pageNumber)")
        Button("Next Page", action: goForward)
    }
    .accessibilityElement(children: .ignore)
    .accessibilityValue("Page \(pageNumber) of \(pages.count)")
    .accessibilityAdjustableAction { action in
        if action == .increment {
            goForward()
        } else {
            goBack()
        }
    }
}
```

在使用[ignore](ignore.zh-Hans.md)行为之前，请考虑使用[combine](combine.zh-Hans.md)行为。



## 获取行为

- **combine**：任何子辅助元素的属性都会合并到新的辅助元素中。
- **contain**：任何子辅助功能元素都成为新辅助功能元素的子元素。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/ignore
crawled: 2025-12-03T03:39:21Z
---

# ignore

**Type Property**

Any child accessibility elements become hidden.

## Declaration

```swift
static let ignore: AccessibilityChildBehavior
```

## Discussion

Use this behavior when you want a view represented by a single accessibility element. The new accessibility element has no initial properties. So you will need to use other accessibility modifiers, such as [accessibilityLabel(_:)](../View/accessibilityLabel.zh-Hans.md), to begin making it accessible.

```swift
var body: some View {
    VStack {
        Button("Previous Page", action: goBack)
        Text("\(pageNumber)")
        Button("Next Page", action: goForward)
    }
    .accessibilityElement(children: .ignore)
    .accessibilityValue("Page \(pageNumber) of \(pages.count)")
    .accessibilityAdjustableAction { action in
        if action == .increment {
            goForward()
        } else {
            goBack()
        }
    }
}
```

Before using the  [ignore](ignore.zh-Hans.md)behavior, consider using the [combine](combine.zh-Hans.md) behavior.



## Getting behaviors

- **combine**: Any child accessibility element’s properties are merged into the new accessibility element.
- **contain**: Any child accessibility elements become children of the new accessibility element.

