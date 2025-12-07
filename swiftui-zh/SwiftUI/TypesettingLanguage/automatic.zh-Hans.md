---
来源： https://developer.apple.com/documentation/SwiftUI/TypesettingLanguage/automatic
抓取时间： 2025-12-03T06:19:43Z
---

# 自动

**类型属性**

自动语言行为。

## 声明

```swift
static let automatic: TypesettingLanguage
```

## 讨论

在决定使用哪种语言进行排版时，将考虑当前用户界面语言和首选语言。例如，如果当前的用户界面语言是英语，而首选语言中包括泰语，那么行高将会更高，以适应泰语使用的较高的字形。

## 获取语言行为

- **explicit(_:)**：使用明确的语言。


---
source: https://developer.apple.com/documentation/SwiftUI/TypesettingLanguage/automatic
crawled: 2025-12-03T06:19:43Z
---

# automatic

**Type Property**

Automatic language behavior.

## Declaration

```swift
static let automatic: TypesettingLanguage
```

## Discussion

When determining the language to use for typesetting the current UI language and preferred languages will be considered. For example, if the current UI locale is for English and Thai is included in the preferred languages then line heights will be taller to accommodate the taller glyphs used by Thai.

## Getting language behavior

- **explicit(_:)**: Use explicit language.

