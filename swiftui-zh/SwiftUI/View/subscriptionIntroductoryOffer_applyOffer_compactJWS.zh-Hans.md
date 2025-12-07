--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionIntroductoryOffer(applyOffer:compactJWS:)

抓取时间：2025-12-02T17:25:28Z

---

# subscriptionIntroductoryOffer(applyOffer:compactJWS:)

**实例方法**

选择要应用于客户在订阅商店视图中购买的商品的入门优惠资格偏好。

## 声明

```swift
nonisolated func subscriptionIntroductoryOffer(applyOffer: @escaping (Product, Product.SubscriptionInfo) -> Bool, compactJWS: @escaping (Product, Product.SubscriptionInfo) async throws -> String) -> some View

```

## 参数

- **applyOffer**：系统在将给定的订阅产品绘制到订阅商店视图之前调用此函数。返回是否应将入门优惠应用于给定的产品（如果有），以使系统提供的 UI 反映所选优惠下的折扣条款。

- **compactJWS**：系统会在处理购买之前调用此函数，并将待购买的产品作为参数提供。返回一个您在服务器上生成的精简 JWS 签名，用于验证所选优惠的资格偏好。此闭包抛出的错误将通过 [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) 修饰符显示。有关生成 JWS 签名的信息，请参阅 [doc://com.apple.documentation/documentation/StoreKit/generating-jws-to-sign-app-store-requests]。

## 讨论

当您使用系统提供的 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreControlStyle] 来设置应用内订阅商店的样式时，此视图中的订阅商店会使用入门订阅优惠来配置所显示的订阅计划的外观。标准的 [doc://com.apple.documentation/documentation/StoreKit/ProductViewStyle] 实例不会在 UI 中显示入门或促销优惠，而是使用 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView]。

使用 `applyOffer` 确定是否应在视图中显示优惠信息并将其应用于购买。如果签名通过验证，系统将根据优惠资格偏好将优惠应用于或移除购买。如果签名未通过验证，则购买将失败并显示 [doc://com.apple.documentation/documentation/StoreKit/Product/PurchaseError/invalidOfferSignature]。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionIntroductoryOffer(applyOffer:compactJWS:)
crawled: 2025-12-02T17:25:28Z
---

# subscriptionIntroductoryOffer(applyOffer:compactJWS:)

**Instance Method**

Selects the introductory offer eligibility preference to apply to a purchase a customer makes from a subscription store view.

## Declaration

```swift
nonisolated func subscriptionIntroductoryOffer(applyOffer: @escaping (Product, Product.SubscriptionInfo) -> Bool, compactJWS: @escaping (Product, Product.SubscriptionInfo) async throws -> String) -> some View

```

## Parameters

- **applyOffer**: The system calls this function before drawing the given subscription product on the subscription store view. Return if the introductory offer should be applied to a given product, if any, to have system-provided UI reflect the discounted terms under the selected offer.
- **compactJWS**: The system calls this function before processing a purchase, with the product to be purchased provided as a parameter. Return a compact JWS signature you generate on your server that validates the selected offer eligibility preference. Errors thrown from this closure will be surfaced via the [onInAppPurchaseCompletion(perform:)](onInAppPurchaseCompletion_perform.zh-Hans.md) modifier. For information about generating the JWS signature, see [doc://com.apple.documentation/documentation/StoreKit/generating-jws-to-sign-app-store-requests].

## Discussion

Subscription stores within this view uses the introductory subscription offers to configure the appearance of the subscription plans displayed, when you use a system-provided [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreControlStyle] to style the in-app subscription store. Standard [doc://com.apple.documentation/documentation/StoreKit/ProductViewStyle] instances don’t show introductory or promotional offers in UI, instead use [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView].

Determine if the introductory offer should be displayed in the view and applied to the purchase using the `applyOffer`. If the signature passes validation, the system applies or removes the offer to the purchases according to the offer eligibility preference. If the signature fails validation, the purchase will fail with [doc://com.apple.documentation/documentation/StoreKit/Product/PurchaseError/invalidOfferSignature].

