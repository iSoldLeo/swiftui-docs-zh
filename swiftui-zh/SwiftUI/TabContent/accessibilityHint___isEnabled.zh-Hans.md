---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityHint(_:isEnabled:)
抓取时间： 2025-12-03T06:01:43Z
---

# accessibilityHint(_:isEnabled:)

**实例方法**

向用户传达选择选项卡后发生的情况。

## 声明

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## 参数

- **hint**：要应用的辅助功能提示。
- **isEnabled**：如果为 true，则应用辅助功能提示；否则辅助功能提示保持不变。

## 讨论

以简短短语的形式提供提示，如 "打开购物车 "或 "显示下载的附件"。

```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Image(systemName: "play")
        }
        .accessibilityHint("Select videos to download")
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityHint(_:isEnabled:)
crawled: 2025-12-03T06:01:43Z
---

# accessibilityHint(_:isEnabled:)

**Instance Method**

Communicates to the user what happens after selecting the tab.

## Declaration

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## Parameters

- **hint**: The accessibility hint to apply.
- **isEnabled**: If true the accessibility hint is applied; otherwise the accessibility hint is unchanged.

## Discussion

Provide a hint in the form of a brief phrase, like “Open shopping cart” or “Show downloaded attachments”.

```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Image(systemName: "play")
        }
        .accessibilityHint("Select videos to download")
    }
}
```

