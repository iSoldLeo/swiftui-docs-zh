--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transactionTask(_:action:)

抓取时间：2025-11-30T21:11:22Z

---

# transactionTask(_:action:)

**实例方法**

提供一个在此视图显示之前要执行的任务

## 声明

```swift
nonisolated func transactionTask(_ configuration: CredentialTransaction.Configuration?, action: @escaping (CredentialTransaction) async -> Void) -> some View

```

## 参数

- **configuration**：包含事务任务信息的配置。当任务完成或在执行任务时遇到错误时，系统将使此配置失效，并且 `CredentialTransaction` 也将失效。

- **action**：当 `isPerformingTransaction` 为 `true` 时将调用的闭包。它提供一个可用于执行事务的 `CredentialTransaction` 实例。

## 讨论

此任务提供一个 `CredentialTransaction` 实例，用于执行事务。

典型的客户端应按以下顺序使用 API：

1. 在显示任何专有支付界面之前使用 `acquirePresentmentIntentAssertion()`

2. 在调用交易 API 之前使用 `relinquish()` 进行断言

3. 在提供凭证之后使用 `configuration.invalidate()`

4. （可选）使用 `acquirePresentmentIntentAssertion()` 完成任何专有支付界面

5. 使用 `relinquish()` 进行断言

例如：

```swift
 struct TransactionView: View {
     @State private var configuration: CredentialTransaction.Configuration?
     private var assertion: PresentmentIntentAssertion // acquirePresentmentIntentAssertion() before transitioning into this view (step 1)
     private var activeSession: CredentialSession
     private var selectedCredential: Credential

     var body: some View {
         VStack {
             Button("Perform Transaction") {
                 guard let configuration else {
                    configuration = activeSession.configuration()
                    return
                 }

                 configuration.invalidate() // step 3
                 // Optional
                 assertion = try await session.acquirePresentmentIntentAssertion() // step 4
                 // handle any proprietary UI
                 try await assertion.relinquish() // step 5
                 // Optional end
             }
             .transactionTask(configuration) { transaction in
                 do {
                     try await assertion.relinquish() // step 2
                     try await transaction.performTransaction(using: selectedCredential)
                 } catch {
                     // code to handle error
                 }
             }
         }
     }
 }
```

## 访问 Apple Pay 和 Apple Wallet

- **PayWithApplePayButton**：提供一个按钮，用于使用 Apple Pay 付款。

- **AddPassToWalletButton**：提供一个按钮，允许用户向 Apple Wallet 添加新的或现有的通行证。

- **VerifyIdentityWithWalletButton**：用于显示身份验证流程按钮的类型。

- **addOrderToWalletButtonStyle(_:)**：设置按钮的样式。

- **addPassToWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKAddPassButtonStyle`）。

- **onApplePayCouponCodeChange(perform:)**：当用户输入或更新优惠券代码时调用。如果要求用户提供优惠券代码，则此参数为必填项。

- **onApplePayPaymentMethodChange(perform:)**：当付款方式更改并要求更新付款请求时调用。如果未提供此参数，Wallet 将假定付款方式有效。

- **onApplePayShippingContactChange(perform:)**：当用户选择收货地址时调用。如果要求用户提供收货联系人，则此参数为必填项。

- **onApplePayShippingMethodChange(perform:)**：当用户选择配送方式时调用。如果系统要求用户提供配送方式，则此函数为必填项。

- **payLaterViewAction(_:)**：设置“先付后付”视图的操作。参见 `PKPayLaterAction`。

- **payLaterViewDisplayStyle(_:)**：设置“先付后付”视图的显示样式。参见 `PKPayLaterDisplayStyle`。

- **payWithApplePayButtonStyle(_:)**：设置按钮的样式。（参见 `PayWithApplePayButtonStyle`）

- **verifyIdentityWithWalletButtonStyle(_:)**：设置按钮的样式。（参见 `PKIdentityButtonStyle`）

- **AsyncShareablePassConfiguration**


---
source: https://developer.apple.com/documentation/SwiftUI/View/transactionTask(_:action:)
crawled: 2025-11-30T21:11:22Z
---

# transactionTask(_:action:)

**Instance Method**

Provides a task to perform before this view appears

## Declaration

```swift
nonisolated func transactionTask(_ configuration: CredentialTransaction.Configuration?, action: @escaping (CredentialTransaction) async -> Void) -> some View

```

## Parameters

- **configuration**: A configuration containing information about the transaction task. When the task is completed or an error is encountered while performing the task, the system invalidates this configuration, and the `CredentialTransaction` is invalidated.
- **action**: A closure that will be called when `isPerformingTransaction` is `true`. It provides a `CredentialTransaction` instance that can be used to perform transactions.

## Discussion

This task provides an instance of a `CredentialTransaction` to be used to perform transactions.

A typical client should use the APIs in the following sequence:

1. `acquirePresentmentIntentAssertion()` prior to showing any proprietary payment UI
2. `relinquish()` the assertion before invoking the transaction API
3. `configuration.invalidate()` after presenting the credential
4. Optionally, `acquirePresentmentIntentAssertion()` to finish up any proprietary payment UI
5. `relinquish()` the assertion

For example:

```swift
 struct TransactionView: View {
     @State private var configuration: CredentialTransaction.Configuration?
     private var assertion: PresentmentIntentAssertion // acquirePresentmentIntentAssertion() before transitioning into this view (step 1)
     private var activeSession: CredentialSession
     private var selectedCredential: Credential

     var body: some View {
         VStack {
             Button("Perform Transaction") {
                 guard let configuration else {
                    configuration = activeSession.configuration()
                    return
                 }

                 configuration.invalidate() // step 3
                 // Optional
                 assertion = try await session.acquirePresentmentIntentAssertion() // step 4
                 // handle any proprietary UI
                 try await assertion.relinquish() // step 5
                 // Optional end
             }
             .transactionTask(configuration) { transaction in
                 do {
                     try await assertion.relinquish() // step 2
                     try await transaction.performTransaction(using: selectedCredential)
                 } catch {
                     // code to handle error
                 }
             }
         }
     }
 }
```

## Accessing Apple Pay and Wallet

- **PayWithApplePayButton**: A type that provides a button to pay with Apple pay.
- **AddPassToWalletButton**: A type that provides a button that enables people to add a new or existing pass to Apple Wallet.
- **VerifyIdentityWithWalletButton**: A type that displays a button to present the identity verification flow.
- **addOrderToWalletButtonStyle(_:)**: Sets the button’s style.
- **addPassToWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKAddPassButtonStyle`).
- **onApplePayCouponCodeChange(perform:)**: Called when a user has entered or updated a coupon code. This is required if the user is being asked to provide a coupon code.
- **onApplePayPaymentMethodChange(perform:)**: Called when a payment method has changed and asks for an update payment request. If this modifier isn’t provided Wallet will assume the payment method is valid.
- **onApplePayShippingContactChange(perform:)**: Called when a user selected a shipping address. This is required if the user is being asked to provide a shipping contact.
- **onApplePayShippingMethodChange(perform:)**: Called when a user selected a shipping method. This is required if the user is being asked to provide a shipping method.
- **payLaterViewAction(_:)**: Sets the action on the PayLaterView. See `PKPayLaterAction`.
- **payLaterViewDisplayStyle(_:)**: Sets the display style on the PayLaterView. See `PKPayLaterDisplayStyle`.
- **payWithApplePayButtonStyle(_:)**: Sets the style to be used by the button. (see `PayWithApplePayButtonStyle`).
- **verifyIdentityWithWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKIdentityButtonStyle`).
- **AsyncShareablePassConfiguration**

