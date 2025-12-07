---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(value:)
抓取时间： 2025-12-02T17:46:44Z
---

# accessibility(value:)

**实例方法**

添加视图所含值的文字描述。

## 声明

```swift
nonisolated func accessibility(value: Text) -> ModifiedContent<Content, Modifier>
```

## 讨论

使用此方法可以描述视图所代表的值，但前提是该值与视图的标签不同。例如，对于使用[accessibility(label:)](accessibility_label.zh-Hans.md)标记为 "音量 "的滑块，可以使用[accessibility(value:)](accessibility_value.zh-Hans.md)提供当前音量设置，如 "60%"。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(value:)
crawled: 2025-12-02T17:46:44Z
---

# accessibility(value:)

**Instance Method**

Adds a textual description of the value that the view contains.

## Declaration

```swift
nonisolated func accessibility(value: Text) -> ModifiedContent<Content, Modifier>
```

## Discussion

Use this method to describe the value represented by a view, but only if that’s different than the view’s label. For example, for a slider that you label as “Volume” using [accessibility(label:)](accessibility_label.zh-Hans.md), you can provide the current volume setting, like “60%”, using [accessibility(value:)](accessibility_value.zh-Hans.md).

