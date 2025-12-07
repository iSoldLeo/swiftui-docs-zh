---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/combine
抓取时间： 2025-12-03T03:39:20Z
---

# 组合

**类型属性**

任何子无障碍元素的属性都会合并到新的无障碍元素中。

## 声明

```swift
static let combine: AccessibilityChildBehavior
```

## 讨论

当你想用一个辅助元素代表一个视图时，请使用此行为。新的辅助功能元素会合并所有非隐藏子元素的属性。为了达到理想的合并效果，某些属性可能会被转换或忽略。例如，并不是所有的[AccessibilityTraits](../AccessibilityTraits.zh-Hans.md) 都会被合并，[default](../AccessibilityActionKind/default.zh-Hans.md) 操作可能会变成一个已命名的操作（[init(named:)](../AccessibilityActionKind/init_named.zh-Hans.md)）。

```swift
struct UserCell: View {
    var user: User

    var body: some View {
        VStack {
            Image(user.image)
            Text(user.name)
            Button("Options", action: showOptions)
        }
        .accessibilityElement(children: .combine)
    }
}
```

当出现以下情况时，会创建一个新的可访问性元素：

- 视图包含多个或零个辅助功能元素
- 视图封装了一个[UIViewRepresentable](../UIViewRepresentable.zh-Hans.md)/[NSViewRepresentable](../NSViewRepresentable.zh-Hans.md)。



## 获取行为

- **contain**：任何子辅助元素都会成为新辅助元素的子元素。
- **ignore**：任何辅助功能子元素都会被隐藏。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/combine
crawled: 2025-12-03T03:39:20Z
---

# combine

**Type Property**

Any child accessibility element’s properties are merged into the new accessibility element.

## Declaration

```swift
static let combine: AccessibilityChildBehavior
```

## Discussion

Use this behavior when you want a view represented by a single accessibility element. The new accessibility element merges properties from all non-hidden children. Some properties may be transformed or ignored to achieve the ideal combined result. For example, not all of [AccessibilityTraits](../AccessibilityTraits.zh-Hans.md) are merged and a [default](../AccessibilityActionKind/default.zh-Hans.md) action may become a named action ([init(named:)](../AccessibilityActionKind/init_named.zh-Hans.md)).

```swift
struct UserCell: View {
    var user: User

    var body: some View {
        VStack {
            Image(user.image)
            Text(user.name)
            Button("Options", action: showOptions)
        }
        .accessibilityElement(children: .combine)
    }
}
```

A new accessibility element is created when:

- The view contains multiple or zero accessibility elements
- The view wraps a [UIViewRepresentable](../UIViewRepresentable.zh-Hans.md)/[NSViewRepresentable](../NSViewRepresentable.zh-Hans.md).



## Getting behaviors

- **contain**: Any child accessibility elements become children of the new accessibility element.
- **ignore**: Any child accessibility elements become hidden.

