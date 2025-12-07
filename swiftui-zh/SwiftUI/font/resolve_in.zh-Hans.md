--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/resolve(in:)

抓取时间：2025-12-01T11:07:29Z

---

# resolve(in:)

**实例方法**

根据当前上下文，将此字体解析为已解析的字体。

## 声明

```swift
func resolve(in context: Font.Context) -> Font.Resolved
```

## 说明

系统会在给定环境的上下文中使用字体时解析其值，因为 [Font](../Font.zh-Hans.md) 是一个后期绑定标记。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/resolve(in:)
crawled: 2025-12-01T11:07:29Z
---

# resolve(in:)

**Instance Method**

Evaluates this font to a resolved font given the current context.

## Declaration

```swift
func resolve(in context: Font.Context) -> Font.Resolved
```

## Discussion

The system resolves a font’s value at the time it uses the font in a given environment’s context because [Font](../Font.zh-Hans.md) is a late-binding token.



