--- 来源：https://developer.apple.com/documentation/SwiftUI/food-truck-building-a-swiftui-multiplatform-app

抓取时间：2025-12-02T15:51:15Z

---

# 餐车：构建 SwiftUI 多平台应用

**示例代码**

创建适用于 Mac、iPad 和 iPhone 的单一代码库和应用目标。

## 概述

使用餐车应用，餐车经营者可以跟踪订单、发现最受欢迎的菜品，并查看目的地的天气。此示例实现了新的 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 来管理应用的视图，[Layout](Layout.zh-Hans.md) 来显示主界面和待处理订单，[doc://com.apple.documentation/documentation/Charts] 来显示趋势，以及 [doc://com.apple.documentation/documentation/WeatherKit/WeatherService] 来获取天气数据。 Food Truck 还实现了 Live Activities，在锁屏界面（[doc://com.apple.documentation/documentation/ActivityKit]）和主屏幕（[doc://com.apple.documentation/documentation/WidgetKit/DynamicIsland]）上分别显示剩余订单准备时间。

您可以在 [https://github.com/apple/sample-food-truck] 访问此示例的源代码。

Food Truck 示例项目包含两种类型的应用目标：

- 简单应用目标，您可以使用 [https://help.apple.com/xcode/mac/11.4/#/dev17411c009] 签名进行构建。此应用可在模拟器中运行，只需一个标准的 Apple ID 即可安装到设备上。它包含应用内购买项目和一个小组件扩展，使用户能够将小组件添加到 iOS 主屏幕或 macOS 通知中心。

- 功能齐全的 Food Truck All 应用目标。完整版应用可在模拟器和拥有 Apple Developer 会员资格的设备上运行。它还允许您创建并使用密码登录。

### 配置示例代码项目

要在没有 Apple 开发者帐户的情况下配置 Food Truck 应用，请按照以下步骤操作：

1. 在 Food Truck 目标的“签名与功能”面板中，点击“添加帐户”，然后使用您的 Apple ID 登录。

2. 在 Food Truck 和 Widgets 目标的团队菜单中，选择“您的姓名（个人团队）”。

3. 构建并运行您的应用。

4. 在 iOS 和 iPadOS 设备上，前往“设置”>“通用”>“VPN 与设备管理”，并信任您的开发者证书。

要配置 Food Truck All 应用以在您的设备上运行，请按照以下步骤操作：

1. 使用 Xcode 14.3 或更高版本打开示例。

2. 选择顶层 Food Truck 项目。

3. 对于所有目标，请在“签名与功能”面板的“团队”菜单中选择您的团队，以便 Xcode 可以自动管理您的配置文件。

4. 添加“关联域”功能，并使用 `webcredentials` 服务指定您的域。有关 `webcredentials` 服务的更多信息，请参阅 [doc://com.apple.documentation/documentation/BundleResources/Entitlements/com.apple.developer.associated-domains]。

5. 确保您的域中存在 `.well-known` 目录下的 `apple-app-site-association` (AASA) 文件，并且该文件包含此应用的 App ID 条目，用于 `webcredentials` 服务。有关 `apple-app-site-association` 文件的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/supporting-associated-domains]。

6. 在 `AccountManager.swift` 文件中，将所有出现的 `example.com` 替换为您的域名。

### 创建多平台应用

“餐车”是一款多平台应用，没有针对 macOS 或 iOS 的单独目标。它只有一个应用目标，可以同时构建 macOS、iPadOS 和 iOS 版本。

### 定义默认导航目标

示例的导航界面包含一个带有视图的 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 和一个 [NavigationStack](NavigationStack.zh-Hans.md)：

```swift
NavigationSplitView {
    Sidebar(selection: $selection)
} detail: {
    NavigationStack(path: $path) {
        DetailColumn(selection: $selection, model: model)
    }
}
```

应用启动时，示例会将 `TruckView` 作为默认视图。枚举值 `Panel` 编码了用户可以在侧边栏中选择的视图，这些视图也会显示在详情视图中。`TruckView` 对应的值为 `.truck`，应用会将其设置为默认选项。 ```swift
@State private var selection: Panel? = Panel.truck
```

### 构建动态布局

在“卡车”视图中，“新订单”面板显示最近的五个订单，每个订单都显示一个 `DonutStackView`，即呈对角线排列的甜甜圈缩略图。[Layout](Layout.zh-Hans.md) 协议允许应用程序定义一个 `DiagonalDonutStackLayout`，用于将甜甜圈缩略图排列成对角线布局。布局的 [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 实现会计算甜甜圈的位置。

```swift
for index in subviews.indices {
    switch (index, subviews.count) {
    case (_, 1):
        subviews[index].place(
            at: center,
            anchor: .center,
            proposal: ProposedViewSize(size)
        )
        
    case (_, 2):
        let direction = index == 0 ? -1.0 : 1.0
        let offsetX = minBound * direction * 0.15
        let offsetY = minBound * direction * 0.20
        subviews[index].place(
            at: CGPoint(x: center.x + offsetX, y: center.y + offsetY),
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.7, height: size.height * 0.7))
        )
    case (1, 3):
        subviews[index].place(
            at: center,
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.65, height: size.height * 0.65))
        )
        
    case (_, 3):
        let direction = index == 0 ? -1.0 : 1.0
        let offsetX = minBound * direction * 0.15
        let offsetY = minBound * direction * 0.23
        subviews[index].place(
            at: CGPoint(x: center.x + offsetX, y: center.y + offsetY),
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.7, height: size.height * 0.65))
        )
```

### 显示热门商品图表

示例包含多个图表。最热门的商品显示在 `TopFiveDonutsView` 中。此图表在 `TopDonutSalesChart` 中实现，它使用 [doc://com.apple.documentation/documentation/Charts/BarMark] 构建条形图。

```swift
Chart {
    ForEach(sortedSales) { sale in
        BarMark(
            x: .value("Donut", sale.donut.name),
            y: .value("Sales", sale.sales)
        )
        .cornerRadius(6, style: .continuous)
        .foregroundStyle(.linearGradient(colors: [Color("BarBottomColor"), .accentColor], startPoint: .bottom, endPoint: .top))
        .annotation(position: .top, alignment: .top) {
            Text(sale.sales.formatted())
                .padding(.vertical, 4)
                .padding(.horizontal, 8)
                .background(.quaternary.opacity(0.5), in: Capsule())
                .background(in: Capsule())
                .font(.caption)
        }
    }
}
```

图表的 x 轴显示标签，标签包含与每个数据点对应的项目名称和缩略图。

```swift
.chartXAxis {
    AxisMarks { value in
        AxisValueLabel {
            let donut = donutFromAxisValue(for: value)
            VStack {
                DonutView(donut: donut)
                    .frame(height: 35)
                    
                Text(donut.name)
                    .lineLimit(2, reservesSpace: true)
                    .multilineTextAlignment(.center)
            }
            .frame(idealWidth: 80)
            .padding(.horizontal, 4)
            
        }
    }
}
```

### 获取天气预报

应用程序在“卡车”视图的“预报”面板中显示预测温度图。应用程序从 [doc://com.apple.documentation/documentation/WeatherKit] 框架获取此数据。

```swift
.task(id: city.id) {
    for parkingSpot in city.parkingSpots {
        do {
            let weather = try await WeatherService.shared.weather(for: parkingSpot.location)
            condition = weather.currentWeather.condition
            willRainSoon = weather.minuteForecast?.contains(where: { $0.precipitationChance >= 0.3 })
            cloudCover = weather.currentWeather.cloudCover
            temperature = weather.currentWeather.temperature
            symbolName = weather.currentWeather.symbolName
            
            let attribution = try await WeatherService.shared.attribution
            attributionLink = attribution.legalPageURL
            attributionLogo = colorScheme == .light ? attribution.combinedMarkLightURL : attribution.combinedMarkDarkURL
            
            if willRainSoon == false {
                spot = parkingSpot
                break
            }
        } catch {
            print("Could not gather weather information...", error.localizedDescription)
            condition = .clear
            willRainSoon = false
            cloudCover = 0.15
        }
    }
}
```

### 配置 WeatherKit 项目

来自 WeatherKit 中 [doc://com.apple.documentation/documentation/WeatherKit/WeatherService] 实例的数据需要为“Food Truck All”目标进行额外配置。如果您未配置 WeatherKit，示例将检测到错误并改用项目中的静态数据。

1. 在 [https://developer.apple.com/account/resources/certificates/list] 创建一个唯一的 App ID，并在“App 服务”标签页中选择 WeatherKit 服务。

2. 在 Xcode 中，在“签名与功能”标签页中，将 Food Truck All 目标的 Bundle ID 更改为与步骤 1 中的 App ID 相同，并添加 WeatherKit 功能。

3. 在“签名与功能”标签页中，将 Widgets 目标的 Bundle ID 更改为与 Food Truck All 目标的 Bundle ID 相同，其中 `.Widgets` 之前的部分与该目标的 Bundle ID 相同。

4. 等待 30 分钟，以便服务注册您的应用 Bundle ID。

5. 构建并运行 Food Truck All 目标。

### 使用实时活动跟踪准备时间

该应用允许餐车经营者跟踪订单准备时间，保证不超过 60 秒。为了实现这一点，该应用在订单详情页面为状态为`placed`的订单添加了一个工具栏按钮。点击此按钮会将订单状态更改为`preparing`，并创建一个[doc://com.apple.documentation/documentation/ActivityKit/Activity]实例来启动一个动态活动，该活动会在iPhone锁屏上显示倒计时和订单详情。

```swift
let timerSeconds = 60
let activityAttributes = TruckActivityAttributes(
    orderID: String(order.id.dropFirst(6)),
    order: order.donuts.map(\.id),
    sales: order.sales,
    activityName: "Order preparation activity."
)

let future = Date(timeIntervalSinceNow: Double(timerSeconds))

let initialContentState = TruckActivityAttributes.ContentState(timerRange: Date.now...future)

let activityContent = ActivityContent(state: initialContentState, staleDate: Calendar.current.date(byAdding: .minute, value: 2, to: Date())!)

do {
    let myActivity = try Activity<TruckActivityAttributes>.request(attributes: activityAttributes, content: activityContent,
        pushType: nil)
    print(" Requested MyActivity live activity. ID: \(myActivity.id)")
    postNotification()
} catch let error {
    print("Error requesting live activity: \(error.localizedDescription)")
}
```

该应用还实现了[doc://com.apple.documentation/documentation/WidgetKit/DynamicIsland]，以便在iPhone 14 Pro设备的动态岛屿中显示与锁屏相同的信息。

```swift
DynamicIsland {
    DynamicIslandExpandedRegion(.leading) {
        ExpandedLeadingView()
    }

    DynamicIslandExpandedRegion(.trailing, priority: 1) {
        ExpandedTrailingView(orderNumber: context.attributes.orderID, timerInterval: context.state.timerRange)
            .dynamicIsland(verticalPlacement: .belowIfTooWide)
    }
} compactLeading: {
    Image("IslandCompactIcon")
        .padding(4)
        .background(.indigo.gradient, in: ContainerRelativeShape())
       
} compactTrailing: {
    Text(timerInterval: context.state.timerRange, countsDown: true)
        .monospacedDigit()
        .foregroundColor(Color("LightIndigo"))
        .frame(width: 40)
} minimal: {
    Image("IslandCompactIcon")
        .padding(4)
        .background(.indigo.gradient, in: ContainerRelativeShape())
}
.contentMargins(.trailing, 32, for: .expanded)
.contentMargins([.leading, .top, .bottom], 6, for: .compactLeading)
.contentMargins(.all, 6, for: .minimal)
.widgetURL(URL(string: "foodtruck://order/\(context.attributes.orderID)"))
```

再次点击同一按钮会将状态更改为`complete`，并结束动态活动。这将从锁屏和动态岛屿中移除该动态活动。

```swift
Task {
    for activity in Activity<TruckActivityAttributes>.activities {
        // Check if this is the activity associated with this order.
        if activity.attributes.orderID == String(order.id.dropFirst(6)) {
            await activity.end(nil, dismissalPolicy: .immediate)
        }
    }
}
```

## 创建应用

- **Destination Video**：利用 SwiftUI 在多平台应用中构建沉浸式媒体体验。

- **Hello World**：使用窗口、音量和沉浸式空间向人们普及地球知识。

- **Backyard Birds：使用 SwiftData 和组件构建应用**：创建一个包含持久数据、交互式组件和全新应用内购买体验的应用。

- **Fruta：使用 SwiftUI 构建功能丰富的应用**：创建一个共享代码库，构建一个提供组件和 App Clip 的多平台应用。

- **迁移到 SwiftUI 生命周期**：在保留现有代码库的同时，使用 SwiftUI 的基于场景的生命周期。

- **App**：一种表示应用结构和行为的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/food-truck-building-a-swiftui-multiplatform-app
crawled: 2025-12-02T15:51:15Z
---

# Food Truck: Building a SwiftUI multiplatform app

**Sample Code**

Create a single codebase and app target for Mac, iPad, and iPhone.

## Overview

Using the Food Truck app, someone who operates a food truck can keep track of orders, discover the most-popular menu items, and check the weather at their destination. The sample implements the new [NavigationSplitView](NavigationSplitView.zh-Hans.md) to manage the app’s views, [Layout](Layout.zh-Hans.md) to show the main interface and pending orders, [doc://com.apple.documentation/documentation/Charts] to show trends, and [doc://com.apple.documentation/documentation/WeatherKit/WeatherService] to get weather data. Food Truck also implements Live Activities to show the remaining order preparation time with [doc://com.apple.documentation/documentation/ActivityKit] on the lock screen, and with [doc://com.apple.documentation/documentation/WidgetKit/DynamicIsland] on the home screen.

You can access the source code for this sample on [https://github.com/apple/sample-food-truck].



The Food Truck sample project contains two types of app targets:

- Simple app target you can build using [https://help.apple.com/xcode/mac/11.4/#/dev17411c009] signing. This app runs in Simulator, and only requires a standard Apple ID to install on a device. It includes in-app purchase, and a widget extension that enable users to add a widget to their iOS Home Screen or the macOS Notification Center.
- Full-featured Food Truck All app target. The full app runs in Simulator, and on devices with an Apple Developer membership.  It also allows you to create and sign in with passkeys.

### Configure the sample code project

To configure the Food Truck app without an Apple Developer account, follow these steps:

1. In the Food Truck target’s Signing & Capabilities panes click Add Account, and log in with your Apple ID.
2. Chose Your Name (Personal Team) from the team menu for the Food Truck and Widgets targets.
3. Build and run your app.
4. On iOS and iPadOS devices navigate to Settings > General > VPN & Device Management and trust your developer certificate.

To configure the Food Truck All app to run on your devices, follow these steps:

1. Open the sample with Xcode 14.3 or later.
2. Select the top-level Food Truck project.
3. For all targets, choose your team from the Team menu in the Signing & Capabilities pane, so Xcode can automatically manage your provisioning profile.
4. Add the Associated Domains capability, and specify your domain with the `webcredentials` service. For more information about the `webcredentials` service, see [doc://com.apple.documentation/documentation/BundleResources/Entitlements/com.apple.developer.associated-domains].
5. Ensure an `apple-app-site-association` (AASA) file is present on your domain, in the `.well-known` directory, and it contains an entry for this app’s App ID for the `webcredentials` service. For more information about the `apple-app-site-association` file, see [doc://com.apple.documentation/documentation/Xcode/supporting-associated-domains].
6. In the `AccountManager.swift` file, replace all occurrences of `example.com` with the name of your domain.



### Create a multiplatform app

Food Truck is a multiplatform app, and there are no separate targets to run on macOS or iOS. Instead, there is only one app target that builds for macOS, iPadOS, and iOS.

### Define a default navigation destination

The sample’s navigation interface consists of a [NavigationSplitView](NavigationSplitView.zh-Hans.md) with a `Sidebar` view, and a [NavigationStack](NavigationStack.zh-Hans.md):

```swift
NavigationSplitView {
    Sidebar(selection: $selection)
} detail: {
    NavigationStack(path: $path) {
        DetailColumn(selection: $selection, model: model)
    }
}
```

At app launch, the sample presents the `TruckView` as the default view. The `Panel` enum encodes the views the user can select in the sidebar, and hence appear in the detail view. The value corresponding to `TruckView` is `.truck`, and the app sets this to be the default selection.

```swift
@State private var selection: Panel? = Panel.truck
```

### Construct a dynamic layout

In the Truck view, the New Orders panel shows the five most-recent orders, and each order shows a `DonutStackView`, which is a diagonal stack of donut thumbnails. The [Layout](Layout.zh-Hans.md) protocol allows the app to define a `DiagonalDonutStackLayout` that arranges the donut thumbnails into the diagonal layout. The layout’s [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) implementation calculates the donuts’ positions.

```swift
for index in subviews.indices {
    switch (index, subviews.count) {
    case (_, 1):
        subviews[index].place(
            at: center,
            anchor: .center,
            proposal: ProposedViewSize(size)
        )
        
    case (_, 2):
        let direction = index == 0 ? -1.0 : 1.0
        let offsetX = minBound * direction * 0.15
        let offsetY = minBound * direction * 0.20
        subviews[index].place(
            at: CGPoint(x: center.x + offsetX, y: center.y + offsetY),
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.7, height: size.height * 0.7))
        )
    case (1, 3):
        subviews[index].place(
            at: center,
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.65, height: size.height * 0.65))
        )
        
    case (_, 3):
        let direction = index == 0 ? -1.0 : 1.0
        let offsetX = minBound * direction * 0.15
        let offsetY = minBound * direction * 0.23
        subviews[index].place(
            at: CGPoint(x: center.x + offsetX, y: center.y + offsetY),
            anchor: .center,
            proposal: ProposedViewSize(CGSize(width: size.width * 0.7, height: size.height * 0.65))
        )
```

### Display a chart of popular items

The sample contains several charts. The most popular items are shown on the `TopFiveDonutsView`. This chart is implemented in `TopDonutSalesChart`, which uses a [doc://com.apple.documentation/documentation/Charts/BarMark] to construct a bar chart.

```swift
Chart {
    ForEach(sortedSales) { sale in
        BarMark(
            x: .value("Donut", sale.donut.name),
            y: .value("Sales", sale.sales)
        )
        .cornerRadius(6, style: .continuous)
        .foregroundStyle(.linearGradient(colors: [Color("BarBottomColor"), .accentColor], startPoint: .bottom, endPoint: .top))
        .annotation(position: .top, alignment: .top) {
            Text(sale.sales.formatted())
                .padding(.vertical, 4)
                .padding(.horizontal, 8)
                .background(.quaternary.opacity(0.5), in: Capsule())
                .background(in: Capsule())
                .font(.caption)
        }
    }
}
```

The *x* axis of the chart shows labels with the names and thumbnails of the items that correspond to each data point.

```swift
.chartXAxis {
    AxisMarks { value in
        AxisValueLabel {
            let donut = donutFromAxisValue(for: value)
            VStack {
                DonutView(donut: donut)
                    .frame(height: 35)
                    
                Text(donut.name)
                    .lineLimit(2, reservesSpace: true)
                    .multilineTextAlignment(.center)
            }
            .frame(idealWidth: 80)
            .padding(.horizontal, 4)
            
        }
    }
}
```

### Obtain a weather forecast

The app shows a forecasted temperature graph in the Forecast panel in the Truck view. The app obtains this data from the [doc://com.apple.documentation/documentation/WeatherKit] framework.

```swift
.task(id: city.id) {
    for parkingSpot in city.parkingSpots {
        do {
            let weather = try await WeatherService.shared.weather(for: parkingSpot.location)
            condition = weather.currentWeather.condition
            willRainSoon = weather.minuteForecast?.contains(where: { $0.precipitationChance >= 0.3 })
            cloudCover = weather.currentWeather.cloudCover
            temperature = weather.currentWeather.temperature
            symbolName = weather.currentWeather.symbolName
            
            let attribution = try await WeatherService.shared.attribution
            attributionLink = attribution.legalPageURL
            attributionLogo = colorScheme == .light ? attribution.combinedMarkLightURL : attribution.combinedMarkDarkURL
            
            if willRainSoon == false {
                spot = parkingSpot
                break
            }
        } catch {
            print("Could not gather weather information...", error.localizedDescription)
            condition = .clear
            willRainSoon = false
            cloudCover = 0.15
        }
    }
}
```

### Configure the project for WeatherKit

The data from the [doc://com.apple.documentation/documentation/WeatherKit/WeatherService] instance in WeatherKit requires additional configuration for the Food Truck All target. If you don’t configure WeatherKit, the sample will detect an error and use static data in the project instead.

1. Create a unique App ID on the [https://developer.apple.com/account/resources/certificates/list], and select the WeatherKit service on the App Services tab.
2. In Xcode, for the Food Truck All target on the Signing & Capabilities tab, change the bundle ID to be the same as the App ID from step 1, and add the WeatherKit capability.
3. For the Widgets target on the Signing & Capabilities tab, change the bundle ID to make the part before `.Widgets` the same as the bundle ID for the Food Truck All target.
4. Wait 30 minutes while the service registers your app’s bundle ID.
5. Build and run the Food Truck All target.

### Track preparation time with Live Activity

The app allows the food truck operator to keep track of order preparation time, which is guaranteed to be 60 seconds or less. To facilitate this, the app implements a toolbar button on the order details screen for orders with `placed` status. Tapping this button changes the order status to `preparing`, and creates an [doc://com.apple.documentation/documentation/ActivityKit/Activity] instance to start a Live Activity, which shows the countdown timer and order details on an iPhone lock screen.

```swift
let timerSeconds = 60
let activityAttributes = TruckActivityAttributes(
    orderID: String(order.id.dropFirst(6)),
    order: order.donuts.map(\.id),
    sales: order.sales,
    activityName: "Order preparation activity."
)

let future = Date(timeIntervalSinceNow: Double(timerSeconds))

let initialContentState = TruckActivityAttributes.ContentState(timerRange: Date.now...future)

let activityContent = ActivityContent(state: initialContentState, staleDate: Calendar.current.date(byAdding: .minute, value: 2, to: Date())!)

do {
    let myActivity = try Activity<TruckActivityAttributes>.request(attributes: activityAttributes, content: activityContent,
        pushType: nil)
    print(" Requested MyActivity live activity. ID: \(myActivity.id)")
    postNotification()
} catch let error {
    print("Error requesting live activity: \(error.localizedDescription)")
}
```

The app also implements [doc://com.apple.documentation/documentation/WidgetKit/DynamicIsland] to show the same information as on the lock screen in the Dynamic Island on iPhone 14 Pro devices.

```swift
DynamicIsland {
    DynamicIslandExpandedRegion(.leading) {
        ExpandedLeadingView()
    }

    DynamicIslandExpandedRegion(.trailing, priority: 1) {
        ExpandedTrailingView(orderNumber: context.attributes.orderID, timerInterval: context.state.timerRange)
            .dynamicIsland(verticalPlacement: .belowIfTooWide)
    }
} compactLeading: {
    Image("IslandCompactIcon")
        .padding(4)
        .background(.indigo.gradient, in: ContainerRelativeShape())
       
} compactTrailing: {
    Text(timerInterval: context.state.timerRange, countsDown: true)
        .monospacedDigit()
        .foregroundColor(Color("LightIndigo"))
        .frame(width: 40)
} minimal: {
    Image("IslandCompactIcon")
        .padding(4)
        .background(.indigo.gradient, in: ContainerRelativeShape())
}
.contentMargins(.trailing, 32, for: .expanded)
.contentMargins([.leading, .top, .bottom], 6, for: .compactLeading)
.contentMargins(.all, 6, for: .minimal)
.widgetURL(URL(string: "foodtruck://order/\(context.attributes.orderID)"))
```

Tapping the same button again changes the status to `complete`, and ends the Live Activity. This removes the Live Activity from the lock screen and from the Dynamic Island.

```swift
Task {
    for activity in Activity<TruckActivityAttributes>.activities {
        // Check if this is the activity associated with this order.
        if activity.attributes.orderID == String(order.id.dropFirst(6)) {
            await activity.end(nil, dismissalPolicy: .immediate)
        }
    }
}
```

## Creating an app

- **Destination Video**: Leverage SwiftUI to build an immersive media experience in a multiplatform app.
- **Hello World**: Use windows, volumes, and immersive spaces to teach people about the Earth.
- **Backyard Birds: Building an app with SwiftData and widgets**: Create an app with persistent data, interactive widgets, and an all new in-app purchase experience.
- **Fruta: Building a feature-rich app with SwiftUI**: Create a shared codebase to build a multiplatform app that offers widgets and an App Clip.
- **Migrating to the SwiftUI life cycle**: Use a scene-based life cycle in SwiftUI while keeping your existing codebase.
- **App**: A type that represents the structure and behavior of an app.

