--- 来源：https://developer.apple.com/documentation/SwiftUI/restoring-your-app-s-state-with-swiftui

抓取时间：2025-12-02T15:51:18Z

---

# 使用 SwiftUI 恢复应用状态

**示例代码**

通过保留用户当前活动，为用户提供应用的连续性。

## 概述

此 SwiftUI 示例项目演示了如何保留应用的状态信息，并在后续启动时将应用恢复到之前的状态。在后续启动期间，将界面恢复到之前的交互点可以为用户提供连续性，并让他们快速完成当前任务。

用户在使用应用时，会执行影响用户界面的操作。例如，用户可能会查看特定信息页面，在用户离开应用后，操作系统可能会终止该应用以释放其占用的资源。用户可以返回到上次离开的地方——而 UI 状态恢复是实现无缝体验的核心部分。

此示例应用演示了在系统中断应用运行的情况下如何使用状态保存和恢复功能。该示例项目管理一组产品。每个产品都有标题、图片和其他元数据，您可以查看和编辑这些元数据。该项目展示了如何在 `DetailView` 中保存和恢复产品。

### 配置示例代码项目

在 Xcode 中，在 iOS 目标的“签名和功能”选项卡中选择您的开发团队。

### 启用状态保存和恢复

此示例代码项目使用 SwiftUI 的 [Scene](Scene.zh-Hans.md) 来管理应用的用户界面，其生命周期由系统管理。在 iOS 上，状态恢复在窗口或场景级别尤为重要，因为窗口会频繁地出现和消失。因此，必须保存和恢复与每个窗口关联的状态。在 iPad 上，这一点尤其重要，因为切换器中的应用不一定处于运行状态。场景级状态恢复能够保持用户正在运行的错觉。

为了支持状态的保存和恢复，此示例使用了 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] 对象。对于每个用户活动，应用必须提供一个在其 `Info.plist` 中定义的活动类型。

### 使用场景存储

SwiftUI 具有“存储场景数据”或 [SceneStorage](SceneStorage.zh-Hans.md) 的概念。场景存储与 [State](State.zh-Hans.md) 类似，是一种属性包装类型，由键值对组成。键使系统能够正确地保存和恢复值。值必须是 `plist` 类型，以便系统能够正确地保存和恢复它。iOS 使用键值对来接收此场景存储，然后对持久化的、每个场景的存储进行读写操作。操作系统代表用户管理场景存储的保存和恢复。场景存储所依赖的底层数据无法直接访问，因此应用程序必须通过 `@SceneStorage` 属性包装器来访问它。操作系统不保证数据何时以及以何种频率持久化。场景存储中的数据不一定等同于应用程序的数据模型。场景存储旨在与数据模型*配合*使用。最终，可以将场景存储视为“场景范围内的状态”。请勿将敏感数据用于场景存储。

每个需要保存自身状态的视图都实现了一个 `@SceneStorage` 属性包装器。例如，`ContentView` 使用一个 Activity 对象来恢复所选产品：

```swift
@SceneStorage("ContentView.selectedProduct") private var selectedProduct: String?
```

`DetailView` 使用一个 Activity 对象来恢复当前选中的标签页：

```swift
@SceneStorage("DetailView.selectedTab") private var selectedTab = Tabs.detail
```

### 使用 Activity 对象恢复应用状态

`NSUserActivity` 对象捕获应用当前时刻的状态。例如，包含应用当前显示的数据信息。系统会保存提供的对象，并在应用下次启动时将其返回给应用。示例会在用户关闭应用或应用进入后台时创建一个新的 `NSUserActivity` 对象。

每个想要发布用于交接、Spotlight 等功能的 `NSUserActivity` 的 SwiftUI 视图，都必须指定一个 [userActivity(_:isActive:_:)](View/userActivity___isActive.zh-Hans.md) 视图修饰符来发布 `NSUserActivity`。`activityType` 参数是用户活动类型，`isActive` 参数指示是否发布指定类型的用户活动（此参数默认为 `true`），以及是否使用指定的处理程序来填充用户活动内容。用户活动的作用域仅限于视图所在的场景或窗口。多个视图可以发布相同类型的活动，并且所有处理程序都可以为用户活动的内容做出贡献。请注意，仅当视图修饰符的参数为 IC_0018 时，才会调用处理程序。如果所有视图修饰符均未将 IC_0016 指定为 IC_0015，则 iOS 将不会发布用户活动。

每个想要处理传入的 IC_0014 的 SwiftUI 视图都必须指定一个视图修饰符。该修饰符接受 IC_0013 类型和一个处理程序，以便在视图接收到其所在场景或窗口的指定活动类型时调用该处理程序。

```swift
.onContinueUserActivity(DetailView.productUserActivityType) { userActivity in
    if let product = try? userActivity.typedPayload(Product.self) {
        selectedProduct = product.id.uuidString
    }
}
```

### 测试状态恢复

此示例可恢复以下用户界面：

- 详情视图控制器 — 在商品系列视图中点击商品以打开其详情信息。应用将恢复所选商品和所选标签页。

- 详情视图控制器的编辑状态 — 在详情视图中，点击“编辑”。应用将恢复编辑视图及其内容。

- 辅助窗口 — （仅限 iPad）将商品从商品系列视图拖动到设备屏幕的左侧或右侧，以创建第二个场景窗口。应用将恢复该场景及其商品。

状态恢复功能可在真机和模拟器上进行测试。调试示例项目时，如果用户强制退出应用，系统会自动删除其保存的状态。删除保存的状态信息是一项安全措施。此外，如果此应用在启动时崩溃，系统也会删除保存的状态。

要测试示例应用恢复状态的功能，请勿在调试期间使用应用切换器强制退出应用。或者，您可以使用 Xcode 停止应用，或者通过编程方式停止应用。另一种方法是使用 Home 键暂停示例应用，然后在 Xcode 中停止调试器。再次使用 Xcode 启动示例应用，SwiftUI 将启动状态恢复过程。

要将 Spotlight 与 Handoff 结合使用，请按照以下步骤操作：

1. 在 Xcode 中，于 `DetailView.swift` 的 `onContinueUserActivity` 闭包处设置断点。

2. 运行示例项目。

3. 在集合视图中点击一个产品（“樱桃”）以导航至其详细信息。

4. 从屏幕顶部下拉系统面板（强制 Spotlight 更新其索引并请求 Activity）。请注意，`DetailView` `userActivity` 闭包由 iOS 调用。

5. 返回应用，并返回集合视图。

6. 点击除樱桃以外的其他产品（例如芒果）。

7. 点击主屏幕按钮暂停应用。

8. 在主屏幕上向下滑动打开 Spotlight 搜索窗口。

9. 在 Spotlight 搜索框中输入“樱桃”。搜索结果将显示“显示樱桃产品”。

10. 点击它。注意，这里调用了 `DetailView` `onContinueUserActivity` 闭包。`DetailView` 将显示樱桃产品。

## 跨应用启动保存状态

- **defaultAppStorage(_:)**：视图中包含的 `AppStorage` 使用的默认存储。

- **AppStorage**：一种属性包装类型，它反映 `UserDefaults` 中的值，并在该用户默认值发生更改时使视图失效。

- **SceneStorage**：一种属性包装类型，用于读取和写入持久化的、按场景存储的数据。


---
source: https://developer.apple.com/documentation/SwiftUI/restoring-your-app-s-state-with-swiftui
crawled: 2025-12-02T15:51:18Z
---

# Restoring your app’s state with SwiftUI

**Sample Code**

Provide app continuity for users by preserving their current activities.

## Overview

This SwiftUI sample project demonstrates how to preserve your appʼs state information and restore the app to that previous state on subsequent launches. During a subsequent launch, restoring your interface to the previous interaction point provides continuity for the user, and lets them finish active tasks quickly.

When using your app, the user performs actions that affect the user interface. For example, the user might view a specific page of information, and after the user leaves the app, the operating system might terminate it to free up the resources it holds. The user can return to where they left off — and UI state restoration is a core part of making that experience seamless.

This sample app demonstrates the use of state preservation and restoration for scenarios where the system interrupts the app. The sample project manages a set of products. Each product has a title, an image, and other metadata you can view and edit. The project shows how to preserve and restore a product in its `DetailView`.

### Configure the sample code project

In Xcode, select your development team on the iOS target’s Signing and Capabilities tab.

### Enable state preservation and restoration

This sample code project uses SwiftUI’s [Scene](Scene.zh-Hans.md) to manage the app’s user interface with its life cycle managed by the system. On iOS, state restoration is especially important at the window or scene level, because windows come and go frequently. It’s necessary to save and restore state associated with each one. On the iPad, it’s especially important because an app in the switcher is not necessarily running. Scene-level state restoration preserves the illusion they are running.

To support state preservation and restoration, this sample uses [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] objects. For each user activity, the app must supply an activity type defined in its `Info.plist`.

### Use scene storage

SwiftUI has the concept of “storing scene data” or [SceneStorage](SceneStorage.zh-Hans.md). Operating similar to [State](State.zh-Hans.md), scene storage is a property wrapper type that consists of a key/value pair. The key makes it possible for the system to save and restore the value correctly. The value is required to be of a `plist` type, so the system can save and restore it correctly. iOS ingests this scene storage using the key/value and then reads and writes to persisted, per-scene storage. The OS manages saving and restoring scene storage on the user’s behalf. The underlying data that backs scene storage is not directly available, so the app must access it via `@SceneStorage` property wrapper. The OS makes no guarantees as to when and how often the data will be persisted. The data in scene storage is not necessarily equivalent to an application’s data model. Scene storage is intended to be used *with* the data model. Ultimately, consider scene storage a “state scoped to a scene”. Don’t use scene storage with sensitive data.

Each view that needs its own state preservation implements a `@SceneStorage` property wrapper. For example `ContentView` uses one to restore the selected product:

```swift
@SceneStorage("ContentView.selectedProduct") private var selectedProduct: String?
```

`DetailView` uses one to restore its current selected tab:

```swift
@SceneStorage("DetailView.selectedTab") private var selectedTab = Tabs.detail
```



### Restore the app state with an activity object

An `NSUserActivity` object captures the app’s state at the current moment in time. For example, include information about the data the app is currently displaying. The system saves the provided object and returns it to the app the next time it launches. The sample creates a new `NSUserActivity` object when the user closes the app or the app enters the background.

Each SwiftUI view that wants to advertise an `NSUserActivity` for handoff, Spotlight, etc. must specify a [userActivity(_:isActive:_:)](View/userActivity___isActive.zh-Hans.md) view modifier to advertise the `NSUserActivity`. The `activityType` parameter is the user activity’s type, the `isActive` parameter indicates whether a user activity of the specified type is advertised (this parameter defaults to `true`), and whether it uses the specified handler to fill in the user-activity contents. The scope of the user activity applies only to the scene or window in which the view is. Multiple views can advertise the same activity type, and the handlers can all contribute to the contents of the user activity. Note that handlers are only called for `userActivity` view modifiers where the `isActive` parameter is `true`. If none of the `userActivity` view modifiers specify `isActive` as `true`, the user activity will not be advertised by iOS.

Each SwiftUI view that wants to handle incoming `NSUserActivities` must specify a [onContinueUserActivity(_:perform:)](View/onContinueUserActivity___perform.zh-Hans.md) view modifier. This takes the `NSUserActivity` type and a handler to invoke when the view receives the specified activity type for the scene or window in which the view is.

```swift
.onContinueUserActivity(DetailView.productUserActivityType) { userActivity in
    if let product = try? userActivity.typedPayload(Product.self) {
        selectedProduct = product.id.uuidString
    }
}
```

### Test state restoration

This sample restores the following user interface:

- Detail View Controller — Tap a product in the collection view to open its detail information. The app restores the selected product and selected tab.
- Detail View Controller’s Edit State — In the detail view, tap Edit. The app restores the edit view and its content.
- Secondary Window — (iPad only) Drag a product from the collection view over to the left or right of the device screen to create a second scene window. The app restores that scene and its product.

State restoration can be tested both on the device and Simulator. When debugging the sample project, the system automatically deletes its preserved state when the user force quits the app. Deleting the preserved state information is a safety precaution. In addition, the system also deletes the preserved state if this app crashes at launch time.

To test the sample app’s ability to restore the sample’s state, don’t use the app switcher to force quit it during debugging. Instead, use Xcode to stop the app or stop the app programmatically. Another technique is to suspend the sample app using the Home button, and then stop the debugger in Xcode. Launch the sample app again using Xcode, and SwiftUI initiates the state restoration process.

To use Spotlight with Handoff, follow these steps:

1. In Xcode set a breakpoint in `DetailView.swift` at `onContinueUserActivity` closure.
2. Run the sample project.
3. Tap a product (“Cherries”) in the collection view to navigate to its detail information.
4. Pull down the system sheet from the top of the screen (to force Spotlight to update its index and request the activity). Note that the `DetailView` `userActivity` closure is called by iOS.
5. Go back to the app, and go back to the collection view.
6. Tap a product other than Cherries (i.e. Mango).
7. Suspend the app by tapping the Home button.
8. At the Home screen, swipe downwards to open the Spotlight window.
9. In the Spotlight search field, type “Cherries”. The search results will show “Show Cherries Product”.
10. Tap it. Note that `DetailView` `onContinueUserActivity` closure is called. The `DetailView` will show the Cherries product.

## Saving state across app launches

- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the view.
- **AppStorage**: A property wrapper type that reflects a value from `UserDefaults` and invalidates a view on a change in value in that user default.
- **SceneStorage**: A property wrapper type that reads and writes to persisted, per-scene storage.

