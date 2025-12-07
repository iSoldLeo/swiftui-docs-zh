---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:)
抓取时间：2025-12-02T21:47:39Z
---

# init(id:for:makeContent:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- [ init(id:for:makeContent:) ](/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:))

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- init(id:for:makeContent:)

Initializer# init(id:for:makeContent:)

visionOS 26.0+

```
nonisolated
init<C>(
    id: String,
    for type: Data.Type,
    @CompositorContentBuilder makeContent: @escaping (Binding<Data?>) -> C
) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

当 `Content` 符合 `ImmersiveSpaceContent`, `Data` 符合 `Decodable`, `Data` 符合 `Encodable`, `Data` 符合 `Hashable` 时可用。

---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:)
crawled: 2025-12-02T21:47:39Z
---

# init(id:for:makeContent:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

- [ init(id:for:makeContent:) ](/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:))

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

-  init(id:for:makeContent:) 

Initializer# init(id:for:makeContent:)

visionOS 26.0+

```
nonisolated
init<C>(
    id: String,
    for type: Data.Type,
    @CompositorContentBuilder makeContent: @escaping (Binding<Data?>) -> C
) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

Available when `Content` conforms to `ImmersiveSpaceContent`, `Data` conforms to `Decodable`, `Data` conforms to `Encodable`, and `Data` conforms to `Hashable`.