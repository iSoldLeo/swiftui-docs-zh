--- 来源：https://developer.apple.com/documentation/SwiftUI/View/disableAutocorrection(_:)

抓取时间：2025-12-03T05:35:33Z

---

# disableAutocorrection(_:)

**实例方法**

设置是否禁用此视图的自动更正功能。

## 声明

```swift
nonisolated func disableAutocorrection(_ disable: Bool?) -> some View

```

## 参数

- **disable**：一个布尔值，指示是否禁用此视图的自动更正功能。

## 说明

当自动更正功能会使用户更难输入信息时，请使用此方法。例如，输入专有名词和街道地址时，自动更正功能可能会对用户完成数据输入任务的能力产生负面影响。

以下示例使用默认键盘配置 [TextField](../TextField.zh-Hans.md)。禁用自动纠错功能后，用户可以输入任意文本，而系统不会提供建议或试图覆盖用户的输入。

```swift
TextField("1234 Main St.", text: $address)
    .keyboardType(.default)
    .disableAutocorrection(true)
```

## 文本修饰符

- **autocapitalization(_:)**：设置是否在此视图中应用自动大写。


---
source: https://developer.apple.com/documentation/SwiftUI/View/disableAutocorrection(_:)
crawled: 2025-12-03T05:35:33Z
---

# disableAutocorrection(_:)

**Instance Method**

Sets whether to disable autocorrection for this view.

## Declaration

```swift
nonisolated func disableAutocorrection(_ disable: Bool?) -> some View

```

## Parameters

- **disable**: A Boolean value that indicates whether autocorrection is disabled for this view.

## Discussion

Use this method when the effect of autocorrection would make it more difficult for the user to input information. The entry of proper names and street addresses are examples where autocorrection can negatively affect the user’s ability complete a data entry task.

In the example below configures a [TextField](../TextField.zh-Hans.md) with the default keyboard. Disabling autocorrection allows the user to enter arbitrary text without the autocorrection system offering suggestions or attempting to override their input.

```swift
TextField("1234 Main St.", text: $address)
    .keyboardType(.default)
    .disableAutocorrection(true)
```

## Text modifiers

- **autocapitalization(_:)**: Sets whether to apply auto-capitalization to this view.

