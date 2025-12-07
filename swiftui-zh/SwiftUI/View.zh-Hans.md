--- 来源：https://developer.apple.com/documentation/SwiftUI/View 抓取时间：2025-12-02T16:01:53Z --- # View **Protocol** 视图类型，代表应用用户界面的一部分，并提供用于配置视图的修饰符。 ## 声明 ```swift
@MainActor @preconcurrency protocol View
``` ## 概述 您可以通过声明符合 `View` 协议的类型来创建自定义视图。实现所需的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 计算属性，以提供自定义视图的内容。 ```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
``` 通过将一个或多个 SwiftUI 提供的内置视图（例如上面示例中的 [Text](Text.zh-Hans.md) 实例）以及您定义的其他自定义视图组合成视图层次结构，来组装视图主体。有关创建自定义视图的更多信息，请参阅 [Declaring-a-Custom-View](Declaring-a-Custom-View.zh-Hans.md)。`View` 协议提供了一组修饰符（带有默认实现的协议方法），您可以使用这些修饰符来配置应用程序布局中的视图。修饰符的工作原理是将调用它们的视图实例包装在另一个具有指定特征的视图中，如 [Configuring-Views](Configuring-Views.zh-Hans.md) 中所述。例如，将 [opacity(_:)](View/opacity.zh-Hans.md) 修饰符添加到文本视图会返回一个具有一定透明度的新视图：```swift
Text("Hello, World!")
    .opacity(0.5) // Display partially transparent text.
```。完整的默认修饰符列表提供了用于管理视图的大量控件。例如，您可以微调 [View-Layout](View-Layout.zh-Hans.md)、添加 [View-Accessibility](View-Accessibility.zh-Hans.md) 信息以及响应 [View-Input-and-Events](View-Input-and-Events.zh-Hans.md)。您还可以将默认修饰符组收集到新的自定义视图修饰符中，以便轻松重用。如果类型在其原始声明中声明了符合性，则符合此协议的类型将继承协议的隔离性（`@preconcurrency @MainActor`）。默认情况下，隔离到主要参与者，但这不是必需的。在扩展中声明符合性即可选择退出隔离。## 实现自定义视图 - **body**：视图的内容和行为。 - **Body**：表示此视图主体的视图类型。 - **modifier(_:)**：将修饰符应用于视图并返回一个新视图。 - **在 Xcode 中预览**：生成自定义视图的动态交互式预览。## 配置视图元素 - **辅助功能修饰符**：使您的 SwiftUI 应用对所有人（包括残障人士）都可访问。 - **外观修饰符**：配置视图的前景色和背景样式、控件和可见性。- **文本和符号修饰符**：管理视图中文本的渲染、选择和输入。- **辅助视图修饰符**：添加和配置辅助视图，例如工具栏和上下文菜单。- **图表视图修饰符**：配置使用 Swift Charts 声明的图表。## 绘制视图 - **样式修饰符**：将内置样式应用于不同类型的视图。- **布局修饰符**：通过调整视图的大小、位置、对齐方式、内边距等，告诉视图如何在视图层次结构中排列自身。- **图形和渲染修饰符**：影响系统绘制视图的方式，例如缩放或遮罩视图，或应用图形效果。## 提供交互性 - **输入和事件修饰符**：为视图提供响应用户输入和系统事件的操作。 - **搜索修饰符**：允许用户在您的应用中搜索内容。- **呈现修饰符**：定义视图在特定条件下要呈现的附加视图。- **状态修饰符**：访问存储并为子视图提供配置数据。## 已弃用的修饰符 - **已弃用的修饰符**：查看不支持的修饰符及其替代项。## 实例方法 - **accessibilityActions(category:_:)**：为视图添加多个具有特定类别的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互，并按类别分组。当多个具有相同类别的操作修饰符应用于视图时，这些操作将合并在一起。- **accessibilityDefaultFocus(_:_:)**：定义一个区域，通过为给定的辅助功能焦点状态绑定赋值来评估默认的辅助功能焦点。 - **accessibilityScrollStatus(_:isEnabled:)**：更改用户在此视图内滚动浏览时辅助功能技术提供的提示信息。- **addOrderToWalletButtonStyle(_:)**：设置按钮样式。- **addPassToWalletButtonStyle(_:)**：设置按钮使用的样式（参见 `PKAddPassButtonStyle`）。- **allowsWindowActivationEvents()**：配置此视图层级结构中的手势，以处理激活包含窗口的事件。- **appStoreMerchandising(isPresented:kind:onDismiss:)** - **aspectRatio3D(_:contentMode:)**：将此视图的尺寸限制为指定的 3D 纵横比。- **assistiveAccessNavigationIcon(_:)**：配置视图的导航图标。- **assistiveAccessNavigationIcon(systemImage:)**：配置视图的导航图标。 - **attributedTextFormattingDefinition(_:)**：将文本格式定义应用于嵌套视图。- **automatedDeviceEnrollmentAddition(isPresented:)**：显示一个模态视图，使用户能够将设备添加到其组织中。- **backgroundExtensionEffect()**：为视图添加背景扩展效果。视图将被复制成镜像副本，并放置在视图周围任何具有可用安全区域的边缘。此外，还将应用模糊效果以模糊副本。- **backgroundExtensionEffect(isEnabled:)**：为视图添加背景扩展效果。视图将被复制成镜像副本，并放置在视图周围任何具有可用安全区域的边缘。此外，还将应用模糊效果以模糊副本。- **breakthroughEffect(_:)**：确保视图始终对用户可见，即使其他内容（例如 3D 模型）遮挡了视图。 - **buttonSizing(_:)**：视图层级结构中按钮的首选尺寸行为。- **certificateSheet(trust:title:message:help:)**：使用提供的证书信任显示证书页。- **chart3DCameraProjection(_:)** - **chart3DPose(_:)**：关联一个绑定，以便在交互改变 3D 图表姿态时更新。- **chart3DRenderingStyle(_:)** - **chartZAxis(_:)**：设置 Z 轴的可见性。- **chartZAxis(content:)**：配置视图中 3D 图表的 Z 轴。- **chartZAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 Z 轴标签。仅对 3D 图表有效。- **chartZScale(domain:range:type:)**：配置 3D 图表的 Z 轴刻度。 - **chartZScale(domain:type:)**：配置 3D 图表的 Z 轴比例。- **chartZScale(range:type:)**：配置 3D 图表的 Z 轴比例。- **chartZSelection(range:)** - **chartZSelection(value:)** - **contactAccessButtonCaption(_:)** - **contactAccessButtonStyle(_:)** - **contactAccessPicker(isPresented:completionHandler:)**：模态呈现的 UI，允许用户选择您的应用可以访问哪些联系人。- **containerCornerOffset(_:sizeToFit:)**：调整视图布局，以避免指定边缘的容器视图的角部内嵌。- **containerValue(_:_:)**：设置视图的特定容器值。 - **contentCaptureProtected(_:)** - **contentToolbar(for:content:)**：使用您提供的视图填充指定内容视图类型的工具栏。- **continuityDevicePicker(isPresented:onDidConnect:)**：应使用 `continuityDevicePicker` 通过按钮界面或其他激活方式发现并连接附近的连续互通设备。在 tvOS 上，选中后会显示全屏连续互通设备选择器。当满足给定条件时，模态视图会尽可能覆盖 `self` 的屏幕。- **controlWidgetActionHint(_:)**：修改标签所描述的控件的操作提示。- **controlWidgetStatus(_:)**：修改标签所描述的控件的状态。- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。 - **dialogPreventsAppTermination(_:)**：提示或确认对话框是否阻止系统或应用程序终止菜单项退出/终止应用程序。- **documentBrowserContextMenu(_:)**：向 `DocumentLaunchView` 操作添加接受所选文件列表作为参数的功能。- **dragConfiguration(_:)**：配置拖拽会话。- **dragContainer(for:in:_:)**：包含可拖拽视图的容器，其中拖拽有效负载基于拖拽项的多个标识符。- **dragContainer(for:itemID:in:_:)**：包含可拖拽视图的容器。- **dragContainerSelection(_:containerNamespace:)**：为拖拽容器提供多项选择支持。- **dragPreviewsFormation(_:)**：描述拖拽预览的视觉组成方式。 - **draggable(_:containerNamespace:_:)**：激活此视图作为拖放操作的源，允许提供可选的可识别有效负载，并指定此视图所属的拖放容器的命名空间。- **draggable(_:id:containerNamespace:_:)**：激活此视图作为拖放操作的源，允许提供可选的有效负载，并指定此视图所属的拖放容器的命名空间。- **draggable(_:id:item:containerNamespace:)**：激活此视图作为拖放操作的源，允许提供可选的有效负载，并指定此视图所属的拖放容器的命名空间。- **draggable(_:item:containerNamespace:)**：激活此视图作为拖放操作的源，允许提供可选的可识别有效负载，并指定此视图所属的拖放容器的命名空间。- **draggable(containerItemID:containerNamespace:)**：在拖放容器内，激活此视图作为拖放操作的源。支持延迟拖放容器。 - **dropConfiguration(_:)**：配置拖放会话。- **dropDestination(for:isEnabled:action:)**：定义拖放操作的目标位置，该操作提供拖放操作建议，并使用您指定的闭包处理拖放的内容。- **dropPreviewsFormation(_:)**：描述拖放预览的组成方式。- **familyActivityPicker(title:headerText:footerText:isPresented:selection:)**：显示一个活动选择器，用于选择要管理的应用和网站。- **formStyle(_:)**：设置视图层次结构中表单的样式。- **gameSaveSyncingAlert(directory:finishedLoading:)**：在游戏同步目录加载时显示模态视图。- **glassBackgroundEffect(_:displayMode:)**：使用自定义玻璃背景效果和相对于容器的圆角矩形填充视图的背景。 - **glassBackgroundEffect(_:in:displayMode:)**：使用您指定的自定义玻璃背景效果和形状填充视图的背景。- **glassEffect(_:in:)**：将“液态玻璃”效果应用于视图。- **glassEffectID(_:in:)**：将标识值与此视图中定义的“液态玻璃”效果关联。- **glassEffectTransition(_:)**：将玻璃效果过渡与此视图中定义的任何玻璃效果关联。- **glassEffectUnion(id:namespace:)**：将此视图中定义的任何“液态玻璃”效果与具有提供的标识符的联合体关联。- **groupActivityAssociation(_:)**：指定视图应如何与当前 SharePlay 群组活动关联。- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配手势快捷键。- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。 - **handlesGameControllerEvents(matching:)**：指定当视图或其子视图获得焦点时，应通过 GameController 框架传递的游戏控制器事件。- **handlesGameControllerEvents(matching:withOptions:)**：指定当视图或其子视图获得焦点时，应通过 GameController 框架传递的游戏控制器事件。- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**：异步请求读取需要按对象授权的数据类型（例如视力处方）的权限。- **healthDataAccessRequest(store:readTypes:trigger:completion:)**：请求读取指定的 HealthKit 数据类型的权限。- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**：请求保存和读取指定的 HealthKit 数据类型的权限。- **imagePlaygroundGenerationStyle(_:in:)**：设置图像 Playground 的生成样式。- **imagePlaygroundPersonalizationPolicy(_:)**：确定是否支持在 Playground 中使用人物的策略。 - **imagePlaygroundSheet(isPresented:concept:sourceImage:onCompletion:onCancellation:)**：显示系统表单，用于根据指定的输入创建图像。- **imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)**：显示系统表单，用于根据指定的输入创建图像。- **imagePlaygroundSheet(isPresented:concepts:sourceImage:onCompletion:onCancellation:)**：显示系统表单，用于根据指定的输入创建图像。- **imagePlaygroundSheet(isPresented:concepts:sourceImageURL:onCompletion:onCancellation:)**：显示系统表单，用于根据指定的输入创建图像。- **immersiveEnvironmentPicker(content:)**：添加菜单项，以便从媒体播放器的环境选择器打开沉浸式空间。- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从 StoreKit 视图发起购买之前调用该函数，并提供一组购买选项。- **journalingSuggestionsPicker(isPresented:journalingSuggestionToken:onCompletion:)**：显示一个可视化选择器界面，其中包含用户可以选择的事件和图像，以便检索更多信息。 - **journalingSuggestionsPicker(isPresented:onCompletion:)**：显示一个可视化选择器界面，其中包含用户可以选择以获取更多信息的事件和图像。- **labelIconToTitleSpacing(_:)**：设置标签中图标和标题之间的间距。- **labelReservedIconWidth(_:)**：设置标签中图标的宽度。- **labeledContentStyle(_:)**：设置标签内容的样式。- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。- **lineHeight(_:)**：视图层次结构中默认行高的修饰符。- **listRowInsets(_:_:)**：设置列表中指定边缘的行内边距。- **listSectionIndexVisibility(_:)**：更改列表部分索引的可见性。 - **listSectionMargins(_:_:)**：设置特定边的截面边距。- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)** - **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)** - **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)** - **managedContentStyle(_:)**：将托管内容样式应用于视图。- **manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)**：允许使用常用手势操作此视图。- **manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)**：将给定的 3D 仿射变换应用于视图，并允许使用常用手势操作它。- **manipulable(using:)**：允许使用附加到其他视图的操作手势来操作视图。- **manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)**：向此视图添加操作手势，但不允许此视图本身被操作。 - **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值发生变化时，使用指定的关键帧为 `Map` 的摄像机添加动画。- **mapControlVisibility(_:)**：配置环境中所有地图控件的可见性。- **mapControls(_:)**：配置关联环境中所有 `Map` 视图的控件大小和位置均采用标准设置。- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素的选择功能应被禁用。- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详细信息弹出窗口。 - **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出框。- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出框。- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出框。- **mapItemDetailSheet(isPresented:item:displaysMap:)**：显示地图项目详情表。- **mapItemDetailSheet(item:displaysMap:)**：显示地图项目详情表。- **mapScope(_:)**：创建 SwiftUI 用于将地图控件连接到关联地图的 mapScope。- **mapStyle(_:)**：指定要使用的地图样式。- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。 - **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。- **multilineTextAlignment(strategy:)**：用于修饰视图层级结构中默认文本对齐策略的参数。- **navigationLinkIndicatorVisibility(_:)**：配置导航链接是否显示展开指示器。- **navigationTransition(_:)**：设置该视图的导航过渡样式。- **onAppIntentExecution(_:perform:)**：注册一个处理程序，以便在应用接收到指定的应用意图时调用。- **onApplePayCouponCodeChange(perform:)**：当用户输入或更新优惠券代码时调用。如果要求用户提供优惠券代码，则此参数为必填项。- **onApplePayPaymentMethodChange(perform:)**：当支付方式更改并请求更新支付请求时调用。如果未提供此参数，Wallet 将假定支付方式有效。 - **onApplePayShippingContactChange(perform:)**：用户选择收货地址时调用。如果要求用户提供收货联系人，则此函数为必填项。- **onApplePayShippingMethodChange(perform:)**：用户选择配送方式时调用。如果要求用户提供配送方式，则此函数为必填项。- **onCameraCaptureEvent(isEnabled:defaultSoundDisabled:action:)**：用于注册由系统捕获事件触发的操作。- **onCameraCaptureEvent(isEnabled:defaultSoundDisabled:primaryAction:secondaryAction:)**：用于注册由系统捕获事件触发的操作。- **onDragSessionUpdated(_:)**：指定在由 `draggable(_:)` 或其他拖动修饰符激活的正在进行的拖动操作的每次更新时要执行的操作。- **onDropSessionUpdated(_:)**：指定在由 `dropDestination(_:)` 或其他放置修饰符激活的正在进行的放置操作的每次更新时要执行的操作。 - **onGeometryChange3D(for:of:action:)**：返回一个新视图，该视图会在 `transform(proxy)` 计算出的值发生变化时调用 `action(value)`，其中 `proxy` 提供对视图 3D 几何属性的访问。- **onInAppPurchaseCompletion(perform:)**：添加一个操作，当从此视图内的 StoreKit 视图发起的购买操作完成时执行。- **onInAppPurchaseStart(perform:)**：添加一个操作，当用户在此视图内的 StoreKit 视图上点击购买按钮时执行。- **onInteractiveResizeChange(_:)**：添加一个在交互式调整外层窗口大小时执行的操作。- **onMapCameraChange(frequency:_:)**：在地图相机取景框更改时执行操作。- **onOpenURL(prefersInApp:)**：设置一个 `OpenURLAction`，该属性优先使用应用内浏览器打开 URL。它等效于调用 `.onOpenURL(_:)`。- **onWorldRecenter(action:)**：添加一个在使用数码表冠重新定位视图时执行的操作。- **payLaterViewAction(_:)**：设置 PayLaterView 上的操作。请参阅 `PKPayLaterAction`。- **payLaterViewDisplayStyle(_:)**：设置 PayLaterView 上的显示样式。请参阅 `PKPayLaterDisplayStyle`。 - **payWithApplePayButtonDisableCardArt()**：设置允许在支付按钮上显示的功能。- **payWithApplePayButtonStyle(_:)**：设置按钮使用的样式。（参见 `PayWithApplePayButtonStyle`）。- **popoverTip(_:arrowEdge:action:)**：在修改后的视图中显示弹出提示。- **popoverTip(_:isPresented:attachmentAnchor:arrowEdge:action:)**：在修改后的视图中显示弹出提示。- **popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)**：在修改后的视图中显示弹出提示。- **postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)**：显示“添加到共享相册”表单，允许用户将指定项目发布到共享相册。- **preferredSubscriptionOffer(_:)**：选择要应用于客户从订阅商店视图、商店视图或产品视图进行的购买的订阅优惠。 - **preferredWindowClippingMargins(_:_:)**：请求在窗口边界之外绘制内容时增加边距。- **presentationBreakthroughEffect(_:)**：更改外层视图穿透遮挡内容的方式。- **presentationPreventsAppTermination(_:)**：视图是否阻止系统或应用终止菜单项终止/退出应用。- **productDescription(_:)**：配置视图中显示应用内购买产品描述的标签的可见性。- **productIconBorder()**：为应用内购买产品的图标添加标准边框。- **productViewStyle(_:)**：设置视图中应用内购买产品视图的样式。- **realityViewCameraControls(_:)**：添加控制虚拟相机位置和方向的手势。 - **realityViewLayoutBehavior(_:)**：用于控制 `RealityView` 的框架大小和内容对齐行为的视图修改器。 - **rotation3DLayout(_:)**：旋转视图，并对其包含布局中的框架产生影响。 - **rotation3DLayout(_:axis:)**：旋转视图，并对其包含布局中的框架产生影响。 - **safeAreaBar(edge:alignment:spacing:content:)**：将指定内容显示为修改后视图旁边的自定义栏。 - **scaledToFill3D()**：缩放此视图以填充其父视图。 - **scaledToFit3D()**：缩放此视图以适应其父视图。 - **scrollEdgeEffectHidden(_:for:)**：隐藏此层次结构中滚动视图的任何滚动边缘效果。 - **scrollEdgeEffectStyle(_:for:)**：配置此层次结构中滚动视图的滚动边缘效果样式。 - **scrollInputBehavior(_:for:)**：启用或禁用使用特定输入时可滚动视图中的滚动。- **searchSelection(_:)**：将与最近的可搜索修饰符关联的搜索字段的选择绑定到给定的 [TextSelection](TextSelection.zh-Hans.md) 值。- **searchToolbarBehavior(_:)**：配置工具栏中的搜索行为。- **sectionIndexLabel(_:)**：设置用于节索引的标签，使其指向此节，通常只有一个字符。- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。- **sliderThumbVisibility(_:)**：设置此视图中 `Slider` 的缩略图可见性。 - **spatialOverlay(alignment:content:)**：在此视图的 3D 边界内添加辅助视图。- **spatialOverlayPreferenceValue(_:alignment:_:)**：使用视图中指定的首选项值生成另一个视图，该视图占据与第一个视图相同的 3D 空间。- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品的集合，并返回修改后的视图。- **subscriptionIntroductoryOffer(applyOffer:compactJWS:)**：选择要应用于客户从订阅商店视图进行的购买的优惠资格首选项。 - **subscriptionOfferViewButtonVisibility(_:for:)** - **subscriptionOfferViewDetailAction(_:)** - **subscriptionOfferViewStyle(_:)** - **subscriptionPromotionalOffer(offer:compactJWS:)**：选择要应用于客户在订阅商店视图中购买商品的促销优惠。- **subscriptionPromotionalOffer(offer:signature:)**：选择要应用于客户在订阅商店视图中购买商品的促销优惠。- **subscriptionStatusTask(for:priority:action:)**：声明视图依赖于自动续订订阅组的状态，并返回修改后的视图。- **subscriptionStoreButtonLabel(_:)**：配置视图中的订阅商店视图实例以使用提供的按钮标签。- **subscriptionStoreControlBackground(_:)**：设置用于视图中订阅商店视图控件背景的标准效果。 - **subscriptionStoreControlIcon(icon:)**：设置用于装饰订阅商店视图中各个订阅选项的视图。- **subscriptionStoreControlStyle(_:)**：设置视图内订阅商店视图的控件样式。- **subscriptionStoreControlStyle(_:placement:)**：设置视图内订阅商店视图的控件样式和控件位置。- **subscriptionStoreOptionGroupStyle(_:)**：设置此视图内订阅商店视图用于显示订阅选项组的样式。- **subscriptionStorePickerItemBackground(_:)**：设置视图内订阅商店视图实例的选择器项的背景样式。- **subscriptionStorePickerItemBackground(_:in:)**：设置视图内订阅商店视图选择器项的背景形状和样式。- **subscriptionStorePolicyDestination(for:destination:)**：将视图配置为订阅商店视图中策略按钮操作的目标位置。 - **subscriptionStorePolicyDestination(url:for:)**：配置订阅商店视图中政策按钮操作的目标 URL。- **subscriptionStorePolicyForegroundStyle(_:)**：设置订阅商店视图中服务条款和隐私政策按钮的样式。- **subscriptionStorePolicyForegroundStyle(_:_:)**：设置订阅商店视图中服务条款和隐私政策按钮的主要样式和辅助样式。- **subscriptionStoreSignInAction(_:)**：添加用户在订阅商店视图中使用登录按钮时要执行的操作。- **symbolColorRenderingMode(_:)**：设置符号图像的颜色渲染模式。- **symbolVariableValueMode(_:)**：设置此视图中符号图像的可变值模式。- **tabBarMinimizeBehavior(_:)**：设置标签栏最小化的行为。 - **tabViewBottomAccessory(content:)**：将视图放置为标签页视图的底部附件。- **tabViewBottomAccessory(isEnabled:content:)**：将视图放置为标签页视图的底部附件。使用此修饰符可动态显示和隐藏附件视图。- **tabViewSearchActivation(_:)**：配置搜索标签页中搜索功能的激活和停用行为。- **tabletopGame(_:parent:automaticUpdate:)**：向视图添加桌面游戏。- **tabletopGame(_:parent:automaticUpdate:interaction:)**：提供一个闭包，以便在需要时返回新的交互。- **task(id:name:executorPreference:priority:file:line:_:)**：添加一个任务，在该视图显示之前或指定值更改时执行。- **textContentType(_:)**：设置此视图的文本内容类型，系统使用该类型在 macOS 上为用户输入文本提供建议。 - **textInputFormattingControlVisibility(_:for:)**：定义可用的系统文本格式控件。- **textRenderer(_:)**：返回一个新视图，其中的任何文本视图都将使用 `renderer` 来绘制自身。- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。- **tipAnchor(_:)**：设置指定提示锚点的值，用于将提示视图锚定到视图的 `.bounds` 处。- **tipBackground(_:)**：将提示视图的背景设置为某种样式。目前，这仅适用于内联提示，不适用于弹出式提示。- **tipBackgroundInteraction(_:)**：控制用户是否可以与已显示提示背后的视图进行交互。 - **tipCornerRadius(_:antialiased:)**：设置内联提示视图的圆角半径。- **tipImageSize(_:)**：设置提示图像的大小。- **tipImageStyle(_:)**：设置提示图像的样式。- **tipImageStyle(_:_:)**：设置提示图像的样式。- **tipImageStyle(_:_:_:)**：设置提示图像的样式。- **tipViewStyle(_:)**：设置视图层级结构中提示视图的样式。- **toolbarItemHidden(_:)**：隐藏控件组工具栏项中的单个视图。- **transactionPicker(isPresented:selection:)**：显示一个用于选择交易集合的选择器。 - **transactionTask(_:action:)**：提供在此视图显示前要执行的任务。- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**：当给定条件为真时，显示翻译弹出框。- **translationTask(_:action:)**：添加在此视图显示前或翻译配置更改时要执行的任务。- **translationTask(source:target:action:)**：添加在此视图显示前或指定的源语言或目标语言更改时要执行的任务。- **verifyIdentityWithWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKIdentityButtonStyle`）。- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。- **webViewContentBackground(_:)**：指定在此视图中网页自然背景色的可见性。 - **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。- **webViewLinkPreviews(_:)**：确定点击链接时是否显示链接目标位置的预览。- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的放大倍数。- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入时 WebView 中的滚动。- **webViewScrollPosition(_:)**：将滚动位置绑定到 WebView。 - **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本交互。- **windowResizeAnchor(_:)**：设置视图大小变化导致窗口必须调整大小时使用的窗口锚点。- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。- **workoutPreview(_:isPresented:)**：以模态窗口的形式显示训练内容预览。- **writingDirection(strategy:)**：视图层次结构中默认文本书写方向策略的修饰符。- **writingToolsAffordanceVisibility(_:)**：指定系统是否应为受环境影响的文本输入视图显示“书写工具”选项。- **writingToolsBehavior(_:)**：指定环境中文本和文本输入的“书写工具”行为。 ## 创建视图 - **声明自定义视图**：定义视图并将其组装成视图层次结构。 - **ViewBuilder**：一个自定义参数属性，用于从闭包构造视图。 ## 继承自 - DynamicViewContent - InsettableShape - NSViewControllerRepresentable - NSViewRepresentable - RoundedRectangularShape - Shape - ShapeView - UIViewControllerRepresentable - UIViewRepresentable - WKInterfaceObjectRepresentable ## 符合的类型 - AngularGradient - AnyShape - AnyView - AsyncImage - Button - ButtonBorderShape - ButtonStyleConfiguration.Label - Canvas - Capsule - Circle - Color - ColorPicker - ConcentricRectangle - ContainerRelativeShape - ContentUnavailableView - ControlGroup - ControlGroupStyleConfiguration.Content - ControlGroupStyleConfiguration.Label - DatePicker - DatePickerStyleConfiguration.Label - DebugReplaceableView - DefaultButtonLabel - DefaultDateProgressLabel - DefaultDocumentGroupLaunchActions - DefaultGlassEffectShape - DefaultSettingsLinkLabel -默认共享链接标签 - 默认选项卡标签 - 默认窗口可见性切换标签 - 披露组 - 披露组样式配置.内容 - 披露组样式配置.标签 - 分隔线 - 文档启动视图 - 编辑按钮 - 可编辑集合内容 - 椭圆 - 椭圆渐变 - 空视图 - 等距视图 - 填充形状视图 - 循环遍历 - 表单 - 表单样式配置.内容 - 仪表盘 - 仪表盘样式配置.当前值标签 - 仪表盘样式配置.标签 - 仪表盘样式配置.标记值标签 - 仪表盘样式配置.最大值标签 - 仪表盘样式配置.最小值标签 - 几何体读取器 - 3D几何体读取器 - 玻璃背景效果配置.内容 - 玻璃效果容器 - 网格 - 网格行 - 组 - 组框 - GroupBoxStyleConfiguration.Content - GroupBoxStyleConfiguration.Label - GroupElementsOfContent - GroupSectionsOfContent - HSplitView - HStack - HelpLink - Image - KeyframeAnimator - Label - LabelStyleConfiguration.Icon - LabelStyleConfiguration.Title - LabeledContent - LabeledContentStyleConfiguration.Content - LabeledContentStyleConfiguration.Label - LabeledControlGroupContent - LabeledToolbarItemGroupContent - LazyHGrid - LazyHStack - LazyVGrid - LazyVStack - LinearGradient - Link - List - Menu - MenuButton - MenuStyleConfiguration.Content - MenuStyleConfiguration.Label - MeshGradient - ModifiedContent - MultiDatePicker - NavigationLink - NavigationSplitView - NavigationStack - NavigationView - NewDocumentButton - OffsetShape - OutlineGroup - OutlineSubgroupChildren - PasteButton - Path - PhaseAnimator - Picker - PlaceholderContentView - PresentedWindowContent - PreviewModifierContent - PrimitiveButtonStyleConfiguration.Label - ProgressView - ProgressViewStyleConfiguration.CurrentValueLabel - ProgressViewStyleConfiguration.Label - RadialGradient - Rectangle - RenameButton - RotatedShape - RoundedRectangle - ScaledShape - ScrollView - ScrollViewReader - SearchUnavailableContent.Actions - SearchUnavailableContent.Description - SearchUnavailableContent.Label - Section - SectionConfiguration.Actions - SecureField - SettingsLink - ShareLink - Slider - Spacer - Stepper - StrokeBorderShapeView - StrokeShapeView - SubscriptionView - Subview - SubviewsCollection - SubviewsCollectionSlice - TabContentBuilder.Content - TabView - Table - Text - TextEditor - TextField - TextFieldLink - TimelineView - Toggle - ToggleStyleConfiguration.Label -变形形状 - 元组视图 - 不规则圆角矩形 - VSplitView - VStack - ViewThatFits - WindowVisibilityToggle - ZStack - ZStackContent3D

---
source: https://developer.apple.com/documentation/SwiftUI/View
crawled: 2025-12-02T16:01:53Z
---

# View

**Protocol**

A type that represents part of your app’s user interface and provides modifiers that you use to configure views.

## Declaration

```swift
@MainActor @preconcurrency protocol View
```

## Overview

You create custom views by declaring types that conform to the `View` protocol. Implement the required [body-8kl5o](View/body-8kl5o.zh-Hans.md) computed property to provide the content for your custom view.

```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
```

Assemble the view’s body by combining one or more of the built-in views provided by SwiftUI, like the [Text](Text.zh-Hans.md) instance in the example above, plus other custom views that you define, into a hierarchy of views. For more information about creating custom views, see [Declaring-a-Custom-View](Declaring-a-Custom-View.zh-Hans.md).

The `View` protocol provides a set of modifiers — protocol methods with default implementations — that you use to configure views in the layout of your app. Modifiers work by wrapping the view instance on which you call them in another view with the specified characteristics, as described in [Configuring-Views](Configuring-Views.zh-Hans.md). For example, adding the [opacity(_:)](View/opacity.zh-Hans.md) modifier to a text view returns a new view with some amount of transparency:

```swift
Text("Hello, World!")
    .opacity(0.5) // Display partially transparent text.
```

The complete list of default modifiers provides a large set of controls for managing views. For example, you can fine tune [View-Layout](View-Layout.zh-Hans.md), add [View-Accessibility](View-Accessibility.zh-Hans.md) information, and respond to [View-Input-and-Events](View-Input-and-Events.zh-Hans.md). You can also collect groups of default modifiers into new, custom view modifiers for easy reuse.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is declared in its original declaration. Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt-out the isolation.

## Implementing a custom view

- **body**: The content and behavior of the view.
- **Body**: The type of view representing the body of this view.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **Previews in Xcode**: Generate dynamic, interactive previews of your custom views.

## Configuring view elements

- **Accessibility modifiers**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Appearance modifiers**: Configure a view’s foreground and background styles, controls, and visibility.
- **Text and symbol modifiers**: Manage the rendering, selection, and entry of text in your view.
- **Auxiliary view modifiers**: Add and configure supporting views, like toolbars and context menus.
- **Chart view modifiers**: Configure charts that you declare with Swift Charts.

## Drawing views

- **Style modifiers**: Apply built-in styles to different types of views.
- **Layout modifiers**: Tell a view how to arrange itself within a view hierarchy by adjusting its size, position, alignment, padding, and so on.
- **Graphics and rendering modifiers**: Affect the way the system draws a view, for example by scaling or masking a view, or by applying graphical effects.

## Providing interactivity

- **Input and event modifiers**: Supply actions for a view to perform in response to user input and system events.
- **Search modifiers**: Enable people to search for content in your app.
- **Presentation modifiers**: Define additional views for the view to present under specified conditions.
- **State modifiers**: Access storage and provide child views with configuration data.

## Deprecated modifiers

- **Deprecated modifiers**: Review unsupported modifiers and their replacements.

## Instance Methods

- **accessibilityActions(category:_:)**: Adds multiple accessibility actions to the view with a specific category. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action and are grouped by their category. When multiple action modifiers with an equal category are applied to the view, the actions are combined together.
- **accessibilityDefaultFocus(_:_:)**: Defines a region in which default accessibility focus is evaluated by assigning a value to a given accessibility focus state binding.
- **accessibilityScrollStatus(_:isEnabled:)**: Changes the announcement provided by accessibility technologies when a user scrolls a scroll view within this view.
- **addOrderToWalletButtonStyle(_:)**: Sets the button’s style.
- **addPassToWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKAddPassButtonStyle`).
- **allowsWindowActivationEvents()**: Configures gestures in this view hierarchy to handle events that activate the containing window.
- **appStoreMerchandising(isPresented:kind:onDismiss:)**
- **aspectRatio3D(_:contentMode:)**: Constrains this view’s dimensions to the specified 3D aspect ratio.
- **assistiveAccessNavigationIcon(_:)**: Configures the view’s icon for purposes of navigation.
- **assistiveAccessNavigationIcon(systemImage:)**: Configures the view’s icon for purposes of navigation.
- **attributedTextFormattingDefinition(_:)**: Apply a text formatting definition to nested views.
- **automatedDeviceEnrollmentAddition(isPresented:)**: Presents a modal view that enables users to add devices to their organization.
- **backgroundExtensionEffect()**: Adds the background extension effect to the view. The view will be duplicated into mirrored copies which will be placed around the view on any edge with available safe area. Additionally, a blur effect will be applied on top to blur out the copies.
- **backgroundExtensionEffect(isEnabled:)**: Adds the background extension effect to the view. The view will be duplicated into mirrored copies which will be placed around the view on any edge with available safe area. Additionally, a blur effect will be applied on top to blur out the copies.
- **breakthroughEffect(_:)**: Ensures that the view is always visible to the user, even when other content is occluding it, like 3D models.
- **buttonSizing(_:)**: The preferred sizing behavior of buttons in the view hierarchy.
- **certificateSheet(trust:title:message:help:)**: Displays a certificate sheet using the provided certificate trust.
- **chart3DCameraProjection(_:)**
- **chart3DPose(_:)**: Associates a binding to be updated when the 3D chart’s pose is changed by an interaction.
- **chart3DRenderingStyle(_:)**
- **chartZAxis(_:)**: Sets the visibility of the z axis.
- **chartZAxis(content:)**: Configures the z-axis for 3D charts in the view.
- **chartZAxisLabel(_:position:alignment:spacing:)**: Adds z axis label for charts in the view. It effects 3D charts only.
- **chartZScale(domain:range:type:)**: Configures the z scale for 3D charts.
- **chartZScale(domain:type:)**: Configures the z scale for 3D charts.
- **chartZScale(range:type:)**: Configures the z scale for 3D charts.
- **chartZSelection(range:)**
- **chartZSelection(value:)**
- **contactAccessButtonCaption(_:)**
- **contactAccessButtonStyle(_:)**
- **contactAccessPicker(isPresented:completionHandler:)**: Modally present UI which allows the user to select which contacts your app has access to.
- **containerCornerOffset(_:sizeToFit:)**: Adjusts the view’s layout to avoid the container view’s corner insets for the specified edges.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **contentCaptureProtected(_:)**
- **contentToolbar(for:content:)**: Populates the toolbar of the specified content view type with the views you provide.
- **continuityDevicePicker(isPresented:onDidConnect:)**: A `continuityDevicePicker` should be used to discover and connect nearby continuity device through a button interface or other form of activation. On tvOS, this presents a fullscreen continuity device picker experience when selected. The modal view covers as much the screen of `self` as possible when a given condition is true.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.
- **currentEntitlementTask(for:priority:action:)**: Declares the view as dependent on the entitlement of an In-App Purchase product, and returns a modified view.
- **dialogPreventsAppTermination(_:)**: Whether the alert or confirmation dialog prevents the app from being quit/terminated by the system or app termination menu item.
- **documentBrowserContextMenu(_:)**: Adds to a `DocumentLaunchView` actions that accept a list of selected files as their parameter.
- **dragConfiguration(_:)**: Configures a drag session.
- **dragContainer(for:in:_:)**: A container with draggable views where the drag payload is based on multiple identifiers of dragged items.
- **dragContainer(for:itemID:in:_:)**: A container with draggable views.
- **dragContainerSelection(_:containerNamespace:)**: Provides multiple item selection support for drag containers.
- **dragPreviewsFormation(_:)**: Describes the way dragged previews are visually composed.
- **draggable(_:containerNamespace:_:)**: Activates this view as the source of a drag and drop operation, allowing to provide optional identifiable payload and specify the namespace of the drag container this view belongs to.
- **draggable(_:id:containerNamespace:_:)**: Activates this view as the source of a drag and drop operation, allowing to provide optional payload and specify the namespace of the drag container this view belongs to.
- **draggable(_:id:item:containerNamespace:)**: Activates this view as the source of a drag and drop operation, allowing to provide optional payload and specify the namespace of the drag container this view belongs to.
- **draggable(_:item:containerNamespace:)**: Activates this view as the source of a drag and drop operation, allowing to provide optional identifiable payload and specify the namespace of the drag container this view belongs to.
- **draggable(containerItemID:containerNamespace:)**: Inside a drag container, activates this view as the source of a drag and drop operation. Supports lazy drag containers.
- **dropConfiguration(_:)**: Configures a drop session.
- **dropDestination(for:isEnabled:action:)**: Defines the destination of a drag and drop operation that provides a drop operation proposal and handles the dropped content with a closure that you specify.
- **dropPreviewsFormation(_:)**: Describes the way previews for a drop are composed.
- **familyActivityPicker(title:headerText:footerText:isPresented:selection:)**: Present an activity picker sheet for selecting apps and websites to manage.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **gameSaveSyncingAlert(directory:finishedLoading:)**: Presents a modal view while the game synced directory loads.
- **glassBackgroundEffect(_:displayMode:)**: Fills the view’s background with a custom glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(_:in:displayMode:)**: Fills the view’s background with a custom glass background effect and a shape that you specify.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **glassEffectID(_:in:)**: Associates an identity value to Liquid Glass effects defined within this view.
- **glassEffectTransition(_:)**: Associates a glass effect transition with any glass effects defined within this view.
- **glassEffectUnion(id:namespace:)**: Associates any Liquid Glass effects defined within this view to a union with the provided identifier.
- **groupActivityAssociation(_:)**: Specifies how a view should be associated with the current SharePlay group activity.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **handlesGameControllerEvents(matching:)**: Specifies the game controllers events which should be delivered through the GameController framework when the view, or one of its descendants has focus.
- **handlesGameControllerEvents(matching:withOptions:)**: Specifies the game controllers events which should be delivered through the GameController framework when the view or one of its descendants has focus.
- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**: Asynchronously requests permission to read a data type that requires per-object authorization (such as vision prescriptions).
- **healthDataAccessRequest(store:readTypes:trigger:completion:)**: Requests permission to read the specified HealthKit data types.
- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**: Requests permission to save and read the specified HealthKit data types.
- **imagePlaygroundGenerationStyle(_:in:)**: Sets the generation style for an image playground.
- **imagePlaygroundPersonalizationPolicy(_:)**: Policy determining whether to support the usage of people in the playground or not.
- **imagePlaygroundSheet(isPresented:concept:sourceImage:onCompletion:onCancellation:)**: Presents the system sheet to create images from the specified input.
- **imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)**: Presents the system sheet to create images from the specified input.
- **imagePlaygroundSheet(isPresented:concepts:sourceImage:onCompletion:onCancellation:)**: Presents the system sheet to create images from the specified input.
- **imagePlaygroundSheet(isPresented:concepts:sourceImageURL:onCompletion:onCancellation:)**: Presents the system sheet to create images from the specified input.
- **immersiveEnvironmentPicker(content:)**: Add menu items to open immersive spaces from a media player’s environment picker.
- **inAppPurchaseOptions(_:)**: Add a function to call before initiating a purchase from StoreKit view within this view, providing a set of options for the purchase.
- **journalingSuggestionsPicker(isPresented:journalingSuggestionToken:onCompletion:)**: Presents a visual picker interface that contains events and images that a person can select to retrieve more information.
- **journalingSuggestionsPicker(isPresented:onCompletion:)**: Presents a visual picker interface that contains events and images that a person can select to retrieve more information.
- **labelIconToTitleSpacing(_:)**: Set the spacing between the icon and title in labels.
- **labelReservedIconWidth(_:)**: Set the width reserved for icons in labels.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **lineHeight(_:)**: A modifier for the default line height in the view hierarchy.
- **listRowInsets(_:_:)**: Sets the insets of rows in a list on the specified edges.
- **listSectionIndexVisibility(_:)**: Changes the visibility of the list section index.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**
- **managedContentStyle(_:)**: Applies a managed content style to the view.
- **manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)**: Allows this view to be manipulated using common hand gestures.
- **manipulable(transform:coordinateSpace:operations:inertia:isEnabled:onChanged:)**: Applies the given 3D affine transform to the view and allows it to be manipulated using common hand gestures.
- **manipulable(using:)**: Allows the view to be manipulated using a manipulation gesture attached to a different view.
- **manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)**: Adds a manipulation gesture to this view without allowing this view to be manipulable itself.
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **mapControlVisibility(_:)**: Configures all Map controls in the environment to have the specified visibility
- **mapControls(_:)**: Configures all `Map` views in the associated environment to have standard size and position controls
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapFeatureSelectionContent(content:)**: Specifies a custom presentation for the currently selected feature.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailSheet(isPresented:item:displaysMap:)**: Presents a map item detail sheet.
- **mapItemDetailSheet(item:displaysMap:)**: Presents a map item detail sheet.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapStyle(_:)**: Specifies the map style to be used.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **multilineTextAlignment(strategy:)**: A modifier for the default text alignment strategy in the view hierarchy.
- **navigationLinkIndicatorVisibility(_:)**: Configures whether navigation links show a disclosure indicator.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **onAppIntentExecution(_:perform:)**: Registers a handler to invoke in response to the specified app intent that your app receives.
- **onApplePayCouponCodeChange(perform:)**: Called when a user has entered or updated a coupon code. This is required if the user is being asked to provide a coupon code.
- **onApplePayPaymentMethodChange(perform:)**: Called when a payment method has changed and asks for an update payment request. If this modifier isn’t provided Wallet will assume the payment method is valid.
- **onApplePayShippingContactChange(perform:)**: Called when a user selected a shipping address. This is required if the user is being asked to provide a shipping contact.
- **onApplePayShippingMethodChange(perform:)**: Called when a user selected a shipping method. This is required if the user is being asked to provide a shipping method.
- **onCameraCaptureEvent(isEnabled:defaultSoundDisabled:action:)**: Used to register an action triggered by system capture events.
- **onCameraCaptureEvent(isEnabled:defaultSoundDisabled:primaryAction:secondaryAction:)**: Used to register actions triggered by system capture events.
- **onDragSessionUpdated(_:)**: Specifies an action to perform on each update of an ongoing dragging operation activated by `draggable(_:)` or anther drag modifiers.
- **onDropSessionUpdated(_:)**: Specifies an action to perform on each update of an ongoing drop operation activated by `dropDestination(_:)` or other drop modifiers.
- **onGeometryChange3D(for:of:action:)**: Returns a new view that arranges to call `action(value)` whenever the value computed by `transform(proxy)` changes, where `proxy` provides access to the view’s 3D geometry properties.
- **onInAppPurchaseCompletion(perform:)**: Add an action to perform when a purchase initiated from a StoreKit view within this view completes.
- **onInAppPurchaseStart(perform:)**: Add an action to perform when a user triggers the purchase button on a StoreKit view within this view.
- **onInteractiveResizeChange(_:)**: Adds an action to perform when the enclosing window is being interactively resized.
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **onOpenURL(prefersInApp:)**: Sets an `OpenURLAction` that prefers opening URL with an in-app browser. It’s equivalent to calling `.onOpenURL(_:)`
- **onWorldRecenter(action:)**: Adds an action to perform when recentering the view with the digital crown.
- **payLaterViewAction(_:)**: Sets the action on the PayLaterView. See `PKPayLaterAction`.
- **payLaterViewDisplayStyle(_:)**: Sets the display style on the PayLaterView. See `PKPayLaterDisplayStyle`.
- **payWithApplePayButtonDisableCardArt()**: Sets the features that should be allowed to show on the payment buttons.
- **payWithApplePayButtonStyle(_:)**: Sets the style to be used by the button. (see `PayWithApplePayButtonStyle`).
- **popoverTip(_:arrowEdge:action:)**: Presents a popover tip on the modified view.
- **popoverTip(_:isPresented:attachmentAnchor:arrowEdge:action:)**: Presents a popover tip on the modified view.
- **popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)**: Presents a popover tip on the modified view.
- **postToPhotosSharedAlbumSheet(isPresented:items:photoLibrary:defaultAlbumIdentifier:completion:)**: Presents an “Add to Shared Album” sheet that allows the user to post the given items to a shared album.
- **preferredSubscriptionOffer(_:)**: Selects a subscription offer to apply to a purchase that a customer makes from a subscription store view, a store view, or a product view.
- **preferredWindowClippingMargins(_:_:)**: Requests additional margins for drawing beyond the bounds of the window.
- **presentationBreakthroughEffect(_:)**: Changes the way the enclosing presentation breaks through content occluding it.
- **presentationPreventsAppTermination(_:)**: Whether a presentation prevents the app from being terminated/quit by the system or app termination menu item.
- **productDescription(_:)**: Configure the visibility of labels displaying an in-app purchase product description within the view.
- **productIconBorder()**: Adds a standard border to an in-app purchase product’s icon .
- **productViewStyle(_:)**: Sets the style for In-App Purchase product views within a view.
- **realityViewCameraControls(_:)**: Adds gestures that control the position and direction of a virtual camera.
- **realityViewLayoutBehavior(_:)**: A view modifier that controls the frame sizing and content alignment behavior for `RealityView`
- **rotation3DLayout(_:)**: Rotates a view with impacts to its frame in a containing layout
- **rotation3DLayout(_:axis:)**: Rotates a view with impacts to its frame in a containing layout
- **safeAreaBar(edge:alignment:spacing:content:)**: Shows the specified content as a custom bar beside the modified view.
- **scaledToFill3D()**: Scales this view to fill its parent.
- **scaledToFit3D()**: Scales this view to fit its parent.
- **scrollEdgeEffectHidden(_:for:)**: Hides any scroll edge effects for scroll views within this hierarchy.
- **scrollEdgeEffectStyle(_:for:)**: Configures the scroll edge effect style for scroll views within this hierarchy.
- **scrollInputBehavior(_:for:)**: Enables or disables scrolling in scrollable views when using particular inputs.
- **searchSelection(_:)**: Binds the selection of the search field associated with the nearest searchable modifier to the given [TextSelection](TextSelection.zh-Hans.md) value.
- **searchToolbarBehavior(_:)**: Configures the behavior for search in the toolbar.
- **sectionIndexLabel(_:)**: Sets the label that is used in a section index to point to this section, typically only a single character long.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).
- **sliderThumbVisibility(_:)**: Sets the thumb visibility for `Slider`s within this view.
- **spatialOverlay(alignment:content:)**: Adds secondary views within the 3D bounds of this view.
- **spatialOverlayPreferenceValue(_:alignment:_:)**: Uses the specified preference value from the view to produce another view occupying the same 3D space of the first view.
- **storeButton(_:for:)**: Specifies the visibility of auxiliary buttons that store view and subscription store view instances may use.
- **storeProductTask(for:priority:action:)**: Declares the view as dependent on an In-App Purchase product and returns a modified view.
- **storeProductsTask(for:priority:action:)**: Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.
- **subscriptionIntroductoryOffer(applyOffer:compactJWS:)**: Selects the introductory offer eligibility preference to apply to a purchase a customer makes from a subscription store view.
- **subscriptionOfferViewButtonVisibility(_:for:)**
- **subscriptionOfferViewDetailAction(_:)**
- **subscriptionOfferViewStyle(_:)**
- **subscriptionPromotionalOffer(offer:compactJWS:)**: Selects a promotional offer to apply to a purchase a customer makes from a subscription store view.
- **subscriptionPromotionalOffer(offer:signature:)**: Selects a promotional offer to apply to a purchase a customer makes from a subscription store view.
- **subscriptionStatusTask(for:priority:action:)**: Declares the view as dependent on the status of an auto-renewable subscription group, and returns a modified view.
- **subscriptionStoreButtonLabel(_:)**: Configures subscription store view instances within a view to use the provided button label.
- **subscriptionStoreControlBackground(_:)**: Set a standard effect to use for the background of subscription store view controls within the view.
- **subscriptionStoreControlIcon(icon:)**: Sets a view to use to decorate individual subscription options within a subscription store view.
- **subscriptionStoreControlStyle(_:)**: Sets the control style for subscription store views within a view.
- **subscriptionStoreControlStyle(_:placement:)**: Sets the control style and control placement for subscription store views within a view.
- **subscriptionStoreOptionGroupStyle(_:)**: Sets the style subscription store views within this view use to display groups of subscription options.
- **subscriptionStorePickerItemBackground(_:)**: Sets the background style for picker items of the subscription store view instances within a view.
- **subscriptionStorePickerItemBackground(_:in:)**: Sets the background shape and style for subscription store view picker items within a view.
- **subscriptionStorePolicyDestination(for:destination:)**: Configures a view as the destination for a policy button action in subscription store views.
- **subscriptionStorePolicyDestination(url:for:)**: Configures a URL as the destination for a policy button action in subscription store views.
- **subscriptionStorePolicyForegroundStyle(_:)**: Sets the style for the terms of service and privacy policy buttons within a subscription store view.
- **subscriptionStorePolicyForegroundStyle(_:_:)**: Sets the primary and secondary style for the terms of service and privacy policy buttons within a subscription store view.
- **subscriptionStoreSignInAction(_:)**: Adds an action to perform when a person uses the sign-in button on a subscription store view within a view.
- **symbolColorRenderingMode(_:)**: Sets the color rendering mode for symbol images.
- **symbolVariableValueMode(_:)**: Sets the variable value mode mode for symbol images within this view.
- **tabBarMinimizeBehavior(_:)**: Sets the behavior for tab bar minimization.
- **tabViewBottomAccessory(content:)**: Places a view as the bottom accessory of the tab view.
- **tabViewBottomAccessory(isEnabled:content:)**: Places a view as the bottom accessory of the tab view. Use this modifier to dynamically show and hide the accessory view.
- **tabViewSearchActivation(_:)**: Configures the activation and deactivation behavior of search in the search tab.
- **tabletopGame(_:parent:automaticUpdate:)**: Adds a tabletop game to a view.
- **tabletopGame(_:parent:automaticUpdate:interaction:)**: Supplies a closure which returns a new interaction whenever needed.
- **task(id:name:executorPreference:priority:file:line:_:)**: Adds a task to perform before this view appears or when a specified value changes.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textInputFormattingControlVisibility(_:for:)**: Define which system text formatting controls are available.
- **textRenderer(_:)**: Returns a new view such that any text views within it will use `renderer` to draw themselves.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **tipAnchor(_:)**: Sets a value for the specified tip anchor to be used to anchor a tip view to the `.bounds` of the view.
- **tipBackground(_:)**: Sets the tip’s view background to a style. Currently this only applies to inline tips, not popover tips.
- **tipBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presented tip.
- **tipCornerRadius(_:antialiased:)**: Sets the corner radius for an inline tip view.
- **tipImageSize(_:)**: Sets the size for a tip’s image.
- **tipImageStyle(_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:_:)**: Sets the style for a tip’s image.
- **tipViewStyle(_:)**: Sets the given style for TipView within the view hierarchy.
- **toolbarItemHidden(_:)**: Hides an individual view within a control group toolbar item.
- **transactionPicker(isPresented:selection:)**: Presents a picker that selects a collection of transactions.
- **transactionTask(_:action:)**: Provides a task to perform before this view appears
- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**: Presents a translation popover when a given condition is true.
- **translationTask(_:action:)**: Adds a task to perform before this view appears or when the translation configuration changes.
- **translationTask(source:target:action:)**: Adds a task to perform before this view appears or when the specified source or target languages change.
- **verifyIdentityWithWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKIdentityButtonStyle`).
- **webViewBackForwardNavigationGestures(_:)**: Determines whether horizontal swipe gestures trigger backward and forward page navigation.
- **webViewContentBackground(_:)**: Specifies the visibility of the webpage’s natural background color within this view.
- **webViewContextMenu(menu:)**: Adds an item-based context menu to a WebView, replacing the default set of context menu items.
- **webViewElementFullscreenBehavior(_:)**: Determines whether a web view can display content full screen.
- **webViewLinkPreviews(_:)**: Determines whether pressing a link displays a preview of the destination for the link.
- **webViewMagnificationGestures(_:)**: Determines whether magnify gestures change the view’s magnification.
- **webViewOnScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.
- **windowResizeAnchor(_:)**: Sets the window anchor point used when the size of the view changes such that the window must resize.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **workoutPreview(_:isPresented:)**: Presents a preview of the workout contents as a modal sheet
- **writingDirection(strategy:)**: A modifier for the default text writing direction strategy in the view hierarchy.
- **writingToolsAffordanceVisibility(_:)**: Specifies whether the system should show the Writing Tools affordance for text input views affected by the environment.
- **writingToolsBehavior(_:)**: Specifies the Writing Tools behavior for text and text input in the environment.

## Creating a view

- **Declaring a custom view**: Define views and assemble them into a view hierarchy.
- **ViewBuilder**: A custom parameter attribute that constructs views from closures.

## Inherited By

- DynamicViewContent
- InsettableShape
- NSViewControllerRepresentable
- NSViewRepresentable
- RoundedRectangularShape
- Shape
- ShapeView
- UIViewControllerRepresentable
- UIViewRepresentable
- WKInterfaceObjectRepresentable

## Conforming Types

- AngularGradient
- AnyShape
- AnyView
- AsyncImage
- Button
- ButtonBorderShape
- ButtonStyleConfiguration.Label
- Canvas
- Capsule
- Circle
- Color
- ColorPicker
- ConcentricRectangle
- ContainerRelativeShape
- ContentUnavailableView
- ControlGroup
- ControlGroupStyleConfiguration.Content
- ControlGroupStyleConfiguration.Label
- DatePicker
- DatePickerStyleConfiguration.Label
- DebugReplaceableView
- DefaultButtonLabel
- DefaultDateProgressLabel
- DefaultDocumentGroupLaunchActions
- DefaultGlassEffectShape
- DefaultSettingsLinkLabel
- DefaultShareLinkLabel
- DefaultTabLabel
- DefaultWindowVisibilityToggleLabel
- DisclosureGroup
- DisclosureGroupStyleConfiguration.Content
- DisclosureGroupStyleConfiguration.Label
- Divider
- DocumentLaunchView
- EditButton
- EditableCollectionContent
- Ellipse
- EllipticalGradient
- EmptyView
- EquatableView
- FillShapeView
- ForEach
- Form
- FormStyleConfiguration.Content
- Gauge
- GaugeStyleConfiguration.CurrentValueLabel
- GaugeStyleConfiguration.Label
- GaugeStyleConfiguration.MarkedValueLabel
- GaugeStyleConfiguration.MaximumValueLabel
- GaugeStyleConfiguration.MinimumValueLabel
- GeometryReader
- GeometryReader3D
- GlassBackgroundEffectConfiguration.Content
- GlassEffectContainer
- Grid
- GridRow
- Group
- GroupBox
- GroupBoxStyleConfiguration.Content
- GroupBoxStyleConfiguration.Label
- GroupElementsOfContent
- GroupSectionsOfContent
- HSplitView
- HStack
- HelpLink
- Image
- KeyframeAnimator
- Label
- LabelStyleConfiguration.Icon
- LabelStyleConfiguration.Title
- LabeledContent
- LabeledContentStyleConfiguration.Content
- LabeledContentStyleConfiguration.Label
- LabeledControlGroupContent
- LabeledToolbarItemGroupContent
- LazyHGrid
- LazyHStack
- LazyVGrid
- LazyVStack
- LinearGradient
- Link
- List
- Menu
- MenuButton
- MenuStyleConfiguration.Content
- MenuStyleConfiguration.Label
- MeshGradient
- ModifiedContent
- MultiDatePicker
- NavigationLink
- NavigationSplitView
- NavigationStack
- NavigationView
- NewDocumentButton
- OffsetShape
- OutlineGroup
- OutlineSubgroupChildren
- PasteButton
- Path
- PhaseAnimator
- Picker
- PlaceholderContentView
- PresentedWindowContent
- PreviewModifierContent
- PrimitiveButtonStyleConfiguration.Label
- ProgressView
- ProgressViewStyleConfiguration.CurrentValueLabel
- ProgressViewStyleConfiguration.Label
- RadialGradient
- Rectangle
- RenameButton
- RotatedShape
- RoundedRectangle
- ScaledShape
- ScrollView
- ScrollViewReader
- SearchUnavailableContent.Actions
- SearchUnavailableContent.Description
- SearchUnavailableContent.Label
- Section
- SectionConfiguration.Actions
- SecureField
- SettingsLink
- ShareLink
- Slider
- Spacer
- Stepper
- StrokeBorderShapeView
- StrokeShapeView
- SubscriptionView
- Subview
- SubviewsCollection
- SubviewsCollectionSlice
- TabContentBuilder.Content
- TabView
- Table
- Text
- TextEditor
- TextField
- TextFieldLink
- TimelineView
- Toggle
- ToggleStyleConfiguration.Label
- TransformedShape
- TupleView
- UnevenRoundedRectangle
- VSplitView
- VStack
- ViewThatFits
- WindowVisibilityToggle
- ZStack
- ZStackContent3D

