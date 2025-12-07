---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityLabel(_:isEnabled:)
抓取时间： 2025-12-01T10:50:43Z
---

# accessibilityLabel(_:isEnabled:)

**实例方法**

为标签页添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## 参数

- **label**：要应用的辅助功能标签。
- **isEnabled**：如果为 true，则应用辅助功能标签；否则辅助功能标签保持不变。

## 讨论

使用此方法可为包含图标等内容的标签页提供辅助功能标签。不要在标签中包含重复用户已有信息的文本。例如，不要使用 "图书馆选项卡 "标签，因为选项卡已经有了标识其为选项卡的特征。

```swift
var body: some View {
    TabView {
        Tab {
            FavoritesView()
        } label: {
            Image(systemName: "star.fill")
        }
        .accessibilityLabel("Favorites")
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/accessibilityLabel(_:isEnabled:)
crawled: 2025-12-01T10:50:43Z
---

# accessibilityLabel(_:isEnabled:)

**Instance Method**

Adds a label to the tab that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool = true) -> some TabContent<Self.TabValue>

```

## Parameters

- **label**: The accessibility label to apply.
- **isEnabled**: If true the accessibility label is applied; otherwise the accessibility label is unchanged.

## Discussion

Use this method to provide an accessibility label for a tab that contains content like an icon. Don’t include text in the label that repeats information that users already have. For example, don’t use the label “Library tab” because a tab already has a trait that identifies it as a tab.

```swift
var body: some View {
    TabView {
        Tab {
            FavoritesView()
        } label: {
            Image(systemName: "star.fill")
        }
        .accessibilityLabel("Favorites")
    }
}
```

