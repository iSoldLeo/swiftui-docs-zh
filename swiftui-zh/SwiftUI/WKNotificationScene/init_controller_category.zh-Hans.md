---
来源：https://developer.apple.com/documentation/SwiftUI/WKNotificationScene/init(controller:category:)
抓取时间：2025-12-03T05:31:31Z
---

# init(controller:category:)

**Initializer**

创建一个场景，以响应接收特定类别的远程或本地通知。

### 声明

```swift
init(controller: Controller.Type = Controller.self, category: String)
```

## 参数

- **controller**：收到指定通知类别时要显示的 [WKUserNotificationHostingController](../WKUserNotificationHostingController.zh-Hans.md) 类型。
- **category**：要监听的通知类别。

## 讨论

使用手表通知实例可添加对一个或多个 Apple Watch 通知场景的支持，这些场景会在收到您指定的本地或远程通知类别时出现。下面的示例为应用程序声明添加了两个通知场景：

```swift
@main
struct PopQuizApp : App {
    var body: some Scene {
        MainScene {
            RootView()
        }

        WKNotificationScene(
            controller: QuizTimeController.self,
            category: "com.example.quiztime"
        )

        WKNotificationScene(
            controller: QuizResultsController.self,
            category: "com.example.results"
        )
    }
}
```

每个[WKNotificationScene](../WKNotificationScene.zh-Hans.md) 声明都会引用一个[WKUserNotificationHostingController](../WKUserNotificationHostingController.zh-Hans.md) 和您提供的类别字符串。托管控制器会在收到本地通知或[doc://com.apple.documentation/documentation/PushKit] 通知时显示您的通知内容视图。您指定的类别字符串与通知字典中的类别名称相对应，描述了包含通知视图所显示内容的特定通知。


---
source: https://developer.apple.com/documentation/SwiftUI/WKNotificationScene/init(controller:category:)
crawled: 2025-12-03T05:31:31Z
---

# init(controller:category:)

**Initializer**

Creates a scene that appears in response to receiving a specific category of remote or local notifications.

## Declaration

```swift
init(controller: Controller.Type = Controller.self, category: String)
```

## Parameters

- **controller**: The type of [WKUserNotificationHostingController](../WKUserNotificationHostingController.zh-Hans.md) to display upon receipt of the specified notification category.
- **category**: The category of notifications to listen for.

## Discussion

Use a watch notification instance to add support for one or more Apple Watch notification scenes that appear on receipt of the local or remote notification categories you specify. The example below, adds two notification scenes to the app declaration:

```swift
@main
struct PopQuizApp : App {
    var body: some Scene {
        MainScene {
            RootView()
        }

        WKNotificationScene(
            controller: QuizTimeController.self,
            category: "com.example.quiztime"
        )

        WKNotificationScene(
            controller: QuizResultsController.self,
            category: "com.example.results"
        )
    }
}
```

Each [WKNotificationScene](../WKNotificationScene.zh-Hans.md) declaration references a [WKUserNotificationHostingController](../WKUserNotificationHostingController.zh-Hans.md) and a category string that you provide. The hosting controller displays your notification’s content view upon receipt of a local or a [doc://com.apple.documentation/documentation/PushKit] notification. The category string you specify corresponds to the category name in the notification’s dictionary and describes a specific notification that contains the content displayed by the notification view.

