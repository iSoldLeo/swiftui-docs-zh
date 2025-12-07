--- 来源：https://developer.apple.com/documentation/SwiftUI/View/preferredSubscriptionOffer(_:)

抓取时间：2025-12-02T17:25:08Z

---

# preferredSubscriptionOffer(_:)

**实例方法**

为客户从订阅商店视图、商店视图或产品视图中购买的商品选择要应用的订阅优惠。

## 声明

```swift
nonisolated func preferredSubscriptionOffer(_ offer: @escaping (Product, Product.SubscriptionInfo, [Product.SubscriptionOffer]) -> Product.SubscriptionOffer?) -> some View

```

## 参数

- **offer**：返回要应用于客户购买的订阅优惠的闭包。

## 说明

此视图中的订阅商店使用您指定的订阅优惠来配置订阅计划的外观。 [doc://com.apple.documentation/documentation/StoreKit/ProductView] 不会在用户界面中显示订阅优惠的条款，但您仍然可以使用此修饰符来声明视图层级结构中的哪些优惠产品视图适用于购买。

使用此修饰符的优惠偏好会覆盖父视图中的优惠偏好。

如果 StoreKit 确定客户符合多个优惠条件，系统会在将产品绘制到订阅商店视图之前，或在客户在商店视图或产品视图上发起购买之前，调用 `offer` 闭包。返回要应用于产品的订阅优惠（如有），以便系统提供的用户界面反映所选优惠下的折扣价格条款。

如果您的 `offer` 闭包返回 nil，则系统会选择入门优惠（如果存在且客户符合条件）。

以下代码示例将首选订阅优惠设置为客户符合条件的第一个优惠：

```swift
import SwiftUI
import StoreKit

@available(iOS 18.0, macOS 15.0, tvOS 18.0, watchOS 11.0, visionOS 2.0, *)
struct MyView: View {

    var body: some View {
        SubscriptionStoreView(groupID: groupIdentifier)
            .preferredSubscriptionOffer { product, subscription, eligibleOffers in
                // Determine the offer to use from the list of eligibleOffers.
                // This example just uses the first offer.
                return eligibleOffers.first
            }
    }
}
```

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 叠加层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，客户可以使用该表单兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠表单的过程。

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
source: https://developer.apple.com/documentation/SwiftUI/View/preferredSubscriptionOffer(_:)
crawled: 2025-12-02T17:25:08Z
---

# preferredSubscriptionOffer(_:)

**Instance Method**

Selects a subscription offer to apply to a purchase that a customer makes from a subscription store view, a store view, or a product view.

## Declaration

```swift
nonisolated func preferredSubscriptionOffer(_ offer: @escaping (Product, Product.SubscriptionInfo, [Product.SubscriptionOffer]) -> Product.SubscriptionOffer?) -> some View

```

## Parameters

- **offer**: A closure that returns the subscription offer to apply to the customer’s purchase.

## Discussion

Subscription stores within this view use the subscription offer you specify to configure the appearance of the subscription plans. [doc://com.apple.documentation/documentation/StoreKit/ProductView] doesn’t display the terms of a subscription offer in the UI, but you can still use this modifier to declare which offer product views within a view hierarchy apply to a purchase.

Offer preferences that use this modifier override offer preferences from ancestor views.



If StoreKit determines that the customer is eligible for more than one offer, the system calls the `offer` closure before it draws the product on the subscription store view, or before the customer initiates a purchase on a store view or product view. Return the subscription offer to apply to the product, if any, to have system-provided UI reflect the discounted pricing terms under the selected offer.

If your `offer` closure returns nil, the system selects the introductory offer, if it exists, and if the customer is eligible for it.

The following code example sets the preferred subscription offer to the first offer the customer is eligible for:

```swift
import SwiftUI
import StoreKit

@available(iOS 18.0, macOS 15.0, tvOS 18.0, watchOS 11.0, visionOS 2.0, *)
struct MyView: View {

    var body: some View {
        SubscriptionStoreView(groupID: groupIdentifier)
            .preferredSubscriptionOffer { product, subscription, eligibleOffers in
                // Determine the offer to use from the list of eligibleOffers.
                // This example just uses the first offer.
                return eligibleOffers.first
            }
    }
}
```

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

