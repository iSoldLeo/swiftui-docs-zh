--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/systemAction(_:)

抓取时间：2025-12-04T13:39:31Z

---

# systemAction(_:)

**类型：方法**

此处理程序请求系统打开修改后的 URL。

## 声明

```swift
static func systemAction(_ url: URL) -> OpenURLAction.Result
```

## 参数

- **url**：处理程序请求系统打开的 URL。

## 说明

此操作会调用其完成处理程序，并传递一个值，该值取决于系统尝试打开 URL 的结果。

## 获取结果

- **discarded**：处理程序丢弃了该 URL。

- **handled**：处理程序打开了该 URL。

- **systemAction**：该处理程序请求系统打开原始 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/Result/systemAction(_:)
crawled: 2025-12-04T13:39:31Z
---

# systemAction(_:)

**Type Method**

The handler asks the system to open the modified URL.

## Declaration

```swift
static func systemAction(_ url: URL) -> OpenURLAction.Result
```

## Parameters

- **url**: The URL that the handler asks the system to open.

## Discussion

The action invokes its completion handler with a value that depends on the outcome of the system’s attempt to open the URL.

## Getting the results

- **discarded**: The handler discarded the URL.
- **handled**: The handler opened the URL.
- **systemAction**: The handler asks the system to open the original URL.

