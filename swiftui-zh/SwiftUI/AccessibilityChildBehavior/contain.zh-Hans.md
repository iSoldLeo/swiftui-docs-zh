---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/contain
抓取时间： 2025-12-03T03:39:20Z
---

# 包含

**类型属性**

任何子无障碍元素都将成为新无障碍元素的子元素。

## 声明

```swift
static let contain: AccessibilityChildBehavior
```

## 讨论

如果希望视图成为辅助功能容器，请使用此行为。辅助功能容器可以将子辅助功能元素分组，从而改善导航效果。例如，在浏览下一个辅助功能容器之前，会按顺序浏览辅助功能容器的所有子元素。

```swift
var body: some View {
    ScrollView {
        VStack {
            HStack {
                ForEach(users) { user in
                    UserCell(user)
                }
            }
            .accessibilityElement(children: .contain)
            .accessibilityLabel("Users")

            VStack {
                ForEach(messages) { message in
                    MessageCell(message)
                }
            }
            .accessibilityElement(children: .contain)
            .accessibilityLabel("Messages")
        }
    }
}
```

当出现以下情况时，就会创建一个新的辅助功能元素：

- 视图包含多个或零个辅助功能元素
- 视图包含一个无子元素的辅助功能元素



## 获取行为

- **combine**：任何子辅助元素的属性都会合并到新的辅助元素中。
- **ignore**：任何子辅助功能元素都会被隐藏。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior/contain
crawled: 2025-12-03T03:39:20Z
---

# contain

**Type Property**

Any child accessibility elements become children of the new accessibility element.

## Declaration

```swift
static let contain: AccessibilityChildBehavior
```

## Discussion

Use this behavior when you want a view to be an accessibility container. An accessibility container groups child accessibility elements which improves navigation. For example, all children of an accessibility container are navigated in order before navigating through the next accessibility container.

```swift
var body: some View {
    ScrollView {
        VStack {
            HStack {
                ForEach(users) { user in
                    UserCell(user)
                }
            }
            .accessibilityElement(children: .contain)
            .accessibilityLabel("Users")

            VStack {
                ForEach(messages) { message in
                    MessageCell(message)
                }
            }
            .accessibilityElement(children: .contain)
            .accessibilityLabel("Messages")
        }
    }
}
```

A new accessibility element is created when:

- The view contains multiple or zero accessibility elements
- The view contains a single accessibility element with no children



## Getting behaviors

- **combine**: Any child accessibility element’s properties are merged into the new accessibility element.
- **ignore**: Any child accessibility elements become hidden.

