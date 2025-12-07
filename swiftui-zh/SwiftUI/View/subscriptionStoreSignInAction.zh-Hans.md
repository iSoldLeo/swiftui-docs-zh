--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreSignInAction(_:)

抓取时间：2025-12-02T17:25:58Z

---

# subscriptionStoreSignInAction(_:)

**实例方法**

在视图内的订阅商店视图中添加一个操作，当用户点击登录按钮时执行该操作。

## 声明

```swift
nonisolated func subscriptionStoreSignInAction(_ action: (() -> ())?) -> some View

```

## 参数

- **action**：要执行的操作。传递 `nil` 可移除此视图内订阅商店的登录操作。默认值为 `nil`。

## 说明

一个视图只能有一个登录操作。如果父视图指定了登录操作，使用此修饰符将替换父视图的登录操作。

如果值为 `nil`，订阅商店将永远不会显示登录按钮。您还可以使用 [storeButton(_:for:)](storeButton___for.zh-Hans.md) 修饰符隐藏登录按钮，而无需移除该操作，并将按钮类型设置为 [doc://com.apple.documentation/documentation/StoreKit/StoreButtonKind/signIn]。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，客户可以通过该表单兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠的流程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从本视图内的 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从本视图内的 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，用于在用户点击本视图内的 StoreKit 视图上的购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionStoreSignInAction(_:)
crawled: 2025-12-02T17:25:58Z
---

# subscriptionStoreSignInAction(_:)

**Instance Method**

Adds an action to perform when a person uses the sign-in button on a subscription store view within a view.

## Declaration

```swift
nonisolated func subscriptionStoreSignInAction(_ action: (() -> ())?) -> some View

```

## Parameters

- **action**: The action to perform. Pass `nil` to remove the sign in action for subscription stores within this view. The default value is `nil`.

## Discussion

You can only have one sign in action for a view. If an ancestor view specifies a sign in action, using this modifier will replace the ancestor’s sign in action.

If the value is `nil`, subscription stores will never show a sign in button. You can also hide the sign in button without removing the action by using the [storeButton(_:for:)](storeButton___for.zh-Hans.md) modifier, providing [doc://com.apple.documentation/documentation/StoreKit/StoreButtonKind/signIn] as the button kind.

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

