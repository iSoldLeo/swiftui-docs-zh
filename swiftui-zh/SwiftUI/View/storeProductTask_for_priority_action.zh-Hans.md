--- 来源：https://developer.apple.com/documentation/swiftui/view/storeproducttask(for:priority:action:)

抓取时间：2025-12-03T05:37:11Z

---

# storeProductTask(for:priority:action:)

**实例方法**

声明视图依赖于应用内购买产品，并返回修改后的视图。

## 声明

```swift
nonisolated func storeProductTask(for id: Product.ID, priority: TaskPriority = .medium, action: @escaping (Product.TaskState) async -> ()) -> some View

```

## 参数

- **id**：要从 App Store 加载的产品 ID。此参数更改时，任务将重新启动。

- **priority**：创建任务时使用的任务优先级。

- **action**：任务状态更改时要执行的操作。

## 讨论

在使用此方法修改的视图显示之前，后台会启动一个任务，从 App Store 加载产品。视图显示期间，每当产品发生变化或任务状态发生变化时，该任务都会调用 `action`。

## 与 App Store 和 Apple Music 交互

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 覆盖层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示给定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，客户可以通过该表单兑换您在 App Store Connect 中配置的优惠码。

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当绑定为 `true` 时，启动显示 Apple Music 订阅优惠的流程。

- **currentEntitlementTask(for:priority:action:)**：声明视图依赖于应用内购买产品的授权，并返回修改后的视图。

- **inAppPurchaseOptions(_:)**：添加一个函数，用于在从此视图内的 StoreKit 视图发起购买之前调用，并提供一组购买选项。

- **manageSubscriptionsSheet(isPresented:subscriptionGroupID:)**

- **onInAppPurchaseCompletion(perform:)**：添加一个操作，用于在从此视图内的 StoreKit 视图发起的购买完成后执行。

- **onInAppPurchaseStart(perform:)**：添加一个操作，用于在用户点击此视图内的 StoreKit 视图上的购买按钮时执行。

- **productIconBorder()**：为应用内购买产品的图标添加标准边框。

- **productViewStyle(_:)**：设置视图内应用内购买产品视图的样式。

- **productDescription(_:)**：配置视图内显示应用内购买产品描述的标签的可见性。

- **storeButton(_:for:)**：指定商店视图和订阅商店视图实例可以使用的辅助按钮的可见性。

- **storeProductsTask(for:priority:action:)**：声明视图依赖于应用内购买产品集合，并返回修改后的视图。


---
source: https://developer.apple.com/documentation/swiftui/view/storeproducttask(for:priority:action:)
crawled: 2025-12-03T05:37:11Z
---

# storeProductTask(for:priority:action:)

**Instance Method**

Declares the view as dependent on an In-App Purchase product and returns a modified view.

## Declaration

```swift
nonisolated func storeProductTask(for id: Product.ID, priority: TaskPriority = .medium, action: @escaping (Product.TaskState) async -> ()) -> some View

```

## Parameters

- **id**: The product ID to load from the App Store. The task restarts whenever this parameter changes.
- **priority**: The task priority to use when creating the task.
- **action**: The action to perform when the task’s state changes.

## Discussion

Before a view modified with this method appears, a task will start in the background to load the product from the App Store. While the view is presented, the task will call `action` whenever the product changes or the task’s state changes.

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
- **storeProductsTask(for:priority:action:)**: Declares the view as dependent on a collection of In-App Purchase products and returns a modified view.

