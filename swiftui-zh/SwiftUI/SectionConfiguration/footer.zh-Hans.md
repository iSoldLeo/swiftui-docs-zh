--- 来源：https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/footer

抓取时间：2025-12-03T06:41:44Z

---

# 页脚

**实例属性**

页脚的内容。

## 声明

```swift
var footer: SubviewsCollection { get }
```

## 讨论

值得注意的是，页脚是 `SubviewsCollection`，而不是 `Subview`，因为它可以由多个子视图组成。这意味着在大多数情况下，子视图集合应该被视为一个集合（要么通过索引访问，要么使用 `ForEach`），或者应该将其包装在一个容器视图中，例如布局或其他自定义容器：

```swift
ForEach(sections: content) {
    VStack {
        HStack { section.header }
        HStack { section.footer }
    }
}
```

这里，我们将页眉和页脚包裹在一个 `HStack` 布局中，以避免页眉和页脚的子视图垂直堆叠，从而在视觉上将它们分组在一起。此外，我们将 `ForEach` 主体包裹在一个 VStack 中，这样它就会被传递给它的容器视为一个单独的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/footer
crawled: 2025-12-03T06:41:44Z
---

# footer

**Instance Property**

The contents of the section footer.

## Declaration

```swift
var footer: SubviewsCollection { get }
```

## Discussion

Notably, the section’s footer is a `SubviewsCollection`, not a `Subview`, as it can be made up of multiple subviews. That means in most cases, the subviews collection should be treated as a collection (either indexed into, or used with a `ForEach`), or the subviews collection should be wrapped in a container view, like a layout, or other custom container:

```swift
ForEach(sections: content) {
    VStack {
        HStack { section.header }
        HStack { section.footer }
    }
}
```

Here, we surround the header and footer in an `HStack` layout to avoid vertically stacking the subviews of the header and footer which we want visually grouped together. Additionally, we surround the `ForEach` body in a VStack, so it is treated as a single view by containers it gets passed to.

