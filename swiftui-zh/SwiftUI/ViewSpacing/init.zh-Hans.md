---
来源： https://developer.apple.com/documentation/SwiftUI/ViewSpacing/init()
抓取时间： 2025-12-03T06:39:31Z
---

# init()

**Initializer**

使用默认间距值初始化一个实例。

## 声明

```swift
init()
```

## 讨论

使用此初始化程序创建一个带有默认值的间距首选项实例。然后使用 [formUnion(_:edges:)](formUnion___edges.zh-Hans.md) 将其他视图中的首选项与新实例结合起来。通常，您可以在自定义布局的[spacing(subviews:cache:)](../Layout/spacing_subviews_cache.zh-Hans.md) 方法实现中这样做。

## 创建间距实例

- **zero**：视图间距实例，所有边上的值都为零。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewSpacing/init()
crawled: 2025-12-03T06:39:31Z
---

# init()

**Initializer**

Initializes an instance with default spacing values.

## Declaration

```swift
init()
```

## Discussion

Use this initializer to create a spacing preferences instance with default values. Then use [formUnion(_:edges:)](formUnion___edges.zh-Hans.md) to combine preferences from other views with the new instance. You typically do this in a custom layout’s implementation of the [spacing(subviews:cache:)](../Layout/spacing_subviews_cache.zh-Hans.md) method.

## Creating spacing instances

- **zero**: A view spacing instance that contains zero on all edges.

