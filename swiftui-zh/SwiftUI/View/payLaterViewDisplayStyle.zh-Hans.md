--- 来源：https://developer.apple.com/documentation/SwiftUI/View/payLaterViewDisplayStyle(_:)

抓取时间：2025-11-30T21:10:09Z

---

# payLaterViewDisplayStyle(_:)

**实例方法**

设置 PayLaterView 的显示样式。参见 `PKPayLaterDisplayStyle`。

## 声明

```swift
nonisolated func payLaterViewDisplayStyle(_ displayStyle: PayLaterViewDisplayStyle) -> some View

```

## 访问 Apple Pay 和钱包

- **PayWithApplePayButton**：提供一个按钮，用于使用 Apple Pay 付款。

- **AddPassToWalletButton**：提供一个按钮，允许用户将新卡或现有卡添加到 Apple 钱包。

- **VerifyIdentityWithWalletButton**：提供一个按钮，用于显示身份验证流程。

- **addOrderToWalletButtonStyle(_:)**：设置按钮样式。

- **addPassToWalletButtonStyle(_:)**：设置按钮使用的样式。（参见 `PKAddPassButtonStyle`）。

- **onApplePayCouponCodeChange(perform:)**：当用户输入或更新优惠券代码时调用。如果要求用户提供优惠券代码，则此参数为必填项。

- **onApplePayPaymentMethodChange(perform:)**：当付款方式更改并请求更新付款请求时调用。如果未提供此参数，钱包将假定付款方式有效。

- **onApplePayShippingContactChange(perform:)**：当用户选择收货地址时调用。如果要求用户提供收货联系人，则此参数为必填项。

- **onApplePayShippingMethodChange(perform:)**：当用户选择配送方式时调用。如果要求用户提供配送方式，则此项为必填项。

- **payLaterViewAction(_:)**：设置“稍后付款”视图的操作。参见 `PKPayLaterAction`。

- **payWithApplePayButtonStyle(_:)**：设置按钮的样式。（参见 `PayWithApplePayButtonStyle`）

- **verifyIdentityWithWalletButtonStyle(_:)**：设置按钮的样式。（参见 `PKIdentityButtonStyle`）

- **AsyncShareablePassConfiguration**

- **transactionTask(_:action:)**：提供在此视图显示之前要执行的任务


---
source: https://developer.apple.com/documentation/SwiftUI/View/payLaterViewDisplayStyle(_:)
crawled: 2025-11-30T21:10:09Z
---

# payLaterViewDisplayStyle(_:)

**Instance Method**

Sets the display style on the PayLaterView. See `PKPayLaterDisplayStyle`.

## Declaration

```swift
nonisolated func payLaterViewDisplayStyle(_ displayStyle: PayLaterViewDisplayStyle) -> some View

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
- **payWithApplePayButtonStyle(_:)**: Sets the style to be used by the button. (see `PayWithApplePayButtonStyle`).
- **verifyIdentityWithWalletButtonStyle(_:)**: Sets the style to be used by the button. (see `PKIdentityButtonStyle`).
- **AsyncShareablePassConfiguration**
- **transactionTask(_:action:)**: Provides a task to perform before this view appears

