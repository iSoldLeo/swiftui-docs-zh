---
来源： https://developer.apple.com/documentation/SwiftUI/Documents
抓取时间： 2025-12-02T17:20:44Z
---

# 文件

** 应用程序集**

使人们能够打开和管理文件。

## 概览

使用[DocumentGroup](DocumentGroup.zh-Hans.md) 场景类型创建用于打开和编辑文档的用户界面。



您可以用一个描述文档数据组织的模型和一个 SwiftUI 用于向用户显示文档内容的视图层次结构来初始化场景。您可以使用符合[FileDocument](FileDocument.zh-Hans.md) 协议的值类型模型（通常存储为结构），也可以使用存储在符合[ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) 协议的类实例中的引用类型模型。您还可以使用类似[init(editing:contentType:editor:prepareDocument:)](DocumentGroup/init_editing_contentType_editor_prepareDocument.zh-Hans.md) 的初始化器来使用 SwiftData 支持的文档。

SwiftUI 支持用户期望从基于文档的应用程序中获得的适合各平台的标准行为，例如多窗口支持、打开和保存面板、拖放等。有关设计指南，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/patterns]。

## 创建文档

- 使用 SwiftUI 创建基于文档的应用程序**：在多平台应用程序中创建、保存和打开文档。
- 使用 SwiftData 构建基于文档的应用程序**：与 WWDC 演示者一起编写代码，使用 SwiftData 转换应用程序。
- **DocumentGroup**：支持打开、创建和保存文档的场景。

## 在结构实例中存储文档数据

- **FileDocument**：用于将文档序列化到文件或从文件序列化到文档的类型。
- **FileDocumentConfiguration**：打开的文件文档的属性。

### 在类实例中存储文档数据

- **ReferenceFileDocument**：用于将引用类型文档序列化到文件或从文件序列化到引用类型文档的类型。
- **ReferenceFileDocumentConfiguration**：打开的引用文件文档的属性。
- **undoManager**：用于注册视图撤销操作的撤销管理器。

## 访问文档配置

- **documentConfiguration**：[DocumentGroup](DocumentGroup.zh-Hans.md)中文档的配置。
- **DocumentConfiguration**：文件在[DocumentGroup](DocumentGroup.zh-Hans.md)中的配置。

## 读写文件

- **FileDocumentReadConfiguration**：读取文件内容的配置。
- **FileDocumentWriteConfiguration**：用于序列化文件内容的配置。

## 以编程方式打开文档

- **newDocument**：环境中显示新文档的操作。
- **NewDocumentAction**：显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。
- **OpenDocumentAction**：显示现有文档的操作。

## 配置文档启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。
- **DocumentLaunchView**：在启动与文档相关的用户体验时呈现的视图。
- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。
- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。
- **NewDocumentButton**：创建和打开新文档的按钮。
- **DocumentBaseBox**：可设置文档底座的方框，调用者无需知道方框及其底座的确切类型。

## 重命名文档

- **RenameButton**：触发标准重命名操作的按钮。
- **renameAction(_:)**：为重命名操作设置要运行的闭包。
- **rename**：激活标准重命名交互的操作。
- **RenameAction**：激活标准重命名交互的操作。

## 应用程序结构

- 应用程序组织**：定义应用程序的入口点和顶层结构。
- **Scenes**：声明构成应用程序各部分的用户界面分组。
- **Windows**：在窗口或窗口集合中显示用户界面内容。
- ** 无限空间**：在人的周围显示无限制的内容。
- **Navigation**：让用户可以在场景中应用程序视图层次结构的不同部分之间移动。
- 模态演示**：在单独的视图中展示内容，提供集中的交互。
- **Toolbars**：提供对常用命令和控件的即时访问。
- **Search**：使人们能够在您的应用程序中搜索文本或其他内容。
- **应用扩展**：将应用程序的基本功能扩展到系统的其他部分，如添加 Widget。


---
source: https://developer.apple.com/documentation/SwiftUI/Documents
crawled: 2025-12-02T17:20:44Z
---

# Documents

**API Collection**

Enable people to open and manage documents.

## Overview

Create a user interface for opening and editing documents using the [DocumentGroup](DocumentGroup.zh-Hans.md) scene type.



You initialize the scene with a model that describes the organization of the document’s data, and a view hierarchy that SwiftUI uses to display the document’s contents to the user. You can use either a value type model, which you typically store as a structure, that conforms to the [FileDocument](FileDocument.zh-Hans.md) protocol, or a reference type model you store in a class instance that conforms to the [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) protocol. You can also use SwiftData-backed documents using an initializer like [init(editing:contentType:editor:prepareDocument:)](DocumentGroup/init_editing_contentType_editor_prepareDocument.zh-Hans.md).

SwiftUI supports standard behaviors that users expect from a document-based app, appropriate for each platform, like multiwindow support, open and save panels, drag and drop, and so on. For related design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/patterns] in the Human Interface Guidelines.

## Creating a document

- **Building a document-based app with SwiftUI**: Create, save, and open documents in a multiplatform app.
- **Building a document-based app using SwiftData**: Code along with the WWDC presenter to transform an app with SwiftData.
- **DocumentGroup**: A scene that enables support for opening, creating, and saving documents.

## Storing document data in a structure instance

- **FileDocument**: A type that you use to serialize documents to and from file.
- **FileDocumentConfiguration**: The properties of an open file document.

## Storing document data in a class instance

- **ReferenceFileDocument**: A type that you use to serialize reference type documents to and from file.
- **ReferenceFileDocumentConfiguration**: The properties of an open reference file document.
- **undoManager**: The undo manager used to register a view’s undo operations.

## Accessing document configuration

- **documentConfiguration**: The configuration of a document in a [DocumentGroup](DocumentGroup.zh-Hans.md).
- **DocumentConfiguration**

## Reading and writing documents

- **FileDocumentReadConfiguration**: The configuration for reading file contents.
- **FileDocumentWriteConfiguration**: The configuration for serializing file contents.

## Opening a document programmatically

- **newDocument**: An action in the environment that presents a new document.
- **NewDocumentAction**: An action that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **OpenDocumentAction**: An action that presents an existing document.

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **NewDocumentButton**: A button that creates and opens new documents.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Renaming a document

- **RenameButton**: A button that triggers a standard rename action.
- **renameAction(_:)**: Sets a closure to run for the rename action.
- **rename**: An action that activates the standard rename interaction.
- **RenameAction**: An action that activates a standard rename interaction.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

