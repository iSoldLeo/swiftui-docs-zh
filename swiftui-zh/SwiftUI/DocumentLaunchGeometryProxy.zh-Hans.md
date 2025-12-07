--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchGeometryProxy
抓取时间：2025-12-02T17:29:26Z

---

# DocumentLaunchGeometryProxy

**Structure**

用于访问场景框架及其标题视图的代理。

## 声明

```swift
struct DocumentLaunchGeometryProxy
```

## 实例属性

- **frame**：文档启动界面的框架。

- **titleViewFrame**：界面内标题视图的框架。

## 配置文档启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。

- **DocumentLaunchView**：启动与文档相关的用户体验时要显示的视图。

- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。

- **NewDocumentButton**：用于创建和打开新文档的按钮。

- **DocumentBaseBox**：一个允许设置其文档基准的框，调用者无需了解框及其基准的具体类型。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchGeometryProxy
crawled: 2025-12-02T17:29:26Z
---

# DocumentLaunchGeometryProxy

**Structure**

A proxy for access to the frame of the scene and its title view.

## Declaration

```swift
struct DocumentLaunchGeometryProxy
```

## Instance Properties

- **frame**: Frame of the document launch interface.
- **titleViewFrame**: Frame of the title view within the interface.

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **NewDocumentButton**: A button that creates and opens new documents.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

