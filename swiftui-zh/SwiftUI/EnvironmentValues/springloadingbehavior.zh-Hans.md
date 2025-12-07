---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/springloadingbehavior
抓取时间： 2025-12-04T13:10:41Z
---

# SpringLoadingBehavior

**实例属性**

与此环境关联的视图的弹簧加载交互行为。

## 声明

```swift
var springLoadingBehavior: SpringLoadingBehavior { get }
```

## 讨论

弹簧加载指的是视图在拖放交互过程中被激活。在 iOS 上，当在有拖放内容的视图顶部短暂暂停时可能会出现这种情况。在 macOS 上，类似的短暂停顿或在压力感应系统上拖动过程中的 "强制点击 "也会发生这种情况。这对 tvOS 或 watchOS 没有影响。

这通常用于具有导航或展示效果的视图，允许在不暂停拖动交互的情况下显示目的地。例如，一个按钮可以显示可将拖动的项目投放到其中的文件夹列表。

`enabled`的值表示视图应支持弹簧加载交互（如果可以的话），`disabled`的值表示视图不应支持弹簧加载交互。`automatic`的值表示视图应遵循其默认行为，例如`TabView`自动允许弹簧加载，但具有`Picker`样式的`segmented`则不允许。

## 配置弹簧加载

- **springLoadingBehavior(_:)**：设置此视图的弹簧加载行为。
- **SpringLoadingBehavior**：控制视图弹簧加载行为的选项。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/springloadingbehavior
crawled: 2025-12-04T13:10:41Z
---

# springLoadingBehavior

**Instance Property**

The behavior of spring loaded interactions for the views associated with this environment.

## Declaration

```swift
var springLoadingBehavior: SpringLoadingBehavior { get }
```

## Discussion

Spring loading refers to a view being activated during a drag and drop interaction. On iOS this can occur when pausing briefly on top of a view with dragged content. On macOS this can occur with similar brief pauses or on pressure-sensitive systems by “force clicking” during the drag. This has no effect on tvOS or watchOS.

This is commonly used with views that have a navigation or presentation effect, allowing the destination to be revealed without pausing the drag interaction. For example, a button that reveals a list of folders that a dragged item can be dropped onto.

A value of `enabled` means that a view should support spring loaded interactions if it is able, and `disabled` means it should not. A value of `automatic` means that a view should follow its default behavior, such as a `TabView` automatically allowing spring loading, but a `Picker` with `segmented` style would not.

## Configuring spring loading

- **springLoadingBehavior(_:)**: Sets the spring loading behavior this view.
- **SpringLoadingBehavior**: The options for controlling the spring loading behavior of views.

