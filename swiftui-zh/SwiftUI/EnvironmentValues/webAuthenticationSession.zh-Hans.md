---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/webAuthenticationSession
抓取时间： 2025-12-02T17:45:19Z
---

# 网络身份验证会话

**实例属性**

SwiftUI 环境中提供的值，视图可使用该值通过网络服务对用户进行身份验证。

## 声明

```swift
var webAuthenticationSession: WebAuthenticationSession { get }
```

## 讨论

例如，您可以在用户点击按钮时启动网络身份验证会话：

```swift
struct WebAuthenticationSessionExample: View {
    @Environment(\.webAuthenticationSession) private var webAuthenticationSession

    var body: some View {
        Button("Sign In") {
            Task {
                do {
                    let urlWithToken = try await webAuthenticationSession.authenticate(
                        using: URL(string: "https://www.example.com")!,
                        callbackURLScheme: "x-example-app")
                    try await signIn(using: urlWithToken) // defined elsewhere
                } catch {
                    // code to handle authentication errors
                }
            }
        }
    }
}
```

使用`WebAuthenticationSession/BrowserSession/ephemeral` 要求浏览器不在身份验证会话和用户的正常浏览器会话之间共享 cookie 或其他浏览数据。该请求是否被接受取决于用户的默认网络浏览器。Safari 浏览器始终支持该请求。

```swift
let urlWithToken = try await webAuthenticationSession.authenticate(
    using: URL(string: "https://www.example.com")!,
    callbackURLScheme: "x-example-app",
    preferredBrowserSession: .ephemeral)
```

用户通过身份验证后，身份验证提供程序会将浏览器重定向到使用回调方案的 URL。浏览器检测到重定向后会自动退出，并返回完整的 URL。检查 URL 以确定身份验证的结果：

```swift
let queryItems = URLComponents(string: urlWithToken.absoluteString)?.queryItems
let token = queryItems?.first(where: { $0.name == "token" })?.value
```

上述示例查找的是作为查询参数存储的令牌。您需要进行的具体解析取决于身份验证提供程序如何构建回调 URL。

## 授权和身份验证

- **LocalAuthenticationView**：显示身份验证界面的 SwiftUI 视图。
- **SignInWithAppleButton**：一个 SwiftUI 视图，可创建用于显示的 "使用 Apple 登录 "按钮。
- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（请参阅`SignInWithAppleButton.Style`）。
- **authorizationController**：SwiftUI 环境中提供的值，视图可使用该值执行授权请求。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/webAuthenticationSession
crawled: 2025-12-02T17:45:19Z
---

# webAuthenticationSession

**Instance Property**

A value provided in the SwiftUI environment that views can use to authenticate a user through a web service.

## Declaration

```swift
var webAuthenticationSession: WebAuthenticationSession { get }
```

## Discussion

For example, you can start a web authentication session when the user taps a button:

```swift
struct WebAuthenticationSessionExample: View {
    @Environment(\.webAuthenticationSession) private var webAuthenticationSession

    var body: some View {
        Button("Sign In") {
            Task {
                do {
                    let urlWithToken = try await webAuthenticationSession.authenticate(
                        using: URL(string: "https://www.example.com")!,
                        callbackURLScheme: "x-example-app")
                    try await signIn(using: urlWithToken) // defined elsewhere
                } catch {
                    // code to handle authentication errors
                }
            }
        }
    }
}
```

Use `WebAuthenticationSession/BrowserSession/ephemeral` to request that the browser doesn’t share cookies or other browsing data between the authentication session and the user’s normal browser session. Whether the request is honored depends on the user’s default web browser. Safari always honors the request.

```swift
let urlWithToken = try await webAuthenticationSession.authenticate(
    using: URL(string: "https://www.example.com")!,
    callbackURLScheme: "x-example-app",
    preferredBrowserSession: .ephemeral)
```

After the user authenticates, the authentication provider redirects the browser to a URL that uses the callback scheme. The browser detects the redirect, dismisses itself, and the complete URL will be returned. Inspect the URL to determine the outcome of the authentication:

```swift
let queryItems = URLComponents(string: urlWithToken.absoluteString)?.queryItems
let token = queryItems?.first(where: { $0.name == "token" })?.value
```

The above example looks for a token stored as a query parameter. The specific parsing that you have to do depends on how the authentication provider structures the callback URL.

## Authorizing and authenticating

- **LocalAuthenticationView**: A SwiftUI view that displays an authentication interface.
- **SignInWithAppleButton**: A SwiftUI view that creates the Sign in with Apple button for display.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).
- **authorizationController**: A value provided in the SwiftUI environment that views can use to perform authorization requests.

