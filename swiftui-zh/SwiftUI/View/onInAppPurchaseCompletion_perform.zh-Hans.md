--- 来源：https://developer.apple.com/documentation/swiftui/view/oninapppurchasecompletion(perform:)

抓取时间：2025-12-01T10:26:15Z

---

# onInAppPurchaseCompletion(perform:)

**实例方法**

添加一个操作，用于在应用内商店视图中发起的购买操作完成时执行。

## 声明

```swift
nonisolated func onInAppPurchaseCompletion(perform action: ((Product, Result<Product.PurchaseResult, any Error>) async -> ())?) -> some View

```

## 参数

- **action**：要执行的操作，产品价值和购买结果作为参数提供。

## 说明

默认情况下，成功的应用内商店视图购买交易将从 `Transaction.updates` 发出。如果购买失败并出现错误，则会显示警告。您可以通过为操作提供 `nil` 来将视图恢复到此行为。

每次购买只会执行一个操作。子视图可以使用另一个 [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) 修饰符来覆盖此操作。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当给定条件为真时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，客户可以通过该表单兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠的流程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在用户从 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseStart(perform:)**：添加一个操作，用于在用户点击 StoreKit 视图上的购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于某个应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于一组应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/swiftui/view/oninapppurchasecompletion(perform:)
crawled: 2025-12-01T10:26:15Z
---

# onInAppPurchaseCompletion(perform:)

**Instance Method**

Add an action to perform when a purchase initiated from a StoreKit view within this view completes.

## Declaration

```swift
nonisolated func onInAppPurchaseCompletion(perform action: ((Product, Result<Product.PurchaseResult, any Error>) async -> ())?) -> some View

```

## Parameters

- **action**: The action to perform, with the product value and the purchase result provided as parameters.

## Discussion

By default, transactions from successful in-app store view purchases will be emitted from `Transaction.updates`. If the purchase fails with an error, an alert will be displayed. You can revert a view back to this behavior by providing `nil` for action.

Only one action will be performed for each purchase. Descendant views can override the action by using another [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) modifier.

## Interacting with the App Store and Apple Music

- **appStoreOverlay(isPresented:configuration:)**: Presents a StoreKit overlay when a given condition is true.
- **manageSubscriptionsSheet(isPresented:)**
- **refundRequestSheet(for:isPresented:onDismiss:)**: Display the refund request sheet for the given transaction.
- **offerCodeRedemption(isPresented:onCompletion:)**: Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.
- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**: Initiates the process of presenting a sheet with subscription offers for Apple Music when the `isPresented` binding is `true`.
- **currentEntitlementTask(for:priority:action:)**: Declares the view as dependent on the entitlement of an In-App Purchase product, and returns a modified view.
- **inAppPurchaseOptions(_:)**: Add a function to call before initiating a purchase from StoreKit view within this view, providing a set of options for the purchase.
- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**
- **onInAppPurchaseStart(perform:)**: Add an action to perform when a user triggers the purchase button on a StoreKit view within this view.
- **productIconBorder()**: Adds a standard border to an in-app purchase product’s icon .
- **productViewStyle(_:)**: Sets the style for In-App Purchase product views within a view.
- **productDescription(_:)**: Configure the visibility of labels displaying an in-app purchase product description within the view.
- **storeButton(_:for:)**: Specifies the visibility of auxiliary buttons that store view and subscription store view instances may use.
- **storeProductTask(for:priority:action:)**: Declares the view as dependent on an In-App Purchase product and returns a modified view.
- **storeProductsTask(for:priority:action:)**: Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.

