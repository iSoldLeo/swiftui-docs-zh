--- 来源：https://developer.apple.com/documentation/SwiftUI/View/interactionActivityTrackingTag(_:)

抓取时间：2025-11-30T21:17:47Z

---

# interactionActivityTrackingTag(_:)

**实例方法**

设置用于跟踪交互的标签。

## 声明

```swift
nonisolated func interactionActivityTrackingTag(_ tag: String) -> some View

```

## 参数

- **tag**：用于跟踪此视图中用户交互（作为活动）的标签。

## 返回值

一个使用跟踪标签的视图。

## 说明

以下示例跟踪 [List](../List.zh-Hans.md) 的滚动活动：

```swift
List {
    Section("Today") {
        ForEach(messageStore.today) { message in
            Text(message.title)
        }
    }
}
.interactionActivityTrackingTag("MessagesList")
```

解析后的活动跟踪标签是累加的，因此在视图层次结构中使用该修饰符会从上到下构建标签。以下示例展示了此修饰符的层级用法，生成的标签为 `Home-Feed`：

```swift
var body: some View {
    Home()
        .interactionActivityTrackingTag("Home")
}

struct Home: View {
    var body: some View {
        List {
            Text("A List Item")
            Text("A Second List Item")
            Text("A Third List Item")
        }
        .interactionActivityTrackingTag("Feed")
    }
}
```

## 管理视图交互

- **disabled(_:)**：添加一个条件，用于控制用户是否可以与此视图交互。

- **isEnabled**：一个布尔值，指示与此环境关联的视图是否允许用户交互。

- **invalidatableContent(_:)**：标记接收者，因为其内容可能无效。


---
source: https://developer.apple.com/documentation/SwiftUI/View/interactionActivityTrackingTag(_:)
crawled: 2025-11-30T21:17:47Z
---

# interactionActivityTrackingTag(_:)

**Instance Method**

Sets a tag that you use for tracking interactivity.

## Declaration

```swift
nonisolated func interactionActivityTrackingTag(_ tag: String) -> some View

```

## Parameters

- **tag**: The tag used to track user interactions hosted by this view as activities.

## Return Value

A view that uses a tracking tag.

## Discussion

The following example tracks the scrolling activity of a [List](../List.zh-Hans.md):

```swift
List {
    Section("Today") {
        ForEach(messageStore.today) { message in
            Text(message.title)
        }
    }
}
.interactionActivityTrackingTag("MessagesList")
```

The resolved activity tracking tag is additive, so using the modifier across the view hierarchy builds the tag from top to bottom. The example below shows a hierarchical usage of this modifier with the resulting tag `Home-Feed`:

```swift
var body: some View {
    Home()
        .interactionActivityTrackingTag("Home")
}

struct Home: View {
    var body: some View {
        List {
            Text("A List Item")
            Text("A Second List Item")
            Text("A Third List Item")
        }
        .interactionActivityTrackingTag("Feed")
    }
}
```

## Managing view interaction

- **disabled(_:)**: Adds a condition that controls whether users can interact with this view.
- **isEnabled**: A Boolean value that indicates whether the view associated with this environment allows user interaction.
- **invalidatableContent(_:)**: Mark the receiver as their content might be invalidated.

