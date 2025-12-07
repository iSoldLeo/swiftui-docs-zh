--- 来源：https://developer.apple.com/documentation/swiftui/view/appstoreoverlay(ispresented:configuration:)

抓取时间：2025-12-01T10:26:04Z

---

# appStoreOverlay(isPresented:configuration:)

**实例方法**

当给定条件为真时，显示 StoreKit 覆盖层。

## 声明

```swift
nonisolated func appStoreOverlay(isPresented: Binding<Bool>, configuration: @escaping () -> SKOverlay.Configuration) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，指示是否应显示覆盖层。

- **configuration**：提供覆盖层配置的闭包。

## 说明

您可以使用 `appStoreOverlay` 显示一个推荐其他应用的覆盖层。此叠加层使用户能够立即查看其他应用在 App Store 中的页面。

当 `isPresented` 为真时，系统将运行 `configuration` 来确定如何配置此叠加层。叠加层将自动显示在当前场景之上。

## 与 App Store 和 Apple Music 交互

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当 `isPresented` 绑定为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从此视图内的 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从此视图内的 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，用于在用户点击此视图内的 StoreKit 视图上的购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图中显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于某个应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于一组应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/swiftui/view/appstoreoverlay(ispresented:configuration:)
crawled: 2025-12-01T10:26:04Z
---

# appStoreOverlay(isPresented:configuration:)

**Instance Method**

Presents a StoreKit overlay when a given condition is true.

## Declaration

```swift
nonisolated func appStoreOverlay(isPresented: Binding<Bool>, configuration: @escaping () -> SKOverlay.Configuration) -> some View

```

## Parameters

- **isPresented**: A Binding to a boolean value indicating whether the overlay should be presented.
- **configuration**: A closure providing the configuration of the overlay.

## Discussion

You use `appStoreOverlay` to display an overlay that recommends another app. The overlay enables users to instantly view the other app’s page on the App Store.

When `isPresented` is true, the system will run `configuration` to determine how to configure the overlay. The overlay will automatically be presented over the current scene.



## Interacting with the App Store and Apple Music

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

