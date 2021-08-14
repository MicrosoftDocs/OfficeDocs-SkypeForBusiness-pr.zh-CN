---
title: 禁用混合以仅完成到 Teams 的迁移
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文包括禁用混合功能的详细步骤，作为云解决方案和Teams Skype for Business。
ms.openlocfilehash: eb7e72644bf5f69a763540c1c256d7aabb5f9f6f474d1d570071f68a4c2584e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330696"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>禁用混合配置以完成仅Teams迁移 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


本文介绍如何在停用本地部署环境之前禁用Skype for Business配置。 这是停止使用本地环境的以下步骤的第 2 步：

- 步骤 1. [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。

- **步骤 2.禁用混合配置。**  (本文) 

- 步骤 3. [将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。

- 步骤 4. [删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。

> [!NOTE]
> 步骤 2 和步骤 3 应在同一维护窗口中完成，因为任何现有的混合应用程序终结点在步骤 2 和步骤 3 完成之间将不可发现。


## <a name="summary"></a>摘要

在将所有用户从本地Skype for Business升级到Teams仅在 Microsoft 365 中，可以停用内部部署Skype for Business部署。

在停用内部部署部署Skype for Business删除任何硬件之前，必须通过禁用混合在逻辑上将本地部署与Microsoft 365分开。 禁用混合包括以下四个步骤：

1. [更新 DNS 记录以指向Microsoft 365。](#update-dns-to-point-to-microsoft-365)

2. [将组织的共存模式更改为"仅Teams"。](#change-the-coexistence-mode-for-your-organization-to-teams-only)

3. 在组织 (共享 sip 地址空间[) "拆分Microsoft 365共享 sip 地址空间](#disable-shared-sip-address-space-in-microsoft-365-organization)。

4. [禁用内部部署和内部部署之间的Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

这些步骤在逻辑上将本地部署的 Skype for Business Server 与 Microsoft 365，并确保你的组织完全Teams Only。 完成这些步骤后，可以使用 Decide [how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md)中引用的两种方法之一停用内部部署 Skype for Business 部署。

> [!Important] 
> 完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD 连接同步到 Azure AD。 如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。 请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！ 在决定在停用后如何管理属性中介绍了这两种停用方法 [的详细信息和权衡](cloud-consolidation-managing-attributes.md)。

## <a name="update-dns-to-point-to-microsoft-365"></a>更新 DNS 以指向Microsoft 365

需要更新内部部署组织的组织外部 DNS，以便Skype for Business记录指向Microsoft 365部署。。 

此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。 最后，应删除Skype for Business网络的任何 DNS 记录。

有关更新 DNS 记录的详细信息，请参阅[更新 DNS](decommission-manage-dns-entries.md)条目以使你的组织能够全部Teams记录。

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>将组织的共存模式更改为"仅Teams"

此步骤可确保将组织的任何新用户始终创建为仅Teams用户。 

尝试将租户模式更改为 Teams Only 将自动检查是否存在步骤 1 中可能遗漏的任何本地 DNS 记录，并会在输出中标识这些记录。 将租户模式Teams只有更新组织的所有 DNS 记录后才会成功。 

若要将租户模式更改为 Teams请仅从 PowerShell 窗口Teams以下命令。

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

或者，可以使用 Teams 管理中心将租户共存模式更改为 TeamsOnly，在"组织范围的设置"->"Teams升级"下。    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>禁用组织中共享的 sip 地址Microsoft 365空间
    
若要禁用共享 sip 地址空间，请从 PowerShell Teams运行以下命令。

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>禁用内部部署和内部部署之间的Microsoft 365

若要禁用本地环境和 Microsoft 365之间的通信，请从本地 PowerShell 窗口运行以下命令：

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>另请参阅

- [云解决方案Teams Skype for Business](cloud-consolidation.md)

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

