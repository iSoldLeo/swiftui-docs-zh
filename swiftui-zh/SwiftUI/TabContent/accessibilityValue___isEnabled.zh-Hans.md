---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityValue(_:isEnabled:)
抓取时间： 2025-12-01T10:50:43Z
---

# accessibilityValue(_:isEnabled:)

**实例方法**

添加选项卡所含值的文字描述。

## 声明

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## 参数

- **valueDescription**：要应用的可访问性值。
- **isEnabled**：如果为 true，则应用辅助功能值；否则辅助功能值保持不变。

## 讨论

使用此方法来描述标签页所代表的值，但仅限于该值与标签页的标签不同的情况，例如当图标代表标签页的信息时。

```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Text("Messages")
        }
        .badge(30)
        .accessibilityValue("30 Unread")
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityValue(_:isEnabled:)
crawled: 2025-12-01T10:50:43Z
---

# accessibilityValue(_:isEnabled:)

**Instance Method**

Adds a textual description of the value that the tab contains.

## Declaration

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## Parameters

- **valueDescription**: The accessibility value to apply.
- **isEnabled**: If true the accessibility value is applied; otherwise the accessibility value is unchanged.

## Discussion

Use this method to describe the value represented by a tab, but only if that’s different than the tab’s label such as when an icon represent information about a tab.

```swift
var body: some View {
    TabView {
        Tab {
            MessagesView()
        } label: {
            Text("Messages")
        }
        .badge(30)
        .accessibilityValue("30 Unread")
    }
}
```

