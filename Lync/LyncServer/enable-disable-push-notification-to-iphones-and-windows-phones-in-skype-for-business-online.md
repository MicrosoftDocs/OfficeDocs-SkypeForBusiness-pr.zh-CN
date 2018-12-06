---
title: 为 iPhone 和 Windows Phone 启用/禁用推送通知
TOCTitle: 为 iPhone 和 Windows Phone 启用/禁用推送通知
ms:assetid: 64482dcb-6354-4fb5-a2e4-1564b3d0e047
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362792(v=OCS.15)
ms:contentKeyID: 56271154
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 iPhone 和 Windows Phone 启用/禁用推送通知

 

_**上一次修改主题：** 2015-06-22_

要禁止推送通知发送到 iPhone 或 Windows Phone，请使用 [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md) cmdlet，并将 EnableApplePushNotificationService 和 EnableMicrosoftPushNotificationService 属性的值设置为 False ($False)：

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $False

请注意，iPhone 和 Windows Phone 可以独立进行设置。例如，此命令可在 iPhone 上禁用推送通知，而在 Windows Phone 上启用这些通知：

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $True

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

