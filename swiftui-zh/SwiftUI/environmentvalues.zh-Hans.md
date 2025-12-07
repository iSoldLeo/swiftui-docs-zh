--- 来源：https://developer.apple.com/documentation/swiftui/environmentvalues 抓取时间：2025-12-02T17:53:23Z --- # EnvironmentValues **Structure** 在视图层级结构中传播的环境值集合。 ## 声明 ```swift
struct EnvironmentValues
``` ## 概述 SwiftUI 以 `EnvironmentValues` 结构的形式向应用程序的视图公开一组值。要从结构中读取值，请使用 [Environment](Environment.zh-Hans.md) 属性包装器声明属性并指定值的键路径。例如，您可以读取当前区域设置： ```swift
@Environment(\.locale) var locale: Locale
``` 使用您声明的属性来动态控制视图的布局。 SwiftUI 会根据设备特性、系统状态或用户设置自动设置或更新许多环境变量值，例如 [pixelLength](EnvironmentValues/pixelLength.zh-Hans.md)、[scenePhase](EnvironmentValues/scenePhase.zh-Hans.md) 或 [locale](EnvironmentValues/locale.zh-Hans.md)。对于其他一些变量值，例如 [lineLimit](EnvironmentValues/lineLimit.zh-Hans.md)，SwiftUI 会提供一个合理的默认值。您可以使用视图修饰符 [environment(_:_:)](View/environment.zh-Hans.md) 来设置或覆盖某些值：```swift
MyView()
    .environment(\.lineLimit, 2)
```。您设置的值会影响您正在修改的视图的环境变量（包括其在视图层次结构中的子视图），但仅限于您应用其他环境修饰符之前。SwiftUI 提供了专用的视图修饰符来设置某些值，这通常可以使您的代码更易于阅读。例如，与其像前面的例子那样直接设置 [lineLimit](EnvironmentValues/lineLimit.zh-Hans.md) 值，不如使用 [lineLimit(_:)](View/lineLimit.zh-Hans.md) 修改器：```swift
MyView()
    .lineLimit(2)
``` 在某些情况下，使用专用视图修改器可以提供额外的功能。例如，您必须使用 [preferredColorScheme(_:)](View/preferredColorScheme.zh-Hans.md) 修饰符，而不是直接设置 [colorScheme](EnvironmentValues/colorScheme.zh-Hans.md)，以确保在显示弹出框等视图时，新值能够传递到呈现容器：```swift
MyView()
    .popover(isPresented: $isPopped) {
        PopoverContent()
            .preferredColorScheme(.dark)
    }
``` 通过在环境值结构的扩展中声明一个新属性，并将 [Entry()](Entry.zh-Hans.md) 宏应用于变量声明，来创建自定义环境值：```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
}

extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
``` 然后，值的客户端可以像往常一样访问该值，使用 [Environment](Environment.zh-Hans.md) 属性包装器读取它，并使用 `myCustomValue` 视图修饰符设置它。## 创建和访问值 - **init()**：创建环境值实例。 - **subscript(_:)**：访问与自定义键关联的环境值。 - **description**：表示环境值实例内容的字符串。## 辅助功能 - **accessibilityAssistiveAccessEnabled**：指示辅助功能是否正在使用的布尔值。- **accessibilityDimFlashingLights**：是否启用了减少视频内容中闪烁或频闪灯光的设置。此设置还可用于确定是否应在播放控件中显示 UI 以指示即将播放的内容包含闪烁或频闪灯光。- **accessibilityDifferentiateWithoutColor**：是否启用了“不使用颜色区分”的系统首选项。- **accessibilityEnabled**：指示用户是否已启用辅助技术的布尔值。- **accessibilityInvertColors**：是否启用了“反转颜色”的系统首选项。- **accessibilityLargeContentViewerEnabled**：是否启用了“大内容查看器”。 - **accessibilityPlayAnimatedImages**：是否启用“在动画图像中播放动画”设置。如果此值为 false，则任何包含动画的图像都不会自动播放。- **accessibilityPrefersHeadAnchorAlternative**：是否启用“优先显示头部锚定内容的替代方案”系统设置。- **accessibilityQuickActionsEnabled**：一个布尔值，指示是否启用了快速操作功能。- **accessibilityReduceMotion**：是否启用了“减少动态效果”系统首选项。- **accessibilityReduceTransparency**：是否启用了“降低透明度”系统首选项。- **accessibilityShowButtonShapes**：是否启用了“显示按钮形状”系统首选项。- **accessibilitySwitchControlEnabled**：一个布尔值，指示是否正在使用“开关控制”电机辅助功能。 - **accessibilityVoiceOverEnabled**：一个布尔值，指示是否正在使用 VoiceOver 屏幕阅读器。- **legibilityWeight**：要应用于文本的字体粗细。## 操作 - **dismiss**：关闭当前演示的操作。- **dismissSearch**：结束当前搜索交互的操作。- **dismissWindow**：存储在视图环境中的窗口关闭操作。- **openImmersiveSpace**：呈现沉浸式空间的操作。- **dismissImmersiveSpace**：存储在视图环境中的沉浸式空间关闭操作。- **newDocument**：环境中呈现新文档的操作。- **openDocument**：环境中呈现现有文档的操作。 - **openURL**：打开 URL 的操作。- **openWindow**：存储在视图环境中的窗口呈现操作。- **pushWindow**：存储在视图环境中的窗口呈现操作。- **purchase**：启动应用内购买的操作。- **refresh**：存储在视图环境中的刷新操作。- **rename**：激活标准重命名交互的操作。- **resetFocus**：请求焦点系统重新评估默认焦点的操作。- **openSettings**：存储在视图环境中的设置呈现操作。 ## 身份验证 - **authorizationController**：SwiftUI 环境中提供的值，视图可以使用该值执行授权请求。 - **webAuthenticationSession**：SwiftUI 环境中提供的值，视图可以使用该值通过 Web 服务验证用户身份。 ## 控件和输入 - **buttonRepeatBehavior**：与此环境关联的按钮是否应在长时间交互时重复触发其操作。 - **controlSize**：应用于视图中控件的大小。 - **defaultWheelPickerItemHeight**：滚轮式选择器（例如日期选择器）中项目的默认高度。 - **keyboardShortcut**：用于触发此环境中按钮的键盘快捷键。 - **menuIndicatorVisibility**：应用于视图中控件的菜单指示器可见性。 - **menuOrder**：此视图中菜单项的首选顺序。- **searchSuggestionsPlacement**：搜索建议的当前位置。- **preferredPencilDoubleTapAction**：用户在“设置”应用中选择的双击 Apple Pencil 后首选执行的操作。- **preferredPencilSqueezeAction**：用户在“设置”应用中选择的挤压 Apple Pencil 后首选执行的操作。## 显示特性 - **appearsActive**：此环境中的视图和样式是否应优先显示活动状态而非非活动状态。- **colorScheme**：此环境的配色方案。- **colorSchemeContrast**：与此环境配色方案关联的对比度。- **displayScale**：此环境的显示比例。 - **horizontalSizeClass**：此环境的水平尺寸类别。- **imageScale**：此环境的图像缩放比例。- **pixelLength**：屏幕上像素的大小。- **sidebarRowSize**：侧边栏行的当前大小。- **verticalSizeClass**：此环境的垂直尺寸类别。- **immersiveSpaceDisplacement**：系统将沉浸式空间从其默认位置移动时施加的位移量（以米为单位）。- **labelsVisibility**：由 [labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md) 设置的标签可见性。- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。 - **TabBarPlacement**：选项卡视图中选项卡的位置。- **toolbarLabelStyle**：应用于工具栏中控件的标签样式。## 全局对象 - **calendar**：视图处理日期时应使用的当前日历。- **documentConfiguration**：文档在 [DocumentGroup](DocumentGroup.zh-Hans.md) 中的配置。- **locale**：视图应使用的当前区域设置。- **managedObjectContext** - **modelContext**：将用于此环境中的查询和其他模型操作的 SwiftData 模型上下文。- **timeZone**：视图处理日期时应使用的当前时区。 - **undoManager**：用于注册视图撤销操作的撤销管理器。## 滚动 - **isScrollEnabled**：一个布尔值，指示与此环境关联的任何滚动视图是否允许滚动。- **horizontalScrollIndicatorVisibility**：应用于任何水平可滚动内容的滚动指示器的可见性。- **verticalScrollIndicatorVisibility**：应用于任何垂直可滚动内容的滚动指示器的可见性。- **scrollDismissesKeyboardMode**：可滚动内容与软件键盘的交互方式。- **horizontalScrollBounceBehavior**：可滚动视图水平轴的滚动回弹模式。- **verticalScrollBounceBehavior**：可滚动视图垂直轴的滚动回弹模式。 ## 状态 - **editMode**：指示用户是否可以编辑与此环境关联的视图的内容。 - **isActivityFullscreen**：布尔值，指示实时活动是否以全屏显示。 - **isEnabled**：布尔值，指示与此环境关联的视图是否允许用户交互。 - **isFocused**：返回最近的可聚焦祖先是否具有焦点。 - **isFocusEffectEnabled**：布尔值，指示与此环境关联的视图是否允许显示焦点效果。 - **isHoverEffectEnabled**：布尔值，指示与此环境关联的视图是否允许显示悬停效果。 - **isLuminanceReduced**：布尔值，指示显示器或环境当前是否需要降低亮度。 - **isPresented**：一个布尔值，指示当前是否显示与此环境关联的视图。- **isSceneCaptured**：当前捕获状态。- **isSearching**：一个布尔值，指示用户何时进行搜索。- **isTabBarShowingSections**：一个布尔值，确定选项卡视图是否显示选项卡部分的展开内容。- **scenePhase**：场景的当前阶段。- **supportsMultipleWindows**：一个布尔值，指示当前平台是否支持打开多个窗口。## StoreKit 配置 - **displayStoreKitMessage** - **requestReview** ## 文本样式 - **allowsTightening**：一个布尔值，指示是否应缩小字符间距以适应可用空间。 - **autocorrectionDisabled**：一个布尔值，用于确定视图层次结构是否启用自动更正。- **dynamicTypeSize**：当前动态字体大小。- **font**：此环境的默认字体。- **layoutDirection**：与当前环境关联的布局方向。- **lineLimit**：文本在视图中可以占据的最大行数。- **lineSpacing**：一行文本底部与下一行文本顶部之间的距离（以磅为单位）。- **minimumScaleFactor**：为使文本适应可用空间而缩小字体大小的最小允许比例。- **multilineTextAlignment**：一个环境值，指示文本视图在内容换行或包含换行符时如何对齐其行。 - **textCase**：用于在显示时根据环境的区域设置更改 `Text` 的大小写样式。- **truncationMode**：指示布局如何截断文本最后一行以适应可用空间的值。- **textSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联。当处理双向文本（包含从左到右和从右到左脚本的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。## 视图属性 - **allowedDynamicRange**：视图允许的动态范围，或为 nil。- **backgroundMaterial**：当前视图下方的材质。- **backgroundProminence**：与此环境关联的视图下方背景的突出显示程度。 - **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。- **badgeProminence**：应用于与此环境关联的徽章的突出显示级别。- **contentTransition**：视图内容动画的当前方法。- **contentTransitionAddsDrawingGroup**：布尔值，控制渲染内容过渡的视图是否使用 GPU 加速渲染。- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。- **defaultMinListRowHeight**：列表中行的默认最小高度。- **headerProminence**：应用于视图中节标题的突出显示级别。- **physicalMetrics**：与场景关联的物理度量。 - **realityKitScene** - **realityViewCameraControls**：现实视图的相机控制。 - **redactionReasons**：当前应用于视图层级的编辑原因。 - **springLoadingBehavior**：与此环境关联的视图的弹簧加载交互行为。 - **symbolRenderingMode**：当前符号渲染模式，或 `nil` 表示使用当前图像和前景样式作为参数自动选择模式。 - **symbolVariants**：此环境中要使用的符号变体。 - **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。 ## 小部件 - **showsWidgetContainerBackground**：指示小部件背景是否显示的环境变量。 - **showsWidgetLabel**：一个布尔值，指示配件系列控件是否可以显示配件标签。- **widgetFamily**：控件的模板——小、中或大。- **widgetRenderingMode**：控件的渲染模式，取决于系统显示控件的位置。- **widgetContentMargins**：一个属性，用于标识控件的内容边距。## 已弃用的环境值 - **disableAutocorrection**：一个布尔值，用于确定视图层次结构是否启用了自动更正。- **sizeCategory**：内容的大小。- **presentationMode**：绑定到与此环境关联的视图的当前呈现模式。- **PresentationMode**：指示视图当前是否由另一个视图呈现。 - **complicationRenderingMode**：当前环境的复杂渲染模式。- **controlActiveState**：窗口中控件的预期活动外观。## 实例属性 - **accessibilityShowBorders**：是否启用“显示边框”系统偏好设置。在 macOS 上，启用“增强对比度”时，此值为真。- **activityFamily**：当前 Live Activity 的尺寸系列。- **buttonSizing**：视图层级结构中按钮的首选尺寸行为。- **credentialDataManager**：此环境变量适用于 ASCredentialDataManager API 的 SwiftUI 客户端。例如：- **credentialExportManager**：此环境变量适用于凭据交换 API 的 SwiftUI 客户端。示例用法如下： - **credentialImportManager**：此环境变量用于凭据交换 API 的 SwiftUI 客户端。示例用法如下： - **devicePickerSupports**：检查是否支持显示 DevicePicker。 - **findContext** - **fontResolutionContext**：用于解析字体的信息。 - **imagePlaygroundAllowedGenerationStyles** - **imagePlaygroundPersonalizationPolicy** - **imagePlaygroundSelectedGenerationStyle** - **isActivityUpdateReduced**：一个布尔值，指示是否降低了实时活动更新同步速率。 - **isUserAuthenticationEnabled**：当前系统用户身份验证启用状态。 - **labelIconToTitleSpacing**：标签图标和标题之间的间距。 - **labelReservedIconWidth**：标签中图标的保留宽度。- **levelOfDetail**：建议的视图详细程度。- **lineHeight**：受此环境影响的文本的默认行高。- **navigationLinkIndicatorVisibility**：一个值，指示内置导航链接在当前上下文中是否显示展开指示器。- **remoteDeviceIdentifier**：一个不透明对象，用于标识呈现场景（从中访问此值）的设备。- **requestAgeRange**：一个环境值，提供用于请求年龄范围的平台配置操作。- **supportedActivityFamilies**：一个环境值，指示实时活动的潜在渲染家庭。- **supportsImagePlayground**：一个布尔值，指示当前设备是否支持图像生成。 - **supportsRemoteScenes**：指示当前设备是否支持在远程设备上显示 [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md)。- **surfaceSnappingInfo**：提供有关场景当前捕捉状态的信息。- **symbolColorRenderingMode**：指定符号图像如何填充其图层的属性，如果为 nil 则使用默认填充样式。- **symbolVariableValueMode**：当前符号变量值模式，如果为 `nil` 则表示模式自动选择。- **tabBarPlacement**：选项卡栏的当前位置。- **tabViewBottomAccessoryPlacement**：选项卡视图底部附件的当前位置。- **windowClippingMargins** - **writingToolsBehavior**：文本和文本输入的当前书写工具行为。 ## 访问环境变量- **Environment**：一个属性包装器，用于从视图的环境中读取值。## 符合 CustomStringConvertible 协议

---
source: https://developer.apple.com/documentation/swiftui/environmentvalues
crawled: 2025-12-02T17:53:23Z
---

# EnvironmentValues

**Structure**

A collection of environment values propagated through a view hierarchy.

## Declaration

```swift
struct EnvironmentValues
```

## Overview

SwiftUI exposes a collection of values to your app’s views in an `EnvironmentValues` structure. To read a value from the structure, declare a property using the [Environment](Environment.zh-Hans.md) property wrapper and specify the value’s key path. For example, you can read the current locale:

```swift
@Environment(\.locale) var locale: Locale
```

Use the property you declare to dynamically control a view’s layout. SwiftUI automatically sets or updates many environment values, like [pixelLength](EnvironmentValues/pixelLength.zh-Hans.md), [scenePhase](EnvironmentValues/scenePhase.zh-Hans.md), or [locale](EnvironmentValues/locale.zh-Hans.md), based on device characteristics, system state, or user settings. For others, like [lineLimit](EnvironmentValues/lineLimit.zh-Hans.md), SwiftUI provides a reasonable default value.

You can set or override some values using the [environment(_:_:)](View/environment.zh-Hans.md) view modifier:

```swift
MyView()
    .environment(\.lineLimit, 2)
```

The value that you set affects the environment for the view that you modify — including its descendants in the view hierarchy — but only up to the point where you apply a different environment modifier.

SwiftUI provides dedicated view modifiers for setting some values, which typically makes your code easier to read. For example, rather than setting the [lineLimit](EnvironmentValues/lineLimit.zh-Hans.md) value directly, as in the previous example, you should instead use the [lineLimit(_:)](View/lineLimit.zh-Hans.md) modifier:

```swift
MyView()
    .lineLimit(2)
```

In some cases, using a dedicated view modifier provides additional functionality. For example, you must use the [preferredColorScheme(_:)](View/preferredColorScheme.zh-Hans.md) modifier rather than setting [colorScheme](EnvironmentValues/colorScheme.zh-Hans.md) directly to ensure that the new value propagates up to the presenting container when presenting a view like a popover:

```swift
MyView()
    .popover(isPresented: $isPopped) {
        PopoverContent()
            .preferredColorScheme(.dark)
    }
```

Create a custom environment value by declaring a new property in an extension to the environment values structure and applying the [Entry()](Entry.zh-Hans.md) macro to the variable declaration:

```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
}

extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
```

Clients of your value then access the value in the usual way, reading it with the [Environment](Environment.zh-Hans.md) property wrapper, and setting it with the `myCustomValue` view modifier.

## Creating and accessing values

- **init()**: Creates an environment values instance.
- **subscript(_:)**: Accesses the environment value associated with a custom key.
- **description**: A string that represents the contents of the environment values instance.

## Accessibility

- **accessibilityAssistiveAccessEnabled**: A Boolean value that indicates whether Assistive Access is in use.
- **accessibilityDimFlashingLights**: Whether the setting to reduce flashing or strobing lights in video content is on. This setting can also be used to determine if UI in playback controls should be shown to indicate upcoming content that includes flashing or strobing lights.
- **accessibilityDifferentiateWithoutColor**: Whether the system preference for Differentiate without Color is enabled.
- **accessibilityEnabled**: A Boolean value that indicates whether the user has enabled an assistive technology.
- **accessibilityInvertColors**: Whether the system preference for Invert Colors is enabled.
- **accessibilityLargeContentViewerEnabled**: Whether the Large Content Viewer is enabled.
- **accessibilityPlayAnimatedImages**: Whether the setting for playing animations in an animated image is on. When this value is false, any presented image that contains animation should not play automatically.
- **accessibilityPrefersHeadAnchorAlternative**: Whether the system setting to prefer alternatives to head-anchored content is on.
- **accessibilityQuickActionsEnabled**: A Boolean that indicates whether the quick actions feature is enabled.
- **accessibilityReduceMotion**: Whether the system preference for Reduce Motion is enabled.
- **accessibilityReduceTransparency**: Whether the system preference for Reduce Transparency is enabled.
- **accessibilityShowButtonShapes**: Whether the system preference for Show Button Shapes is enabled.
- **accessibilitySwitchControlEnabled**: A Boolean value that indicates whether the Switch Control motor accessibility feature is in use.
- **accessibilityVoiceOverEnabled**: A Boolean value that indicates whether the VoiceOver screen reader is in use.
- **legibilityWeight**: The font weight to apply to text.

## Actions

- **dismiss**: An action that dismisses the current presentation.
- **dismissSearch**: An action that ends the current search interaction.
- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **openImmersiveSpace**: An action that presents an immersive space.
- **dismissImmersiveSpace**: An immersive space dismissal action stored in a view’s environment.
- **newDocument**: An action in the environment that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **openURL**: An action that opens a URL.
- **openWindow**: A window presentation action stored in a view’s environment.
- **pushWindow**: A window presentation action stored in a view’s environment.
- **purchase**: An action that starts an in-app purchase.
- **refresh**: A refresh action stored in a view’s environment.
- **rename**: An action that activates the standard rename interaction.
- **resetFocus**: An action that requests the focus system to reevaluate default focus.
- **openSettings**: A Settings presentation action stored in a view’s environment.

## Authentication

- **authorizationController**: A value provided in the SwiftUI environment that views can use to perform authorization requests.
- **webAuthenticationSession**: A value provided in the SwiftUI environment that views can use to authenticate a user through a web service.

## Controls and input

- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **controlSize**: The size to apply to controls within a view.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **menuIndicatorVisibility**: The menu indicator visibility to apply to controls within a view.
- **menuOrder**: The preferred order of items for menus presented from this view.
- **searchSuggestionsPlacement**: The current placement of search suggestions.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.

## Display characteristics

- **appearsActive**: Whether views and styles in this environment should prefer an active appearance over an inactive appearance.
- **colorScheme**: The color scheme of this environment.
- **colorSchemeContrast**: The contrast associated with the color scheme of this environment.
- **displayScale**: The display scale of this environment.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **imageScale**: The image scale for this environment.
- **pixelLength**: The size of a pixel on the screen.
- **sidebarRowSize**: The current size of sidebar rows.
- **verticalSizeClass**: The vertical size class of this environment.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md).
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.

## Global objects

- **calendar**: The current calendar that views should use when handling dates.
- **documentConfiguration**: The configuration of a document in a [DocumentGroup](DocumentGroup.zh-Hans.md).
- **locale**: The current locale that views should use.
- **managedObjectContext**
- **modelContext**: The SwiftData model context that will be used for queries and other model operations within this environment.
- **timeZone**: The current time zone that views should use when handling dates.
- **undoManager**: The undo manager used to register a view’s undo operations.

## Scrolling

- **isScrollEnabled**: A Boolean value that indicates whether any scroll views associated with this environment allow scrolling to occur.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.
- **scrollDismissesKeyboardMode**: The way that scrollable content interacts with the software keyboard.
- **horizontalScrollBounceBehavior**: The scroll bounce mode for the horizontal axis of scrollable views.
- **verticalScrollBounceBehavior**: The scroll bounce mode for the vertical axis of scrollable views.

## State

- **editMode**: An indication of whether the user can edit the contents of a view associated with this environment.
- **isActivityFullscreen**: A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.
- **isEnabled**: A Boolean value that indicates whether the view associated with this environment allows user interaction.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **isFocusEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows focus effects to be displayed.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **isLuminanceReduced**: A Boolean value that indicates whether the display or environment currently requires reduced luminance.
- **isPresented**: A Boolean value that indicates whether the view associated with this environment is currently presented.
- **isSceneCaptured**: The current capture state.
- **isSearching**: A Boolean value that indicates when the user is searching.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **scenePhase**: The current phase of the scene.
- **supportsMultipleWindows**: A Boolean value that indicates whether the current platform supports opening multiple windows.

## StoreKit configuration

- **displayStoreKitMessage**
- **requestReview**

## Text styles

- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **dynamicTypeSize**: The current Dynamic Type size.
- **font**: The default font of this environment.
- **layoutDirection**: The layout direction associated with the current environment.
- **lineLimit**: The maximum number of lines that text can occupy in a view.
- **lineSpacing**: The distance in points between the bottom of one line fragment and the top of the next.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **multilineTextAlignment**: An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).

## View attributes

- **allowedDynamicRange**: The allowed dynamic range for the view, or nil.
- **backgroundMaterial**: The material underneath the current view.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **badgeProminence**: The prominence to apply to badges associated with this environment.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **headerProminence**: The prominence to apply to section headers within a view.
- **physicalMetrics**: The physical metrics associated with a scene.
- **realityKitScene**
- **realityViewCameraControls**: The camera controls for the reality view.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **springLoadingBehavior**: The behavior of spring loaded interactions for the views associated with this environment.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **symbolVariants**: The symbol variant to use in this environment.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.

## Widgets

- **showsWidgetContainerBackground**: An environment variable that indicates whether the background of a widget appears.
- **showsWidgetLabel**: A Boolean value that indicates whether an accessory family widget can display an accessory label.
- **widgetFamily**: The template of the widget — small, medium, or large.
- **widgetRenderingMode**: The widget’s rendering mode, based on where the system is displaying it.
- **widgetContentMargins**: A property that identifies the content margins of a widget.

## Deprecated environment values

- **disableAutocorrection**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **sizeCategory**: The size of content.
- **presentationMode**: A binding to the current presentation mode of the view associated with this environment.
- **PresentationMode**: An indication whether a view is currently presented by another view.
- **complicationRenderingMode**: The complication rendering mode for the current environment.
- **controlActiveState**: The active appearance expected of controls in a window.

## Instance Properties

- **accessibilityShowBorders**: Whether the system preference for Show Borders is enabled. On macOS this is true when Increased Contrast is enabled.
- **activityFamily**: The size family of the current Live Activity.
- **buttonSizing**: The preferred sizing behavior of buttons in the view hierarchy.
- **credentialDataManager**: This environment variable is for SwiftUI clients of the ASCredentialDataManager API. An example usage might look like:
- **credentialExportManager**: This environment variable is for SwiftUI clients of the credential exchange API. An example usage might look like:
- **credentialImportManager**: This environment variable is for SwiftUI clients of the credential exchange API. An example usage might look like:
- **devicePickerSupports**: Checks for support to present a DevicePicker.
- **findContext**
- **fontResolutionContext**: Information used to resolve a font.
- **imagePlaygroundAllowedGenerationStyles**
- **imagePlaygroundPersonalizationPolicy**
- **imagePlaygroundSelectedGenerationStyle**
- **isActivityUpdateReduced**: A Boolean value that indicates whether the Live Activity update synchronization rate is reduced.
- **isUserAuthenticationEnabled**: The current system user authentication enablement status.
- **labelIconToTitleSpacing**: The spacing between the icon and title of a label.
- **labelReservedIconWidth**: The width reserved for icons in labels.
- **levelOfDetail**: The level of detail the view is recommended to have.
- **lineHeight**: The default line height for text influenced by this environment.
- **navigationLinkIndicatorVisibility**: A value that says whether a built-in navigation link would show a disclosure indicator in the current context.
- **remoteDeviceIdentifier**: An opaque object that identifies the device on which the scene (from which this value is accessed from) is being presented on.
- **requestAgeRange**: An environment value that provides a platform configured action for requesting age ranges.
- **supportedActivityFamilies**: An environment value that that indicates potential rendered family for a Live Activity.
- **supportsImagePlayground**: A Boolean value that indicates whether image generation is available on the current device.
- **supportsRemoteScenes**: Indicates if the current device supports presenting a [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md) on a remote device.
- **surfaceSnappingInfo**: Provides information about the current snap state of the scene.
- **symbolColorRenderingMode**: The property specifying how symbol images fill their layers, or nil to use the default fill style.
- **symbolVariableValueMode**: The current symbol variable value mode, or `nil` denoting that the mode is picked automatically.
- **tabBarPlacement**: The current placement of the tab bar.
- **tabViewBottomAccessoryPlacement**: The current placement of the tab view bottom accessory.
- **windowClippingMargins**
- **writingToolsBehavior**: The current Writing Tools behavior for text and text input.

## Accessing environment values

- **Environment**: A property wrapper that reads a value from a view’s environment.

## Conforms To

- CustomStringConvertible

