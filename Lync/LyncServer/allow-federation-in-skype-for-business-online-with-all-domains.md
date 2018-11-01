---
title: 允许与所有域进行联盟
TOCTitle: 允许与所有域进行联盟
ms:assetid: d26f1057-a76c-447a-9efe-72efdce4c15e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362855(v=OCS.15)
ms:contentKeyID: 56271208
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 允许与所有域进行联盟

 

_**上一次修改主题：** 2015-06-22_

如果希望允许用户与任何域中的用户进行通信，您必须执行两项操作。首先，使用 [New-CsEdgeAllowAllKnownDomains](new-csedgeallowallknowndomains.md) cmdlet 创建 AllowAllKnownDomains 对象的实例：

    $x = New-CsEdgeAllowAllKnownDomains

之后，调用 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) cmdlet，并将 AllowedDomains 属性值设置为包含 AllowAllKnownDomains 对象的变量（在此示例中为 $x）：

    Set-CsTenantFederationConfiguration -AllowedDomains $x

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

