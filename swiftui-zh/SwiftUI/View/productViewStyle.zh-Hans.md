--- 来源：https://developer.apple.com/documentation/swiftui/view/productviewstyle(_:)

抓取时间：2025-12-01T10:26:17Z

---

# productViewStyle(_:)

**实例方法**

设置视图中应用内购买产品视图的样式。

## 声明

```swift
nonisolated func productViewStyle(_ style: some ProductViewStyle) -> some View

```

## 参数

- **style**：要应用于视图中应用内购买产品视图的样式。

## 说明

此修饰符会设置视图中任何 [doc://com.apple.documentation/documentation/StoreKit/ProductView] 或 [doc://com.apple.documentation/documentation/StoreKit/StoreView] 实例的样式。

## 与 App Store 和 Apple Music 的交互

- **appStoreOverlay(isPresented:configuration:)**：当给定条件为真时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，在从 StoreKit 视图发起购买之前调用该函数，提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，当用户从本视图内的 StoreKit 视图发起的购买操作完成时执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，当用户在本视图内的 StoreKit 视图上点击购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品集合，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/swiftui/view/productviewstyle(_:)
crawled: 2025-12-01T10:26:17Z
---

# productViewStyle(_:)

**Instance Method**

Sets the style for In-App Purchase product views within a view.

## Declaration

```swift
nonisolated func productViewStyle(_ style: some ProductViewStyle) -> some View

```

## Parameters

- **style**: The style to apply to the in-app purchase product views within the view.

## Discussion

This modifier styles any [doc://com.apple.documentation/documentation/StoreKit/ProductView] or [doc://com.apple.documentation/documentation/StoreKit/StoreView] instances within a view.

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
- **productDescription(_:)**: Configure the visibility of labels displaying an in-app purchase product description within the view.
- **storeButton(_:for:)**: Specifies the visibility of auxiliary buttons that store view and subscription store view instances may use.
- **storeProductTask(for:priority:action:)**: Declares the view as dependent on an In-App Purchase product and returns a modified view.
- **storeProductsTask(for:priority:action:)**: Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.

