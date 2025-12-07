--- 来源：https://developer.apple.com/documentation/swiftui/referencefiledocumentconfiguration/document

抓取时间：2025-12-04T13:07:55Z

---

# document

**实例属性**

当前文档模型。

## 声明

```swift
@ObservedObject @MainActor @preconcurrency var document: Document { get set }
```

## 讨论

对文档的更改会污染文档状态，表明需要保存。SwiftUI 不会自动注册撤销操作。

## 获取和设置文档

- **$document**


---
source: https://developer.apple.com/documentation/swiftui/referencefiledocumentconfiguration/document
crawled: 2025-12-04T13:07:55Z
---

# document

**Instance Property**

The current document model.

## Declaration

```swift
@ObservedObject @MainActor @preconcurrency var document: Document { get set }
```

## Discussion

Changes to the document dirty the document state, indicating that it needs to be saved. SwiftUI doesn’t automatically register undo actions.

## Getting and setting the document

- **$document**

