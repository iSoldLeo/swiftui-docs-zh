--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreButtonLabel(_:)

抓取时间：2025-11-30T21:10:54Z

---

# subscriptionStoreButtonLabel(_:)

**实例方法**

配置视图中的订阅商店视图实例，使其使用提供的按钮标签。

## 声明

```swift
nonisolated func subscriptionStoreButtonLabel(_ label: SubscriptionStoreButtonLabel) -> some View

```

## 讨论

按钮标签并非在所有情况下都有效。例如，如果您的订阅商店显示多个订阅按钮，将按钮标签设置为 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreButtonLabel/action-swift.type.property] 时，按钮标签将回退到每个订阅的显示名称。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当给定条件为真时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：在此视图中添加一个函数，在从 StoreKit 视图发起购买之前调用该函数，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，当用户从本视图内的 StoreKit 视图发起的购买操作完成时执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，当用户在本视图内的 StoreKit 视图上点击购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreButtonLabel(_:)
crawled: 2025-11-30T21:10:54Z
---

# subscriptionStoreButtonLabel(_:)

**Instance Method**

Configures subscription store view instances within a view to use the provided button label.

## Declaration

```swift
nonisolated func subscriptionStoreButtonLabel(_ label: SubscriptionStoreButtonLabel) -> some View

```

## Discussion

The button label is not always respected in every context. For example, if you have a subscription store that shows multiple subscribe buttons, setting [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreButtonLabel/action-swift.type.property] as the button label will fall back to each subscription’s display name.

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

