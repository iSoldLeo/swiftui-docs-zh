---
来源： https://developer.apple.com/documentation/SwiftUI/DocumentConfiguration/isEditable
抓取时间： 2025-12-04T13:07:56Z
---

# isEditable

**实例属性**

布尔值，表示是否可以编辑文档。

## 声明

```swift
var isEditable: Bool { get }
```

## 讨论

在 macOS 上，如果用户没有写入权限、父目录或卷是只读的，或者文档无法自动保存，文档可能不可编辑。

在 iOS 上，如果读取或保存文档时发生错误、存在未解决的冲突、文档正在上传或下载，或者文档当前繁忙且不适合用户编辑，则文档不可编辑。

## 获取配置值

- **fileURL**：打开文档的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentConfiguration/isEditable
crawled: 2025-12-04T13:07:56Z
---

# isEditable

**Instance Property**

A Boolean value that indicates whether you can edit the document.

## Declaration

```swift
var isEditable: Bool { get }
```

## Discussion

On macOS, the document could be non-editable if the user lacks write permissions, the parent directory or volume is read-only, or the document couldn’t be autosaved.

On iOS, the document is not editable if there was an error reading or saving it, there’s an unresolved conflict, the document is being uploaded or downloaded, or otherwise, it is currently busy and unsafe for user edits.

## Getting configuration values

- **fileURL**: A URL of an open document.

