--- 来源：https://developer.apple.com/documentation/SwiftUI/View/handlesExternalEvents(preferring:allowing:)

抓取时间：2025-12-02T17:43:27Z

---

# handlesExternalEvents(preferring:allowing:)

**实例方法**

指定视图场景在已打开的情况下处理的外部事件。

## 声明

```swift
nonisolated func handlesExternalEvents(preferring: Set<String>, allowing: Set<String>) -> some View

```

## 参数

- **preferring**：SwiftUI 会将这些字符串与传入的用户活动或 URL 进行比较，以确定视图场景是否优先处理该外部事件。

- **allowing**：SwiftUI 会将这些字符串与传入的用户活动或 URL 进行比较，以确定视图场景是否可以处理该外部事件。

## 返回值

一个视图，其所在的场景（如果已打开）会处理传入的外部事件。

## 说明

将此修饰符应用于视图，以指示包含该视图的已打开场景是否处理应用接收到的指定用户活动或 URL。指定两组字符串标识符，以区分场景*首选*处理的事件类型和它*可以*处理的事件类型。您可以动态更新每组标识符以反映应用状态的变化。

当您的应用在支持多个并发场景的平台上接收到事件时，SwiftUI 会将事件发送到它找到的第一个首选处理该事件的已打开场景。否则，它会将事件发送到它找到的第一个可以处理该事件的已打开场景。如果找不到这两个场景（包括您未添加此视图修饰符的情况），SwiftUI 会为该事件创建一个新场景。

在仅支持单个场景的平台上，SwiftUI 会忽略此修饰符，并将所有外部事件发送到该已打开的场景。

### 匹配事件

为了找到处理特定外部事件的已打开场景，SwiftUI 会将该事件的属性与您在 `preferring` 和 `allowing` 集合中指定的字符串进行比较。SwiftUI 会检查以下事件属性以进行比较：

- 对于 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] 事件（例如，当您的应用处理 Handoff 时），SwiftUI 会使用 Activity 的 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/targetContentIdentifier] 属性；如果是 `nil` 事件，则会使用渲染为 [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString] 的 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/webpageURL] 属性。

- 对于 [doc://com.apple.documentation/documentation/Foundation/URL] 事件（例如，当另一个进程打开您的应用处理的 URL 时），SwiftUI 会使用该 URL 的 [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString] 属性。

对于这两个参数集，空字符串集永远不会匹配。同样，空字符串也永远不会匹配。相反，作为一种特殊情况，仅包含星号 (`*`) 的字符串可以匹配任何内容。此修饰符执行不区分大小写和变音符号的字符串比较。

如果在单个场景中指定此视图修饰符的多个实例，则场景将使用所有修饰符中相应的 `preferring` 和 `allowing` 集合的并集。

### 处理打开场景中的用户活动

例如，以下视图（通过 [userActivity(_:isActive:_:)](userActivity___isActive.zh-Hans.md) 和 [onContinueUserActivity(_:perform:)](onContinueUserActivity___perform.zh-Hans.md) 方法参与交接）会根据当前选择更新其 `preferring` 集合。包含场景优先处理已选中联系人的事件，但当未选中任何联系人时，该场景不会主动指定自身为首选场景：

```swift
private struct ContactList: View {
    var store: ContactStore
    @State private var selectedContact: UUID?

    var body: some View {
        NavigationSplitView {
            List(store.contacts, selection: $selectedContact) { contact in
                NavigationLink(contact.name) {
                    Text(contact.name)
                }
            }
        } detail: {
            Text("Select a contact")
        }
        .handlesExternalEvents(
            preferring: selectedContact == nil
                ? []
                : [selectedContact!.uuidString],
            allowing: selectedContact == nil
                ? ["*"]
                : []
        )
        .onContinueUserActivity(Contact.userActivityType) { activity in
            if let identifier = activity.targetContentIdentifier {
                selectedContact = UUID(uuidString: identifier)
            }
        }
        .userActivity(
            Contact.userActivityType,
            isActive: selectedContact != nil
        ) { activity in
            activity.title = "Contact"
            activity.targetContentIdentifier = selectedContact?.uuidString
            activity.isEligibleForHandoff = true
        }
    }
}
```

上述代码还会更新 `allowing` 集合，以表明当当前未选中任何联系人时，该场景可以处理任何传入事件；但如果视图已显示联系人，则该场景无法处理任何事件。在传入事件与当前选中联系人完全匹配的特殊情况下，`preferring` 集合优先。

## 处理外部事件

- **handlesExternalEvents(matching:)**：指定 SwiftUI 会为哪些外部事件打开已修改场景的新实例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/handlesExternalEvents(preferring:allowing:)
crawled: 2025-12-02T17:43:27Z
---

# handlesExternalEvents(preferring:allowing:)

**Instance Method**

Specifies the external events that the view’s scene handles if the scene is already open.

## Declaration

```swift
nonisolated func handlesExternalEvents(preferring: Set<String>, allowing: Set<String>) -> some View

```

## Parameters

- **preferring**: A set of strings that SwiftUI compares against the incoming user activity or URL to see if the view’s scene prefers to handle the external event.
- **allowing**: A set of strings that SwiftUI compares against the incoming user activity or URL to see if the view’s scene can handle the exernal event.

## Return Value

A view whose enclosing scene — if already open — handles incoming external events.

## Discussion

Apply this modifier to a view to indicate whether an open scene that contains the view handles specified user activities or URLs that your app receives. Specify two sets of string identifiers to distinguish between the kinds of events that the scene *prefers* to handle and those that it *can* handle. You can dynamically update the identifiers in each set to reflect changing app state.

When your app receives an event on a platform that supports multiple simultaneous scenes, SwiftUI sends the event to the first open scene it finds that prefers to handle the event. Otherwise, it sends the event to the first open scene it finds that can handle the event. If it finds neither — including when you don’t add this view modifier — SwiftUI creates a new scene for the event.



On platforms that support only a single scene, SwiftUI ignores this modifier and sends all external events to the one open scene.

### Matching an event

To find an open scene that handles a particular external event, SwiftUI compares a property of the event against the strings that you specify in the `preferring` and `allowing` sets. SwiftUI examines the following event properties to perform the comparison:

- For an [doc://com.apple.documentation/documentation/Foundation/NSUserActivity], like when your app handles Handoff, SwiftUI uses the activity’s [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/targetContentIdentifier] property, or if that’s `nil`, its [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/webpageURL] property rendered as an [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString].
- For a [doc://com.apple.documentation/documentation/Foundation/URL], like when another process opens a URL that your app handles, SwiftUI uses the URL’s [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString].

For both parameter sets, an empty set of strings never matches. Similarly, empty strings never match. Conversely, as a special case, the string that contains only an asterisk (`*`) matches anything. The modifier performs string comparisons that are case and diacritic insensitive.

If you specify multiple instances of this view modifier inside a single scene, the scene uses the union of the respective `preferring` and `allowing` sets from all the modifiers.

### Handling a user activity in an open scene

As an example, the following view — which participates in Handoff through the [userActivity(_:isActive:_:)](userActivity___isActive.zh-Hans.md) and [onContinueUserActivity(_:perform:)](onContinueUserActivity___perform.zh-Hans.md) methods — updates its `preferring` set according to the current selection. The enclosing scene prefers to handle an event for a contact that’s already selected, but doesn’t volunteer itself as a preferred scene when no contact is selected:

```swift
private struct ContactList: View {
    var store: ContactStore
    @State private var selectedContact: UUID?

    var body: some View {
        NavigationSplitView {
            List(store.contacts, selection: $selectedContact) { contact in
                NavigationLink(contact.name) {
                    Text(contact.name)
                }
            }
        } detail: {
            Text("Select a contact")
        }
        .handlesExternalEvents(
            preferring: selectedContact == nil
                ? []
                : [selectedContact!.uuidString],
            allowing: selectedContact == nil
                ? ["*"]
                : []
        )
        .onContinueUserActivity(Contact.userActivityType) { activity in
            if let identifier = activity.targetContentIdentifier {
                selectedContact = UUID(uuidString: identifier)
            }
        }
        .userActivity(
            Contact.userActivityType,
            isActive: selectedContact != nil
        ) { activity in
            activity.title = "Contact"
            activity.targetContentIdentifier = selectedContact?.uuidString
            activity.isEligibleForHandoff = true
        }
    }
}
```

The above code also updates the `allowing` set to indicate that the scene can handle any incoming event when there’s no current selection, but that it can’t handle any event if the view already displays a contact. The `preferring` set takes precedence in the special case where the incoming event exactly matches the currently selected contact.

## Handling external events

- **handlesExternalEvents(matching:)**: Specifies the external events for which SwiftUI opens a new instance of the modified scene.

