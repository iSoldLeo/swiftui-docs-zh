--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/discarded

抓取时间：2025-12-04T13:39:28Z

---

# 已丢弃

**类型属性**

处理程序丢弃了 URL。

## 声明

```swift
static let discarded: OpenURLAction.Result
```

## 讨论

当您的处理程序返回此值时，操作会使用 `false` 调用其完成处理程序。

## 获取结果

- **handled**：处理程序已打开 URL。

- **systemAction**：处理程序请求系统打开原始 URL。

- **systemAction(_:)**：处理程序请求系统打开修改后的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/discarded
crawled: 2025-12-04T13:39:28Z
---

# discarded

**Type Property**

The handler discarded the URL.

## Declaration

```swift
static let discarded: OpenURLAction.Result
```

## Discussion

The action invokes its completion handler with `false` when your handler returns this value.

## Getting the results

- **handled**: The handler opened the URL.
- **systemAction**: The handler asks the system to open the original URL.
- **systemAction(_:)**: The handler asks the system to open the modified URL.

