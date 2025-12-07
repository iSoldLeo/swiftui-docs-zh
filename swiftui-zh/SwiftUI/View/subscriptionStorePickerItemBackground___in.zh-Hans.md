--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionStorePickerItemBackground(_:in:)

抓取时间：2025-11-30T21:10:59Z

---

# subscriptionStorePickerItemBackground(_:in:)

**实例方法**

设置视图中订阅商店选择器项的背景形状和样式。

## 声明

```swift
nonisolated func subscriptionStorePickerItemBackground(_ backgroundStyle: some ShapeStyle, in shape: some Shape) -> some View

```

## 参数

- **backgroundStyle**：一个 [ShapeStyle](../ShapeStyle.zh-Hans.md) 类型的实例，用于确定订阅商店选择器项的背景样式。

- **shape**：一个符合 [Shape](../Shape.zh-Hans.md) 类型的实例，用于确定订阅商店选择器项的形状。省略 shape 参数将使用默认形状。

## 讨论

使用此视图修饰符可自定义订阅商店视图中选择器选项的形状以及背景样式。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 叠加层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定 `isPresented` 为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从此视图内的 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从此视图内的 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，用于在用户点击此视图内的 StoreKit 视图上的购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图中显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionStorePickerItemBackground(_:in:)
crawled: 2025-11-30T21:10:59Z
---

# subscriptionStorePickerItemBackground(_:in:)

**Instance Method**

Sets the background shape and style for subscription store view picker items within a view.

## Declaration

```swift
nonisolated func subscriptionStorePickerItemBackground(_ backgroundStyle: some ShapeStyle, in shape: some Shape) -> some View

```

## Parameters

- **backgroundStyle**: A [ShapeStyle](../ShapeStyle.zh-Hans.md) that determines the background style for the subscription store view picker items.
- **shape**: An instance of a type that conforms to [Shape](../Shape.zh-Hans.md) and determines the shape of the subscription store view picker items. Omit the shape parameter to use the default shape.

## Discussion

Use this view modifier to customize the shape of the picker options in a subscription store view, as well as the background style.

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

