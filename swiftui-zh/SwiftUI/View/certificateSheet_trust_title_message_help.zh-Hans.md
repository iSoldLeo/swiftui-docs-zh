--- 来源：https://developer.apple.com/documentation/SwiftUI/View/certificateSheet(trust:title:message:help:)

抓取时间：2025-12-02T17:22:38Z

---

# certificateSheet(trust:title:message:help:)

**实例方法**

使用提供的证书信任关系显示证书信息页。

## 声明

```swift
@MainActor @preconcurrency func certificateSheet(trust: Binding<SecTrust?>, title: String? = nil, message: String? = nil, help: URL? = nil) -> some View

```

## 参数

- **trust**：绑定到使用 SecTrustCreateWithCertificates 创建的 SecTrust 引用（参见 <Security/SecTrust.h>），用于确定是否显示证书信息页。

- **title**：要显示的标题。如果为 nil，则使用默认标题。

- **message**：要显示的消息。如果为空，则使用默认消息。

- **help**：“了解更多”按钮的 URL。如果为空，则使用默认 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/View/certificateSheet(trust:title:message:help:)
crawled: 2025-12-02T17:22:38Z
---

# certificateSheet(trust:title:message:help:)

**Instance Method**

Displays a certificate sheet using the provided certificate trust.

## Declaration

```swift
@MainActor @preconcurrency func certificateSheet(trust: Binding<SecTrust?>, title: String? = nil, message: String? = nil, help: URL? = nil) -> some View

```

## Parameters

- **trust**: A binding to a SecTrust reference created with SecTrustCreateWithCertificates (see <Security/SecTrust.h>) that determines whether to present the certificate sheet.
- **title**: The title to display. Uses a default title if nil.
- **message**: The message to display. Uses a default message if nil.
- **help**: URL for the “Learn More” button. Uses a default URL if nil.

