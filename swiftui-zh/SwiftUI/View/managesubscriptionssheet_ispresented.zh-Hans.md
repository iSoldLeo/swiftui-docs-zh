--- 来源：https://developer.apple.com/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)

抓取时间：2025-12-02T17:45:44Z

---

# manageSubscriptionsSheet(isPresented:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ manageSubscriptionsSheet(isPresented:) ](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:))

- [ View ](/documentation/swiftui/view)

- manageSubscriptionsSheet(isPresented:) 

实例方法 # manageSubscriptionsSheet(isPresented:)

StoreKitSwiftUIiOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+visionOS 1.0+

```
nonisolated
func manageSubscriptionsSheet(isPresented: Binding<Bool>) -> some View

```

## [另请参阅](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)#see-also)

### [与 App Store 和 Apple 互动]音乐](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)#与 App Store 和 Apple Music 互动)

[`func appStoreOverlay(isPresented: Binding<Bool>, configuration: () -> SKOverlay.Configuration) -> some View`](/documentation/swiftui/view/appstoreoverlay(ispresented:configuration:))当给定条件为真时，显示 StoreKit 叠加层。[`func refundRequestSheet(for: Transaction.ID, isPresented: Binding<Bool>, onDismiss: ((Result<Transaction.RefundRequestStatus, Transaction.RefundRequestError>) -> ())?) -> some View`](/documentation/swiftui/view/refundrequestsheet(for:ispresented:ondismiss:))显示给定交易的退款申请表单。[`func offerCodeRedemption(isPresented: Binding<Bool>, onCompletion: (Result<Void, any Error>) -> Void) -> some View`](/documentation/swiftui/view/offercoderedemption(ispresented:oncompletion:))显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。[`func musicSubscriptionOffer(isPresented: Binding<Bool>, options: MusicSubscriptionOffer.Options, onLoadCompletion: ((any Error)?) -> Void) -> some View`](/documentation/swiftui/view/musicsubscriptionoffer(ispresented:options:onloadcompletion:))当绑定为 `isPresented` 时，启动显示 Apple Music 订阅优惠表单的过程。 `true`.[`func currentEntitlementTask(for: String, priority: TaskPriority, action: (EntitlementTaskState<VerificationResult<Transaction>?>) async -> ()) -> some View`](/documentation/swiftui/view/currententitlementtask(for:priority:action:))声明视图依赖于应用内购买产品的授权，并返回修改后的视图。[`func inAppPurchaseOptions(((Product) async -> Set<Product.PurchaseOption>)?) -> some View`](/documentation/swiftui/view/inapppurchaseoptions(_:))添加一个函数，用于在从该视图内的 StoreKit 视图发起购买之前调用，并提供一组购买选项。[`func manageSubscriptionsSheet(isPresented: Binding<Bool>, subscriptionGroupID: String) -> some View`](/documentation/swiftui/view/managesubscriptionssheet(ispresented:subscriptiongroupid:))[`func onInAppPurchaseCompletion(perform: ((Product, Result<Product.PurchaseResult, any Error>) async -> ())?) -> some View`](/documentation/swiftui/view/oninapppurchasecompletion(perform:))添加一个操作，用于在从该视图内的 StoreKit 视图发起的购买完成时执行。[`func onInAppPurchaseStart(perform: ((Product) async -> ())?) -> some View`](/documentation/swiftui/view/oninapppurchasestart(perform:))添加一个操作，用于在用户触发购买按钮时执行。在此视图内的 StoreKit 视图中。[`func productIconBorder() -> some View`](/documentation/swiftui/view/producticonborder())为应用内购买产品的图标添加标准边框。[`func productViewStyle(some ProductViewStyle) -> some View`](/documentation/swiftui/view/productviewstyle(_:))设置视图内应用内购买产品视图的样式。[`func productDescription(Visibility) -> some View`](/documentation/swiftui/view/productdescription(_:))配置视图内显示应用内购买产品描述的标签的可见性。[`func storeButton(Visibility, for: StoreButtonKind...) -> some View`](/documentation/swiftui/view/storebutton(_:for:))指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。[`func storeProductTask(for: Product.ID, priority: TaskPriority, action: (Product.TaskState) async -> ()) -> some View`](/documentation/swiftui/view/storeproducttask(for:priority:action:))声明视图依赖于应用内购买产品，并返回修改后的视图。 view.[`func storeProductsTask(for: some Collection<String> & Equatable & Sendable, priority: TaskPriority, action: (Product.CollectionTaskState) async -> ()) -> some View`](/documentation/swiftui/view/storeproductstask(for:priority:action:))声明视图依赖于应用内购买产品的集合，并返回修改后的视图。

---
source: https://developer.apple.com/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)
crawled: 2025-12-02T17:45:44Z
---

# manageSubscriptionsSheet(isPresented:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ manageSubscriptionsSheet(isPresented:) ](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:))

- [ View ](/documentation/swiftui/view)

-  manageSubscriptionsSheet(isPresented:) 

Instance Method# manageSubscriptionsSheet(isPresented:)

StoreKitSwiftUIiOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+visionOS 1.0+

```
nonisolated
func manageSubscriptionsSheet(isPresented: Binding<Bool>) -> some View

```

## [See Also](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)#see-also)

### [Interacting with the App Store and Apple Music](/documentation/SwiftUI/View/manageSubscriptionsSheet(isPresented:)#Interacting-with-the-App-Store-and-Apple-Music)

[`func appStoreOverlay(isPresented: Binding<Bool>, configuration: () -> SKOverlay.Configuration) -> some View`](/documentation/swiftui/view/appstoreoverlay(ispresented:configuration:))Presents a StoreKit overlay when a given condition is true.[`func refundRequestSheet(for: Transaction.ID, isPresented: Binding<Bool>, onDismiss: ((Result<Transaction.RefundRequestStatus, Transaction.RefundRequestError>) -> ())?) -> some View`](/documentation/swiftui/view/refundrequestsheet(for:ispresented:ondismiss:))Display the refund request sheet for the given transaction.[`func offerCodeRedemption(isPresented: Binding<Bool>, onCompletion: (Result<Void, any Error>) -> Void) -> some View`](/documentation/swiftui/view/offercoderedemption(ispresented:oncompletion:))Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.[`func musicSubscriptionOffer(isPresented: Binding<Bool>, options: MusicSubscriptionOffer.Options, onLoadCompletion: ((any Error)?) -> Void) -> some View`](/documentation/swiftui/view/musicsubscriptionoffer(ispresented:options:onloadcompletion:))Initiates the process of presenting a sheet with subscription offers for Apple Music when the `isPresented` binding is `true`.[`func currentEntitlementTask(for: String, priority: TaskPriority, action: (EntitlementTaskState<VerificationResult<Transaction>?>) async -> ()) -> some View`](/documentation/swiftui/view/currententitlementtask(for:priority:action:))Declares the view as dependent on the entitlement of an In-App Purchase product, and returns a modified view.[`func inAppPurchaseOptions(((Product) async -> Set<Product.PurchaseOption>)?) -> some View`](/documentation/swiftui/view/inapppurchaseoptions(_:))Add a function to call before initiating a purchase from StoreKit view within this view, providing a set of options for the purchase.[`func manageSubscriptionsSheet(isPresented: Binding<Bool>, subscriptionGroupID: String) -> some View`](/documentation/swiftui/view/managesubscriptionssheet(ispresented:subscriptiongroupid:))[`func onInAppPurchaseCompletion(perform: ((Product, Result<Product.PurchaseResult, any Error>) async -> ())?) -> some View`](/documentation/swiftui/view/oninapppurchasecompletion(perform:))Add an action to perform when a purchase initiated from a StoreKit view within this view completes.[`func onInAppPurchaseStart(perform: ((Product) async -> ())?) -> some View`](/documentation/swiftui/view/oninapppurchasestart(perform:))Add an action to perform when a user triggers the purchase button on a StoreKit view within this view.[`func productIconBorder() -> some View`](/documentation/swiftui/view/producticonborder())Adds a standard border to an in-app purchase product’s icon .[`func productViewStyle(some ProductViewStyle) -> some View`](/documentation/swiftui/view/productviewstyle(_:))Sets the style for In-App Purchase product views within a view.[`func productDescription(Visibility) -> some View`](/documentation/swiftui/view/productdescription(_:))Configure the visibility of labels displaying an in-app purchase product description within the view.[`func storeButton(Visibility, for: StoreButtonKind...) -> some View`](/documentation/swiftui/view/storebutton(_:for:))Specifies the visibility of auxiliary buttons that store view and subscription store view instances may use.[`func storeProductTask(for: Product.ID, priority: TaskPriority, action: (Product.TaskState) async -> ()) -> some View`](/documentation/swiftui/view/storeproducttask(for:priority:action:))Declares the view as dependent on an In-App Purchase product and returns a modified view.[`func storeProductsTask(for: some Collection<String> & Equatable & Sendable, priority: TaskPriority, action: (Product.CollectionTaskState) async -> ()) -> some View`](/documentation/swiftui/view/storeproductstask(for:priority:action:))Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.