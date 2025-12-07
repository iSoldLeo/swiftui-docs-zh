---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(makeContent:)
抓取时间： 2025-12-02T21:47:52Z
---

# init(makeContent:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- [ init(makeContent:) ](/documentation/SwiftUI/ImmersiveSpace/init(makeContent:))

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- init(makeContent:)

初始化器# init(makeContent:)

visionOS 26.0+

```
nonisolated
init<C>(@CompositorContentBuilder makeContent: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

当 `Content` 符合 `ImmersiveSpaceContent`, `Data` 符合 `Decodable`, `Data` 符合 `Encodable`, `Data` 符合 `Hashable` 时可用。

---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(makeContent:)
crawled: 2025-12-02T21:47:52Z
---

# init(makeContent:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

- [ init(makeContent:) ](/documentation/SwiftUI/ImmersiveSpace/init(makeContent:))

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

-  init(makeContent:) 

Initializer# init(makeContent:)

visionOS 26.0+

```
nonisolated
init<C>(@CompositorContentBuilder makeContent: @escaping () -> C) where Content == CompositorContentBuilder.Content<C>, Data == Never, C : CompositorContent
```

Available when `Content` conforms to `ImmersiveSpaceContent`, `Data` conforms to `Decodable`, `Data` conforms to `Encodable`, and `Data` conforms to `Hashable`.