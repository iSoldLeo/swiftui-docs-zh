---

来源：https://developer.apple.com/documentation/swiftui

抓取时间：2025-12-02T16:01:01Z

---

# SwiftUI | Apple 开发者文档

框架 # SwiftUI

声明应用程序在所有平台上的用户界面和行为。iOS 13.0+、iPadOS 13.0+、Mac Catalyst 13.0+、macOS 10.15+、tvOS 13.0+、vVOS 1.0+、watchOS 6.0+ ## [概述](/documentation/swiftui#Overview)

SwiftUI 提供视图、控件和布局结构，用于声明应用程序的用户界面。该框架提供事件处理程序，用于将点击、手势和其他类型的输入传递给应用程序，并提供工具来管理从应用程序模型到用户看到并与之交互的视图和控件的数据流。

使用 [`App`](/documentation/swiftui/app) 协议定义应用结构，并使用包含构成应用用户界面的视图的场景填充它。创建符合 [`View`](/documentation/swiftui/view) 协议的自定义视图，并将其与 SwiftUI 视图组合，以使用堆栈、列表等方式显示文本、图像和自定义形状。对内置视图和自定义视图应用强大的修饰符，以自定义它们的渲染和交互方式。通过能够适应不同平台上下文和呈现方式的视图和控件，在多个平台上的应用之间共享代码。

您可以将 SwiftUI 视图与 [UIKit](/documentation/UIKit)、[AppKit](/documentation/AppKit) 和 [WatchKit](/documentation/WatchKit) 框架中的对象集成，以进一步利用平台特定的功能。您还可以在 SwiftUI 中自定义辅助功能支持，并针对不同的语言、国家/地区或文化区域本地化应用程序界面。

### [精选示例](/documentation/swiftui#Featured-samples)

[ Landmarks：使用 Liquid Glass 构建应用程序 使用系统提供的和自定义的 Liquid Glass 增强您的应用程序体验。查看示例代码 ](/documentation/swiftui/landmarks-building-an-app-with-liquid-glass)[ Destination Video：利用 SwiftUI 在多平台应用程序中构建沉浸式媒体体验。查看示例代码 ](/documentation/visionOS/destination-video)[ BOT-anist：构建一个使用窗口、音量和动画来创建机器人植物学家温室的多平台应用程序。查看示例代码 ](/documentation/visionOS/BOT-anist)[ 使用 SwiftUI 构建基于文档的应用程序 在多平台应用程序中创建、保存和打开文档。查看示例代码](/documentation/swiftui/building-a-document-based-app-with-swiftui)## [主题](/documentation/swiftui#topics)

### [基础知识](/documentation/swiftui#Essentials)

[采用 Liquid Glass](/documentation/TechnologyOverviews/adopting-liquid-glass)了解如何将这种新材质应用到您的应用中。[学习 SwiftUI](/tutorials/swiftui-concepts)通过这组概念文章和示例代码，探索构建多平台应用的技巧和方法。[探索 SwiftUI 示例应用](/tutorials/Sample-Apps)使用 iPad 上的 Swift Playground 或 Xcode 探索这些 SwiftUI 示例，学习如何定义用户界面、响应用户交互以及管理数据流。[SwiftUI 更新](/documentation/Updates/SwiftUI)了解 SwiftUI 的重要变更。[里程碑：使用 Liquid 构建应用](⟦LU_0061) [玻璃](/documentation/swiftui/landmarks-building-an-app-with-liquid-glass)使用系统提供的和自定义的 Liquid Glass 增强您的应用体验。### [应用结构](/documentation/swiftui#App-structure)

[应用组织](/documentation/swiftui/app-organization)定义应用的入口点和顶层结构。[场景](/documentation/swiftui/scenes)声明构成应用各个部分的用户界面分组。[窗口](/documentation/swiftui/windows)在窗口或窗口集合中显示用户界面内容。[沉浸式空间](/documentation/swiftui/immersive-spaces)在用户的环境中显示无限内容。[文档](/documentation/swiftui/documents)允许用户打开和管理文档。[导航](/documentation/swiftui/navigation)允许用户在应用的不同部分之间移动。场景内的视图层级结构。[模态呈现](/documentation/swiftui/modal-presentations)在单独的视图中呈现内容，提供专注的交互。[工具栏](/documentation/swiftui/toolbars)提供对常用命令和控件的即时访问。[搜索](/documentation/swiftui/search)使用户能够在您的应用中搜索文本或其他内容。[应用扩展](/documentation/swiftui/app-extensions)将应用的基本功能扩展到系统的其他部分，例如通过添加小部件。### [数据和存储](/documentation/swiftui#Data-and-storage)

[模型数据](/documentation/swiftui/model-data)管理应用用于驱动其界面的数据。[环境值](/documentation/swiftui/environment-values)使用环境值在整个视图层级结构中共享数据。环境。[首选项](/documentation/swiftui/preferences) 指示视图对其容器视图的配置首选项。[持久存储](/documentation/swiftui/persistent-storage) 存储数据，以便在应用程序的不同会话中使用。### [视图](/documentation/swiftui#Views)

[视图基础](/documentation/swiftui/view-fundamentals) 使用视图层次结构定义应用程序的视觉元素。[视图配置](/documentation/swiftui/view-configuration) 调整层次结构中视图的特性。[视图样式](/documentation/swiftui/view-styles) 将内置和自定义的外观和行为应用于不同类型的视图。[动画](/documentation/swiftui/animations) 创建响应状态更改的平滑视觉更新。[文本输入和输出](/documentation/swiftui/text-input-and-output) 显示格式化文本并从输入框获取文本输入。用户.[图像](/documentation/swiftui/images)向应用程序的用户界面添加图像和符号。[控件和指示器](/documentation/swiftui/controls-and-indicators)显示值并获取用户选择。[菜单和命令](/documentation/swiftui/menus-and-commands)提供空间高效、上下文相关的命令和控件访问方式。[形状](/documentation/swiftui/shapes)使用颜色、渐变或其他图案描绘和填充内置和自定义形状。[绘图和图形](/documentation/swiftui/drawing-and-graphics)使用图形效果和自定义绘图增强视图。### [视图布局](/documentation/swiftui#View-layout)

[布局基础](/documentation/swiftui/layout-fundamentals)在内置布局容器（例如堆栈和网格）中排列视图。[布局调整](/documentation/swiftui/layout-adjustments)进行微调调整对齐方式、间距、内边距和其他布局参数。[自定义布局](/documentation/swiftui/custom-layout) 将视图放置在自定义排列中，并在布局类型之间创建动画过渡效果。[列表](/documentation/swiftui/lists) 显示结构化的、可滚动的信息列。[表格](/documentation/swiftui/tables) 显示按行和列排列的可选择、可排序的数据。[视图分组](/documentation/swiftui/view-groupings) 在不同类型的用途容器（例如表单或控件组）中呈现视图。[滚动视图](/documentation/swiftui/scroll-views) 允许用户滚动到当前显示内容之外的内容。### [事件处理](/documentation/swiftui#Event-handling)

[手势](/documentation/swiftui/gestures) 定义从点击、单击和滑动等交互方式。精细的手势。[输入事件](/documentation/swiftui/input-events)响应来自硬件设备（例如键盘或触控栏）的输入。[剪贴板](/documentation/swiftui/clipboard)允许用户通过发出复制和粘贴命令来移动或复制项目。[拖放](/documentation/swiftui/drag-and-drop)允许用户通过将项目从一个位置拖动到另一个位置来移动或复制项目。[焦点](/documentation/swiftui/focus)识别并控制哪个可见对象响应用户交互。[系统事件](/documentation/swiftui/system-events)响应系统事件，例如打开 URL。### [辅助功能](/documentation/swiftui#Accessibility)

[辅助功能基础](/documentation/swiftui/accessibility-fundamentals)使您的 SwiftUI 应用对所有人（包括残障人士）都易于使用。[辅助功能](/documentation/swiftui/accessibility-fundamentals) [外观](/documentation/swiftui/accessible-appearance)增强应用界面内容的易读性。[辅助功能控件](/documentation/swiftui/accessible-controls)改善用户对应用可执行操作的访问。[辅助功能描述](/documentation/swiftui/accessible-descriptions)描述界面元素，帮助用户理解其含义。[辅助功能导航](/documentation/swiftui/accessible-navigation)使用户能够使用旋转器导航到特定的用户界面元素。### [框架集成](/documentation/swiftui#Framework-integration)

[AppKit 集成](/documentation/swiftui/appkit-integration)将 AppKit 视图添加到 SwiftUI 应用，或在您的 AppKit 应用中使用 SwiftUI 视图。[UIKit 集成](/documentation/swiftui/uikit-integration)将 UIKit 视图添加到 SwiftUI 应用，或在您的 UIKit 应用中使用 SwiftUI 视图。[WatchKit] [集成](/documentation/swiftui/watchkit-integration)将 WatchKit 视图添加到您的 SwiftUI 应用，或在您的 WatchKit 应用中使用 SwiftUI 视图。[特定技术视图](/documentation/swiftui/technology-specific-views)使用其他 Apple 框架提供的 SwiftUI 视图。### [工具支持](/documentation/swiftui#Tool-support)

[Xcode 预览](/documentation/swiftui/previews-in-xcode)生成自定义视图的动态交互式预览。[Xcode 库自定义](/documentation/swiftui/xcode-library-customization)在 Xcode 库中公开自定义视图和修饰符。[性能分析](/documentation/swiftui/performance-analysis)测量并改进应用的响应速度。

---
source: https://developer.apple.com/documentation/swiftui
crawled: 2025-12-02T16:01:01Z
---

# SwiftUI | Apple Developer Documentation

Framework# SwiftUI

Declare the user interface and behavior for your app on every platform.iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+macOS 10.15+tvOS 13.0+visionOS 1.0+watchOS 6.0+## [Overview](/documentation/swiftui#Overview)

SwiftUI provides views, controls, and layout structures for declaring your app’s user interface. The framework provides event handlers for delivering taps, gestures, and other types of input to your app, and tools to manage the flow of data from your app’s models down to the views and controls that users see and interact with.

Define your app structure using the [`App`](/documentation/swiftui/app) protocol, and populate it with scenes that contain the views that make up your app’s user interface. Create your own custom views that conform to the [`View`](/documentation/swiftui/view) protocol, and compose them with SwiftUI views for displaying text, images, and custom shapes using stacks, lists, and more. Apply powerful modifiers to built-in views and your own views to customize their rendering and interactivity. Share code between apps on multiple platforms with views and controls that adapt to their context and presentation.

You can integrate SwiftUI views with objects from the [UIKit](/documentation/UIKit), [AppKit](/documentation/AppKit), and [WatchKit](/documentation/WatchKit) frameworks to take further advantage of platform-specific functionality. You can also customize accessibility support in SwiftUI, and localize your app’s interface for different languages, countries, or cultural regions.

### [Featured samples](/documentation/swiftui#Featured-samples)

[ Landmarks: Building an app with Liquid Glass Enhance your app experience with system-provided and custom Liquid Glass. View sample code ](/documentation/swiftui/landmarks-building-an-app-with-liquid-glass)[ Destination Video Leverage SwiftUI to build an immersive media experience in a multiplatform app. View sample code ](/documentation/visionOS/destination-video)[ BOT-anist Build a multiplatform app that uses windows, volumes, and animations to create a robot botanist’s greenhouse. View sample code ](/documentation/visionOS/BOT-anist)[ Building a document-based app with SwiftUI Create, save, and open documents in a multiplatform app. View sample code ](/documentation/swiftui/building-a-document-based-app-with-swiftui)## [Topics](/documentation/swiftui#topics)

### [Essentials](/documentation/swiftui#Essentials)

[Adopting Liquid Glass](/documentation/TechnologyOverviews/adopting-liquid-glass)Find out how to bring the new material to your app.[Learning SwiftUI](/tutorials/swiftui-concepts)Discover tips and techniques for building multiplatform apps with this set of conceptual articles and sample code.[Exploring SwiftUI Sample Apps](/tutorials/Sample-Apps)Explore these SwiftUI samples using Swift Playgrounds on iPad or in Xcode to learn about defining user interfaces, responding to user interactions, and managing data flow.[SwiftUI updates](/documentation/Updates/SwiftUI)Learn about important changes to SwiftUI.[Landmarks: Building an app with Liquid Glass](/documentation/swiftui/landmarks-building-an-app-with-liquid-glass)Enhance your app experience with system-provided and custom Liquid Glass.### [App structure](/documentation/swiftui#App-structure)

[App organization](/documentation/swiftui/app-organization)Define the entry point and top-level structure of your app.[Scenes](/documentation/swiftui/scenes)Declare the user interface groupings that make up the parts of your app.[Windows](/documentation/swiftui/windows)Display user interface content in a window or a collection of windows.[Immersive spaces](/documentation/swiftui/immersive-spaces)Display unbounded content in a person’s surroundings.[Documents](/documentation/swiftui/documents)Enable people to open and manage documents.[Navigation](/documentation/swiftui/navigation)Enable people to move between different parts of your app’s view hierarchy within a scene.[Modal presentations](/documentation/swiftui/modal-presentations)Present content in a separate view that offers focused interaction.[Toolbars](/documentation/swiftui/toolbars)Provide immediate access to frequently used commands and controls.[Search](/documentation/swiftui/search)Enable people to search for text or other content within your app.[App extensions](/documentation/swiftui/app-extensions)Extend your app’s basic functionality to other parts of the system, like by adding a Widget.### [Data and storage](/documentation/swiftui#Data-and-storage)

[Model data](/documentation/swiftui/model-data)Manage the data that your app uses to drive its interface.[Environment values](/documentation/swiftui/environment-values)Share data throughout a view hierarchy using the environment.[Preferences](/documentation/swiftui/preferences)Indicate configuration preferences from views to their container views.[Persistent storage](/documentation/swiftui/persistent-storage)Store data for use across sessions of your app.### [Views](/documentation/swiftui#Views)

[View fundamentals](/documentation/swiftui/view-fundamentals)Define the visual elements of your app using a hierarchy of views.[View configuration](/documentation/swiftui/view-configuration)Adjust the characteristics of views in a hierarchy.[View styles](/documentation/swiftui/view-styles)Apply built-in and custom appearances and behaviors to different types of views.[Animations](/documentation/swiftui/animations)Create smooth visual updates in response to state changes.[Text input and output](/documentation/swiftui/text-input-and-output)Display formatted text and get text input from the user.[Images](/documentation/swiftui/images)Add images and symbols to your app’s user interface.[Controls and indicators](/documentation/swiftui/controls-and-indicators)Display values and get user selections.[Menus and commands](/documentation/swiftui/menus-and-commands)Provide space-efficient, context-dependent access to commands and controls.[Shapes](/documentation/swiftui/shapes)Trace and fill built-in and custom shapes with a color, gradient, or other pattern.[Drawing and graphics](/documentation/swiftui/drawing-and-graphics)Enhance your views with graphical effects and customized drawings.### [View layout](/documentation/swiftui#View-layout)

[Layout fundamentals](/documentation/swiftui/layout-fundamentals)Arrange views inside built-in layout containers like stacks and grids.[Layout adjustments](/documentation/swiftui/layout-adjustments)Make fine adjustments to alignment, spacing, padding, and other layout parameters.[Custom layout](/documentation/swiftui/custom-layout)Place views in custom arrangements and create animated transitions between layout types.[Lists](/documentation/swiftui/lists)Display a structured, scrollable column of information.[Tables](/documentation/swiftui/tables)Display selectable, sortable data arranged in rows and columns.[View groupings](/documentation/swiftui/view-groupings)Present views in different kinds of purpose-driven containers, like forms or control groups.[Scroll views](/documentation/swiftui/scroll-views)Enable people to scroll to content that doesn’t fit in the current display.### [Event handling](/documentation/swiftui#Event-handling)

[Gestures](/documentation/swiftui/gestures)Define interactions from taps, clicks, and swipes to fine-grained gestures.[Input events](/documentation/swiftui/input-events)Respond to input from a hardware device, like a keyboard or a Touch Bar.[Clipboard](/documentation/swiftui/clipboard)Enable people to move or duplicate items by issuing Copy and Paste commands.[Drag and drop](/documentation/swiftui/drag-and-drop)Enable people to move or duplicate items by dragging them from one location to another.[Focus](/documentation/swiftui/focus)Identify and control which visible object responds to user interaction.[System events](/documentation/swiftui/system-events)React to system events, like opening a URL.### [Accessibility](/documentation/swiftui#Accessibility)

[Accessibility fundamentals](/documentation/swiftui/accessibility-fundamentals)Make your SwiftUI apps accessible to everyone, including people with disabilities.[Accessible appearance](/documentation/swiftui/accessible-appearance)Enhance the legibility of content in your app’s interface.[Accessible controls](/documentation/swiftui/accessible-controls)Improve access to actions that your app can undertake.[Accessible descriptions](/documentation/swiftui/accessible-descriptions)Describe interface elements to help people understand what they represent.[Accessible navigation](/documentation/swiftui/accessible-navigation)Enable users to navigate to specific user interface elements using rotors.### [Framework integration](/documentation/swiftui#Framework-integration)

[AppKit integration](/documentation/swiftui/appkit-integration)Add AppKit views to your SwiftUI app, or use SwiftUI views in your AppKit app.[UIKit integration](/documentation/swiftui/uikit-integration)Add UIKit views to your SwiftUI app, or use SwiftUI views in your UIKit app.[WatchKit integration](/documentation/swiftui/watchkit-integration)Add WatchKit views to your SwiftUI app, or use SwiftUI views in your WatchKit app.[Technology-specific views](/documentation/swiftui/technology-specific-views)Use SwiftUI views that other Apple frameworks provide.### [Tool support](/documentation/swiftui#Tool-support)

[Previews in Xcode](/documentation/swiftui/previews-in-xcode)Generate dynamic, interactive previews of your custom views.[Xcode library customization](/documentation/swiftui/xcode-library-customization)Expose custom views and modifiers in the Xcode library.[Performance analysis](/documentation/swiftui/performance-analysis)Measure and improve your app’s responsiveness.