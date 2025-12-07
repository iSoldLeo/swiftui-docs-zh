--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/init(_:)

抓取时间：2025-12-01T11:07:11Z

---

# init(_:)

**Initializer**

从平台字体实例创建自定义字体。

## 声明

```swift
init(_ font: CTFont)
```

## 讨论

使用平台字体实例 (doc://com.apple.documentation/documentation/CoreText/CTFont-q6r) 初始化 [Font](../Font.zh-Hans.md) 可以将 SwiftUI [Font](../Font.zh-Hans.md) 与 [doc://com.apple.documentation/documentation/AppKit/NSFont] 或 [doc://com.apple.documentation/documentation/UIKit/UIFont] 连接起来，这两者均可免费桥接到 doc://com.apple.documentation/documentation/CoreText/CTFont-q6r。例如：

```swift
// Use native Core Text API to create desired ctFont.
let ctFont = CTFontCreateUIFontForLanguage(.system, 12, nil)!

// Create SwiftUI Text with the CTFont instance.
let text = Text("Hello").font(Font(ctFont))
```


---
source: https://developer.apple.com/documentation/SwiftUI/Font/init(_:)
crawled: 2025-12-01T11:07:11Z
---

# init(_:)

**Initializer**

Creates a custom font from a platform font instance.

## Declaration

```swift
init(_ font: CTFont)
```

## Discussion

Initializing [Font](../Font.zh-Hans.md) with platform font instance (doc://com.apple.documentation/documentation/CoreText/CTFont-q6r) can bridge SwiftUI [Font](../Font.zh-Hans.md) with [doc://com.apple.documentation/documentation/AppKit/NSFont] or [doc://com.apple.documentation/documentation/UIKit/UIFont], both of which are toll-free bridged to doc://com.apple.documentation/documentation/CoreText/CTFont-q6r. For example:

```swift
// Use native Core Text API to create desired ctFont.
let ctFont = CTFontCreateUIFontForLanguage(.system, 12, nil)!

// Create SwiftUI Text with the CTFont instance.
let text = Text("Hello").font(Font(ctFont))
```

