--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/WritingDirectionStrategy/contentBased

抓取时间：2025-12-03T19:59:42Z

---

# contentBased

**类型属性**

根据布局字符串的语言，确定其书写方向。

## 声明

```swift
static let contentBased: Text.WritingDirectionStrategy
```

## 讨论

系统可能使用不同的来源来确定字符串的语言。这可能包括字符串中使用的字符（尤其是双向隔离标记）、字符串加载来源的本地化文件的语言，或者使用 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/languageIdentifier] 属性进行的显式注释。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/WritingDirectionStrategy/contentBased
crawled: 2025-12-03T19:59:42Z
---

# contentBased

**Type Property**

The writing direction following the language of the string that is laid out.

## Declaration

```swift
static let contentBased: Text.WritingDirectionStrategy
```

## Discussion

The system may use different sources to determine the language of the string. This may include the characters used in the string, especially BiDi isolation markers, the language of the localization file the string was loaded from, or explicit annotations with the [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/languageIdentifier] attribute.

