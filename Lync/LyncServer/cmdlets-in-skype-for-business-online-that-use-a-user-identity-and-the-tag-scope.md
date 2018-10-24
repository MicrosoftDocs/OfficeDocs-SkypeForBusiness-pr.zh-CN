---
title: 使用用户标识和标记作用域的 Cmdlet
TOCTitle: 使用用户标识和标记作用域的 Cmdlet
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56271131
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用用户标识和标记作用域的 Cmdlet

 

_**上一次修改主题：** 2015-06-22_

**Grant-Cs** cmdlet（用于向用户分配策略）需要两种标识符：用户标识（Identity 参数）和每用户策略的标识（PolicyName 参数）。例如，要向用户 Ken Myer 分配语音策略 RedmondVoicePolicy，请使用下列命令：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

向用户分配策略时，请记住两项内容。首先，只能分配每用户策略。不能向用户分配全局策略。例如，此命令将失败：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

此命令失败是因为无需分配全局策略。如果希望使用全局策略管理用户，请确保不要向该用户分配每用户策略。如果未向用户分配每用户策略，则将使用全局策略自动管理用户。

> [!NOTE]
> 如果以前向用户分配了每用户策略，而您希望取消分配该策略并通过全局策略管理该用户，该怎么办？在这种情况下，请首先使用以下语法，它将通过授予该用户 null 策略来取消分配每用户策略：<br />
> Grant-CsVoicePolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null


其次，请记住，每用户策略是在标记作用域创建的。但是，在指定策略名称时，您可以忽略标记 **prefix**。这两个命令是一致的：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果您想要返回所有每用户策略（或者至少指定类型的所有每用户策略，如语音策略）的标识，请使用以下类似命令：

    Get-CsVoicePolicy -Filter "tag:*"

以下 cmdlet 使用用户标识和标记作用域：

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## 另请参阅

#### 概念

[标识、作用域和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

