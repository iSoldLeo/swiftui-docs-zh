--- 来源：https://developer.apple.com/documentation/swiftui/filedocumentconfiguration/document
抓取时间：2025-12-04T13:07:51Z

---

# document

**实例属性**

当前文档模型。

## 声明

```swift
@Binding var document: Document { get nonmutating set }
```

## 说明

设置新值会将文档标记为已更改，以便稍后保存，并注册一个撤销操作，用于将模型恢复到先前的值。

如果 [isEditable](isEditable.zh-Hans.md) 为 `false`，则设置新值无效，因为文档处于查看模式。

## 获取和设置文档

- **$document**


---
source: https://developer.apple.com/documentation/swiftui/filedocumentconfiguration/document
crawled: 2025-12-04T13:07:51Z
---

# document

**Instance Property**

The current document model.

## Declaration

```swift
@Binding var document: Document { get nonmutating set }
```

## Discussion

Setting a new value marks the document as having changes for later saving and registers an undo action to restore the model to its previous value.

If [isEditable](isEditable.zh-Hans.md) is `false`, setting a new value has no effect because the document is in viewing mode.

## Getting and setting the document

- **$document**

