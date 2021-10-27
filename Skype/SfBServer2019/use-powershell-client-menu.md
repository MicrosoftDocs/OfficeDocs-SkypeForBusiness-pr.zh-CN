---
title: 对"客户端"菜单上的任务使用 PowerShell
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 摘要：Skype for Business Server控制面板映射到 Cmdlet。
ms.openlocfilehash: e4d72aad28167e3be427f203b8e5b80e2305a636
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579742"
---
# <a name="client"></a>Client

本文介绍如何使用 cmdlet 实现与旧版控制面板中的"客户端"菜单项类似的结果。

本文介绍了以下子菜单：

- [客户端](#client)
  - [客户端版本策略](#client-version-policy)
  - [客户端版本配置](#client-version-configuration)
  - [设备更新](#device-update)
  - [测试设备](#test-device)
  - [设备日志配置](#device-log-configuration)
  - [设备配置](#device-configuration)
  - [移动策略](#mobility-policy)
  - [推送通知配置](#push-notification-configuration)

## <a name="client-version-policy"></a>客户端版本策略

客户端 **菜单下的"客户端** 版本策略"子菜单项返回有关客户端环境中Skype for Business Server的信息。 通过客户端版本策略，您可以指定可登录到Skype for Business Server客户端。

让我们考虑用户可在客户端版本策略上执行的各种任务，Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有客户端版本策略

   ![列出客户端版本策略](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***示例***

```powershell
 Get-CsClientVersionPolicy
```

---

> **方案 2：** 创建新的客户端版本策略

   ![新客户端版本策略](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***示例***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **方案 3：** 获取所选客户端版本策略的详细信息

   ![获取客户端版本策略](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***示例***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **方案 4：** 删除所选的客户端版本策略

   ![删除客户端版本策略](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***示例***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **方案 5：** 更新客户端版本策略

   ![更新客户端版本策略](./media/clientversionpolicy-5.png)

- **批注 1 - 结果**

    图像上的此批注指示结果，即检索和显示的数据。

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***示例***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **批注 2 - (选项)**

    映像上的此注释指示用户实现的选项，即获取客户端版本策略规则的详细信息。

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***示例***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **批注 3 - (选项)**

    映像上的此注释指示用户实现的选项，即创建新的客户端版本策略规则。

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***示例***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **批注 4 - (选项)**

    映像上的此注释指示用户实现的选项，即提交/保存新创建的客户端版本策略规则。

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***示例***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>客户端版本配置

 "**客户端版本配置**"子菜单项返回有关在客户端环境中Skype for Business Server的信息。

让我们考虑用户可在 CLIENT **VERSION CONFIGURATION** 上执行的各种任务，以及这些任务Skype for Business cmdlet 的 cmdlet。

---
> **方案 1：** 列出所有客户端版本配置

   ![列出客户端版本配置](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***示例***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **方案 2：** 创建新的客户端版本配置

   ![创建客户端版本配置](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***示例***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **方案 3：** 获取所选客户端版本配置的详细信息

   ![获取客户端版本配置](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***示例***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的客户端版本配置

   ![删除客户端版本配置](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***示例***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新客户端版本配置

   ![更新客户端版本配置](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***示例***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **方案 6：** 启用/禁用客户端版本配置

![启用客户端版本配置](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***示例***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>设备更新

**设备更新** 规则用于将固件更新与运行 Skype for Business 电话 Edition 的设备关联。

让我们考虑用户可在 **DEVICE UPDATE** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有设备更新

   ![列出设备更新](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***示例***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **方案 2：** 删除设备更新

   ![删除设备更新](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***示例***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **方案 3：** 取消设备更新

   ![取消设备更新](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***示例***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **方案 4：** 批准设备更新

   ![批准设备更新](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***示例***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **方案 5：** 还原设备更新

   ![还原设备更新](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***示例***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>测试设备

**TEST DEVICE** 子菜单项为管理员提供了一种方法，在将固件更新分发到组织的所有设备之前测试这些更新。

让我们考虑用户可在 **TEST DEVICE** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有测试设备

   ![列出测试设备](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***示例***

```powershell
 Get-CsTestDevice
```

---

> **方案 2：** 创建新的测试设备

   ![创建测试设备](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***示例***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **方案 3：** 获取所选测试设备的详细信息

   ![获取测试设备](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***示例***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **方案 4：** 删除所选测试设备

   ![删除测试设备](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***示例***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **方案 5：** 更新测试设备

   ![更新测试设备](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***示例***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>设备日志配置

**"设备日志** 配置"子菜单项可帮助管理设备更新 Web 服务，这是一个 Skype for Business Server 组件，使管理员能够将固件更新分发到电话和其他运行 Skype for Business。

让我们考虑用户可在 DEVICE **LOG CONFIGURATION** 上执行的各种任务，以及这些任务Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有设备日志配置

   ![列出设备日志配置](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***示例***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **方案 2：** 创建新的设备日志配置

   ![创建设备日志配置](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***示例***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **方案 3：** 获取所选设备日志配置的详细信息

   ![获取设备日志配置](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***示例***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **方案 4：** 删除所选设备日志配置

   ![删除设备日志配置](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***示例***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新设备日志配置

   ![更新设备日志配置](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***示例***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>设备配置

**"设备配置** "子菜单项有助于管理有关 UC 电话管理选项的信息。 这些选项包括所需的安全模式，以及是否应在指定的非活动时间后自动锁定电话。

让我们考虑用户可在 DEVICE **CONFIGURATION** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有移动策略

   ![列出设备配置](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***示例***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **方案 2：** 创建新的设备配置

   ![创建设备配置](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***示例***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **方案 3：** 获取所选设备配置的详细信息

   ![获取设备配置](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***示例***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选设备配置

   ![删除设备配置](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***示例***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新设备配置

   ![更新设备配置](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***示例***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>移动策略

**移动策略** 确定用户是否可以在移动Skype for Business移动。 这些策略还管理用户使用“通过工号拨号”的能力，这是一种使用户能够使用其工 作电话号码而不是其移动电话号码在其移动电话上发起和接收电话呼叫的功能。 移动策略还可用于使Wi-Fi呼叫时要求进行连接。

让我们考虑用户可在 **MOBILITY POLICY** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有移动策略

   ![列出移动策略](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***示例***

```powershell
 Get-CsMobilityPolicy
```

---

> **方案 2：** 创建新的移动策略

   ![创建移动策略](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***示例***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **方案 3：** 获取所选移动策略的详细信息

   ![获取移动策略](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***示例***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **方案 4：** 删除所选的移动策略

   ![删除移动策略](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***示例***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **方案 5：** 更新移动策略

   ![更新移动策略](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***示例***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>推送通知配置

推送通知服务 (Apple 推送通知服务和 Microsoft 推送通知服务) 提供了一种将有关事件（如新即时消息或新语音邮件）的通知发送到移动设备（如 iPhone 和 Windows Phones）的方法。 这些通知配置为发送，即使这些Skype for Business上的应用程序当前已暂停或在后台运行。

让我们考虑用户可在 **PUSH NOTIFICATION CONFIGURATION** 上执行的各种任务，以及这些任务Skype for Business cmdlet 的 cmdlet。

---

> **方案 1：** 列出所有移动策略

   ![列出推送通知配置](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***示例***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **方案 2：** 创建新的推送通知配置

   ![创建推送通知配置](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***示例***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **方案 3：** 获取所选推送通知配置的详细信息

   ![获取推送通知配置](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***示例***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **方案 4：** 删除所选的推送通知配置

   ![删除推送通知配置](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***示例***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **方案 5：** 更新推送通知配置

   ![更新推送通知配置](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***示例***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
