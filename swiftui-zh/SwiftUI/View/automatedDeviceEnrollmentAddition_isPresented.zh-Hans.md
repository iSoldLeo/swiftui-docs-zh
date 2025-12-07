--- 来源：https://developer.apple.com/documentation/SwiftUI/View/automatedDeviceEnrollmentAddition(isPresented:)

抓取时间：2025-12-02T17:22:34Z

---

# automatedDeviceEnrollmentAddition(isPresented:)

**实例方法**

呈现一个模态视图，使用户能够将设备添加到其组织。

## 声明

```swift
@MainActor @preconcurrency func automatedDeviceEnrollmentAddition(isPresented: Binding<Bool>) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于确定是否显示该视图。

## 返回值

系统向用户呈现的模态视图。

## 说明

使用此视图修饰符，可以在您的应用中呈现用户界面，供设备管理员将通过非官方渠道（例如 Apple 校园教务管理、Apple 商务管理或 Apple Business Essentials）购买的设备添加到其组织。该系统要求使用具有设备注册权限的受管理 Apple 帐户登录。

以下代码示例展示了向用户呈现此视图的一种方法：

示例用法：

```swift
import SwiftUI
import AutomatedDeviceEnrollment

struct ContentView: View {
    @State private var isAddingDevices: Bool = false

    var body: some View {
        Button("Add Devices to Automated Device Enrollment") {
            isAddingDevices = true
        }
        .automatedDeviceEnrollmentAddition(isPresented: $isAddingDevices)
        .onChange(of: isAddingDevices) {
            if !isAddingDevices {
                // Handle dismiss action
            }
        }
    }
}
```

## 使用受管理设备

- **managedContentStyle(_:)**：将受管理内容样式应用于视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/automatedDeviceEnrollmentAddition(isPresented:)
crawled: 2025-12-02T17:22:34Z
---

# automatedDeviceEnrollmentAddition(isPresented:)

**Instance Method**

Presents a modal view that enables users to add devices to their organization.

## Declaration

```swift
@MainActor @preconcurrency func automatedDeviceEnrollmentAddition(isPresented: Binding<Bool>) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the view.

## Return Value

The modal view that the system presents to the user.

## Discussion

Use this view modifier to present UI in your app for device administrators to add devices purchased outside of the official channel to their organization — Apple School Manager, Apple Business Manager, or Apple Business Essentials. The system requires sign in with a Managed Apple Account that includes device enrollment privileges.

The following code example shows one way to present this view to your users:

Example Usage:

```swift
import SwiftUI
import AutomatedDeviceEnrollment

struct ContentView: View {
    @State private var isAddingDevices: Bool = false

    var body: some View {
        Button("Add Devices to Automated Device Enrollment") {
            isAddingDevices = true
        }
        .automatedDeviceEnrollmentAddition(isPresented: $isAddingDevices)
        .onChange(of: isAddingDevices) {
            if !isAddingDevices {
                // Handle dismiss action
            }
        }
    }
}
```

## Working with managed devices

- **managedContentStyle(_:)**: Applies a managed content style to the view.

