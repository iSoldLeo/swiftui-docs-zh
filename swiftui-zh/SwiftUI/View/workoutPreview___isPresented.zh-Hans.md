--- 来源：https://developer.apple.com/documentation/SwiftUI/View/workoutPreview(_:isPresented:)

抓取时间：2025-12-02T17:26:26Z

---

# workoutPreview(_:isPresented:)

**实例方法**

以模态窗口的形式呈现锻炼内容的预览

## 声明

```swift
nonisolated func workoutPreview(_ workout: WorkoutPlan, isPresented: Binding<Bool>) -> some View

```

## 参数

- **workout**：预览所显示的窗口

- **isPresented**：绑定到一个布尔值，用于确定是否显示预览

## 讨论

```swift
struct WorkoutPreviewer: View {
    let workout: WorkoutPlan
    @State var presented: Bool = false
    var body: some View {
        Button {
            isPresented = true
        } label: {
            WorkoutContainerView(workout)
        }
        .workoutPreview(workout, isPresented: $presented)
    }
}
```

## 访问健康数据

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**：异步请求读取权限需要逐个对象授权的数据类型（例如视力处方）。

- **healthDataAccessRequest(store:readTypes:trigger:completion:)**：请求读取指定 HealthKit 数据类型的权限。

- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**：请求保存和读取指定 HealthKit 数据类型的权限。


---
source: https://developer.apple.com/documentation/SwiftUI/View/workoutPreview(_:isPresented:)
crawled: 2025-12-02T17:26:26Z
---

# workoutPreview(_:isPresented:)

**Instance Method**

Presents a preview of the workout contents as a modal sheet

## Declaration

```swift
nonisolated func workoutPreview(_ workout: WorkoutPlan, isPresented: Binding<Bool>) -> some View

```

## Parameters

- **workout**: The `WorkoutContainer` the preview displays
- **isPresented**: A binding to a Boolean value that determines whether to present the preview

## Discussion

```swift
struct WorkoutPreviewer: View {
    let workout: WorkoutPlan
    @State var presented: Bool = false
    var body: some View {
        Button {
            isPresented = true
        } label: {
            WorkoutContainerView(workout)
        }
        .workoutPreview(workout, isPresented: $presented)
    }
}
```

## Accessing health data

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**: Asynchronously requests permission to read a data type that requires per-object authorization (such as vision prescriptions).
- **healthDataAccessRequest(store:readTypes:trigger:completion:)**: Requests permission to read the specified HealthKit data types.
- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**: Requests permission to save and read the specified HealthKit data types.

