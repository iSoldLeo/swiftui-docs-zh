--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onApplePayPaymentMethodChange(perform:)

抓取时间：2025-12-02T17:24:52Z

---

# onApplePayPaymentMethodChange(perform:)

**实例方法**

当支付方式发生更改并请求更新支付请求时调用。如果未提供此修饰符，Wallet 将假定该支付方式有效。

## 声明

```swift
nonisolated func onApplePayPaymentMethodChange(perform action: @escaping (PKPaymentMethod) async -> PKPaymentRequestPaymentMethodUpdate) -> some View

```

## 返回值

支付请求方法的更新。

## 访问 Apple Pay 和 Wallet

- **PayWithApplePayButton**：提供一个用于使用 Apple Pay 付款的按钮的类型。

- **AddPassToWalletButton**：提供一个允许用户向 Apple Wallet 添加新卡或现有卡的按钮的类型。

- **VerifyIdentityWithWalletButton**：用于显示身份验证流程按钮的类型。

- **addOrderToWalletButtonStyle(_:)**：设置按钮的样式。

- **addPassToWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKAddPassButtonStyle`）。

- **onApplePayCouponCodeChange(perform:)**：当用户输入或更新优惠券代码时调用。如果系统要求用户提供优惠券代码，则此参数为必填项。

- **onApplePayShippingContactChange(perform:)**：当用户选择收货地址时调用。如果系统要求用户提供收货联系人信息，则此参数为必填项。

- **onApplePayShippingMethodChange(perform:)**：当用户选择配送方式时调用。如果系统要求用户提供配送方式，则此参数为必填项。

- **payLaterViewAction(_:)**：设置 PayLaterView 的操作。参见 `PKPayLaterAction`。

- **payLaterViewDisplayStyle(_:)**：设置 PayLaterView 的显示样式。参见 `PKPayLaterDisplayStyle`。

- **payWithApplePayButtonStyle(_:)**：设置按钮使用的样式。（参见 `PayWithApplePayButtonStyle`）

- **verifyIdentityWithWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKIdentityButtonStyle`）

- **AsyncShareablePassConfiguration**

- **transactionTask(_:action:)**：提供在此视图显示之前要执行的任务


---
source: https://developer.apple.com/documentation/SwiftUI/View/onApplePayPaymentMethodChange(perform:)
crawled: 2025-12-02T17:24:52Z
---

# onApplePayPaymentMethodChange(perform:)

**Instance Method**

Called when a payment method has changed and asks for an update payment request. If this modifier isn’t provided Wallet will assume the payment method is valid.

## Declaration

```swift
nonisolated func onApplePayPaymentMethodChange(perform action: @escaping (PKPaymentMethod) async -> PKPaymentRequestPaymentMethodUpdate) -> some View

```

## Return Value

An update to the payment request method.

## Accessing Apple Pay and Wallet

- **PayWithApplePayButton**: A type that provides a button to pay with Apple pay.
- **AddPassToWalletButton**: A type that provides a button that enables people to add a new or existing pass to Apple Wallet.
- **VerifyIdentityWithWalletButton**: A type that displays a button to present the identity verification flow.
- **addOrderToWalletButtonStyle(_:)**: Sets the button’s style.
- **addPassToWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKAddPassButtonStyle`).
- **onApplePayCouponCodeChange(perform:)**: Called when a user has entered or updated a coupon code. This is required if the user is being asked to provide a coupon code.
- **onApplePayShippingContactChange(perform:)**: Called when a user selected a shipping address. This is required if the user is being asked to provide a shipping contact.
- **onApplePayShippingMethodChange(perform:)**: Called when a user selected a shipping method. This is required if the user is being asked to provide a shipping method.
- **payLaterViewAction(_:)**: Sets the action on the PayLaterView. See `PKPayLaterAction`.
- **payLaterViewDisplayStyle(_:)**: Sets the display style on the PayLaterView. See `PKPayLaterDisplayStyle`.
- **payWithApplePayButtonStyle(_:)**: Sets the style to be used by the button. (see `PayWithApplePayButtonStyle`).
- **verifyIdentityWithWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKIdentityButtonStyle`).
- **AsyncShareablePassConfiguration**
- **transactionTask(_:action:)**: Provides a task to perform before this view appears

