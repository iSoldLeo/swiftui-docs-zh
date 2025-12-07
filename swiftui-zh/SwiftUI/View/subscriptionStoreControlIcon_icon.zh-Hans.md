--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreControlIcon(icon:)

抓取时间：2025-12-02T17:25:50Z

---

# subscriptionStoreControlIcon(icon:)

**实例方法**

设置一个视图，用于装饰订阅商店视图中的各个订阅选项。

## 声明

```swift
nonisolated func subscriptionStoreControlIcon(@ViewBuilder icon: @escaping (Product, Product.SubscriptionInfo) -> some View) -> some View

```

## 参数

- **icon**：一个闭包，接受 [doc://com.apple.documentation/documentation/StoreKit/Product] 和 [doc://com.apple.documentation/documentation/StoreKit/Product/SubscriptionInfo] 参数并返回一个视图。

## 讨论

您可以调整此视图，为每个订阅选项提供不同的外观。

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


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreControlIcon(icon:)
crawled: 2025-12-02T17:25:50Z
---

# subscriptionStoreControlIcon(icon:)

**Instance Method**

Sets a view to use to decorate individual subscription options within a subscription store view.

## Declaration

```swift
nonisolated func subscriptionStoreControlIcon(@ViewBuilder icon: @escaping (Product, Product.SubscriptionInfo) -> some View) -> some View

```

## Parameters

- **icon**: A closure that takes a [doc://com.apple.documentation/documentation/StoreKit/Product] and [doc://com.apple.documentation/documentation/StoreKit/Product/SubscriptionInfo] and returns a view.

## Discussion

You can adjust this view to provide a different appearance for each subscription option.

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

