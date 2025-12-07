--- 来源：https://developer.apple.com/documentation/SwiftUI/View/subscriptionStorePolicyDestination(for:destination:)

抓取时间：2025-12-02T17:25:55Z

---

# subscriptionStorePolicyDestination(for:destination:)

**实例方法**

配置订阅商店视图中策略按钮操作的目标视图。

## 声明

```swift
nonisolated func subscriptionStorePolicyDestination(for button: SubscriptionStorePolicyKind, @ViewBuilder destination: () -> some View) -> some View

```

## 参数

- **button**：要关联 URL 的策略按钮。

- **destination**：用户选择查看策略时要显示的视图。

## 说明

除 tvOS 外，您还可以使用 [subscriptionStorePolicyDestination(url:for:)](subscriptionStorePolicyDestination_url_for.zh-Hans.md) 将 URL 设置为目标视图。如果您未设置目标位置，系统将使用自动行为。请查看您为 `button` 提供的值的文档，以了解自动行为。

默认情况下，如果您为至少一项政策设置了目标位置，订阅商店将显示服务条款和隐私政策按钮。未显式设置的政策将使用自动行为。您可以使用 [storeButton(_:for:)](storeButton___for.zh-Hans.md) 修饰符覆盖此行为，并将 [doc://com.apple.documentation/documentation/StoreKit/StoreButtonKind/policies] 作为第二个参数。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当给定条件为真时，显示 StoreKit 叠加层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表格，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当 `isPresented` 绑定为 `true` 时，启动显示 Apple Music 订阅优惠表格的过程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从本视图中的 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从本视图中的 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加用户在此视图内的 StoreKit 视图上点击购买按钮时要执行的操作。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/subscriptionStorePolicyDestination(for:destination:)
crawled: 2025-12-02T17:25:55Z
---

# subscriptionStorePolicyDestination(for:destination:)

**Instance Method**

Configures a view as the destination for a policy button action in subscription store views.

## Declaration

```swift
nonisolated func subscriptionStorePolicyDestination(for button: SubscriptionStorePolicyKind, @ViewBuilder destination: () -> some View) -> some View

```

## Parameters

- **button**: The policy button to associate the URL with.
- **destination**: The view to present when someone chooses to view the policy.

## Discussion

Except on tvOS, you can also set a URL as the destination using [subscriptionStorePolicyDestination(url:for:)](subscriptionStorePolicyDestination_url_for.zh-Hans.md). If you do not set a destination, the system will use the automatic behavior. Check the documentation for the value you provide for `button` to understand the automatic behavior.

By default, the subscription store shows the terms of service & privacy policy buttons if you set a destination for at least one policy. The policy that is not explicitly set will use the automatic behavior. You can override this behavior using the [storeButton(_:for:)](storeButton___for.zh-Hans.md) modifier, with [doc://com.apple.documentation/documentation/StoreKit/StoreButtonKind/policies] as the second parameter.

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

