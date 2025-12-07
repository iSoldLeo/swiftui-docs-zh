---
来源： https://developer.apple.com/documentation/swiftui/defaultdocumentgrouplaunchactions
抓取时间： 2025-12-04T11:34:17Z
---

# 默认文档组启动操作

**Structure**

文档组启动场景和文档启动视图的默认操作。

## 声明

```swift
struct DefaultDocumentGroupLaunchActions
```

## 概览

该`View` 用默认操作填充[DocumentGroupLaunchScene](DocumentGroupLaunchScene.zh-Hans.md) 和[DocumentLaunchView](DocumentLaunchView.zh-Hans.md)。

## 初始化器

- **init()**

## 配置文件启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。
- **DocumentLaunchView**：在启动与文档相关的用户体验时呈现的视图。
- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。
- **NewDocumentButton**：用于创建和打开新文档的按钮。
- **DocumentBaseBox**：可设置文档底座的方框，调用者无需知道方框及其底座的确切类型。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/swiftui/defaultdocumentgrouplaunchactions
crawled: 2025-12-04T11:34:17Z
---

# DefaultDocumentGroupLaunchActions

**Structure**

The default actions for the document group launch scene and the document launch view.

## Declaration

```swift
struct DefaultDocumentGroupLaunchActions
```

## Overview

This `View` populates [DocumentGroupLaunchScene](DocumentGroupLaunchScene.zh-Hans.md) and [DocumentLaunchView](DocumentLaunchView.zh-Hans.md) with the default actions.

## Initializers

- **init()**

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **NewDocumentButton**: A button that creates and opens new documents.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Conforms To

- View

