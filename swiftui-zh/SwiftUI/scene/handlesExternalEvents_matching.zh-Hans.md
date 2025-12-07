--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/handlesExternalEvents(matching:)

抓取时间：2025-11-30T21:28:26Z

---

# handlesExternalEvents(matching:)

**实例方法**

指定 SwiftUI 会为哪些外部事件打开已修改场景的新实例。

## 声明

```swift
nonisolated func handlesExternalEvents(matching conditions: Set<String>) -> some Scene

```

## 参数

- **conditions**：一组字符串，SwiftUI 会将这些字符串与传入的用户活动或 URL 进行比较，以确定 SwiftUI 是否可以打开一个新的场景实例来处理外部事件。

## 返回值

一个场景类型，用于限制 SwiftUI 会为哪些类型的外部事件打开新实例。

## 讨论

当你的应用接收到外部事件（例如用户活动或 URL）时，SwiftUI 会将事件路由到相应的场景进行处理。SwiftUI 会根据以下规则选择接收事件的场景，并按顺序评估这些规则，直到找到目标场景：

- 在每个应用仅支持一个场景的平台上，将事件发送到唯一打开的场景。

- 查找已打开且表明其优先处理或能够处理该事件的场景（如果有），并将事件发送到该场景。你可以在场景内的视图上使用 `[handlesExternalEvents(preferring:allowing:)](../View/handlesExternalEvents_preferring_allowing.zh-Hans.md)` 视图修饰符来注册此偏好。

- 查找包含 ``handlesExternalEvents(matching:)`` 场景修饰符且与外部事件匹配的场景声明。创建第一个匹配场景的新实例，并将事件路由到该实例。

- 查找第一个不包含场景修饰符的场景声明。创建该场景的新实例，并将事件路由到该实例。

请确保您的应用在处理所有声称要处理的事件时，至少满足以下规则之一。此外，还要确保接收事件的场景确实处理了该事件。例如，确保接收用户活动的场景使用合适的 [onContinueUserActivity(_:perform:)](../View/onContinueUserActivity___perform.zh-Hans.md) 视图修饰符来处理这些活动。

不要将 `handlesExternalEvents(matching:)` 场景修饰符与 [handlesExternalEvents(preferring:allowing:)](../View/handlesExternalEvents_preferring_allowing.zh-Hans.md) *视图* 修饰符混淆。场景修饰符用于帮助 SwiftUI 在没有已打开的场景处理外部事件时选择要打开的新场景，而视图修饰符用于指示已打开的场景可以或更倾向于处理某些事件。

### 匹配事件

为了找到处理特定外部事件的场景类型，SwiftUI 会将事件的属性与您在 `conditions` 集合中指定的字符串进行比较。 SwiftUI 会检查以下事件属性以进行比较：

- 对于 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] 事件（例如，当您的应用处理 Handoff 事件时），SwiftUI 会使用 Activity 的 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/targetContentIdentifier] 属性；如果是 `nil` 事件，则会使用渲染为 [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString] 的 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/webpageURL] 属性。

- 对于 [doc://com.apple.documentation/documentation/Foundation/URL] 事件（例如，当另一个进程打开您的应用处理的 URL 时），SwiftUI 会使用 URL 的 [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString] 属性。

空字符串集合永远不会匹配。同样，空字符串也永远不会匹配。相反，作为一种特殊情况，仅包含星号的字符串 (`*`) 可以匹配任何内容。此修饰符执行的字符串比较不区分大小写和变音符号。

### 选择要打开的窗口

以下示例展示了一个应用程序，其中包含一个照片浏览器场景（用于显示照片集）和一个照片详情场景（用于查看特定照片）：

```swift
@main
struct MyPhotos: App {
    var body: some Scene {
        WindowGroup {
            PhotosBrowser()
        }

        WindowGroup("Photo") {
            PhotoDetail()
        }
        .handlesExternalEvents(matching: ["photoIdentifier="])
    }
}
```

该应用程序在第二个场景上使用 `handlesExternalEvents(matching:)` 修饰符，以确保标识符包含字符串 `photoIdentifier=` 的外部事件会创建一个新的第二种类型的场景。其他事件，如果未被已打开的场景处理，则会创建一个新的浏览器窗口。

## 处理外部事件

- **handlesExternalEvents(preferring:allowing:)**：指定视图场景在已打开的情况下要处理的外部事件。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/handlesExternalEvents(matching:)
crawled: 2025-11-30T21:28:26Z
---

# handlesExternalEvents(matching:)

**Instance Method**

Specifies the external events for which SwiftUI opens a new instance of the modified scene.

## Declaration

```swift
nonisolated func handlesExternalEvents(matching conditions: Set<String>) -> some Scene

```

## Parameters

- **conditions**: A set of strings that SwiftUI compares against the incoming user activity or URL to see if SwiftUI can open a new scene instance to handle the external event.

## Return Value

A scene type that limits the kinds of external events for which SwiftUI opens a new instance.

## Discussion

When your app receives an external event like a user activity or a URL, SwiftUI routes the event to a scene for processing. SwiftUI selects the scene that receives the event according to the following rules, which it evaluates in order until it finds a destination scene:

- On platforms that support only a single scene per app, send the event to the one open scene.
- Find an open scene that indicates it prefers to or can handle the event, if any, and send the event to that scene. You use the [handlesExternalEvents(preferring:allowing:)](../View/handlesExternalEvents_preferring_allowing.zh-Hans.md) view modifier on a view inside the scene to register this preference.
- Find a scene declaration with a `handlesExternalEvents(matching:)` scene modifier containing `conditions` that match the external event. Create a new instance of the first scene that matches and route the event there.
- Find the first scene declaration that doesn’t have the scene modifier. Create a new instance of this scene and route the event there.

Make sure that at least one of these rules succeeds in your app for all events that your app claims to handle. Also, make sure that the scene that receives an event actually handles it. For example, be sure that a scene that receives user activities handles them with an appropriate [onContinueUserActivity(_:perform:)](../View/onContinueUserActivity___perform.zh-Hans.md) view modifier.

Don’t confuse the `handlesExternalEvents(matching:)` scene modifier with the [handlesExternalEvents(preferring:allowing:)](../View/handlesExternalEvents_preferring_allowing.zh-Hans.md) *view* modifier. You use the scene modifier to help SwiftUI choose a new scene to open when no open scene handles an external event, whereas you use the view modifier to indicate that an open scene can or prefers to handle certain events.

### Matching an event

To find a scene type that handles a particular external event, SwiftUI compares a property of the event against the strings that you specify in the `conditions` set. SwiftUI examines the following event properties to perform the comparison:

- For an [doc://com.apple.documentation/documentation/Foundation/NSUserActivity], like when your app handles Handoff, SwiftUI uses the activity’s [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/targetContentIdentifier] property, or if that’s `nil`, its [doc://com.apple.documentation/documentation/Foundation/NSUserActivity/webpageURL] property rendered as an [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString].
- For a [doc://com.apple.documentation/documentation/Foundation/URL], like when another process opens a URL that your app handles, SwiftUI uses the URL’s [doc://com.apple.documentation/documentation/Foundation/URL/absoluteString].

An empty set of strings never matches. Similarly, empty strings never match. Conversely, as a special case, the string that contains only an asterisk (`*`) matches anything. The modifier performs string comparisons that are case and diacritic insensitive.



### Choosing a window to open

The following example shows an app with a photo browser scene that displays a collection of photos, and a photo detail scene that enables closer examination of a particular photo:

```swift
@main
struct MyPhotos: App {
    var body: some Scene {
        WindowGroup {
            PhotosBrowser()
        }

        WindowGroup("Photo") {
            PhotoDetail()
        }
        .handlesExternalEvents(matching: ["photoIdentifier="])
    }
}
```

The app uses the `handlesExternalEvents(matching:)` modifier on the second scene to ensure that an external event with an identifier that contains the string `photoIdentifier=` creates a new scene of the second type. Other events, if not handled by an open scene, cause the creation of a new browser window instead.

## Handling external events

- **handlesExternalEvents(preferring:allowing:)**: Specifies the external events that the view’s scene handles if the scene is already open.

