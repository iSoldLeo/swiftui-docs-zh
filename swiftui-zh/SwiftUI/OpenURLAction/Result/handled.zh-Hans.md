--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/handled
抓取时间：2025-12-04T13:39:29Z

---

# 已处理

**类型属性**

处理程序打开了 URL。

## 声明

```swift
static let handled: OpenURLAction.Result
```

## 讨论

当您的处理程序返回此值时，操作会使用 `true` 调用其完成处理程序。

## 获取结果

- **discarded**：处理程序丢弃了 URL。

- **systemAction**：处理程序请求系统打开原始 URL。

- **systemAction(_:)**：处理程序请求系统打开修改后的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/handled
crawled: 2025-12-04T13:39:29Z
---

# handled

**Type Property**

The handler opened the URL.

## Declaration

```swift
static let handled: OpenURLAction.Result
```

## Discussion

The action invokes its completion handler with `true` when your handler returns this value.

## Getting the results

- **discarded**: The handler discarded the URL.
- **systemAction**: The handler asks the system to open the original URL.
- **systemAction(_:)**: The handler asks the system to open the modified URL.

