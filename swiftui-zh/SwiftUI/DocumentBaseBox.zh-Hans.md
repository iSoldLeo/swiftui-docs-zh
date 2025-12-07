---
来源： https://developer.apple.com/documentation/SwiftUI/DocumentBaseBox
抓取时间： 2025-12-02T17:29:27Z
---

# DocumentBaseBox

**Protocol**

允许设置其文档底层的方框，调用者无需知道方框及其底层的确切类型。

### 声明

```swift
protocol DocumentBaseBox<Document> : AnyObject
```

## 关联类型

- **Document**：基础文档类型。

### 实例属性

- **base**：将基础文档更新为新值。

## 配置文件启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。
- **DocumentLaunchView**：在启动与文档相关的用户体验时呈现的视图。
- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。
- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。
- **NewDocumentButton**：创建和打开新文档的按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentBaseBox
crawled: 2025-12-02T17:29:27Z
---

# DocumentBaseBox

**Protocol**

A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Declaration

```swift
protocol DocumentBaseBox<Document> : AnyObject
```

## Associated Types

- **Document**: The underlying document type.

## Instance Properties

- **base**: Updates the underlying document to a new value.

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **NewDocumentButton**: A button that creates and opens new documents.

