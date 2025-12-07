--- 来源：https://developer.apple.com/documentation/SwiftUI/View/healthDataAccessRequest(store:readTypes:trigger:completion:)

抓取时间：2025-11-30T21:09:01Z

---

# healthDataAccessRequest(store:readTypes:trigger:completion:)

**实例方法**

请求读取指定 HealthKit 数据类型的权限。

## 声明

```swift
@preconcurrency nonisolated func healthDataAccessRequest(store: HKHealthStore, readTypes: Set<HKObjectType>, trigger: some Equatable, completion: @escaping (Result<Bool, any Error>) -> Void) -> some View

```

## 参数

- **store**：请求授权的 HealthKit 存储。

- **readTypes**：包含要读取的数据类型的可选集合。此集合可以包含 [doc://com.apple.documentation/documentation/HealthKit/HKObjectType] 类的任何具体子类（[doc://com.apple.documentation/documentation/HealthKit/HKCharacteristicType]、[doc://com.apple.documentation/documentation/HealthKit/HKQuantityType]、[doc://com.apple.documentation/documentation/HealthKit/HKCategoryType]、[doc://com.apple.documentation/documentation/HealthKit/HKWorkoutType] 或 [doc://com.apple.documentation/documentation/HealthKit/HKCorrelationType] 类中的任何一个）。如果用户授予权限，您的应用可以从 HealthKit 存储中读取这些数据类型。

- **trigger**：用于触发请求的值。此值必须是 [doc://com.apple.documentation/documentation/SwiftUI/State] 变量。对该变量的任何更改都会触发请求。

- **completion**：系统在请求完成后调用的代码块。系统会传递结果参数。

## 讨论

当您修改触发器的值时，HealthKit 会异步执行此请求。如果您使用新的数据类型（用户之前未在此应用中授予或拒绝权限的数据类型）调用此方法，系统会在您修改触发器的值时自动显示授权表单。授权表单会列出所有请求的权限。用户完成响应后，HealthKit 会在后台队列中调用完成代码块。如果用户已选择授予或禁止访问所有指定类型，则当您修改触发器时，HealthKit 会在不提示用户的情况下调用完成代码块。

您可以通过设置以下键来自定义权限表单上显示的消息：

- [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/NSHealthShareUsageDescription] 自定义读取数据的消息。

在应用“信息”选项卡的“目标属性”列表中设置此键。

用户设置应用权限后，始终可以使用“设置”或“健康”应用进行更改。即使用户未授予读取数据的权限，您的应用也会显示在“健康”应用的“来源”选项卡中。

## 访问健康数据

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**：异步请求读取需要逐个对象授权的数据类型（例如视力处方）的权限。

- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**：请求保存和读取指定 HealthKit 数据类型的权限。

- **workoutPreview(_:isPresented:)**：以模态窗口的形式显示锻炼内容预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/healthDataAccessRequest(store:readTypes:trigger:completion:)
crawled: 2025-11-30T21:09:01Z
---

# healthDataAccessRequest(store:readTypes:trigger:completion:)

**Instance Method**

Requests permission to read the specified HealthKit data types.

## Declaration

```swift
@preconcurrency nonisolated func healthDataAccessRequest(store: HKHealthStore, readTypes: Set<HKObjectType>, trigger: some Equatable, completion: @escaping (Result<Bool, any Error>) -> Void) -> some View

```

## Parameters

- **store**: The HealthKit store where you’re requesting authorization.
- **readTypes**: An optional set containing the data types you want to read. This set can contain any concrete subclass of the [doc://com.apple.documentation/documentation/HealthKit/HKObjectType] class (any of the [doc://com.apple.documentation/documentation/HealthKit/HKCharacteristicType], [doc://com.apple.documentation/documentation/HealthKit/HKQuantityType], [doc://com.apple.documentation/documentation/HealthKit/HKCategoryType], [doc://com.apple.documentation/documentation/HealthKit/HKWorkoutType], or [doc://com.apple.documentation/documentation/HealthKit/HKCorrelationType] classes ). If the user grants permission, your app can read these data types from the HealthKit store.
- **trigger**: A value used to trigger the request. This value must be a [doc://com.apple.documentation/documentation/SwiftUI/State] variable. Any change to the variable triggers a request.
- **completion**: A block that the system calls after the request is complete. The system passes the result parameter.

## Discussion

HealthKit performs this request asynchronously when you modify the trigger’s value. If you call this method with a new data type (a type of data that the user hasn’t previously granted or denied permission for in this app), the system automatically displays the authorization sheet when you modify the trigger’s value. The authorization sheet lists all the requested permissions. After the user finishes responding, HealthKit calls the completion block on a background queue. If the user has already chosen to grant or prohibit access to all of the types specified, HealthKit calls the completion when you modify the trigger without prompting the user.



Customize the messages displayed on the permissions sheet by setting the following key:

- [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/NSHealthShareUsageDescription] customizes the message for reading data.



Set the key in the Target Properties list on the app’s Info tab.

After users set the permissions for your app, they can always change them using either the Settings or the Health app. Your app appears in the Health app’s Sources tab, even if the user didn’t allow permission to read data.

## Accessing health data

- **healthDataAccessRequest(store:objectType:predicate:trigger:completion:)**: Asynchronously requests permission to read a data type that requires per-object authorization (such as vision prescriptions).
- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**: Requests permission to save and read the specified HealthKit data types.
- **workoutPreview(_:isPresented:)**: Presents a preview of the workout contents as a modal sheet

