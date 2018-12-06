---
title: 参数与属性
TOCTitle: 参数与属性
ms:assetid: 65348f95-f4d4-40cd-8869-f9d72643792d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362796(v=OCS.15)
ms:contentKeyID: 56271155
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 参数与属性

 

_**上一次修改主题：** 2015-06-22_

当查看 Skype for Business Online cmdlet 的帮助主题时，您有时将看到术语*参数*和*属性*互换使用。不要觉得困惑：尽管两个术语在技术上不同，但是在 Skype for Business Online 中，术语的所指基本相同。

从技术上讲，当您运行 cmdlet 时使用参数。例如，在以下 Windows PowerShell 命令中，EnableMicrosoftPushNotificationService 和 EnableApplePushNotificationService 是 [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md) cmdlet 的参数：

    Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService -EnableApplePushNotificationService $True

属性是指 Skype for Business Online 对象的特性（例如，推送通知配置设置的集合）。假设您运行此命令：

    Set-CsPushNotificationConfiguration

执行此操作时，您将获得属性集合及其相关联的值，将包括以下项目：

    EnableMicrosoftPushNotificationService : True
    EnableApplePushNotificationService     : True

如您所见，属性和参数共用相同名称：使用 EnableMicrosoftPushNotificationService 参数配置 EnableMicrosoftPushNotificationService 属性的值。

## 另请参阅

#### 概念

[Windows PowerShell 和 Lync Online 简介](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

