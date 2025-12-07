--- 来源：https://developer.apple.com/documentation/SwiftUI/Link/init(_:destination:)

抓取时间：2025-12-01T10:31:44Z

---

# init(_:destination:)

**Initializer**

创建一个控件，该控件包含一个 URL 和一个标题键，用于导航到指定的 URL。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, destination: URL)
```

## 参数

- **titleKey**：用于描述此链接用途的本地化标题键。

- **destination**：链接的 URL。

## 说明

使用 [Link](../Link.zh-Hans.md) 创建一个控件，供您的应用导航到您提供的 URL。以下示例创建指向 `example.com` 的链接，并使用 `Visit Example Co` 作为标题键，在您的应用中生成链接样式的视图：

```swift
Link("Visit Example Co",
      destination: URL(string: "https://www.example.com/")!)
```

## 创建链接

- **init(destination:label:)**：创建一个控件，该控件包含一个 URL 和一个标签，用于导航到指定的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Link/init(_:destination:)
crawled: 2025-12-01T10:31:44Z
---

# init(_:destination:)

**Initializer**

Creates a control, consisting of a URL and a title key, used to navigate to a URL.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, destination: URL)
```

## Parameters

- **titleKey**: The key for the localized title that describes the purpose of this link.
- **destination**: The URL for the link.

## Discussion

Use [Link](../Link.zh-Hans.md) to create a control that your app uses to navigate to a URL that you provide. The example below creates a link to `example.com` and uses `Visit Example Co` as the title key to generate a link-styled view in your app:

```swift
Link("Visit Example Co",
      destination: URL(string: "https://www.example.com/")!)
```

## Creating a link

- **init(destination:label:)**: Creates a control, consisting of a URL and a label, used to navigate to the given URL.

