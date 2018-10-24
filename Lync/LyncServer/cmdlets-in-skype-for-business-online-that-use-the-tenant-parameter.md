---
title: 使用 Tenant 参数的 Cmdlet
TOCTitle: 使用 Tenant 参数的 Cmdlet
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56271213
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Tenant 参数的 Cmdlet

 

_**上一次修改主题：** 2015-06-22_

修改您的公共提供商设置时，您始终需要提供租户标识；即使您只有一个租户也是如此。例如，此命令将 Windows Live 设置为允许您的用户与其进行通信的唯一公共提供商：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

幸运的是，您不必每次运行其中一个 cmdlet 时都键入租户 ID（例如 bf19b7db-6960-41e5-a139-2aa373474354）。您可以通过以下方法检索租户 ID：运行 [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant) cmdlet，将租户 ID 存储在变量中，然后在调用其中一个其他 cmdlet 时使用该变量。例如：

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

或者，您可以通过检索租户 ID，然后通过管道将该值传递到 Set-CsTenantPublicProvider cmdlet 来在单个命令中执行此操作：

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

当调用 **Get-CsTenant** cmdlet 时，您不需要指定租户 ID。此命令返回有关您的租户的信息：

    Get-CsTenant

以下 cmdlet 接受租户标识。但是，在这些情况下，参数是可选的，调用 cmdlet 时不需要输入。Windows PowerShell 将基于您当前连接到 Skype for Business Online 租户选择性地为您输入租户标识：

  - [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant)

  - [Set-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantFederationConfiguration)

  - [Set-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTenantHybridConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

例如，**Get-CsTenantFederationConfiguration** cmdlet 可以使用此命令调用：

    Get-CsTenantFederationConfiguration

您可以在调用 Get-CsTenantFederationConfiguration 时包括 Tenant 参数，但这不是必需的：

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## 另请参阅

#### 概念

[标识、作用域和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

