---
来源： https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/SharingBehavior
抓取时间： 2025-12-03T05:31:52Z
---

# OpenWindowAction.SharingBehavior | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ OpenWindowAction ](/documentation/swiftui/openwindowaction)

- [ OpenWindowAction.SharingBehavior ](/documentation/SwiftUI/OpenWindowAction/SharingBehavior)

- [ OpenWindowAction ](/documentation/swiftui/openwindowaction)

- OpenWindowAction.SharingBehavior

结构# OpenWindowAction.SharingBehavior

macOS 15.0+

```
struct SharingBehavior
```

## [主题](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#topics)

### [类型属性](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#Type-Properties)

[`static let requested: OpenWindowAction.SharingBehavior`](/documentation/swiftui/openwindowaction/sharingbehavior/requested)如果有可用的共享会话，并且使用您应用程序的人确认了共享提议，则窗口将被共享。无论共享是否成功，窗口都将被打开。[`static let required: OpenWindowAction.SharingBehavior`](/documentation/swiftui/openwindowaction/sharingbehavior/required)如果有可用的共享会话，并且使用您应用程序的人确认了共享提议，窗口将被共享。只有共享成功后，窗口才会打开。##[关系](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#relationships)

### [符合](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#conforms-to)

- [⟦ic_0003⟧](⟦lu_0007⟧)

- [⟦ic_0002⟧](⟦lu_0006⟧)

---
source: https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/SharingBehavior
crawled: 2025-12-03T05:31:52Z
---

# OpenWindowAction.SharingBehavior | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ OpenWindowAction ](/documentation/swiftui/openwindowaction)

- [ OpenWindowAction.SharingBehavior ](/documentation/SwiftUI/OpenWindowAction/SharingBehavior)

- [ OpenWindowAction ](/documentation/swiftui/openwindowaction)

-  OpenWindowAction.SharingBehavior 

Structure# OpenWindowAction.SharingBehavior

macOS 15.0+

```
struct SharingBehavior
```

## [Topics](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#topics)

### [Type Properties](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#Type-Properties)

[`static let requested: OpenWindowAction.SharingBehavior`](/documentation/swiftui/openwindowaction/sharingbehavior/requested)The window will be shared if there is an available sharing session and the person using your app confirms the offer to share. The window will be opened regardless of whether sharing succeeds.[`static let required: OpenWindowAction.SharingBehavior`](/documentation/swiftui/openwindowaction/sharingbehavior/required)The window will be shared if there is an available sharing session and the person using your app confirms the offer to share. The window will only be opened if sharing succeeds.## [Relationships](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#relationships)

### [Conforms To](/documentation/SwiftUI/OpenWindowAction/SharingBehavior#conforms-to)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)