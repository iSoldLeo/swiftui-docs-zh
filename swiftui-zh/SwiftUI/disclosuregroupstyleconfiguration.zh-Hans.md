---
来源： https://developer.apple.com/documentation/swiftui/disclosuregroupstyleconfiguration
抓取时间： 2025-12-05T22:21:14Z
---

# DisclosureGroupStyleConfiguration

**Structure**

披露组实例的属性。

## 声明

```swift
struct DisclosureGroupStyleConfiguration
```

## 配置标签

- **label**：披露组的标签。
- **DisclosureGroupStyleConfiguration.Label**：披露组的类型迭代标签。

## 配置内容

- **content**：信息披露组的内容。
- **DisclosureGroupStyleConfiguration.Content**：信息披露组中经过类型擦除的内容。

## 管理信息披露

- **isExpanded**：与布尔值的绑定，表示披露组是否已展开。
- **$isExpanded**

## 创建自定义披露组样式

- **makeBody(configuration:)**：创建表示披露组正文的视图。
- **DisclosureGroupStyle.Configuration**：披露组实例的属性。
- **Body**：表示披露组主体的视图。


---
source: https://developer.apple.com/documentation/swiftui/disclosuregroupstyleconfiguration
crawled: 2025-12-05T22:21:14Z
---

# DisclosureGroupStyleConfiguration

**Structure**

The properties of a disclosure group instance.

## Declaration

```swift
struct DisclosureGroupStyleConfiguration
```

## Configuring the label

- **label**: The label for the disclosure group.
- **DisclosureGroupStyleConfiguration.Label**: A type-erased label of a disclosure group.

## Configuring the content

- **content**: The content of the disclosure group.
- **DisclosureGroupStyleConfiguration.Content**: A type-erased content of a disclosure group.

## Managing disclosure

- **isExpanded**: A binding to a Boolean that indicates whether the disclosure group is expanded.
- **$isExpanded**

## Creating custom disclosure group styles

- **makeBody(configuration:)**: Creates a view that represents the body of a disclosure group.
- **DisclosureGroupStyle.Configuration**: The properties of a disclosure group instance.
- **Body**: A view that represents the body of a disclosure group.

