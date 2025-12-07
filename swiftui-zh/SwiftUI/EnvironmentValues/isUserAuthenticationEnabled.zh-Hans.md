---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isUserAuthenticationEnabled
抓取时间： 2025-12-03T06:08:08Z
---

# isUserAuthenticationEnabled

**实例属性**

当前系统用户身份验证启用状态。

## 声明

```swift
var isUserAuthenticationEnabled: Bool { get }
```

## 讨论

使用此值可确定在从系统安装的屏蔽下显示此用户界面之前，系统是否会发出额外的设备所有者身份验证挑战。

您的应用程序可以根据此值的变化采取适当的措施，如为敏感内容安装或卸载定制的用户界面屏蔽。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isUserAuthenticationEnabled
crawled: 2025-12-03T06:08:08Z
---

# isUserAuthenticationEnabled

**Instance Property**

The current system user authentication enablement status.

## Declaration

```swift
var isUserAuthenticationEnabled: Bool { get }
```

## Discussion

Use this value to determine whether the system will issue additional device-owner authentication challenges before revealing this piece of user interface from under a system-installed shield.

Your app can respond to changes in this value to take appropriate action, like installing or uninstalling a bespoke UI shield for sensitive content.

