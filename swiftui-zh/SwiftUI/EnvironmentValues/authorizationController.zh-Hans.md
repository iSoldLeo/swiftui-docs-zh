---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/authorizationController
抓取时间： 2025-12-02T17:45:18Z
---

# authorizationController

**实例属性**

SwiftUI 环境中提供的值，视图可使用该值执行授权请求。

## 声明

```swift
var authorizationController: AuthorizationController { get }
```

## 讨论

例如，您可以在用户点击按钮时执行授权请求：

```swift
struct AuthorizationControllerExample: View {
    @Environment(\.authorizationController) private var authorizationController

    var body: some View {
        Button("Sign In") {
            Task {
                do {
                    async let requests = authorizationRequests() // defined elsewhere
                    let result = try await authorizationController
                        .performRequests(requests)

                    switch result {
                    // code to handle the authorization result
                    }
                } catch {
                    // code to handle the authorization error
                }
            }
        }
    }
}
```

## 授权和验证

- **LocalAuthenticationView**：显示身份验证界面的 SwiftUI 视图。
- **SignInWithAppleButton**：一个 SwiftUI 视图，可创建用于显示的 "使用 Apple 登录 "按钮。
- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（请参阅`SignInWithAppleButton.Style`）。
- **webAuthenticationSession**：在 SwiftUI 环境中提供的值，视图可使用该值通过网络服务验证用户身份。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/authorizationController
crawled: 2025-12-02T17:45:18Z
---

# authorizationController

**Instance Property**

A value provided in the SwiftUI environment that views can use to perform authorization requests.

## Declaration

```swift
var authorizationController: AuthorizationController { get }
```

## Discussion

For example, you can perform authorization requests when the user taps a button:

```swift
struct AuthorizationControllerExample: View {
    @Environment(\.authorizationController) private var authorizationController

    var body: some View {
        Button("Sign In") {
            Task {
                do {
                    async let requests = authorizationRequests() // defined elsewhere
                    let result = try await authorizationController
                        .performRequests(requests)

                    switch result {
                    // code to handle the authorization result
                    }
                } catch {
                    // code to handle the authorization error
                }
            }
        }
    }
}
```

## Authorizing and authenticating

- **LocalAuthenticationView**: A SwiftUI view that displays an authentication interface.
- **SignInWithAppleButton**: A SwiftUI view that creates the Sign in with Apple button for display.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).
- **webAuthenticationSession**: A value provided in the SwiftUI environment that views can use to authenticate a user through a web service.

