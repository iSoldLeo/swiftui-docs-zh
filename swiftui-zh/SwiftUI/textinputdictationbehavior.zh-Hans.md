--- 来源：https://developer.apple.com/documentation/swiftui/textinputdictationbehavior

抓取时间：2025-12-03T06:19:26Z

---

# 文本输入听写行为 | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TextInputDictationBehavior ](/documentation/swiftui/textinputdictationbehavior)

- TextInputDictationBehavior 

结构体# TextInputDictationBehavior

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、VisionOS 1.0+

```
struct TextInputDictationBehavior
```

## [主题](/documentation/swiftui/textinputdictationbehavior#topics)

### [获取行为值](/documentation/swiftui/textinputdictationbehavior#Getting-behavior-values)

[`static let automatic: TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/automatic)平台适用的默认文本输入听写行为。[`static func inline(activation: TextInputDictationActivation) -> TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/inline(activation:))在搜索栏中添加语音输入麦克风。[`static let preventDictation: TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/preventdictation)阻止搜索栏拥有语音输入麦克风。## [关联关系](/documentation/swiftui/textinputdictationbehavior#relationships)

### [符合](/documentation/swiftui/textinputdictationbehavior#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [参见]此外](/documentation/swiftui/textinputdictationbehavior#see-also)

### [听写文本](/documentation/swiftui/textinputdictationbehavior#Dictating-text)

[`func searchDictationBehavior(TextInputDictationBehavior) -> some View`](/documentation/swiftui/view/searchdictationbehavior(_:))配置由可搜索修饰符配置的任何搜索字段的听写行为。[`struct TextInputDictationActivation`](/documentation/swiftui/textinputdictationactivation)

---
source: https://developer.apple.com/documentation/swiftui/textinputdictationbehavior
crawled: 2025-12-03T06:19:26Z
---

# TextInputDictationBehavior | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TextInputDictationBehavior ](/documentation/swiftui/textinputdictationbehavior)

-  TextInputDictationBehavior 

Structure# TextInputDictationBehavior

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+visionOS 1.0+

```
struct TextInputDictationBehavior
```

## [Topics](/documentation/swiftui/textinputdictationbehavior#topics)

### [Getting behavior values](/documentation/swiftui/textinputdictationbehavior#Getting-behavior-values)

[`static let automatic: TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/automatic)A platform-appropriate default text input dictation behavior.[`static func inline(activation: TextInputDictationActivation) -> TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/inline(activation:))Adds a dictation microphone in the search bar.[`static let preventDictation: TextInputDictationBehavior`](/documentation/swiftui/textinputdictationbehavior/preventdictation)Prevents the search bar from having a dictation microphone.## [Relationships](/documentation/swiftui/textinputdictationbehavior#relationships)

### [Conforms To](/documentation/swiftui/textinputdictationbehavior#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/swiftui/textinputdictationbehavior#see-also)

### [Dictating text](/documentation/swiftui/textinputdictationbehavior#Dictating-text)

[`func searchDictationBehavior(TextInputDictationBehavior) -> some View`](/documentation/swiftui/view/searchdictationbehavior(_:))Configures the dictation behavior for any search fields configured by the searchable modifier.[`struct TextInputDictationActivation`](/documentation/swiftui/textinputdictationactivation)