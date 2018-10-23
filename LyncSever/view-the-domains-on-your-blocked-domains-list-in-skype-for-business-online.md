---
title: 在阻止的域列表上查看域
TOCTitle: 在阻止的域列表上查看域
ms:assetid: 67c65dbf-1a68-4c77-aabd-bed5001b4267
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362797(v=OCS.15)
ms:contentKeyID: 56271153
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在阻止的域列表上查看域

 

_**上一次修改主题：** 2015-06-22_

要查看阻止的域列表上的所有域，请调用 [Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md) cmdlet，然后将返回的数据通过管道传递到 **Select-Object** cmdlet：

    Get-CsTenantFederationConfiguration | Select-Object -ExpandProperty BlockedDomains

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

