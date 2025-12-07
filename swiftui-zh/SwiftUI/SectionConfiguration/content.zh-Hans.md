--- 来源：https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/content

抓取时间：2025-12-03T06:41:43Z

---

# content

**实例属性**

节主体的内容。

## 声明

```swift
var content: SubviewsCollection { get }
```

## 讨论

值得注意的是，节的内容是 `SubviewsCollection`，而不是 `Subview`，因为它可以由多个子视图组成。这意味着在大多数情况下，子视图集合应该被视为一个集合（要么建立索引，要么与 `ForEach` 一起使用），或者应该将子视图集合包装在一个容器视图中，例如布局或其他自定义容器：

```swift
PinboardSectionsLayout {
    ForEach(sections: content) { section in
        VStack {
            section.content
        }
    }
}
```

这里，我们希望为 `PinboardSectionsLayout` 创建一个视图，以便将其放置在内容中的每个部分。为此，我们将 `ForEach` 主体包装在另一个容器中，即 `VStack` 布局，以确保 section.content 的不同子视图被外层的布局视为单个视图。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionConfiguration/content
crawled: 2025-12-03T06:41:43Z
---

# content

**Instance Property**

The contents of the section body.

## Declaration

```swift
var content: SubviewsCollection { get }
```

## Discussion

Notably, the section’s content is a `SubviewsCollection`, not a `Subview`, as it can be made up of multiple subviews. That means in most cases, the subviews collection should be treated as a collection (either indexed into, or used with a `ForEach`), or the subviews collection should be wrapped in a container view, like a layout, or other custom container:

```swift
PinboardSectionsLayout {
    ForEach(sections: content) { section in
        VStack {
            section.content
        }
    }
}
```

Here, we want to create one view for `PinboardSectionsLayout` to place per section in content. To do that, we surround the `ForEach` body in another container, a `VStack` layout, ensuring the different subviews of section.content are treated as a single view by the surrounding layout.

