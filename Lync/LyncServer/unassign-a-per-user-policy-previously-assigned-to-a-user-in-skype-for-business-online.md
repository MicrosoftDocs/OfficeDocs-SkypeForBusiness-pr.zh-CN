---
title: 取消分配以前分配给用户的每用户策略
TOCTitle: 取消分配以前分配给用户的每用户策略
ms:assetid: bdba1d22-28e4-4203-a109-a3fb408783d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362840(v=OCS.15)
ms:contentKeyID: 56271197
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 取消分配以前分配给用户的每用户策略

 

_**上一次修改主题：** 2015-06-22_

如果想要取消分配以前分配给用户的每用户策略，请重新运行合适的 **Grant-Cs** cmdlet（例如，[Grant-CsVoicePolicy](grant-csvoicepolicy.md) cmdlet 可取消分配语音策略）并将 PolicyName 参数设置为 null 值 ($Null)：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

要从您的所有用户取消分配策略，请使用此命令：

    Get-CsOnlineUser | Grant-CsVoicePolicy -PolicyName $Null

当从某用户取消分配策略时，该用户将由全局策略管理。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

