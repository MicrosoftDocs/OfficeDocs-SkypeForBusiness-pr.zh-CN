---
title: 向用户分配每用户策略
TOCTitle: 向用户分配每用户策略
ms:assetid: 37e07da7-6391-4d6d-a428-c70272897039
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362779(v=OCS.15)
ms:contentKeyID: 56271134
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向用户分配每用户策略

 

_**上一次修改主题：** 2015-06-22_

要向用户分配每用户策略，您首先必须选择合适的 **Grant-Cs** cmdlet。（例如，[Grant-CsVoicePolicy](grant-csvoicepolicy.md)，如果您想要分配每用户语音策略。）运行 cmdlet，确保指定要向其分配策略的用户的标识和分配的策略的名称：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果您想要向所有用户分配相同策略，请使用此语法：

    Get-CsOnlineUser | Grant-CsVoicePolicy -PolicyName "RedmondVoicePolicy"

请注意，由于不同的许可协议和不同的国家/地区限制，可能无法向特定用户分配特定会议策略、外部访问策略或移动策略。要验证可实际分配给指定用户（例如，kenmyer@litwareinc.com）的每用户策略，请根据需要使用以下其中一个命令（和 ApplicableTo 参数）：

    Get-CsConferencingPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsExternalAccessPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsMobilityPolicy -ApplicableTo "kenmyer@litwareinc.com"

上述语法仅返回可实际分配给 Ken Myer 的那些每用户策略。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

