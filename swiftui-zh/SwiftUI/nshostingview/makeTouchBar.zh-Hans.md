--- 来源：https://developer.apple.com/documentation/swiftui/nshostingview/maketouchbar()

抓取时间：2025-12-04T13:41:44Z

---

# makeTouchBar() | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- [ makeTouchBar() ](/documentation/swiftui/nshostingview/maketouchbar())

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- makeTouchBar() 

实例方法 # makeTouchBar()

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic func makeTouchBar() -> NSTouchBar?
```

## [另请参阅](/documentation/swiftui/nshostingview/maketouchbar()#see-also)

### [管理键盘交互](/documentation/swiftui/nshostingview/maketouchbar()#Managing-keyboard-interaction)

[`func keyDown(with: NSEvent)`](/documentation/swiftui/nshostingview/keydown(with:))当用户按下键盘上的某个键时调用当此视图处于响应链中时，键盘会触发此事件。[`func keyUp(with: NSEvent)`](/documentation/swiftui/nshostingview/keyup(with:))当用户在此视图处于响应链中时释放键盘上的某个键时，会调用此事件。[`func performKeyEquivalent(with: NSEvent) -> Bool`](/documentation/swiftui/nshostingview/performkeyequivalent(with:))[`func insertText(Any)`](/documentation/swiftui/nshostingview/inserttext(_:))[`func didChangeValue(forKey: String)`](/documentation/swiftui/nshostingview/didchangevalue(forkey:))

---
source: https://developer.apple.com/documentation/swiftui/nshostingview/maketouchbar()
crawled: 2025-12-04T13:41:44Z
---

# makeTouchBar() | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingView ](/documentation/swiftui/nshostingview)

- [ makeTouchBar() ](/documentation/swiftui/nshostingview/maketouchbar())

- [ NSHostingView ](/documentation/swiftui/nshostingview)

-  makeTouchBar() 

Instance Method# makeTouchBar()

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic func makeTouchBar() -> NSTouchBar?
```

## [See Also](/documentation/swiftui/nshostingview/maketouchbar()#see-also)

### [Managing keyboard interaction](/documentation/swiftui/nshostingview/maketouchbar()#Managing-keyboard-interaction)

[`func keyDown(with: NSEvent)`](/documentation/swiftui/nshostingview/keydown(with:))Called when the user presses a key on the keyboard while this view is in the responder chain.[`func keyUp(with: NSEvent)`](/documentation/swiftui/nshostingview/keyup(with:))Called when the user releases a key on the keyboard while this view is in the responder chain.[`func performKeyEquivalent(with: NSEvent) -> Bool`](/documentation/swiftui/nshostingview/performkeyequivalent(with:))[`func insertText(Any)`](/documentation/swiftui/nshostingview/inserttext(_:))[`func didChangeValue(forKey: String)`](/documentation/swiftui/nshostingview/didchangevalue(forkey:))