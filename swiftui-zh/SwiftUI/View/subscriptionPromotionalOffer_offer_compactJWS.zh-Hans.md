--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionPromotionalOffer(offer:compactJWS:)

抓取时间：2025-11-30T21:10:52Z

---

# subscriptionPromotionalOffer(offer:compactJWS:)

**实例方法**

为客户在订阅商店视图中购买的产品选择要应用的促销优惠。

## 声明

```swift
nonisolated func subscriptionPromotionalOffer(offer: @escaping (Product, Product.SubscriptionInfo) -> Product.SubscriptionOffer?, compactJWS: @escaping (Product, Product.SubscriptionInfo, Product.SubscriptionOffer) async throws -> String) -> some View

```

## 参数

- **offer**：系统会在订阅商店视图中绘制给定的订阅产品之前调用此函数。返回要应用于该产品的促销优惠（如有），以便系统提供的 UI 反映所选优惠下的折扣条款。

- **compactJWS**：系统会在处理购买之前调用此函数，并将待购买的产品以及要应用于此次购买的订阅优惠作为参数提供。返回一个您在服务器上生成的用于验证所选优惠的精简 JWS 签名。此闭包抛出的错误将通过 [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) 修饰符显示。有关生成 JWS 签名的信息，请参阅 [doc://com.apple.documentation/documentation/StoreKit/generating-jws-to-sign-app-store-requests]。

## 讨论

当您使用系统提供的 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreControlStyle] 来设置应用内订阅商店的样式时，此视图中的订阅商店会使用指定的订阅优惠来配置所显示的订阅计划的外观。标准的 [doc://com.apple.documentation/documentation/StoreKit/ProductViewStyle] 实例不会在用户界面中显示入门优惠或促销优惠。请改用 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView] 来在用户界面中显示这些优惠。

如果您选择的优惠的签名通过验证，系统会将该优惠应用于此次购买。如果您选择的优惠的签名未通过验证，则购买失败，并显示错误代码 [doc://com.apple.documentation/documentation/StoreKit/Product/PurchaseError/invalidOfferSignature]。

您在此处选择的促销优惠会覆盖您在父视图中指定的任何优惠。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionPromotionalOffer(offer:compactJWS:)
crawled: 2025-11-30T21:10:52Z
---

# subscriptionPromotionalOffer(offer:compactJWS:)

**Instance Method**

Selects a promotional offer to apply to a purchase a customer makes from a subscription store view.

## Declaration

```swift
nonisolated func subscriptionPromotionalOffer(offer: @escaping (Product, Product.SubscriptionInfo) -> Product.SubscriptionOffer?, compactJWS: @escaping (Product, Product.SubscriptionInfo, Product.SubscriptionOffer) async throws -> String) -> some View

```

## Parameters

- **offer**: The system calls this function before drawing the given subscription product on the subscription store view. Return the promotional offer to apply to the product, if any, to have system-provided UI reflect the discounted terms under the selected offer.
- **compactJWS**: The system calls this function before processing a purchase, with the product to be purchased provided as a parameter, along with the selected subscription offer to be applied to the purchase. Return a compact JWS signature you generate on your server that validates the selected offer. Errors thrown from this closure will be surfaced via the [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) modifier. For information about generating the JWS signature, see [doc://com.apple.documentation/documentation/StoreKit/generating-jws-to-sign-app-store-requests]..

## Discussion

Subscription stores within this view uses the specified subscription offer to configure the appearance of the subscription plans displayed, when you use a system-provided [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreControlStyle] to style the in-app subscription store. Standard [doc://com.apple.documentation/documentation/StoreKit/ProductViewStyle] instances don’t show introductory or promotional offers in UI. Use the [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView] instead to show these offers in the UI.

If the signature passes validation for the offer you select, the system applies the offer to the purchase. If the signature fails validation for the offer you select, the purchase fails with [doc://com.apple.documentation/documentation/StoreKit/Product/PurchaseError/invalidOfferSignature].

Promotional offers you select in this modifier overwrite any offers you specified in ancestor views.

