---

来源：https://developer.apple.com/documentation/SwiftUI/Technology-specific-views

抓取时间：2025-12-02T17:44:50Z

---

# 技术特定视图

**API 集合**

使用其他 Apple 框架提供的 SwiftUI 视图。

## 概述

要访问其他框架定义的 SwiftUI 视图，请将 SwiftUI 和其他框架导入到使用该视图的文件中。您可以通过查看视图文档页面上的可用性信息来找到要导入的框架。

例如，要在您的应用中使用 [doc://com.apple.documentation/documentation/MapKit/Map] 视图，请同时导入 SwiftUI 和 MapKit。

```swift
import SwiftUI
import MapKit

struct MyMapView: View {
    // Center the map on Joshua Tree National Park.
    var region = MKCoordinateRegion(
            center: CLLocationCoordinate2D(latitude: 34.011_286, longitude: -116.166_868),
            span: MKCoordinateSpan(latitudeDelta: 0.2, longitudeDelta: 0.2)
        )

    var body: some View {
        Map(initialPosition: .region(region))
    }
}
```

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/technologies]。

## 显示网页内容

- **WebView**：用于显示网页内容的视图。

- **WebPage**：用于控制和管理交互式网页内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定网页自然背景色在此视图中的可见性。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接是否显示链接目标页面的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否会改变视图的放大倍数。

- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入时网页视图中的滚动功能。

- **webViewScrollPosition(_:)**：将网页视图的滚动位置绑定到相应的控件。

- **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本交互。

## 访问 Apple Pay 和钱包

- **PayWithApplePayButton**：提供一个按钮，用于使用 Apple Pay 付款。

- **AddPassToWalletButton**：提供一个按钮，允许用户将新的或现有的通行证添加到 Apple Wallet。

- **VerifyIdentityWithWalletButton**：用于显示身份验证流程按钮的类型。

- **addOrderToWalletButtonStyle(_:)**：设置按钮的样式。

- **addPassToWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKAddPassButtonStyle`）。

- **onApplePayCouponCodeChange(perform:)**：当用户输入或更新优惠券代码时调用。如果要求用户提供优惠券代码，则此参数为必填项。

- **onApplePayPaymentMethodChange(perform:)**：当付款方式更改并要求更新付款请求时调用。如果未提供此参数，Wallet 将假定付款方式有效。

- **onApplePayShippingContactChange(perform:)**：当用户选择收货地址时调用。如果要求用户提供收货联系人，则此参数为必填项。

- **onApplePayShippingMethodChange(perform:)**：当用户选择配送方式时调用。如果系统要求用户提供配送方式，则此函数为必填项。

- **payLaterViewAction(_:)**：设置“稍后付款”视图的操作。参见 `PKPayLaterAction`。

- **payLaterViewDisplayStyle(_:)**：设置“稍后付款”视图的显示样式。参见 `PKPayLaterDisplayStyle`。

- **payWithApplePayButtonStyle(_:)**：设置按钮使用的样式。（参见 `PayWithApplePayButtonStyle`）

- **verifyIdentityWithWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKIdentityButtonStyle`）

- **AsyncShareablePassConfiguration**

- **transactionTask(_:action:)**：提供在此视图显示之前要执行的任务

## 授权和身份验证

- **LocalAuthenticationView**：显示身份验证界面的 SwiftUI 视图。

- **SignInWithAppleButton**：创建“使用 Apple 登录”按钮以供显示的 SwiftUI 视图。

- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。

- **authorizationController**：SwiftUI 环境中提供的值，视图可以使用该值来执行授权请求。

- **webAuthenticationSession**：SwiftUI 环境中提供的值，视图可以使用该值通过 Web 服务对用户进行身份验证。

## 配置家庭共享

- **FamilyActivityPicker**：用户可在视图中指定应用程序、网站域和类别，而无需向应用程序透露其选择。

- **familyActivityPicker(isPresented:selection:)**：以工作表的形式呈现活动选择器视图。

- **familyActivityPicker(headerText:footerText:isPresented:selection:)**：以工作表的形式呈现活动选择器视图。

## 设备活动报告

- **DeviceActivityReport**：以保护隐私的方式报告用户的应用程序、类别和网站域活动。

## 使用受管设备

- **managedContentStyle(_:)**：为视图应用受管内容样式。

- **automatedDeviceEnrollmentAddition(isPresented:)**：呈现模态视图，使用户能够将设备添加到其组织。

## 创建图形

- **Chart**：用于显示图表的 SwiftUI 视图。

- **SceneView**：用于显示 3D SceneKit 内容的 SwiftUI 视图。

- **SpriteView**：用于渲染 SpriteKit 场景的 SwiftUI 视图。

## 获取位置信息

- **LocationButton**：用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：用于显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 mapScope，SwiftUI 使用该 mapScope 将地图控件连接到关联的地图。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。

- **mapControls(_:)**：将关联环境中所有 `Map` 视图配置为具有标准大小和位置控件。

- **mapControlVisibility(_:)**：将环境中所有地图控件配置为具有指定的可见性。

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值发生变化时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：当地图相机取景框发生变化时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口

- **mapItemDetailSheet(isPresented:item:displaysMap:)**：显示地图项目详情页

- **mapItemDetailSheet(item:displaysMap:)**：显示地图项目详情页

## 显示媒体

- **CameraView**：一个用于渲染视频流或图像快照的 SwiftUI 视图。

- **NowPlayingView**：一个用于显示系统“正在播放”界面的视图，以便用户可以控制音频。

- **VideoPlayer**：一个用于显示播放器内容和用于控制播放的原生用户界面的视图。

- **continuityDevicePicker(isPresented:onDidConnect:)**：`continuityDevicePicker` 用于通过按钮界面或其他激活方式发现并连接附近的连续互通设备。在 tvOS 上，选中后会显示一个全屏的连续互通设备选择器。当满足特定条件时，模态视图会尽可能覆盖 `self` 的屏幕。

- **cameraAnchor(isActive:)**：指定用作 Apple Vision Pro 2D Persona 流虚拟摄像机的视图。

## 选择照片

- **PhotosPicker**：显示照片选择器，用于从照片库中选择素材的视图。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定的照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定照片库中选择一组照片。

- **photosPickerAccessoryVisibility(_:edges:)**：设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

- **photosPickerDisabledCapabilities(_:)**：禁用照片选择器的功能。

- **photosPickerStyle(_:)**：设置照片选择器的模式。

## 预览内容

- **quickLookPreview(_:)**：显示单个 URL 内容的快速预览。

- **quickLookPreview(_:in:)**：显示您提供的 URL 的快速预览。

## 与联网设备交互

- **DevicePicker**：一个 SwiftUI 视图，用于显示网络上的其他设备，并与运行在该设备上的应用副本建立加密连接。

- **devicePickerSupports**：检查是否支持显示设备选择器 (DevicePicker)。

## 配置 Live Activity

- **activitySystemActionForegroundColor(_:)**：系统在锁屏界面 Live Activity 旁边显示的辅助操作按钮的文本颜色。

- **activityBackgroundTint(_:)**：设置显示在锁屏界面上的 Live Activity 的背景色调。

- **isActivityFullscreen**：一个布尔值，指示 Live Activity 是否以全屏模式显示。

- **activityFamily**：当前 Live Activity 的尺寸范围。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：在此视图中，添加一个在从 StoreKit 视图发起购买之前调用的函数，提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，当从此视图中的 StoreKit 视图发起的购买完成时执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，当用户在此视图中的 StoreKit 视图上点击购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图中应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图中显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品的集合，并返回修改后的视图。

- **subscriptionStatusTask(for:priority:action:)**：声明视图依赖于自动续订订阅组的状态，并返回修改后的视图。

- **subscriptionStoreButtonLabel(_:)**：配置视图内的订阅商店视图实例以使用提供的按钮标签。

- **subscriptionStoreControlIcon(icon:)**：设置用于装饰订阅商店视图中各个订阅选项的视图。

- **subscriptionStoreControlStyle(_:)**：设置视图内订阅商店视图的控件样式。

- **subscriptionStoreControlStyle(_:placement:)**：设置视图内订阅商店视图的控件样式和控件位置。

- **subscriptionStoreOptionGroupStyle(_:)**：设置此视图内订阅商店视图用于显示订阅选项组的样式。

- **subscriptionStorePickerItemBackground(_:)**：设置视图内订阅商店视图实例的选择器项的背景样式。

- **subscriptionStorePickerItemBackground(_:in:)**：设置视图内订阅商店视图选择器项的背景形状和样式。

- **subscriptionStorePolicyDestination(for:destination:)**：将视图配置为订阅商店视图中策略按钮操作的目标位置。

- **subscriptionStorePolicyDestination(url:for:)**：将 URL 配置为订阅商店视图中策略按钮操作的目标位置。

- **subscriptionStorePolicyForegroundStyle(_:)**：设置订阅商店视图中服务条款和隐私政策按钮的样式。

- **subscriptionStorePolicyForegroundStyle(_:_:)**：设置订阅商店视图中服务条款和隐私政策按钮的主要样式和辅助样式。

- **subscriptionStoreSignInAction(_:)**：添加用户在视图内的订阅商店视图中使用登录按钮时要执行的操作。

- **subscriptionStoreControlBackground(_:)**：设置视图内订阅商店视图控件背景的标准效果。

- **subscriptionPromotionalOffer(offer:signature:)**：选择要应用于客户在订阅商店视图中购买商品的促销优惠。

- **preferredSubscriptionOffer(_:)**：选择要应用于客户在订阅商店视图、商店视图或产品视图中购买商品的订阅优惠。

## 访问健康数据

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**：异步请求读取需要逐对象授权的数据类型（例如视力处方）的权限。

- **healthDataAccessRequest(store:readTypes:trigger:completion:)**：请求读取指定 HealthKit 数据类型的权限。

- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**：请求保存和读取指定 HealthKit 数据类型的权限。

- **workoutPreview(_:isPresented:)**：以模态窗口的形式显示锻炼内容预览。

## 提供提示

- **popoverTip(_:arrowEdge:action:)**：在修改后的视图中显示弹出提示。

- **tipBackground(_:)**：设置提示视图的背景样式。目前仅适用于内联提示，不适用于弹出提示。

- **tipCornerRadius(_:antialiased:)**：设置内联提示视图的圆角半径。

- **tipImageSize(_:)**：设置提示图片的尺寸。

- **tipViewStyle(_:)**：设置提示视图在视图层级结构中的样式。

- **tipImageStyle(_:)**：设置提示图片的样式。

- **tipImageStyle(_:_:)**：设置提示图片的样式。

- **tipImageStyle(_:_:_:)**：设置提示图片的样式。

## 显示翻译

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**：当满足特定条件时，显示翻译弹出窗口。

- **translationTask(_:action:)**：添加一个任务，在该视图显示之前或翻译配置更改时执行。

- **translationTask(source:target:action:)**：添加一项任务，在显示此视图之前或指定的源语言或目标语言更改时执行。

## 显示日记建议

- **journalingSuggestionsPicker(isPresented:onCompletion:)**：显示一个可视化选择器界面，其中包含用户可以选择以获取更多信息的事件和图像。

## 管理联系人访问权限

- **contactAccessButtonCaption(_:)**

- **contactAccessButtonStyle(_:)**

- **contactAccessPicker(isPresented:completionHandler:)**：以模态方式呈现用户界面，允许用户选择您的应用可以访问哪些联系人。

## 处理游戏控制器事件

- **handlesGameControllerEvents(matching:)**：指定当视图或其子视图获得焦点时，应通过 GameController 框架传递的游戏控制器事件。

## 创建桌面游戏

- **tabletopGame(_:parent:automaticUpdate:)**：向视图添加桌面游戏。

- **tabletopGame(_:parent:automaticUpdate:interaction:)**：提供一个闭包，在需要时返回新的交互。

## 配置相机控制

- **realityViewCameraControls**：现实视图的相机控制。

- **realityViewCameraControls(_:)**：添加控制虚拟相机位置和方向的手势。

## 与事务交互

- **transactionPicker(isPresented:selection:)**：显示一个选择器，用于选择事务集合。

## 框架集成

- **AppKit 集成**：将 AppKit 视图添加到您的 SwiftUI 应用，或在您的 AppKit 应用中使用 SwiftUI 视图。

- **UIKit 集成**：将 UIKit 视图添加到您的 SwiftUI 应用，或在您的 UIKit 应用中使用 SwiftUI 视图。

- **WatchKit 集成**：将 WatchKit 视图添加到您的 SwiftUI 应用，或在您的 WatchKit 应用中使用 SwiftUI 视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Technology-specific-views
crawled: 2025-12-02T17:44:50Z
---

# Technology-specific views

**API Collection**

Use SwiftUI views that other Apple frameworks provide.

## Overview

To access SwiftUI views that another framework defines, import both SwiftUI and the other framework into the file where you use the view. You can find the framework to import by looking at the availability information on the view’s documentation page.



For example, to use the [doc://com.apple.documentation/documentation/MapKit/Map] view in your app, import both SwiftUI and MapKit.

```swift
import SwiftUI
import MapKit

struct MyMapView: View {
    // Center the map on Joshua Tree National Park.
    var region = MKCoordinateRegion(
            center: CLLocationCoordinate2D(latitude: 34.011_286, longitude: -116.166_868),
            span: MKCoordinateSpan(latitudeDelta: 0.2, longitudeDelta: 0.2)
        )

    var body: some View {
        Map(initialPosition: .region(region))
    }
}
```

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/technologies] in the Human Interface Guidelines.

## Displaying web content

- **WebView**: A view that displays some web content.
- **WebPage**: An object that controls and manages the behavior of interactive web content.
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

## Accessing Apple Pay and Wallet

- **PayWithApplePayButton**: A type that provides a button to pay with Apple pay.
- **AddPassToWalletButton**: A type that provides a button that enables people to add a new or existing pass to Apple Wallet.
- **VerifyIdentityWithWalletButton**: A type that displays a button to present the identity verification flow.
- **addOrderToWalletButtonStyle(_:)**: Sets the button’s style.
- **addPassToWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKAddPassButtonStyle`).
- **onApplePayCouponCodeChange(perform:)**: Called when a user has entered or updated a coupon code. This is required if the user is being asked to provide a coupon code.
- **onApplePayPaymentMethodChange(perform:)**: Called when a payment method has changed and asks for an update payment request. If this modifier isn’t provided Wallet will assume the payment method is valid.
- **onApplePayShippingContactChange(perform:)**: Called when a user selected a shipping address. This is required if the user is being asked to provide a shipping contact.
- **onApplePayShippingMethodChange(perform:)**: Called when a user selected a shipping method. This is required if the user is being asked to provide a shipping method.
- **payLaterViewAction(_:)**: Sets the action on the PayLaterView. See `PKPayLaterAction`.
- **payLaterViewDisplayStyle(_:)**: Sets the display style on the PayLaterView. See `PKPayLaterDisplayStyle`.
- **payWithApplePayButtonStyle(_:)**: Sets the style to be used by the button. (see `PayWithApplePayButtonStyle`).
- **verifyIdentityWithWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKIdentityButtonStyle`).
- **AsyncShareablePassConfiguration**
- **transactionTask(_:action:)**: Provides a task to perform before this view appears

## Authorizing and authenticating

- **LocalAuthenticationView**: A SwiftUI view that displays an authentication interface.
- **SignInWithAppleButton**: A SwiftUI view that creates the Sign in with Apple button for display.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).
- **authorizationController**: A value provided in the SwiftUI environment that views can use to perform authorization requests.
- **webAuthenticationSession**: A value provided in the SwiftUI environment that views can use to authenticate a user through a web service.

## Configuring Family Sharing

- **FamilyActivityPicker**: A view in which users specify applications, web domains, and categories without revealing their choices to the app.
- **familyActivityPicker(isPresented:selection:)**: Presents an activity picker view as a sheet.
- **familyActivityPicker(headerText:footerText:isPresented:selection:)**: Presents an activity picker view as a sheet.

## Reporting on device activity

- **DeviceActivityReport**: A view that reports the user’s application, category, and web domain activity in a privacy-preserving way.

## Working with managed devices

- **managedContentStyle(_:)**: Applies a managed content style to the view.
- **automatedDeviceEnrollmentAddition(isPresented:)**: Presents a modal view that enables users to add devices to their organization.

## Creating graphics

- **Chart**: A SwiftUI view that displays a chart.
- **SceneView**: A SwiftUI view for displaying 3D SceneKit content.
- **SpriteView**: A SwiftUI view that renders a SpriteKit scene.

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapFeatureSelectionContent(content:)**: Specifies a custom presentation for the currently selected feature.
- **mapControls(_:)**: Configures all `Map` views in the associated environment to have standard size and position controls
- **mapControlVisibility(_:)**: Configures all Map controls in the environment to have the specified visibility
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailSheet(isPresented:item:displaysMap:)**: Presents a map item detail sheet.
- **mapItemDetailSheet(item:displaysMap:)**: Presents a map item detail sheet.

## Displaying media

- **CameraView**: A SwiftUI view into which a video stream or an image snapshot is rendered.
- **NowPlayingView**: A view that displays the system’s Now Playing interface so that the user can control audio.
- **VideoPlayer**: A view that displays content from a player and a native user interface to control playback.
- **continuityDevicePicker(isPresented:onDidConnect:)**: A `continuityDevicePicker` should be used to discover and connect nearby continuity device through a button interface or other form of activation. On tvOS, this presents a fullscreen continuity device picker experience when selected. The modal view covers as much the screen of `self` as possible when a given condition is true.
- **cameraAnchor(isActive:)**: Specifies the view that should act as the virtual camera for Apple Vision Pro 2D Persona stream.

## Selecting photos

- **PhotosPicker**: A view that displays a Photos picker for choosing assets from the photo library.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a `PhotosPickerItem`.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerAccessoryVisibility(_:edges:)**: Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.
- **photosPickerDisabledCapabilities(_:)**: Disables capabilities of the Photos picker.
- **photosPickerStyle(_:)**: Sets the mode of the Photos picker.

## Previewing content

- **quickLookPreview(_:)**: Presents a Quick Look preview of the contents of a single URL.
- **quickLookPreview(_:in:)**: Presents a Quick Look preview of the URLs you provide.

## Interacting with networked devices

- **DevicePicker**: A SwiftUI view that displays other devices on the network, and creates an encrypted connection to a copy of your app running on that device.
- **devicePickerSupports**: Checks for support to present a DevicePicker.

## Configuring a Live Activity

- **activitySystemActionForegroundColor(_:)**: The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.
- **activityBackgroundTint(_:)**: Sets the tint color for the background of a Live Activity that appears on the Lock Screen.
- **isActivityFullscreen**: A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.
- **activityFamily**: The size family of the current Live Activity.

## Interacting with the App Store and Apple Music

- **appStoreOverlay(isPresented:configuration:)**: Presents a StoreKit overlay when a given condition is true.
- **manageSubscriptionsSheet(isPresented:)**
- **refundRequestSheet(for:isPresented:onDismiss:)**: Display the refund request sheet for the given transaction.
- **offerCodeRedemption(isPresented:onCompletion:)**: Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.
- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**: Initiates the process of presenting a sheet with subscription offers for Apple Music when the `isPresented` binding is `true`.
- **currentEntitlementTask(for:priority:action:)**: Declares the view as dependent on the entitlement of an In-App Purchase product, and returns a modified view.
- **inAppPurchaseOptions(_:)**: Add a function to call before initiating a purchase from StoreKit view within this view, providing a set of options for the purchase.
- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**
- **onInAppPurchaseCompletion(perform:)**: Add an action to perform when a purchase initiated from a StoreKit view within this view completes.
- **onInAppPurchaseStart(perform:)**: Add an action to perform when a user triggers the purchase button on a StoreKit view within this view.
- **productIconBorder()**: Adds a standard border to an in-app purchase product’s icon .
- **productViewStyle(_:)**: Sets the style for In-App Purchase product views within a view.
- **productDescription(_:)**: Configure the visibility of labels displaying an in-app purchase product description within the view.
- **storeButton(_:for:)**: Specifies the visibility of auxiliary buttons that store view and subscription store view instances may use.
- **storeProductTask(for:priority:action:)**: Declares the view as dependent on an In-App Purchase product and returns a modified view.
- **storeProductsTask(for:priority:action:)**: Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.
- **subscriptionStatusTask(for:priority:action:)**: Declares the view as dependent on the status of an auto-renewable subscription group, and returns a modified view.
- **subscriptionStoreButtonLabel(_:)**: Configures subscription store view instances within a view to use the provided button label.
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
- **subscriptionStoreControlBackground(_:)**: Set a standard effect to use for the background of subscription store view controls within the view.
- **subscriptionPromotionalOffer(offer:signature:)**: Selects a promotional offer to apply to a purchase a customer makes from a subscription store view.
- **preferredSubscriptionOffer(_:)**: Selects a subscription offer to apply to a purchase that a customer makes from a subscription store view, a store view, or a product view.

## Accessing health data

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**: Asynchronously requests permission to read a data type that requires per-object authorization (such as vision prescriptions).
- **healthDataAccessRequest(store:readTypes:trigger:completion:)**: Requests permission to read the specified HealthKit data types.
- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**: Requests permission to save and read the specified HealthKit data types.
- **workoutPreview(_:isPresented:)**: Presents a preview of the workout contents as a modal sheet

## Providing tips

- **popoverTip(_:arrowEdge:action:)**: Presents a popover tip on the modified view.
- **tipBackground(_:)**: Sets the tip’s view background to a style. Currently this only applies to inline tips, not popover tips.
- **tipCornerRadius(_:antialiased:)**: Sets the corner radius for an inline tip view.
- **tipImageSize(_:)**: Sets the size for a tip’s image.
- **tipViewStyle(_:)**: Sets the given style for TipView within the view hierarchy.
- **tipImageStyle(_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:_:)**: Sets the style for a tip’s image.

## Showing a translation

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**: Presents a translation popover when a given condition is true.
- **translationTask(_:action:)**: Adds a task to perform before this view appears or when the translation configuration changes.
- **translationTask(source:target:action:)**: Adds a task to perform before this view appears or when the specified source or target languages change.

## Presenting journaling suggestions

- **journalingSuggestionsPicker(isPresented:onCompletion:)**: Presents a visual picker interface that contains events and images that a person can select to retrieve more information.

## Managing contact access

- **contactAccessButtonCaption(_:)**
- **contactAccessButtonStyle(_:)**
- **contactAccessPicker(isPresented:completionHandler:)**: Modally present UI which allows the user to select which contacts your app has access to.

## Handling game controller events

- **handlesGameControllerEvents(matching:)**: Specifies the game controllers events which should be delivered through the GameController framework when the view, or one of its descendants has focus.

## Creating a tabletop game

- **tabletopGame(_:parent:automaticUpdate:)**: Adds a tabletop game to a view.
- **tabletopGame(_:parent:automaticUpdate:interaction:)**: Supplies a closure which returns a new interaction whenever needed.

## Configuring camera controls

- **realityViewCameraControls**: The camera controls for the reality view.
- **realityViewCameraControls(_:)**: Adds gestures that control the position and direction of a virtual camera.

## Interacting with transactions

- **transactionPicker(isPresented:selection:)**: Presents a picker that selects a collection of transactions.

## Framework integration

- **AppKit integration**: Add AppKit views to your SwiftUI app, or use SwiftUI views in your AppKit app.
- **UIKit integration**: Add UIKit views to your SwiftUI app, or use SwiftUI views in your UIKit app.
- **WatchKit integration**: Add WatchKit views to your SwiftUI app, or use SwiftUI views in your WatchKit app.

