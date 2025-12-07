--- 来源：https://developer.apple.com/documentation/swiftui/view/contactaccesspicker(ispresented:completionhandler:)

抓取时间：2025-12-01T10:25:33Z

---

# contactAccessPicker(isPresented:completionHandler:)

**实例方法**

以模态方式呈现用户界面，允许用户选择您的应用可以访问哪些联系人。

## 声明

```swift
@MainActor @preconcurrency func contactAccessPicker(isPresented: Binding<Bool>, completionHandler: @escaping ([String]) -> () = {_ in }) -> some View

```

## 说明

此 API 仅应在您的应用拥有“有限”授权时使用。请参阅 `CNAuthorizationStatus` 和 `CNContactStore/authorizationStatus(for:)`。如果您的应用没有正确的授权状态，则完成处理程序将返回空结果。

您的完成处理程序将接收一个新授予您应用的联系人标识符数组。您的应用已失去访问权限的联系人将不会列出。可以使用 `CNContactStore` 访问新添加的联系人。

参数：

- isPresented：联系人选择器是否显示的绑定。

- completionHandler：管理界面关闭时要调用的函数。接收一个包含新添加联系人的联系人标识符的数组。

## 管理联系人访问

- **contactAccessButtonCaption(_:)**

- **contactAccessButtonStyle(_:)**


---
source: https://developer.apple.com/documentation/swiftui/view/contactaccesspicker(ispresented:completionhandler:)
crawled: 2025-12-01T10:25:33Z
---

# contactAccessPicker(isPresented:completionHandler:)

**Instance Method**

Modally present UI which allows the user to select which contacts your app has access to.

## Declaration

```swift
@MainActor @preconcurrency func contactAccessPicker(isPresented: Binding<Bool>, completionHandler: @escaping ([String]) -> () = {_ in }) -> some View

```

## Discussion

This API should only be used when your app has “Limited” authorization.  See `CNAuthorizationStatus` and `CNContactStore/authorizationStatus(for:)`.  The completion handler will be invoked with an empty result if your app doesn’t have the correct authorization status.

Your completion handler will receive an array of contact identifiers that were newly granted to your app.  Contacts which your app lost access to are not listed.  The newly-available contacts can be accessed using `CNContactStore`.

Parameters:

- isPresented: The binding to whether the contact picker should be shown.
- completionHandler: A function to invoke when the management UI is dismissed.  Receives an array containing contact identifiers of newly-available contacts.

## Managing contact access

- **contactAccessButtonCaption(_:)**
- **contactAccessButtonStyle(_:)**

