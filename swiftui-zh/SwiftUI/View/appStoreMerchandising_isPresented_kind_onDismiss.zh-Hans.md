--- 来源：https://developer.apple.com/documentation/SwiftUI/View/appStoreMerchandising(isPresented:kind:onDismiss:)

抓取时间：2025-12-02T17:22:30Z

---

# appStoreMerchandising(isPresented:kind:onDismiss:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ appStoreMerchandising(isPresented:kind:onDismiss:) ](/documentation/SwiftUI/View/appStoreMerchandising(isPresented:kind:onDismiss:))

- [ View ](/documentation/swiftui/view)

- appStoreMerchandising(isPresented:kind:onDismiss:) 

实例方法# appStoreMerchandising(isPresented:kind:onDismiss:)

StoreKitSwiftUIiOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.2+BetatvOS 26.0+

```
nonisolated
func appStoreMerchandising(
    isPresented: Binding<Bool>,
    kind: AppStoreMerchandisingKind,
    onDismiss: ((Result<AppStoreMerchandisingKind.PresentationResult, any Error>) async -> ())? = nil
) -> some View

```

Beta 版软件

本文档包含有关正在开发中的 API 或技术的初步信息。此信息可能会有所变更，根据本文档实现的软件应使用最终操作系统软件进行测试。

[了解更多关于使用 Apple 测试版软件的信息](https://developer.apple.com/support/beta-software/)

---
source: https://developer.apple.com/documentation/SwiftUI/View/appStoreMerchandising(isPresented:kind:onDismiss:)
crawled: 2025-12-02T17:22:30Z
---

# appStoreMerchandising(isPresented:kind:onDismiss:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ appStoreMerchandising(isPresented:kind:onDismiss:) ](/documentation/SwiftUI/View/appStoreMerchandising(isPresented:kind:onDismiss:))

- [ View ](/documentation/swiftui/view)

-  appStoreMerchandising(isPresented:kind:onDismiss:) 

Instance Method# appStoreMerchandising(isPresented:kind:onDismiss:)

StoreKitSwiftUIiOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.2+BetatvOS 26.0+

```
nonisolated
func appStoreMerchandising(
    isPresented: Binding<Bool>,
    kind: AppStoreMerchandisingKind,
    onDismiss: ((Result<AppStoreMerchandisingKind.PresentationResult, any Error>) async -> ())? = nil
) -> some View

```

Beta Software

 This documentation contains preliminary information about an API or technology in development. This information is subject to change, and software implemented according to this documentation should be tested with final operating system software. 

[ Learn more about using Apple's beta software ](https://developer.apple.com/support/beta-software/)