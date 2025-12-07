---
来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:defaultValue:)
抓取时间：2025-12-02T21:47:45Z
---

# init(id:for:makeContent:defaultValue:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- init(id:for:makeContent:defaultValue:) ](/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:defaultValue:))

- [ 沉浸式空间 ](/documentation/swiftui/immersivespace)

- init(id:for:makeContent:defaultValue:)

Initializer# init(id:for:makeContent:defaultValue:)

visionOS 26.0+

```
nonisolated
init<C>(
    id: String,
    for type: Data.Type = Data.self,
    @CompositorContentBuilder makeContent: @escaping (Binding<Data>) -> C,
    defaultValue: @escaping () -> Data
) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

当 `Content` 符合 `ImmersiveSpaceContent`, `Data` 符合 `Decodable`, `Data` 符合 `Encodable`, `Data` 符合 `Hashable` 时可用。

---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:defaultValue:)
crawled: 2025-12-02T21:47:45Z
---

# init(id:for:makeContent:defaultValue:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

- [ init(id:for:makeContent:defaultValue:) ](/documentation/SwiftUI/ImmersiveSpace/init(id:for:makeContent:defaultValue:))

- [ ImmersiveSpace ](/documentation/swiftui/immersivespace)

-  init(id:for:makeContent:defaultValue:) 

Initializer# init(id:for:makeContent:defaultValue:)

visionOS 26.0+

```
nonisolated
init<C>(
    id: String,
    for type: Data.Type = Data.self,
    @CompositorContentBuilder makeContent: @escaping (Binding<Data>) -> C,
    defaultValue: @escaping () -> Data
) where Content == CompositorContentBuilder.Content<C>, C : CompositorContent
```

Available when `Content` conforms to `ImmersiveSpaceContent`, `Data` conforms to `Decodable`, `Data` conforms to `Encodable`, and `Data` conforms to `Hashable`.