--- 来源：https://developer.apple.com/documentation/SwiftUI/View/signInWithAppleButtonStyle(_:)

抓取时间：2025-12-02T17:25:21Z

---

# signInWithAppleButtonStyle(_:)

**实例方法**

设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。

## 声明

```swift
nonisolated func signInWithAppleButtonStyle(_ style: SignInWithAppleButton.Style) -> some View

```

## 参数

- **style**：要应用于此按钮的登录样式。

## 授权和身份验证

- **LocalAuthenticationView**：显示身份验证界面的 SwiftUI 视图。

- **SignInWithAppleButton**：创建用于显示的“使用 Apple 登录”按钮的 SwiftUI 视图。

- **authorizationController**：SwiftUI 环境中提供的一个值，视图可以使用该值来执行授权请求。

- **webAuthenticationSession**：SwiftUI 环境中提供的一个值，视图可以使用该值通过 Web 服务对用户进行身份验证。


---
source: https://developer.apple.com/documentation/SwiftUI/View/signInWithAppleButtonStyle(_:)
crawled: 2025-12-02T17:25:21Z
---

# signInWithAppleButtonStyle(_:)

**Instance Method**

Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

## Declaration

```swift
nonisolated func signInWithAppleButtonStyle(_ style: SignInWithAppleButton.Style) -> some View

```

## Parameters

- **style**: The sign in style to apply to this button.

## Authorizing and authenticating

- **LocalAuthenticationView**: A SwiftUI view that displays an authentication interface.
- **SignInWithAppleButton**: A SwiftUI view that creates the Sign in with Apple button for display.
- **authorizationController**: A value provided in the SwiftUI environment that views can use to perform authorization requests.
- **webAuthenticationSession**: A value provided in the SwiftUI environment that views can use to authenticate a user through a web service.

