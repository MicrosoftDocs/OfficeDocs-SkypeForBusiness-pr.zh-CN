---
title: 使用租户参数的 Skype for Business Online 中的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121133ce163b73bd0ddf49faa1db03ae352056d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000927"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>使用租户参数的 Skype for Business Online 中的 cmdlet

 


修改公共提供商设置时，始终需要提供租户标识;即使只有一个租户，也是如此。 例如，此命令将 Windows Live 设置为允许用户与之通信的唯一公共提供程序：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

幸运的是，每次运行这些 cmdlet 时，不需要键入租户 ID （例如，bf19b7db-6960-41e5-a139-2aa373474354）。 相反，您可以通过运行[get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet，将租户 id 存储在一个变量中，然后在调用其他 cmdlet 之一时使用该变量来检索租户 id。 例如：

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

或者，您可以在单个命令中执行此操作，方法是检索租户 ID，然后通过管道将此值 Set-cstenantpublicprovider cmdlet：

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

调用**get-cstenant** cmdlet 时无需指定租户 ID。 此命令将返回有关你的租户的信息：

    Get-CsTenant

以下 cmdlet 接受租户标识。 但是，在这些情况下，参数是可选的，并且在调用 cmdlet 时不需要输入。 相反，Windows PowerShell 将根据你当前连接到的 Skype for Business Online 租户有效地为你输入租户标识：

  - [Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

例如，可以使用以下命令调用**CsTenantFederationConfiguration** cmdlet：

    Get-CsTenantFederationConfiguration

尽管不是必需的，但您可以在调用 CsTenantFederationConfiguration 时包含租户参数：

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

