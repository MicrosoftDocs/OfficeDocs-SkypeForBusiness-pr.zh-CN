---
title: Windows PowerShell 和 Lync Online 简介
TOCTitle: Windows PowerShell 和 Lync Online 简介
ms:assetid: 4b4cf534-c950-4d6c-abd9-d3d0e6f53bb7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362785(v=OCS.15)
ms:contentKeyID: 56271136
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell 和 Lync Online 简介

 

_**上一次修改主题：** 2015-06-22_

Windows PowerShell 是一种可用于管理 Skype for Business Online 的命令外壳和脚本语言。不必使用图形 Skype for Business Online 管理中心管理 Skype for Business Online，您可以选择使用与此类似的命令行命令管理产品：

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

除了上例所示（将返回有关 UPN 为 kenmyer@litwareinc.com 的用户的信息）的简单命令之外，具备更丰富的 Windows PowerShell 经验的用户也可以将这些命令组织成脚本。这些命令可用于自动化过程和/或执行重复任务。

一般而言，您可以使用 Skype for Business Online 管理中心执行的任何任务也可以使用 Windows PowerShell 执行。例如，您可以使用管理中心管理移动电话通知（也称为*推送通知*）。推送通知使您能够向 iPhone 和 Windows Phone 等移动设备发送有关事件（例如，新即时消息或新语音邮件）的通知。即使这些设备上的 Lync 应用程序在后台运行，也可以在移动设备上接收这些通知。

如何管理推送通知？一种方法是使用 Skype for Business Online 管理中心，在这里，您可以通过从“组织”选项卡选择合适的选项来启用或禁用推送通知：

![LyncOnlinePowerShell\_Push\_Notifications](images/Dn362807.0a6ec1f5-1999-427f-880b-0587c98d7670(OCS.15).png "LyncOnlinePowerShell_Push_Notifications")

您也可以使用远程 Windows PowerShell 会话和 [Set-CsPushNotificationConfiguration](set-cspushnotificationconfiguration.md) cmdlet 启用或禁用推送通知。例如，此命令可禁用 iPhone 和 Windows Phone 的推送通知：

    Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False -EnableMicrosoftPushNotificationService $False

如您所见，与 **Set-CsPushNotificationConfiguration** cmdlet 一起使用的参数（即，EnableApplePushNotificationService 和 EnableMicrosoftPushNotificationService）对应于 Skype for Business Online 管理中心中可用的选项：

![显示了 Lync 选项 / PS cmdlet 之间的关联](images/Dn362785.f20086fd-3b51-4bbf-8d81-e643d9bf3a2e(OCS.15).png "显示了 Lync 选项 / PS cmdlet 之间的关联")

总而言之，您可以使用管理中心或 Windows PowerShell cmdlet 以及合适的参数管理推送通知。两种方法都可行，并且两种方法的效果相当。

> [!NOTE]  
> 有关特定 Windows PowerShell 术语（例如，<em>cmdlet</em>、<em>形式参数</em>、<em>参数值</em>和<em>实际参数</em>）的定义，请参阅 <a href="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online.md">Windows PowerShell Cmdlet、参数和参数值</a>。



这会引发一个显而易见的问题：如果 Skype for Business Online 管理中心和 Windows PowerShell 提供完全相同的功能，为什么选择一个而放弃另一个？就这一点而论，为什么您曾经选择在 Windows PowerShell 中键入命令，而不是在管理中心中选择或清除复选框？

在前面示例类似的简单情形下，确定使用哪种方法取决于个人喜好：一些人偏好使用图形用户界面，而一些人偏好命令行工具（如 Windows PowerShell）。但是，在某些情况下，Windows PowerShell 提供最高效的方法执行管理任务，或者它是执行管理任务的唯一方法。例如，Skype for Business Online 管理中心使您能够自定义会议邀请：

![Lync 管理中心 - 会议邀请设置](images/Dn362785.3fb00c33-0bd4-46dd-beb1-8f71e24cf630(OCS.15).png "Lync 管理中心 -  会议邀请设置")

您可以使用 [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md) cmdlet 执行相同自定义操作。但是，**Set-CsMeetingConfiguration** cmdlet 也包括 Skype for Business Online 管理中心中不可用的选项。例如，如果您的组织内的某人加入会议，默认情况下，他们会自动被配置为会议演示者。此设置不能使用 Skype for Business Online 管理中心进行更改，只能使用 Windows PowerShell 和 **Set-CsMeetingConfiguration** cmdlet 进行更改。具体而言，此命令将 DesignateAsPresenter 属性设置为 None，这意味着加入会议时，仅会议组织者将被配置为演示者：

    Set-CsMeetingConfiguration -DesignateAsPresenter "Everyone"

有关使用 Windows PowerShell 的更多详细信息，请参阅以下主题：

  - [Windows PowerShell Cmdlet、参数和参数值](windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online.md)

  - [使用参数](working-with-parameters-in-skype-for-business-online.md)

  - [强制参数和可选参数](mandatory-and-optional-parameters-in-skype-for-business-online.md)

  - [参数与属性](parameters-vs-properties-in-skype-for-business-online.md)

  - [将 Lync Online Cmdlet 与其他 Windows PowerShell Cmdlet 组合使用](combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in.md)

  - [有关使用 Windows PowerShell 的更多帮助](more-help-for-using-windows-powershell-in-skype-for-business-online.md)

