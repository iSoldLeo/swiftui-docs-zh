---

来源：https://developer.apple.com/documentation/swiftui/view/searchdictationbehavior(_:)

抓取时间：2025-12-03T06:19:20Z

---

# searchDictationBehavior(_:)

**实例方法**

配置由 searchable 修饰符配置的任何搜索字段的听写行为。

## 声明

```swift
nonisolated func searchDictationBehavior(_ dictationBehavior: TextInputDictationBehavior) -> some View

```

## 说明

默认情况下，在 visionOS 上，当用户注视搜索字段中的听写按钮时，搜索字段会自动开始听写。您可以通过为该修饰符提供 [preventDictation](../TextInputDictationBehavior/preventDictation.zh-Hans.md) 值来更改此行为。

有关可用听写行为的更多信息，请参阅 [TextInputDictationBehavior](../TextInputDictationBehavior.zh-Hans.md) 类型。

## 听写文本

- **TextInputDictationActivation**
- **TextInputDictationBehavior**


---
source: https://developer.apple.com/documentation/swiftui/view/searchdictationbehavior(_:)
crawled: 2025-12-03T06:19:20Z
---

# searchDictationBehavior(_:)

**Instance Method**

Configures the dictation behavior for any search fields configured by the searchable modifier.

## Declaration

```swift
nonisolated func searchDictationBehavior(_ dictationBehavior: TextInputDictationBehavior) -> some View

```

## Discussion

By default, search fields on visionOS will automatically start dictation when looking at the dictation button in the search field. You can change this behavior by providing a value of [preventDictation](../TextInputDictationBehavior/preventDictation.zh-Hans.md) to this modifier.

See the [TextInputDictationBehavior](../TextInputDictationBehavior.zh-Hans.md) type for more information on the available dictation behaviors.

## Dictating text

- **TextInputDictationActivation**
- **TextInputDictationBehavior**

