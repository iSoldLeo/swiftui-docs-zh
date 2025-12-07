--- 来源：https://developer.apple.com/documentation/swiftui/view/musicsubscriptionoffer(ispresented:options:onloadcompletion:)

抓取时间：2025-12-03T05:37:05Z

---

# musicSubscriptionOffer(isPresented:options:onLoadCompletion:)

**实例方法**

当绑定参数 `isPresented` 为 `true` 时，启动显示 Apple Music 订阅优惠信息表的过程。

## 声明

```swift
nonisolated func musicSubscriptionOffer(isPresented: Binding<Bool>, options: MusicSubscriptionOffer.Options = .default, onLoadCompletion: @escaping ((any Error)?) -> Void = { _ in }) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，您可以将其设置为 `true` 以显示 Apple Music 订阅优惠信息表。

- **options**：用于加载 Apple Music 订阅优惠的选项。

- **onLoadCompletion**：完成此订阅优惠的初始加载过程后要调用的函数。当此函数被调用且错误参数为 `nil` 时，订阅优惠界面将显示。如果加载过程中出现错误，订阅优惠会调用此函数并传入非 `nil` 类型的错误，并将 `isPresented` 绑定重置为 `false`。

## 讨论

以下示例显示了一个简单的按钮，用户可以激活该按钮以开始显示 Apple Music 的订阅优惠。此按钮的操作处理程序通过将 `isShowingOffer` 变量设置为 `true` 来启动这些优惠的显示。

```swift
struct MusicSubscriptionOfferButton: View {
    @State var isShowingOffer = false
    var body: some View {
        Button("Apple Music Subscription Offer") {
            isShowingOffer = true
        }
        .musicSubscriptionOffer(isPresented: $isShowingOffer)
    }
}
```

您还可以通过创建 `MusicSubscriptionOffer.Options` 的实例，设置相关属性，并将其传递给 `.musicSubscriptionOffer(…)` 来配置 Apple Music 订阅优惠。例如，要显示突出显示特定专辑的上下文优惠，您可以按如下方式配置订阅优惠：

```swift
struct MusicSubscriptionOfferButton: View {
    var album: Album
    @State var isShowingOffer = false
    @State var offerOptions = MusicSubscriptionOffer.Options(
        affiliateToken: "<affiliate_token>", 
        campaignToken: "<campaign_token>"
    )

    var body: some View {
        Button("Apple Music Subscription Offer") {
            offerOptions.itemID = album.id
            isShowingOffer = true
        }
        .musicSubscriptionOffer(
            isPresented: $isShowingOffer, 
            options: offerOptions
        )
    }
}
```

`offerOptions` 的初始值包含相关令牌（联盟令牌和推广活动令牌），您可以通过推荐新的 Apple Music 订阅者获得佣金。有关更多信息，请参阅 [https://affiliate.itunes.apple.com/resources/] 的演示文稿。

您还可以将 `isShowingOffer` 设置为 `false` 以通过编程方式关闭订阅优惠（或中止其加载过程）。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足特定条件时，显示 StoreKit 叠加层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的权限，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，在从 StoreKit 视图发起购买之前调用该函数，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，当用户从本视图内的 StoreKit 视图发起的购买操作完成时执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，当用户在本视图内的 StoreKit 视图上点击购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品的集合，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/swiftui/view/musicsubscriptionoffer(ispresented:options:onloadcompletion:)
crawled: 2025-12-03T05:37:05Z
---

# musicSubscriptionOffer(isPresented:options:onLoadCompletion:)

**Instance Method**

Initiates the process of presenting a sheet with subscription offers for Apple Music when the `isPresented` binding is `true`.

## Declaration

```swift
nonisolated func musicSubscriptionOffer(isPresented: Binding<Bool>, options: MusicSubscriptionOffer.Options = .default, onLoadCompletion: @escaping ((any Error)?) -> Void = { _ in }) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that you can set to `true` to show a sheet with subscription offers for Apple Music.
- **options**: Options to use for loading the subscription offer for Apple Music.
- **onLoadCompletion**: The function to call upon completing the initial loading process for this subscription offer. The subscription offer UI becomes visible when it calls this function with the error argument as `nil`. If there is an error in the loading process, the subscription offer calls this function with a non-`nil` error, and it resets the `isPresented` binding to `false`.

## Discussion

The example below displays a simple button that the user can activate to begin presenting subscription offers for Apple Music. The action handler of this button initiates the presentation of those offers by setting the `isShowingOffer` variable to `true`.

```swift
struct MusicSubscriptionOfferButton: View {
    @State var isShowingOffer = false
    var body: some View {
        Button("Apple Music Subscription Offer") {
            isShowingOffer = true
        }
        .musicSubscriptionOffer(isPresented: $isShowingOffer)
    }
}
```

You can also configure the Apple Music subscription offer by creating an instance of `MusicSubscriptionOffer.Options`, setting relevant properties on it, and passing it to `.musicSubscriptionOffer(…)`. For example, to present contextual offers that highlight a specific album, you can configure the subscription offer like the following:

```swift
struct MusicSubscriptionOfferButton: View {
    var album: Album
    @State var isShowingOffer = false
    @State var offerOptions = MusicSubscriptionOffer.Options(
        affiliateToken: "<affiliate_token>", 
        campaignToken: "<campaign_token>"
    )

    var body: some View {
        Button("Apple Music Subscription Offer") {
            offerOptions.itemID = album.id
            isShowingOffer = true
        }
        .musicSubscriptionOffer(
            isPresented: $isShowingOffer, 
            options: offerOptions
        )
    }
}
```

The initial value of `offerOptions` includes relevant tokens (affiliate and campaign tokens) that allow you to receive compensation for referring new Apple Music subscribers. For more information, see this presentation of the [https://affiliate.itunes.apple.com/resources/].

You may also set `isShowingOffer` to `false` to programmatically dismiss the subscription offer (or to abort its loading process).

## Interacting with the App Store and Apple Music

- **appStoreOverlay(isPresented:configuration:)**: Presents a StoreKit overlay when a given condition is true.
- **manageSubscriptionsSheet(isPresented:)**
- **refundRequestSheet(for:isPresented:onDismiss:)**: Display the refund request sheet for the given transaction.
- **offerCodeRedemption(isPresented:onCompletion:)**: Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.
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

