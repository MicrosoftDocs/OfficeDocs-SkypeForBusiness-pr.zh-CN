---
title: 在允许的域列表上查看域
TOCTitle: 在允许的域列表上查看域
ms:assetid: 13bceaba-5c4f-431f-864f-9e374cafa986
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362772(v=OCS.15)
ms:contentKeyID: 56271119
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在允许的域列表上查看域

 

_**上一次修改主题：** 2015-06-22_

要查看允许的域列表上的所有域，请使用 [Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md) 和以下语法：

    Get-CsTenantFederationConfiguration | Select-Object -ExpandProperty AllowedDomains | Select-Object AllowedDomain

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

