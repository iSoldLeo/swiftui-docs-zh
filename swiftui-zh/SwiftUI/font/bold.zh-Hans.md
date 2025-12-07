--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/bold(_:)

抓取时间：2025-12-01T11:07:25Z

---

# bold(_:)

**实例方法**

为字体添加或移除粗体或强调样式。

## 声明

```swift
func bold(_ isActive: Bool) -> Font
```

## 讨论

对于由文本样式创建的字体，传递 `true` 可能意味着应用强调样式，但这并不一定意味着特指粗体，因此请勿将此修饰符与 [doc://com.apple.documentation/documentation/SwiftUI/Font/weight(_:)] 混淆。

例如：

```swift
Font.body.bold(true)
```

很可能会得到正文样式的强调版本，其字重通常为 [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/semibold]。使用

```swift
Font.body.weight(.bold)
```

将使正文字体的字重变为 [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/bold]。

使用：

```swift
Font.body.bold(false)
```

将移除字体的所有强调样式，使其恢复到默认字重，该字重很可能为 0.0 或 [regular](../Font/Weight/regular.zh-Hans.md)，但不保证一定如此。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/bold(_:)
crawled: 2025-12-01T11:07:25Z
---

# bold(_:)

**Instance Method**

Adds or removes bold or emphasized styling on the font.

## Declaration

```swift
func bold(_ isActive: Bool) -> Font
```

## Discussion

For fonts created from text styles, passing `true` could mean applying emphasized styling, which does not necessarily mean the bold weight specifically, so this modifier is not to be confused with [doc://com.apple.documentation/documentation/SwiftUI/Font/weight(_:)].

For example:

```swift
Font.body.bold(true)
```

will most likely get you the emphasized version of body text style, which is often in [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/semibold] weight. While

```swift
Font.body.weight(.bold)
```

will specifically get you the body text style font in the [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/bold] weight.

Using:

```swift
Font.body.bold(false)
```

will remove any emphasized styling from the font returning to its default weight which is most likely but not guaranteed to be 0.0 or [regular](../Font/Weight/regular.zh-Hans.md).

