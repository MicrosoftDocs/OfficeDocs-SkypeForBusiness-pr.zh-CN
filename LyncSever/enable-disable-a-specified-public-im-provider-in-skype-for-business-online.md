---
title: 启用/禁用特定公共 IM 提供商
TOCTitle: 启用/禁用特定公共 IM 提供商
ms:assetid: 9d3e2607-01c0-4ae9-accc-39f03ce253bb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362825(v=OCS.15)
ms:contentKeyID: 56271182
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用/禁用特定公共 IM 提供商

 

_**上一次修改主题：** 2015-06-22_

Skype for Business Online 使您能够与以下一个或多个公共即时消息 (IM) 提供商上的用户建立联盟：

  - Internet 服务的 Windows Live 网络

  - Yahoo\!

  - AOL

要允许与以上一个或多个提供商建立联盟，请使用 [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md) cmdlet 并将 Provider 属性的值设置为以下一个或多个值：

  - Windows Live

  - Yahoo

  - AOL

例如，此命令与 Windows Live 和 AOL 建立联盟：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "AOL","WindowsLive"

请注意，任何时候您希望添加或删除提供商时，您都必须在命令中包括所有相关的联盟提供商。例如，您可能希望添加 Yahoo\!，请运行此命令：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "Yahoo"

此命令可将 Yahoo\! 保留为唯一的联盟提供商，因为这是命令中调出的提供商。要与所有三个公共 IM 提供商建立联盟，您必须包括所有三个提供商：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "Yahoo", "AOL","WindowsLive"

请注意，在调用 Set-CsTenantPublicProvider cmdlet 时，您必须包括 Tenant 参数；如果不包括，系统将提示您输入租户 ID。您可以使用此命令返回您的 Skype for Business Online 租户的租户 ID：

    Get-CsTenant | Select-Object TenantID

或者，使用此命令将租户 ID 存储在变量中：

    $tenantID = (Get-CsTenant | Select-Object TenantID)

然后，您可以在调用 Set-CsTenantPublicProvider 时使用该变量（在此示例中为 $tenantID）：

    Set-CsTenantPublicProvider -Tenant $tenantID -Provider "Yahoo", "AOL","WindowsLive"

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

