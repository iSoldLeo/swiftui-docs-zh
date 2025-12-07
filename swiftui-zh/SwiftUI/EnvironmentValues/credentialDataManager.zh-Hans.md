---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialDataManager
抓取时间： 2025-12-03T06:07:39Z
---

# credentialDataManager

**实例属性**

此环境变量用于 ASCredentialDataManager API 的 SwiftUI 客户端。示例用法如下

## 声明

```swift
var credentialDataManager: CredentialDataManager { get }
```

## 讨论

```swift
struct CredentialDataManagerExample: View {
    @Environment(\.credentialDataManager) private var credentialDataManager

    var body: some View {
        Button("Save Credentials") {
            Task {
                do {
                    let credential = getCredential() // defined elsewhere
                    let scope = getScope()
                    try await credentialDataManager.save(credential: credential, for: scope)
                } catch {
                    // code to handle the save error
                }
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/credentialDataManager
crawled: 2025-12-03T06:07:39Z
---

# credentialDataManager

**Instance Property**

This environment variable is for SwiftUI clients of the ASCredentialDataManager API. An example usage might look like:

## Declaration

```swift
var credentialDataManager: CredentialDataManager { get }
```

## Discussion

```swift
struct CredentialDataManagerExample: View {
    @Environment(\.credentialDataManager) private var credentialDataManager

    var body: some View {
        Button("Save Credentials") {
            Task {
                do {
                    let credential = getCredential() // defined elsewhere
                    let scope = getScope()
                    try await credentialDataManager.save(credential: credential, for: scope)
                } catch {
                    // code to handle the save error
                }
            }
        }
    }
}
```

