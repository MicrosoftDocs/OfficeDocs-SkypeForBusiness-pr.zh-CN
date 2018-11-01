---
title: 获取有关 Lync Online 租户的信息
TOCTitle: 获取有关 Lync Online 租户的信息
ms:assetid: 06467515-9114-45bb-8d09-26a915c3fc4d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362768(v=OCS.15)
ms:contentKeyID: 56271113
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 获取有关 Lync Online 租户的信息

 

_**上一次修改主题：** 2015-06-22_

要返回有关您的 Skype for Business Online 租户的信息，请不带任何附加参数调用 [Get-CsTenant](get-cstenant.md) cmdlet：

    Get-CsTenant

要仅返回租户名称和 ID（运行 cmdlet 时需要 TenantID 参数的值，例如 [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md) 和 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)），请使用此命令：

    Get-CsTenant | Select-Object Name, TenantID

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

