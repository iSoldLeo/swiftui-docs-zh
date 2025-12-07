--- 来源：https://developer.apple.com/documentation/SwiftUI/View/offerCodeRedemption(isPresented:onCompletion:)

抓取时间：2025-12-02T17:45:45Z

---

# offerCodeRedemption(isPresented:onCompletion:)

**实例方法**

显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

## 声明

```swift
nonisolated func offerCodeRedemption(isPresented: Binding<Bool>, onCompletion: @escaping @MainActor (Result<Void, any Error>) -> Void = { _ in }) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，该值决定系统是否显示表单。将布尔值设置为 true 会使系统显示表单。系统关闭表单时，会将其设置为 false。

- **onCompletion**：返回表单呈现结果的闭包。在 macOS 15 之前的版本中，使用 Mac Catalyst 构建的 Mac 应用的完成处理程序会返回一个包含错误信息的失败结果。

## 讨论

[offerCodeRedemption(isPresented:onCompletion:)](offercoderedemption_ispresented_oncompletion.zh-Hans.md) 方法会显示一个系统表单，用户可以在其中输入和兑换优惠码。如果您在 App Store Connect 中生成优惠码，请调用此函数以允许用户兑换优惠。要使用 UIKit 显示表单，请参阅 `presentOfferCodeRedeemSheet(in:)`。

以下代码示例展示了一个视图，该视图会在按下按钮时显示优惠码兑换表单：

```swift
import SwiftUI
import StoreKit

struct ContentView: View {
    @State private var redeemSheetIsPresented = false

    var body: some View {
        Button("Present offer code redemption sheet.") {
            redeemSheetIsPresented = true
        }
        .offerCodeRedemption(isPresented: $redeemSheetIsPresented) { result in
            // Handle result
        }
    }
}
```

当用户兑换优惠码时，StoreKit 会在 [doc://com.apple.documentation/documentation/StoreKit/Transaction/updates] 中发出相应的事务。请在应用启动后立即设置事务监听器，以便在应用运行时接收新的事务。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠的流程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加用户在此视图内的 StoreKit 视图上点击购买按钮时要执行的操作。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductTask(for:priority:action:)**：声明视图依赖于应用内购买产品，并返回修改后的视图。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品集合，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/offerCodeRedemption(isPresented:onCompletion:)
crawled: 2025-12-02T17:45:45Z
---

# offerCodeRedemption(isPresented:onCompletion:)

**Instance Method**

Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.

## Declaration

```swift
nonisolated func offerCodeRedemption(isPresented: Binding<Bool>, onCompletion: @escaping @MainActor (Result<Void, any Error>) -> Void = { _ in }) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether the system displays the sheet. You set the Boolean value to true to cause the system to display the sheet. The system sets it to false when it dismisses the sheet.
- **onCompletion**: A closure that returns the result of the presentation. In Mac apps built with Mac Catalyst, the completion handler returns a failure with an error prior to macOS 15.

## Discussion

The [offerCodeRedemption(isPresented:onCompletion:)](offercoderedemption_ispresented_oncompletion.zh-Hans.md) method displays a system sheet where customers can enter and redeem offer codes. If you generate offer codes in App Store Connect, call this function to enable customers to redeem the offer. To display the sheet using UIKit, see `presentOfferCodeRedeemSheet(in:)`.



The following code example shows a view that displays the offer code redemption sheet upon a button press:

```swift
import SwiftUI
import StoreKit

struct ContentView: View {
    @State private var redeemSheetIsPresented = false

    var body: some View {
        Button("Present offer code redemption sheet.") {
            redeemSheetIsPresented = true
        }
        .offerCodeRedemption(isPresented: $redeemSheetIsPresented) { result in
            // Handle result
        }
    }
}
```

When customers redeem an offer code, StoreKit emits the resulting transaction in [doc://com.apple.documentation/documentation/StoreKit/Transaction/updates]. Set up a transaction listener as soon as your app launches to receive new transactions while the app is running.

## Interacting with the App Store and Apple Music

- **appStoreOverlay(isPresented:configuration:)**: Presents a StoreKit overlay when a given condition is true.
- **manageSubscriptionsSheet(isPresented:)**
- **refundRequestSheet(for:isPresented:onDismiss:)**: Display the refund request sheet for the given transaction.
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

