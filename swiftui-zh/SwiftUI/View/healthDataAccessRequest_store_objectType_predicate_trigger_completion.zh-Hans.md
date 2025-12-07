--- 来源：https://developer.apple.com/documentation/SwiftUI/View/healthDataAccessRequest(store:objectType:predicate:trigger:completion:)

抓取时间：2025-11-30T21:09:00Z

---

# healthDataAccessRequest(store:objectType:predicate:trigger:completion:)

**实例方法**

异步请求读取需要逐对象授权的数据类型（例如视力处方）的权限。

## 声明

```swift
@preconcurrency nonisolated func healthDataAccessRequest(store: HKHealthStore, objectType: HKObjectType, predicate: NSPredicate? = nil, trigger: some Equatable, completion: @escaping (Result<Bool, any Error>) -> Void) -> some View

```

## 参数

- **store**：请求授权的 HealthKit 存储。

- **objectType**：要读取的数据类型。此类型必须是需要逐对象授权的类型。

- **predicate**：一个可选谓词，用于进一步限制感兴趣的对象。

- **trigger**：用于触发请求的值。此值必须是 [doc://com.apple.documentation/documentation/SwiftUI/State] 变量。对该变量的任何更改都会触发请求。

- **completion**：系统在请求完成后调用的代码块。系统会传递结果参数。

## 讨论

某些示例需要按对象授权。对于这些示例，用户可以逐个选择您的应用可以读取哪些示例。默认情况下，您的应用可以读取已保存到 HealthKit 存储中的任何按对象授权的示例；但是，您可能并非始终拥有这些示例的访问权限。用户可以随时更新任何这些示例的授权状态。

您的应用可以首先在 SwiftUI 中设置请求。

```swift
@State private var trigger = false
let store = HKHealthStore()

var body: some Scene {
    WindowGroup {
        ContentView(enabled: $authenticated)
            .healthDataAccessRequest(store: store,
                                     objectType: .visionPrescriptionType(),
                                     predicate: nil,
                                     trigger: trigger) { result in

                switch result {
                case .success(_):
                    authenticated = true
                case .failure(let error):
                    // Handle the error here.
                    fatalError("*** An error occurred while requesting authentication: \(error) ***")
                }

                logger.debug("Authentication Complete.")
            }
    }
}
```

接下来，查询应用已拥有读取权限的所有样本。

```swift
// Read the newest prescription from the HealthKit store.
let queryDescriptor = HKSampleQueryDescriptor(predicates: [.visionPrescription()],
                                              sortDescriptors: [SortDescriptor(\.startDate, order: .reverse)],
                                              limit: 1)

let prescription: HKVisionPrescription

do {
    guard let result = try await queryDescriptor.result(for: store).first else {
        print("*** No prescription found. ***")
        return
    }

    prescription = result
} catch {
    // Handle the error here.
    fatalError("*** An error occurred while reading the most recent vision prescriptions: \(error.localizedDescription) ***")
}
```

根据查询结果，您可以决定是否需要请求读取其他样本的授权。修改触发器的值，提示用户修改您的应用有权读取的样本。

```swift
// Request authorization for additional samples.
trigger.toggle()
```

当您的应用调用此方法时，HealthKit 会显示一个授权表单，请求读取与谓词和对象类型匹配的样本的权限。使用您应用的用户可以选择要与您的应用共享的单个样本。无论用户之前是否授予过权限，系统始终会请求权限。

用户可以单独启用每个处方。用户响应后，系统会调用任意后台队列上的回调处理程序。

## 访问健康数据

- **healthDataAccessRequest(store:readTypes:trigger:completion:)**：请求读取指定 HealthKit 数据类型的权限。

- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**：请求保存和读取指定 HealthKit 数据类型的权限。

- **workoutPreview(_:isPresented:)**：以模态窗口的形式显示锻炼内容预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/healthDataAccessRequest(store:objectType:predicate:trigger:completion:)
crawled: 2025-11-30T21:09:00Z
---

# healthDataAccessRequest(store:objectType:predicate:trigger:completion:)

**Instance Method**

Asynchronously requests permission to read a data type that requires per-object authorization (such as vision prescriptions).

## Declaration

```swift
@preconcurrency nonisolated func healthDataAccessRequest(store: HKHealthStore, objectType: HKObjectType, predicate: NSPredicate? = nil, trigger: some Equatable, completion: @escaping (Result<Bool, any Error>) -> Void) -> some View

```

## Parameters

- **store**: The HealthKit store where you’re requesting authorization.
- **objectType**: The data type you want to read. This type must be a type that requires per-object authorization.
- **predicate**: An optional predicate that further restricts the objects of interest.
- **trigger**: A value used to trigger the request. This value must be a [doc://com.apple.documentation/documentation/SwiftUI/State] variable. Any change to the variable triggers a request.
- **completion**: A block that the system calls after the request is complete. The system passes the result parameter.

## Discussion

Some samples require per-object authorization. For these samples, people can select which ones your app can read on a sample-by-sample basis. By default, your app can read any of the per-object authorization samples that it has saved to the HealthKit store; however, you may not always have access to those samples. People can update the authorization status for any of these samples at any time.

Your app can begin by setting up the request in SwiftUI.

```swift
@State private var trigger = false
let store = HKHealthStore()

var body: some Scene {
    WindowGroup {
        ContentView(enabled: $authenticated)
            .healthDataAccessRequest(store: store,
                                     objectType: .visionPrescriptionType(),
                                     predicate: nil,
                                     trigger: trigger) { result in

                switch result {
                case .success(_):
                    authenticated = true
                case .failure(let error):
                    // Handle the error here.
                    fatalError("*** An error occurred while requesting authentication: \(error) ***")
                }

                logger.debug("Authentication Complete.")
            }
    }
}
```

Next, query for any samples that it already has permission to read.

```swift
// Read the newest prescription from the HealthKit store.
let queryDescriptor = HKSampleQueryDescriptor(predicates: [.visionPrescription()],
                                              sortDescriptors: [SortDescriptor(\.startDate, order: .reverse)],
                                              limit: 1)

let prescription: HKVisionPrescription

do {
    guard let result = try await queryDescriptor.result(for: store).first else {
        print("*** No prescription found. ***")
        return
    }

    prescription = result
} catch {
    // Handle the error here.
    fatalError("*** An error occurred while reading the most recent vision prescriptions: \(error.localizedDescription) ***")
}
```

Based on the results, you can then decide whether you need to request authorization for additional samples. Modify the trigger’s value to prompt someone to modify the samples your app has access to read.

```swift
// Request authorization for additional samples.
trigger.toggle()
```



When your app calls this method, HealthKit displays an authorization sheet that asks for permission to read the samples that match the predicate and object type. The person using your app can then select individual samples to share with your app. The system always asks for permission, regardless of whether the user previously granted it.

People can individually enable each of the prescriptions. After they respond, the system calls the callback handler on an arbitrary background queue.

## Accessing health data

- **healthDataAccessRequest(store:readTypes:trigger:completion:)**: Requests permission to read the specified HealthKit data types.
- **healthDataAccessRequest(store:shareTypes:readTypes:trigger:completion:)**: Requests permission to save and read the specified HealthKit data types.
- **workoutPreview(_:isPresented:)**: Presents a preview of the workout contents as a modal sheet

