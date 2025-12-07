---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/levelOfDetail
抓取时间： 2025-12-03T06:08:11Z
---

# levelOfDetail

**实例属性**

建议视图的详细程度。

## 声明

```swift
var levelOfDetail: LevelOfDetail { get set }
```

## 讨论

从环境中读取

```swift
@Environment(\.levelOfDetail) var levelOfDetail
```

要根据推荐的详细程度自定义视图，可使用 `.levelOfDetail` 键读取环境值，然后应用该值更改视图。

```swift
var body: some View {
     switch levelOfDetail {
     case .default:
         VStack {
            NewsTitleView()
            NewsBodyView()
         }
     case .simplified:
         NewsImageOverview()
     }
}
```




---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/levelOfDetail
crawled: 2025-12-03T06:08:11Z
---

# levelOfDetail

**Instance Property**

The level of detail the view is recommended to have.

## Declaration

```swift
var levelOfDetail: LevelOfDetail { get set }
```

## Discussion

Read from the environment with

```swift
@Environment(\.levelOfDetail) var levelOfDetail
```

To customize your view based on recommended level of detail, read the environment value using the `.levelOfDetail` key and apply that to change your view.

```swift
var body: some View {
     switch levelOfDetail {
     case .default:
         VStack {
            NewsTitleView()
            NewsBodyView()
         }
     case .simplified:
         NewsImageOverview()
     }
}
```



