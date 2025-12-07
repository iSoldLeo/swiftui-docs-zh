---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialExportManager
抓取时间： 2025-12-03T06:07:40Z
---

# credentialExportManager

**实例属性**

此环境变量用于凭证交换 API 的 SwiftUI 客户端。示例用法如下

## 声明

```swift
var credentialExportManager: ASCredentialExportManager { get }
```

## 讨论

```swift
struct CredentialExchangeManagerExample: View {
    @Environment(\.credentialExchangeManager) private var credentialExchangeManager

    var body: some View {
        Button("Export Credentials") {
            Task {
                do {
                    let credentialData = getCredentialData() // defined elsewhere
                    try await credentialExchangeManager.exportCredentials(credentialData)
                } catch {
                    // code to handle the export error
                }
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialExportManager
crawled: 2025-12-03T06:07:40Z
---

# credentialExportManager

**Instance Property**

This environment variable is for SwiftUI clients of the credential exchange API. An example usage might look like:

## Declaration

```swift
var credentialExportManager: ASCredentialExportManager { get }
```

## Discussion

```swift
struct CredentialExchangeManagerExample: View {
    @Environment(\.credentialExchangeManager) private var credentialExchangeManager

    var body: some View {
        Button("Export Credentials") {
            Task {
                do {
                    let credentialData = getCredentialData() // defined elsewhere
                    try await credentialExchangeManager.exportCredentials(credentialData)
                } catch {
                    // code to handle the export error
                }
            }
        }
    }
}
```

