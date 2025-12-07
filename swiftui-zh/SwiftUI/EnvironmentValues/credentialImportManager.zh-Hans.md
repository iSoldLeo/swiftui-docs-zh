---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialImportManager
抓取时间： 2025-12-03T06:07:41Z
---

# credentialImportManager

**实例属性**

此环境变量用于凭证交换 API 的 SwiftUI 客户端。示例用法如下

## 声明

```swift
var credentialImportManager: ASCredentialImportManager { get }
```

## 讨论

```swift
struct CredentialImportManagerExample: View {
    @Environment(\.credentialImportManager) private var credentialImportManager

    var body: some View {
        content // defined elsewhere
            .onContinueUserActivity(ASCredentialExchangeActivityType) { activity in
                Task {
                    do {
                        guard let token = activity.userInfo?[ASCredentialImportToken] as? UUID else { return }
                        let credentialData = try await credentialImportManager.importCredentials(token: token)
                        // do something with the data
                    } catch {
                        // code to handle the import error
                    }
                }
            }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialImportManager
crawled: 2025-12-03T06:07:41Z
---

# credentialImportManager

**Instance Property**

This environment variable is for SwiftUI clients of the credential exchange API. An example usage might look like:

## Declaration

```swift
var credentialImportManager: ASCredentialImportManager { get }
```

## Discussion

```swift
struct CredentialImportManagerExample: View {
    @Environment(\.credentialImportManager) private var credentialImportManager

    var body: some View {
        content // defined elsewhere
            .onContinueUserActivity(ASCredentialExchangeActivityType) { activity in
                Task {
                    do {
                        guard let token = activity.userInfo?[ASCredentialImportToken] as? UUID else { return }
                        let credentialData = try await credentialImportManager.importCredentials(token: token)
                        // do something with the data
                    } catch {
                        // code to handle the import error
                    }
                }
            }
    }
}
```

