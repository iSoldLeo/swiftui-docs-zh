--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/typesettingLanguage(_:isEnabled:)

抓取时间：2025-12-02T21:48:36Z

---

# typesettingLanguage(_:isEnabled:)

**实例方法**

指定排版语言。

## 声明

```swift
func typesettingLanguage(_ language: Locale.Language, isEnabled: Bool = true) -> Text
```

## 参数

- **language**：用于排版的显式语言。

- **isEnabled**：一个布尔值，指示是否添加文本语言。

## 返回值

使用您提供的值设置排版语言的文本。

## 说明

在某些情况下，`Text` 可能包含与设备 UI 语言不匹配的特定语言的文本。在这种情况下，指定语言会很有用，这样行高、换行和间距就会遵循该语言使用的脚本。例如：

```swift
Text(verbatim: "แอปเปิล")
    .typesettingLanguage(.init(languageCode: .thai))
```

注意：此语言不会影响文本本地化。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/typesettingLanguage(_:isEnabled:)
crawled: 2025-12-02T21:48:36Z
---

# typesettingLanguage(_:isEnabled:)

**Instance Method**

Specifies the language for typesetting.

## Declaration

```swift
func typesettingLanguage(_ language: Locale.Language, isEnabled: Bool = true) -> Text
```

## Parameters

- **language**: The explicit language to use for typesetting.
- **isEnabled**: A Boolean value that indicates whether text language is added

## Return Value

Text with the typesetting language set to the value you supply.

## Discussion

In some cases `Text` may contain text of a particular language which doesn’t match the device UI language. In that case it’s useful to specify a language so line height, line breaking and spacing will respect the script used for that language. For example:

```swift
Text(verbatim: "แอปเปิล")
    .typesettingLanguage(.init(languageCode: .thai))
```

Note: this language does not affect text localization.

