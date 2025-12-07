---
来源： https://developer.apple.com/documentation/SwiftUI/DropSession
抓取时间： 2025-12-02T17:42:45Z
---

# DropSession | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ DropSession ](/documentation/SwiftUI/DropSession)

- 删除会话

结构# DropSession

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+visionOS 26.0+

```
struct DropSession
```

## [主题](/documentation/SwiftUI/DropSession#topics)

### [结构](/documentation/SwiftUI/DropSession#Structures)

[`struct ID`](/documentation/swiftui/dropsession/id-swift.struct)拖动会话的标识符。[`struct LocalSession`](/documentation/swiftui/dropsession/localsession-swift.struct)描述源于应用程序内部的会话。### [实例属性](/documentation/SwiftUI/DropSession#Instance-Properties)

[`var id: DropSession.ID`](/documentation/swiftui/dropsession/id-swift.property)下拉会话的唯一标识符。 [`var itemsCount: Int`](/documentation/swiftui/dropsession/itemscount)下拉的项目数。[`var localSession: DropSession.LocalSession?`](/documentation/swiftui/dropsession/localsession-swift.property)提供有关会话的附加信息（如果该会话源自应用程序内部）。[`var location: CGPoint`](/documentation/swiftui/dropsession/location)空投在本地坐标空间中的位置[`var phase: DropSession.Phase`](/documentation/swiftui/dropsession/phase-swift.property)当前空投会话的阶段。[`var size: CGSize`](/documentation/swiftui/dropsession/size)拖放目标视图的大小。 [`var suggestedOperations: DropOperation.Set`](/documentation/swiftui/dropsession/suggestedoperations)拖放源建议的操作。

[`enum Phase`](/documentation/swiftui/dropsession/phase-swift.enum)The phase of the current drop session.### [Relationships](/documentation/SwiftUI/DropSession#relationships)

### [符合](/documentation/SwiftUI/DropSession#conforms-to)

- [⟦ic_0005⟧](⟦lu_0021⟧)

- [⟦ic_0004⟧](⟦lu_0020⟧)

- [⟦ic_0003⟧](⟦lu_0019⟧)

## [See Also](/documentation/SwiftUI/DropSession#see-also)

### [移动项目](/documentation/SwiftUI/DropSession#Moving-items)

[`struct DragSession`](/documentation/swiftui/dragsession)描述正在进行的拖动会话。

---
source: https://developer.apple.com/documentation/SwiftUI/DropSession
crawled: 2025-12-02T17:42:45Z
---

# DropSession | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ DropSession ](/documentation/SwiftUI/DropSession)

-  DropSession 

Structure# DropSession

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+visionOS 26.0+

```
struct DropSession
```

## [Topics](/documentation/SwiftUI/DropSession#topics)

### [Structures](/documentation/SwiftUI/DropSession#Structures)

[`struct ID`](/documentation/swiftui/dropsession/id-swift.struct)The identifier of a drag session.[`struct LocalSession`](/documentation/swiftui/dropsession/localsession-swift.struct)Describes the session originated within the app.### [Instance Properties](/documentation/SwiftUI/DropSession#Instance-Properties)

[`var id: DropSession.ID`](/documentation/swiftui/dropsession/id-swift.property)The unique identifier of the drop session.[`var itemsCount: Int`](/documentation/swiftui/dropsession/itemscount)Number of items for the drop.[`var localSession: DropSession.LocalSession?`](/documentation/swiftui/dropsession/localsession-swift.property)Provides additional information about a session if it originated within the app.[`var location: CGPoint`](/documentation/swiftui/dropsession/location)Location of drop in the local coordinate space[`var phase: DropSession.Phase`](/documentation/swiftui/dropsession/phase-swift.property)The phase of the current drop session.[`var size: CGSize`](/documentation/swiftui/dropsession/size)Size of the drop destination view.[`var suggestedOperations: DropOperation.Set`](/documentation/swiftui/dropsession/suggestedoperations)Operations suggested by the drag source.### [Enumerations](/documentation/SwiftUI/DropSession#Enumerations)

[`enum Phase`](/documentation/swiftui/dropsession/phase-swift.enum)The phase of the current drop session.## [Relationships](/documentation/SwiftUI/DropSession#relationships)

### [Conforms To](/documentation/SwiftUI/DropSession#conforms-to)

- [`Copyable`](/documentation/Swift/Copyable)

- [`CustomDebugStringConvertible`](/documentation/Swift/CustomDebugStringConvertible)

- [`Identifiable`](/documentation/Swift/Identifiable)

## [See Also](/documentation/SwiftUI/DropSession#see-also)

### [Moving items](/documentation/SwiftUI/DropSession#Moving-items)

[`struct DragSession`](/documentation/swiftui/dragsession)Describes the ongoing dragging session.