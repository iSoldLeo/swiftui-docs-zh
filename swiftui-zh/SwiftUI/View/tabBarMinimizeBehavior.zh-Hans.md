--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabBarMinimizeBehavior(_:)

抓取时间：2025-12-02T17:26:00Z

---

# tabBarMinimizeBehavior(_:)

**实例方法**

设置标签栏最小化的行为。

## 声明

```swift
nonisolated func tabBarMinimizeBehavior(_ behavior: TabBarMinimizeBehavior) -> some View

```

## 参数

- **behavior**：最小化行为。

## 说明

以下 TabView 在 iPhone 的“数字”或“提醒”标签页中滚动时会最小化其标签栏。

```swift
struct ContentView: View {
    var body: some View {
         TabView {
             Tab("Numbers", systemImage: "number") {
                 ScrollView {
                    ForEach(0 ..< 50) { index in
                        Text("\(index)")
                            .padding()
                    }
                 }
             }
             Tab("Alerts", systemImage: "bell") {
                 AlertsView()
             }
         }
         .tabBarMinimizeBehavior(.onScrollDown)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabBarMinimizeBehavior(_:)
crawled: 2025-12-02T17:26:00Z
---

# tabBarMinimizeBehavior(_:)

**Instance Method**

Sets the behavior for tab bar minimization.

## Declaration

```swift
nonisolated func tabBarMinimizeBehavior(_ behavior: TabBarMinimizeBehavior) -> some View

```

## Parameters

- **behavior**: The minimize behavior.

## Discussion

The following TabView minimizes its tab bar when scrolling in the ‘Numbers’ or ‘Alerts’ tabs on iPhone.

```swift
struct ContentView: View {
    var body: some View {
         TabView {
             Tab("Numbers", systemImage: "number") {
                 ScrollView {
                    ForEach(0 ..< 50) { index in
                        Text("\(index)")
                            .padding()
                    }
                 }
             }
             Tab("Alerts", systemImage: "bell") {
                 AlertsView()
             }
         }
         .tabBarMinimizeBehavior(.onScrollDown)
    }
}
```

