--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:)

抓取时间：2025-12-01T11:40:50Z

---

# performKeyEquivalent(with:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- [ performKeyEquivalent(with:) ](/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:))

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- performKeyEquivalent(with:) 

实例方法# performKeyEquivalent(with:)

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic func performKeyEquivalent(with nsEvent: NSEvent) -> Bool
```

## [另请参阅](/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:)#see-also)

### [管理键盘] [`func keyDown(with: NSEvent)`](/documentation/swiftui/nshostingview/keydown(with:)当用户按下键盘上的某个键，且此视图位于响应链中时调用。[`func keyUp(with: NSEvent)`](/documentation/swiftui/nshostingview/keyup(with:)当用户松开键盘上的某个键，且此视图位于响应链中时调用。[`func insertText(Any)`](/documentation/swiftui/nshostingview/inserttext(_:)[`func didChangeValue(forKey: String)`](/documentation/swiftui/nshostingview/didchangevalue(forkey:)[`func makeTouchBar() -> NSTouchBar?`](/documentation/swiftui/nshostingview/maketouchbar()

---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:)
crawled: 2025-12-01T11:40:50Z
---

# performKeyEquivalent(with:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- [ performKeyEquivalent(with:) ](/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:))

- [ NSHostingView ](/documentation/swiftui/nshostingview)

-  performKeyEquivalent(with:) 

Instance Method# performKeyEquivalent(with:)

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic func performKeyEquivalent(with nsEvent: NSEvent) -> Bool
```

## [See Also](/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:)#see-also)

### [Managing keyboard interaction](/documentation/SwiftUI/NSHostingView/performKeyEquivalent(with:)#Managing-keyboard-interaction)

[`func keyDown(with: NSEvent)`](/documentation/swiftui/nshostingview/keydown(with:))Called when the user presses a key on the keyboard while this view is in the responder chain.[`func keyUp(with: NSEvent)`](/documentation/swiftui/nshostingview/keyup(with:))Called when the user releases a key on the keyboard while this view is in the responder chain.[`func insertText(Any)`](/documentation/swiftui/nshostingview/inserttext(_:))[`func didChangeValue(forKey: String)`](/documentation/swiftui/nshostingview/didchangevalue(forkey:))[`func makeTouchBar() -> NSTouchBar?`](/documentation/swiftui/nshostingview/maketouchbar())