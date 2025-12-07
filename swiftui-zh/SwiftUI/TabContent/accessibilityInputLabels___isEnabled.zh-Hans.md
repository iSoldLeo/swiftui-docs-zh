---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityInputLabels(_:isEnabled:)
抓取时间： 2025-12-03T06:01:45Z
---

# accessibilityInputLabels(_:isEnabled:)

**实例方法**

设置备用输入标签，以便用户识别标签页。

## 声明

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey], isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## 参数

- **inputLabelKeys**：要应用的无障碍输入标签。
- **isEnabled**：如果为 true，则应用无障碍输入标签；否则无障碍输入标签保持不变。

## 讨论

按重要性降序提供标签。语音控制和全键盘访问会使用输入标签。



```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Image(systemName: "mail")
        }
        .accessibilityInputLabels(["Messages", "Mail", "Conversations"])
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityInputLabels(_:isEnabled:)
crawled: 2025-12-03T06:01:45Z
---

# accessibilityInputLabels(_:isEnabled:)

**Instance Method**

Sets alternate input labels with which users identify a tab.

## Declaration

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey], isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## Parameters

- **inputLabelKeys**: The accessibility input labels to apply.
- **isEnabled**: If true the accessibility input labels are applied; otherwise the accessibility input labels are unchanged.

## Discussion

Provide labels in descending order of importance. Voice Control and Full Keyboard Access use the input labels.



```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Image(systemName: "mail")
        }
        .accessibilityInputLabels(["Messages", "Mail", "Conversations"])
    }
}
```

