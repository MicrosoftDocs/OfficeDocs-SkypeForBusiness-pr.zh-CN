---
title: Skype for Business Online 中使用租户参数的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233090"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Skype for Business Online 中使用租户参数的 cmdlet

 


修改公共提供程序设置时, 你始终需要提供租户标识;即使只有单个租户, 也是如此。 例如, 此命令将 Windows Live 设置为允许用户与之通信的唯一公共提供程序:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

幸运的是, 每次运行其中一个 cmdlet 时无需键入租户 ID (例如, bf19b7db-6960-41e5-a139-2aa373474354)。 相反, 你可以通过运行[CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet 来检索租户 id, 将租户 id 存储在一个变量中, 然后在调用其他 cmdlet 之一时使用该变量。 例如：

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

或者, 你可以在单个命令中执行此操作, 方法是检索租户 ID, 然后将该值管道 CsTenantPublicProvider cmdlet:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

在调用**CsTenant** cmdlet 时, 无需指定租户 ID。 此命令将返回有关租户的信息:

    Get-CsTenant

以下 cmdlet 接受租户标识。 但是, 在这些情况下, 该参数是可选的, 并且无需在调用 cmdlet 时输入。 因此, Windows PowerShell 将根据您当前连接到的 Skype for business Online 租户有效地为您输入租户标识:

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

例如, 可以使用以下命令调用**CsTenantFederationConfiguration** cmdlet:

    Get-CsTenantFederationConfiguration

尽管不是必需的, 但你可以在调用 CsTenantFederationConfiguration 时包含租户参数:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的身份、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

