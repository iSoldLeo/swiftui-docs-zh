--- 来源：https://developer.apple.com/documentation/swiftui/openurlaction/result
抓取时间：2025-12-05T22:29:39Z

---

# OpenURLAction.Result

**Structure**

自定义打开 URL 操作的结果。

## 声明

```swift
struct Result
```

## 概述

如果您在 [Environment](../Environment.zh-Hans.md) 中声明了自定义 [OpenURLAction](../OpenURLAction.zh-Hans.md)，则返回其处理程序的结果值之一。

- 使用 [handled](Result/handled.zh-Hans.md) 表示处理程序已打开 URL。

- 使用 [discarded](Result/discarded.zh-Hans.md) 表示处理程序已丢弃 URL。

- 使用不带参数的 [systemAction](Result/systemAction.zh-Hans.md) 可以请求 SwiftUI 使用系统处理程序打开 URL。

- 使用带有 URL 参数的 [systemAction(_:)](Result/systemAction.zh-Hans.md) 可以请求 SwiftUI 使用系统处理程序打开指定的 URL。

您可以使用最后一个选项来转换 URL，同时仍然依赖系统来打开 URL。例如，您可以将路径组件附加到每个 URL：

```swift
.environment(\.openURL, OpenURLAction { url in
    .systemAction(url.appendingPathComponent("edit"))
})
```

## 获取结果

- **discarded**：处理程序丢弃了 URL。

- **handled**：处理程序打开了 URL。

- **systemAction**：处理程序请求系统打开原始 URL。

- **systemAction(_:)**：处理程序请求系统打开修改后的 URL。

## 类型方法

- **systemAction(_:prefersInApp:)**

## 创建操作

- **init(handler:)**：创建一个打开 URL 的操作。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/openurlaction/result
crawled: 2025-12-05T22:29:39Z
---

# OpenURLAction.Result

**Structure**

The result of a custom open URL action.

## Declaration

```swift
struct Result
```

## Overview

If you declare a custom [OpenURLAction](../OpenURLAction.zh-Hans.md) in the [Environment](../Environment.zh-Hans.md), return one of the result values from its handler.

- Use [handled](Result/handled.zh-Hans.md) to indicate that the handler opened the URL.
- Use [discarded](Result/discarded.zh-Hans.md) to indicate that the handler discarded the URL.
- Use [systemAction](Result/systemAction.zh-Hans.md) without an argument to ask SwiftUI to open the URL with the system handler.
- Use [systemAction(_:)](Result/systemAction.zh-Hans.md) with a URL argument to ask SwiftUI to open the specified URL with the system handler.

You can use the last option to transform URLs, while still relying on the system to open the URL. For example, you could append a path component to every URL:

```swift
.environment(\.openURL, OpenURLAction { url in
    .systemAction(url.appendingPathComponent("edit"))
})
```

## Getting the results

- **discarded**: The handler discarded the URL.
- **handled**: The handler opened the URL.
- **systemAction**: The handler asks the system to open the original URL.
- **systemAction(_:)**: The handler asks the system to open the modified URL.

## Type Methods

- **systemAction(_:prefersInApp:)**

## Creating the action

- **init(handler:)**: Creates an action that opens a URL.

## Conforms To

- Sendable
- SendableMetatype

