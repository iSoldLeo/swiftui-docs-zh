--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:)

抓取时间：2025-12-03T06:23:02Z

---

# buildBlock(_:_:_:_:_:_:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ CommandsBuilder ](/documentation/swiftui/commandsbuilder)

- [ buildBlock(_:_:_:_:_:_:) ](/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:))

- [ CommandsBuilder ](/documentation/swiftui/commandsbuilder)

- buildBlock(_:_:_:_:_:_:) 

类型 方法# buildBlock(_:_:_:_:_:_:_:)

iOS 14.0+、iPadOS 14.0+、Mac Catalyst 14.0+、macOS 11.0+、VisionOS 1.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5
) -> some Commands where C0 : Commands, C1 : Commands, C2 : Commands, C3 : Commands, C4 : Commands, C5 : Commands

```

## [另请参阅](/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:)#see-also)

### [构建中] [/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:]#构建内容)

[`static func buildBlock() -> EmptyCommands`](/documentation/swiftui/commandsbuilder/buildblock())从不包含任何语句的块构建一个空命令集。[`static func buildBlock<C>(C) -> C`](/documentation/swiftui/commandsbuilder/buildblock(_:))传递一个作为子组编写的单个命令组。已修改。[`static func buildBlock<C0, C1>(C0, C1) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:))[`static func buildBlock<C0, C1, C2>(C0, C1, C2) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:))[`static func buildBlock<C0, C1, C2, C3>(C0, C1, C2, C3) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4>(C0, C1, C2, C3, C4) -> some Commands`](⟦LU_00 16⟧))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6>(C0, C1, C2, C3, C4, C5, C6) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7>(C0, C1, C2, C3, C4, C5, C6, C7) -> some Commands`](⟦LU_0014 ⟧))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8>(C0, C1, C2, C3, C4, C5, C6, C7, C8) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8, C9>(C0, C1, C2, C3, C4, C5, C6, C7, C8, C9) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:_:_:_:))

---
source: https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:)
crawled: 2025-12-03T06:23:02Z
---

# buildBlock(_:_:_:_:_:_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ CommandsBuilder ](/documentation/swiftui/commandsbuilder)

- [ buildBlock(_:_:_:_:_:_:) ](/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:))

- [ CommandsBuilder ](/documentation/swiftui/commandsbuilder)

-  buildBlock(_:_:_:_:_:_:) 

Type Method# buildBlock(_:_:_:_:_:_:)

iOS 14.0+iPadOS 14.0+Mac Catalyst 14.0+macOS 11.0+visionOS 1.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5
) -> some Commands where C0 : Commands, C1 : Commands, C2 : Commands, C3 : Commands, C4 : Commands, C5 : Commands

```

## [See Also](/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:)#see-also)

### [Building content](/documentation/SwiftUI/CommandsBuilder/buildBlock(_:_:_:_:_:_:)#Building-content)

[`static func buildBlock() -> EmptyCommands`](/documentation/swiftui/commandsbuilder/buildblock())Builds an empty command set from a block containing no statements.[`static func buildBlock<C>(C) -> C`](/documentation/swiftui/commandsbuilder/buildblock(_:))Passes a single command group written as a child group through modified.[`static func buildBlock<C0, C1>(C0, C1) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:))[`static func buildBlock<C0, C1, C2>(C0, C1, C2) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:))[`static func buildBlock<C0, C1, C2, C3>(C0, C1, C2, C3) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4>(C0, C1, C2, C3, C4) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6>(C0, C1, C2, C3, C4, C5, C6) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7>(C0, C1, C2, C3, C4, C5, C6, C7) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8>(C0, C1, C2, C3, C4, C5, C6, C7, C8) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:_:_:))[`static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8, C9>(C0, C1, C2, C3, C4, C5, C6, C7, C8, C9) -> some Commands`](/documentation/swiftui/commandsbuilder/buildblock(_:_:_:_:_:_:_:_:_:_:))