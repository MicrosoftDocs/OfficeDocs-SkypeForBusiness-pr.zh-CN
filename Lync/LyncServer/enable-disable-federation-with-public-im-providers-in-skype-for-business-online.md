---
title: 启用/禁用与公共 IM 提供商的联盟
TOCTitle: 启用/禁用与公共 IM 提供商的联盟
ms:assetid: 8609682c-97d3-48e6-a243-d84c1f9c8419
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362809(v=OCS.15)
ms:contentKeyID: 56271175
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用/禁用与公共 IM 提供商的联盟

 

_**上一次修改主题：** 2015-06-22_

要使您的用户能够与在公共即时消息 (IM) 提供商上拥有帐户的用户进行通信，请使用 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) cmdlet 并将 AllowPublicUsers 属性设置为 True ($True)：

    Set-CsTenantFederationConfiguration -AllowPublicUsers $True

请注意，您随后必须使用 [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md) cmdlet 指定允许您的用户与之通信的公共 IM 提供商。

要禁用与公共提供商的联盟，请再次将 AllowPublicUsers 属性设置为 false ($False)：

    Set-CsTenantFederationConfiguration -AllowPublicUsers $False

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

