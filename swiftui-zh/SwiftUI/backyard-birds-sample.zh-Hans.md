---

来源：https://developer.apple.com/documentation/swiftui/backyard-birds-sample
抓取时间：2025-12-04T11:32:31Z

---

# Backyard Birds：使用 SwiftData 和组件构建应用

**示例代码**

创建一个具有持久数据、交互式组件和全新应用内购买体验的应用。

## 概述

Backyard Birds 提供了一个丰富的环境，您可以在其中观察光顾您后花园的鸟儿。您可以监控它们的饮水和食物供应，确保它们始终有新鲜的水和充足的食物，或者通过应用内购买升级游戏，为鸟儿提供更美味的食物。

该示例使用 [doc://com.apple.documentation/documentation/SwiftData] 实现数据持久化，并使用 [doc://com.apple.documentation/documentation/Observation] 协议与 SwiftUI 无缝集成。游戏的组件实现了 [doc://com.apple.documentation/documentation/AppIntents]，用于实现交互式和可配置组件。应用内购买体验使用了 StoreKit 中的 [doc://com.apple.documentation/documentation/StoreKit/ProductView] 和 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView]。

您可以在 [https://github.com/apple/sample-backyard-birds] 访问此示例的源代码。

### 配置示例代码项目

要配置 Backyard Birds 应用以在您的设备上运行，请按照以下步骤操作：

1. 在 Xcode 15 或更高版本中打开项目。

2. 编辑多平台目标的 scheme，并在“选项”选项卡中选择 `Store.storekit` 文件进行 StoreKit 配置。

3. 对 watchOS 目标的 scheme 重复上一步。

4. 选择顶层 Backyard Birds 项目。

5. 对于所有目标，请在“签名与功能”面板的“团队”菜单中选择您的团队，以便 Xcode 可以自动管理您的配置文件。

### 创建数据驱动型应用

该应用通过使用宏 [doc://com.apple.documentation/documentation/SwiftData/Model()] 将模型对象与 [doc://com.apple.documentation/documentation/SwiftData/PersistentModel] 保持一致来定义其数据模型。使用带有 [doc://com.apple.documentation/documentation/SwiftData/Schema/Attribute/Option/unique] 选项的宏 [doc://com.apple.documentation/documentation/SwiftData/Attribute(_:originalName:hashModifier:)] 可确保 `id` 属性的唯一性。

```swift
@Model public class BirdSpecies {
    @Attribute(.unique) public var id: String
    public var naturalScale: Double
    public var isEarlyAccess: Bool
    public var parts: [BirdPart]
    
    @Relationship(deleteRule: .cascade, inverse: \Bird.species)
    public var birds: [Bird] = []
    
    public var info: BirdSpeciesInfo { BirdSpeciesInfo(rawValue: id) }
    
    public init(info: BirdSpeciesInfo, naturalScale: Double = 1, isEarlyAccess: Bool = false, parts: [BirdPart]) {
        self.id = info.rawValue
        self.naturalScale = naturalScale
        self.isEarlyAccess = isEarlyAccess
        self.parts = parts
    }
}
```

### 构建交互式组件

Backyard Birds 通过显示 [Button](Button.zh-Hans.md) 来显示交互式组件，以便在水和食物不足时补充后院的物资。该应用通过在控件视图中放置一个 `Button` 并将一个 `ResupplyBackyardIntent` 实例传递给 [doc://com.apple.documentation/documentation/SwiftUI/Button/init(intent:label:)] 初始化器来实现此功能：

```swift
Button(intent: ResupplyBackyardIntent(backyard: BackyardEntity(from: snapshot.backyard))) {
    Label("Refill Water", systemImage: "arrow.clockwise")
        .foregroundStyle(.secondary)
        .frame(maxWidth: .infinity)
        .padding(.vertical, 8)
        .padding(.horizontal, 12)
        .background(.quaternary, in: .containerRelative)
}
```

该应用允许通过实现 [doc://com.apple.documentation/documentation/AppIntents/WidgetConfigurationIntent] 协议来配置控件：

```swift
struct BackyardWidgetIntent: WidgetConfigurationIntent {
    static let title: LocalizedStringResource = "Backyard"
    static let description = IntentDescription("Keep track of your backyards.")
    
    @Parameter(title: "Backyards", default: BackyardWidgetContent.all)
    var backyards: BackyardWidgetContent
    
    @Parameter(title: "Backyard")
    var specificBackyard: BackyardEntity?
    
    init(backyards: BackyardWidgetContent = .all, specificBackyard: BackyardEntity? = nil) {
        self.backyards = backyards
        self.specificBackyard = specificBackyard
    }
    
    init() {
    }
    
    static var parameterSummary: some ParameterSummary {
        When(\.$backyards, .equalTo, BackyardWidgetContent.specific) {
            Summary {
                \.$backyards
                \.$specificBackyard
            }
        } otherwise: {
            Summary {
                \.$backyards
            }
        }
    }
}
```

### 提供全新的应用内购买体验

示例应用使用 [doc://com.apple.documentation/documentation/StoreKit/ProductView] 在商店货架上显示几种可供购买的不同鸟食升级选项。为了突出显示应用内购买项目，该应用使用 [doc://com.apple.documentation/documentation/SwiftUI/View/productViewStyle(_:)] 修饰符：

```swift
ProductView(id: product.id) {
    BirdFoodProductIcon(birdFood: birdFood, quantity: product.quantity)
        .bestBirdFoodValueBadge()
}
.padding(.vertical)
.background(.background.secondary, in: .rect(cornerRadius: 20))
.productViewStyle(.large)
```

“后院鸟类通行证”页面使用 [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView] 视图显示可续订的订阅。该应用使用 `PassMarketingContent` 视图作为 `SubscriptionStoreView` 的内容：

```swift
SubscriptionStoreView(
    groupID: passGroupID,
    visibleRelationships: showPremiumUpgrade ? .upgrade : .all
) {
    PassMarketingContent(showPremiumUpgrade: showPremiumUpgrade)
        #if !os(watchOS)
        .containerBackground(for: .subscriptionStoreFullHeight) {
            SkyBackground()
        }
        #endif
}
```

## 创建应用

- **目的地视频**：利用 SwiftUI 在多平台应用中构建沉浸式媒体体验。

- **Hello World**：使用窗口、音量和沉浸式空间向人们普及地球知识。

- **餐车：构建 SwiftUI 多平台应用**：为 Mac、iPad 和 iPhone 创建单一代码库和应用目标。

- **Fruta：使用 SwiftUI 构建功能丰富的应用**：创建共享代码库，构建提供小部件和 App Clip 的多平台应用。

- **迁移到 SwiftUI 生命周期**：在保留现有代码库的同时，使用 SwiftUI 的基于场景的生命周期。

- **App**：一种表示应用程序结构和行为的类型。


---
source: https://developer.apple.com/documentation/swiftui/backyard-birds-sample
crawled: 2025-12-04T11:32:31Z
---

# Backyard Birds: Building an app with SwiftData and widgets

**Sample Code**

Create an app with persistent data, interactive widgets, and an all new in-app purchase experience.

## Overview

Backyard Birds offers a rich environment in which you can watch the birds that visit your backyard garden. You can monitor their water and food supply to ensure they always have fresh water and plenty to eat, or upgrade the game using an in-app purchase to provide tastier food for the birds to eat.

The sample implements its data model using [doc://com.apple.documentation/documentation/SwiftData] for persistence, and integrates seamlessly with SwiftUI using the [doc://com.apple.documentation/documentation/Observation] protocol. The game’s widgets implement [doc://com.apple.documentation/documentation/AppIntents] for interactive and configurable widgets. The in-app purchase experience uses the [doc://com.apple.documentation/documentation/StoreKit/ProductView] and [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView] from StoreKit.

You can access the source code for this sample on [https://github.com/apple/sample-backyard-birds].



### Configure the sample code project

To configure the Backyard Birds app to run on your devices, follow these steps:

1. Open the project in Xcode 15 or later.
2. Edit the multiplatform target’s scheme, and on the Options tab, choose the `Store.storekit` file for StoreKit configuration.
3. Repeat the previous step for the watchOS target’s scheme.
4. Select the top-level Backyard Birds project.
5. For all targets, choose your team from the Team menu in the Signing & Capabilities pane so Xcode can automatically manage your provisioning profile.

### Create a data-driven app

The app defines its data model by conforming the model objects to [doc://com.apple.documentation/documentation/SwiftData/PersistentModel] using the [doc://com.apple.documentation/documentation/SwiftData/Model()] macro. Using the [doc://com.apple.documentation/documentation/SwiftData/Attribute(_:originalName:hashModifier:)] macro with the [doc://com.apple.documentation/documentation/SwiftData/Schema/Attribute/Option/unique] option ensures that the `id` property is unique.

```swift
@Model public class BirdSpecies {
    @Attribute(.unique) public var id: String
    public var naturalScale: Double
    public var isEarlyAccess: Bool
    public var parts: [BirdPart]
    
    @Relationship(deleteRule: .cascade, inverse: \Bird.species)
    public var birds: [Bird] = []
    
    public var info: BirdSpeciesInfo { BirdSpeciesInfo(rawValue: id) }
    
    public init(info: BirdSpeciesInfo, naturalScale: Double = 1, isEarlyAccess: Bool = false, parts: [BirdPart]) {
        self.id = info.rawValue
        self.naturalScale = naturalScale
        self.isEarlyAccess = isEarlyAccess
        self.parts = parts
    }
}
```

### Construct interactive widgets

Backyard Birds displays interactive widgets by presenting a [Button](Button.zh-Hans.md) to refill a backyard’s supplies when the water and food are running low. The app does this by placing a `Button` in the widget’s view, and passing a `ResupplyBackyardIntent` instance to the [doc://com.apple.documentation/documentation/SwiftUI/Button/init(intent:label:)] initializer:

```swift
Button(intent: ResupplyBackyardIntent(backyard: BackyardEntity(from: snapshot.backyard))) {
    Label("Refill Water", systemImage: "arrow.clockwise")
        .foregroundStyle(.secondary)
        .frame(maxWidth: .infinity)
        .padding(.vertical, 8)
        .padding(.horizontal, 12)
        .background(.quaternary, in: .containerRelative)
}
```

The app allows for configuration of the widget by implementing the [doc://com.apple.documentation/documentation/AppIntents/WidgetConfigurationIntent] protocol:

```swift
struct BackyardWidgetIntent: WidgetConfigurationIntent {
    static let title: LocalizedStringResource = "Backyard"
    static let description = IntentDescription("Keep track of your backyards.")
    
    @Parameter(title: "Backyards", default: BackyardWidgetContent.all)
    var backyards: BackyardWidgetContent
    
    @Parameter(title: "Backyard")
    var specificBackyard: BackyardEntity?
    
    init(backyards: BackyardWidgetContent = .all, specificBackyard: BackyardEntity? = nil) {
        self.backyards = backyards
        self.specificBackyard = specificBackyard
    }
    
    init() {
    }
    
    static var parameterSummary: some ParameterSummary {
        When(\.$backyards, .equalTo, BackyardWidgetContent.specific) {
            Summary {
                \.$backyards
                \.$specificBackyard
            }
        } otherwise: {
            Summary {
                \.$backyards
            }
        }
    }
}
```

### Provide a new in-app purchase experience

The sample app uses [doc://com.apple.documentation/documentation/StoreKit/ProductView] to display several different bird food upgrades available for purchase on a store shelf. To prominently feature an in-app purchase item, the app uses the [doc://com.apple.documentation/documentation/SwiftUI/View/productViewStyle(_:)] modifier:

```swift
ProductView(id: product.id) {
    BirdFoodProductIcon(birdFood: birdFood, quantity: product.quantity)
        .bestBirdFoodValueBadge()
}
.padding(.vertical)
.background(.background.secondary, in: .rect(cornerRadius: 20))
.productViewStyle(.large)
```

The Backyard Birds Pass page displays renewable subscriptions using the [doc://com.apple.documentation/documentation/StoreKit/SubscriptionStoreView] view. The app uses the `PassMarketingContent` view as the content of the `SubscriptionStoreView`:

```swift
SubscriptionStoreView(
    groupID: passGroupID,
    visibleRelationships: showPremiumUpgrade ? .upgrade : .all
) {
    PassMarketingContent(showPremiumUpgrade: showPremiumUpgrade)
        #if !os(watchOS)
        .containerBackground(for: .subscriptionStoreFullHeight) {
            SkyBackground()
        }
        #endif
}
```

## Creating an app

- **Destination Video**: Leverage SwiftUI to build an immersive media experience in a multiplatform app.
- **Hello World**: Use windows, volumes, and immersive spaces to teach people about the Earth.
- **Food Truck: Building a SwiftUI multiplatform app**: Create a single codebase and app target for Mac, iPad, and iPhone.
- **Fruta: Building a feature-rich app with SwiftUI**: Create a shared codebase to build a multiplatform app that offers widgets and an App Clip.
- **Migrating to the SwiftUI life cycle**: Use a scene-based life cycle in SwiftUI while keeping your existing codebase.
- **App**: A type that represents the structure and behavior of an app.

