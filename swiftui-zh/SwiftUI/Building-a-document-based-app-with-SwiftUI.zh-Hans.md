---
来源： https://developer.apple.com/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI
抓取时间： 2025-12-02T16:15:58Z
---

# 使用 SwiftUI | Apple Developer Documentation 构建基于文档的应用程序

- [ SwiftUI ](/documentation/swiftui)

- [ 文档 ](/documentation/swiftui/documents)

- 使用 SwiftUI 构建基于文档的应用程序 ](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI)

- [ 文档 ](/documentation/swiftui/documents)

- 使用 SwiftUI 构建基于文档的应用程序

示例代码# 使用 SwiftUI 构建基于文档的应用程序

在多平台应用程序中创建、保存和打开文档。[ 下载 ](https://docs-assets.developer.apple.com/published/ef10bd7eff0d/BuildingADocumentBasedAppWithSwiftUI.zip)iOS 18.0+iPadOS 18.0+macOS 15.0+Xcode 16.0+## [概述](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Overview)

写作应用程序示例为 iOS、iPadOS 和 macOS 构建了一个基于文档的应用程序。在应用程序定义中，它具有[`DocumentGroup`](/documentation/swiftui/documentgroup)场景，其文档类型符合[`FileDocument`](/documentation/swiftui/filedocument)协议。人们可以创建一个写作应用程序文档，修改文档的标题和内容，并在聚焦模式下阅读故事。

### [配置示例代码项目](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Configure-the-sample-code-project)

要在设备上构建和运行此示例，请使用以下步骤为项目的目标选择您的开发团队：

- 使用最新版本的 Xcode 打开示例。

- 选择顶层项目。

- 对于项目的目标，从 "签名和能力 "窗格中的 "团队 "弹出菜单中选择您的团队，让 Xcode 自动管理您的供应配置文件。

## [定义应用程序的场景](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Define-the-apps-scene)

基于文档的 SwiftUI 应用程序会从其 `DocumentGroup` 属性返回一个 ⟦ 场景。应用程序向文档组的 [⟦IC_00⟧](/documentation/swiftui/documentgroup/init(newdocument:editor:)-4toe2)初始化器提供的`newDocument` 参数符合 [`FileDocument`](/documentation/swiftui/filedocument)或 [`ReferenceFileDocument`](/documentation/swiftui/referencefiledocument)。在本示例中，文档类型符合`FileDocument`。初始化器的尾部闭包返回一个渲染文档内容的视图：



```
@main
struct WritingApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: WritingAppDocument()) { file in
            StoryView(document: file.$document)
        }
    }
}

```

## [自定义 iOS 和 iPadOS 启动体验](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Customize-the-iOS-and-iPadOS-launch-experience)

您可以使用自定义标题、操作按钮和屏幕背景更新 iOS 和 iPadOS 的默认启动体验。要添加带有自定义标签的操作按钮，请使用 [`NewDocumentButton`](/documentation/swiftui/newdocumentbutton)替换默认标签。您可以通过多种方式自定义背景，例如添加视图或带有初始化器的`backgroundStyle`，例如 [`init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:backgroundstyle:_:backgroundaccessoryview:overlayaccessoryview:)-2d13c)。本示例使用 [`init(_:_:background:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:)-2iefz) 初始化程序自定义标题视图的背景：



```
DocumentGroupLaunchScene("Writing App") {
    NewDocumentButton("Start Writing")
} background: {
    Image(.pinkJungle)
    .resizable()
    .scaledToFill()
    .ignoresSafeArea()
} 

```

您还可以使用初始化器为场景添加配件，例如 [`init(_:_:background:backgroundAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:)-1valf)和 [`init(_:_:background:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:overlayaccessoryview:)-1143c)，具体取决于定位。



```
overlayAccessoryView: { _ in
    AccessoryView()
}

```

该示例在 `AccessoryView` 中定义的覆盖位置包含两个附件。它通过应用修饰符自定义配件，包括 [`offset(x:y:)`](/documentation/swiftui/view/offset(x:y:))和 [`frame(width:height:alignment:)`](/documentation/swiftui/view/frame(width:height:alignment:))。



```
ZStack {
    Image(.robot)
        .resizable()
        .offset(x: size.width / 2 - 450, y: size.height / 2 - 300)
        .scaledToFit()
        .frame(width: 200)
        .opacity(horizontal == .compact ? 0 : 1)
    Image(.plant)
        .resizable()
        .offset(x: size.width / 2 + 250, y: size.height / 2 - 225)
        .scaledToFit()
        .frame(width: 200)
        .opacity(horizontal == .compact ? 0 : 1)
}

```

要同时添加背景和叠加附件，请使用初始化器，例如 [`init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:overlayaccessoryview:)-1re6d)。如果不提供任何附件，系统默认会在标题视图下方显示两个淡入淡出的表页。在 macOS 中，该示例会在启动时显示默认的系统文档浏览器。您可能希望在启动时添加额外的体验。

## [创建数据模型](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Create-the-data-model)

本示例的数据模型将故事定义为`String`，并用空字符串初始化`story`：



```
var story: String


init(text: String = "") {
    self.story = text
}

```

## [通过档案文件协议](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Adopt-the-file-document-protocol)

`WritingAppDocument`结构采用`FileDocument`协议将文件序列化，并将文件序列化。`readableContentTypes`](/documentation/swiftui/filedocument/readablecontenttypes)属性定义了样本可以读写的类型，特别是`.writingAppDocument`类型：



```
static var readableContentTypes: [UTType] { [.writingAppDocument] }

```

初始化程序 [`init(configuration:)`](/documentation/swiftui/filedocument/init(configuration:))从文件加载文档。在使用`file`](/documentation/swiftui/filedocumentreadconfiguration/file)属性读取文件数据后，它会反序列化数据并将其存储到文档的数据模型中：



```
init(configuration: ReadConfiguration) throws {
    guard let data = configuration.file.regularFileContents,
          let string = String(data: data, encoding: .utf8)
    else {
        throw CocoaError(.fileReadCorruptFile)
    }
    story = string
}

```

当用户写入文档时，SwiftUI 会调用 [`fileWrapper(configuration:)`](/documentation/swiftui/filedocument/filewrapper(configuration:))函数将数据模型序列化为`FileWrapper`值，该值代表文件系统中的数据：



```
func fileWrapper(configuration: WriteConfiguration) throws -> FileWrapper {
    let data = Data(story.utf8)
    return .init(regularFileWithContents: data)
}

```

由于文档类型符合`FileDocument`，因此该示例会自动处理撤销操作。

## [导出自定义文档类型](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Export-a-custom-document-type)

应用程序为其创建的文档定义并导出自定义内容类型。它在项目的 [`Information Property List`](/documentation/BundleResources/Information-Property-List)键下的 [`UTExportedTypeDeclarations`](/documentation/BundleResources/Information-Property-List/UTExportedTypeDeclarations) 文件中声明了这种自定义类型。本示例使用 `com.example.writingAppDocument` 作为 `Info.plist` 文件中的标识符：



```
<key>CFBundleDocumentTypes</key>
<array>
    <dict>
        <key>CFBundleTypeRole</key>
        <string>Editor</string>
        <key>LSHandlerRank</key>
        <string>Default</string>
        <key>LSItemContentTypes</key>
        <array>
            <string>com.example.writingAppDocument</string>
        </array>
        <key>NSUbiquitousDocumentUserActivityType</key>
        <string>$(PRODUCT_BUNDLE_IDENTIFIER).exampledocument</string>
    </dict>
</array>
<key>UTExportedTypeDeclarations</key>
<array>
    <dict>
        <key>UTTypeConformsTo</key>
        <array>
            <string>public.utf8-plain-text</string>
        </array>
        <key>UTTypeDescription</key>
        <string>Writing App Document</string>
        <key>UTTypeIconFiles</key>
        <array/>
        <key>UTTypeIdentifier</key>
        <string>com.example.writingAppDocument</string>
        <key>UTTypeTagSpecification</key>
        <dict>
            <key>public.filename-extension</key>
            <array>
                <string>story</string>
            </array>
        </dict>
    </dict>
</array>

```

为方便起见，您也可以在代码中定义内容类型。例如



```
extension UTType {
    static var writingapp: UTType {
        UTType(exportedAs: "com.example.writingAppDocument")
    }
}

```

为确保操作系统知道您的应用程序可以打开`Info.plist` 中描述格式的文件，操作系统会为内容类型定义文件扩展名`story`。有关自定义文件和数据类型的更多信息，请参阅 [为您的应用程序定义文件和数据类型](/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app)。

## [另请参阅](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#See-Also)

#### [相关样本](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-samples)

[使用 SwiftData 构建基于文档的应用程序](/documentation/swiftui/building-a-document-based-app-using-swiftdata)与 WWDC 演示者一起使用 SwiftData 改造应用程序的代码.#### [相关文章](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-articles)

[为您的应用程序定义文件和数据类型](/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app)声明统一类型标识符以支持您的应用程序的专有数据格式。[自定义基于文档的应用程序的启动体验](/documentation/UIKit/customizing-a-document-based-app-s-launch-experience)为您的应用程序的文档启动场景添加独特元素.#### [相关视频](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-videos)

[改善您的文档启动体验](https://developer.apple.com/videos/play/wwdc2024/10132)

---
source: https://developer.apple.com/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI
crawled: 2025-12-02T16:15:58Z
---

# Building a document-based app with SwiftUI | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ Documents ](/documentation/swiftui/documents)

- [ Building a document-based app with SwiftUI ](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI)

- [ Documents ](/documentation/swiftui/documents)

-  Building a document-based app with SwiftUI 

Sample Code# Building a document-based app with SwiftUI

Create, save, and open documents in a multiplatform app.[ Download ](https://docs-assets.developer.apple.com/published/ef10bd7eff0d/BuildingADocumentBasedAppWithSwiftUI.zip)iOS 18.0+iPadOS 18.0+macOS 15.0+Xcode 16.0+## [Overview](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Overview)

The Writing App sample builds a document-based app for iOS, iPadOS, and macOS. In the app definition, it has a [`DocumentGroup`](/documentation/swiftui/documentgroup) scene, and its document type conforms to the [`FileDocument`](/documentation/swiftui/filedocument) protocol. People can create a writing app document, modify the title and contents of the document, and read the story in focus mode.

## [Configure the sample code project](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Configure-the-sample-code-project)

To build and run this sample on your device, select your development team for the project’s target using these steps:

- Open the sample with the latest version of Xcode.

- Select the top-level project.

- For the project’s target, choose your team from the Team pop-up menu in the Signing & Capabilities pane to let Xcode automatically manage your provisioning profile.

## [Define the app’s scene](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Define-the-apps-scene)

A document-based SwiftUI app returns a `DocumentGroup` scene from its `body` property. The `newDocument` parameter that an app supplies to the document group’s [`init(newDocument:editor:)`](/documentation/swiftui/documentgroup/init(newdocument:editor:)-4toe2) initializer conforms to either [`FileDocument`](/documentation/swiftui/filedocument) or [`ReferenceFileDocument`](/documentation/swiftui/referencefiledocument). In this sample, the document type conforms to `FileDocument`. The trailing closure of the initializer returns a view that renders the document’s contents:



```
@main
struct WritingApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: WritingAppDocument()) { file in
            StoryView(document: file.$document)
        }
    }
}

```

## [Customize the iOS and iPadOS launch experience](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Customize-the-iOS-and-iPadOS-launch-experience)

You can update the default launch experience on iOS and iPadOS with a custom title, action buttons, and screen background. To add an action button with a custom label, use [`NewDocumentButton`](/documentation/swiftui/newdocumentbutton) to replace the default label. You can customize the background in many ways such as adding a view or a `backgroundStyle` with an initializer, for example [`init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:backgroundstyle:_:backgroundaccessoryview:overlayaccessoryview:)-2d13c). This sample customizes the background of the title view, using the [`init(_:_:background:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:)-2iefz) initializer:



```
DocumentGroupLaunchScene("Writing App") {
    NewDocumentButton("Start Writing")
} background: {
    Image(.pinkJungle)
    .resizable()
    .scaledToFill()
    .ignoresSafeArea()
} 

```

You can also add accessories to the scene using initializers such as [`init(_:_:background:backgroundAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:)-1valf) and [`init(_:_:background:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:overlayaccessoryview:)-1143c) depending on the positioning.



```
overlayAccessoryView: { _ in
    AccessoryView()
}

```

This sample contains two accessories in the overlay position that it defines in `AccessoryView`. It customizes the accessories by applying modifiers, including [`offset(x:y:)`](/documentation/swiftui/view/offset(x:y:)) and [`frame(width:height:alignment:)`](/documentation/swiftui/view/frame(width:height:alignment:)).



```
ZStack {
    Image(.robot)
        .resizable()
        .offset(x: size.width / 2 - 450, y: size.height / 2 - 300)
        .scaledToFit()
        .frame(width: 200)
        .opacity(horizontal == .compact ? 0 : 1)
    Image(.plant)
        .resizable()
        .offset(x: size.width / 2 + 250, y: size.height / 2 - 225)
        .scaledToFit()
        .frame(width: 200)
        .opacity(horizontal == .compact ? 0 : 1)
}

```

To add both background and overlay accessories, use an initializer, such as [`init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)`](/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:overlayaccessoryview:)-1re6d). If you don’t provide any accessories, the system displays two faded sheets below the title view by default. In macOS, this sample displays the default system document browser on launch. You may wish to add an additional experience on launch.

## [Create the data model](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Create-the-data-model)

This sample has a data model that defines a story as a `String`, it initializes `story` with an empty string:



```
var story: String


init(text: String = "") {
    self.story = text
}

```

## [Adopt the file document protocol](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Adopt-the-file-document-protocol)

The `WritingAppDocument` structure adopts the `FileDocument` protocol to serialize documents to and from files. The [`readableContentTypes`](/documentation/swiftui/filedocument/readablecontenttypes) property defines the types that the sample can read and write, specifically, the `.writingAppDocument` type:



```
static var readableContentTypes: [UTType] { [.writingAppDocument] }

```

The [`init(configuration:)`](/documentation/swiftui/filedocument/init(configuration:)) initializer loads documents from a file. After reading the file’s data using the [`file`](/documentation/swiftui/filedocumentreadconfiguration/file) property of the `configuration` input, it deserializes the data and stores it in the document’s data model:



```
init(configuration: ReadConfiguration) throws {
    guard let data = configuration.file.regularFileContents,
          let string = String(data: data, encoding: .utf8)
    else {
        throw CocoaError(.fileReadCorruptFile)
    }
    story = string
}

```

When a person writes a document, SwiftUI calls the [`fileWrapper(configuration:)`](/documentation/swiftui/filedocument/filewrapper(configuration:)) function to serialize the data model into a `FileWrapper` value that represents the data in the file system:



```
func fileWrapper(configuration: WriteConfiguration) throws -> FileWrapper {
    let data = Data(story.utf8)
    return .init(regularFileWithContents: data)
}

```

Because the document type conforms to `FileDocument`, this sample handles undo actions automatically.

## [Export a custom document type](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Export-a-custom-document-type)

The app defines and exports a custom content type for the documents it creates. It declares this custom type in the project’s [`Information Property List`](/documentation/BundleResources/Information-Property-List) file under the [`UTExportedTypeDeclarations`](/documentation/BundleResources/Information-Property-List/UTExportedTypeDeclarations) key. This sample uses `com.example.writingAppDocument` as the identifier in the `Info.plist` file:



```
<key>CFBundleDocumentTypes</key>
<array>
    <dict>
        <key>CFBundleTypeRole</key>
        <string>Editor</string>
        <key>LSHandlerRank</key>
        <string>Default</string>
        <key>LSItemContentTypes</key>
        <array>
            <string>com.example.writingAppDocument</string>
        </array>
        <key>NSUbiquitousDocumentUserActivityType</key>
        <string>$(PRODUCT_BUNDLE_IDENTIFIER).exampledocument</string>
    </dict>
</array>
<key>UTExportedTypeDeclarations</key>
<array>
    <dict>
        <key>UTTypeConformsTo</key>
        <array>
            <string>public.utf8-plain-text</string>
        </array>
        <key>UTTypeDescription</key>
        <string>Writing App Document</string>
        <key>UTTypeIconFiles</key>
        <array/>
        <key>UTTypeIdentifier</key>
        <string>com.example.writingAppDocument</string>
        <key>UTTypeTagSpecification</key>
        <dict>
            <key>public.filename-extension</key>
            <array>
                <string>story</string>
            </array>
        </dict>
    </dict>
</array>

```

For convenience, you can also define the content type in code. For example:



```
extension UTType {
    static var writingapp: UTType {
        UTType(exportedAs: "com.example.writingAppDocument")
    }
}

```

To make sure that the operating system knows that your application can open files with the format described in the `Info.plist`, it defines the file extension `story` for the content type. For more information about custom file and data types, see [Defining file and data types for your app](/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app).

## [See Also](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#See-Also)

#### [Related samples](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-samples)

[Building a document-based app using SwiftData](/documentation/swiftui/building-a-document-based-app-using-swiftdata)Code along with the WWDC presenter to transform an app with SwiftData.#### [Related articles](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-articles)

[Defining file and data types for your app](/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app)Declare uniform type identifiers to support your app’s proprietary data formats.[Customizing a document-based app’s launch experience](/documentation/UIKit/customizing-a-document-based-app-s-launch-experience)Add unique elements to your app’s document launch scene.#### [Related videos](/documentation/SwiftUI/Building-a-document-based-app-with-SwiftUI#Related-videos)

[ Evolve your document launch experience ](https://developer.apple.com/videos/play/wwdc2024/10132)