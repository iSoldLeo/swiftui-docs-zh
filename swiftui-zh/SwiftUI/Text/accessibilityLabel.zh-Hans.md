--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/accessibilityLabel(_:)

抓取时间：2025-12-02T21:48:40Z

---

# accessibilityLabel(_:)

**实例方法**

向视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource) -> Text
```

## 参数

- **label**：用于替代辅助功能标签的字符串资源。

## 说明

使用此方法可为显示的文本提供替代辅助功能标签。例如，您可以为导航标题添加替代标签：

```swift
var body: some View {
    NavigationView {
        ContentView()
            .navigationTitle(Text("􀈤").accessibilityLabel("Inbox"))
    }
}
```

## 提供辅助功能信息

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/accessibilityLabel(_:)
crawled: 2025-12-02T21:48:40Z
---

# accessibilityLabel(_:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource) -> Text
```

## Parameters

- **label**: The string resource for the alternative accessibility label.

## Discussion

Use this method to provide an alternative accessibility label to the text that is displayed. For example, you can give an alternate label to a navigation title:

```swift
var body: some View {
    NavigationView {
        ContentView()
            .navigationTitle(Text("􀈤").accessibilityLabel("Inbox"))
    }
}
```

## Providing accessibility information

- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.

