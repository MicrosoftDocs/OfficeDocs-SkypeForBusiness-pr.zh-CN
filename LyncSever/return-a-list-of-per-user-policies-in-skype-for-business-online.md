---
title: 返回每用户策略列表
TOCTitle: 返回每用户策略列表
ms:assetid: e95a2755-3501-40cc-a704-5ecd01839d76
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362856(v=OCS.15)
ms:contentKeyID: 56271212
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回每用户策略列表

 

_**上一次修改主题：** 2015-06-22_

要返回可用的每用户策略列表，请首先选择合适的 **Get-Cs** cmdlet（例如，[Get-CsVoicePolicy](get-csvoicepolicy.md) cmdlet，如果您希望返回每用户语音策略）。然后使用以下语法返回各个每用户策略的标识：

    Get-CsVoicePolicy -Filter "tag:*" | Select-Object Identity

请注意，由于各个许可协议和国家/地区限制有所不同，可能有些会议策略、外部访问策略或移动策略无法被分配给特定用户。要验证可实际分配给给定用户（例如 kenmyer@litwareinc.com）的每用户策略，请根据需要使用以下其中一个命令（和 ApplicableTo 参数）：

    Get-CsConferencingPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsExternalAccessPolicy -ApplicableTo "kenmyer@litwareinc.com"
    Get-CsMobilityPolicy -ApplicableTo "kenmyer@litwareinc.com"

上述语法仅返回可实际分配给 Ken Myer 的那些每用户策略。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

