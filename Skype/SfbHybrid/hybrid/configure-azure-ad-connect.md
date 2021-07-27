---
title: 配置 Azure AD 连接
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在混合环境中配置 Azure AD 连接的说明。
ms.openlocfilehash: 265ff29f033d6e5e1be6ee00126b4601ff3bbb64
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510623"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>为 Teams 和 Skype for Business 配置 Azure AD Connect

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
具有本地 Skype for Business Server (或 Lync Server) 且计划使用 Teams 或 Skype for Business Online 的组织必须配置 Azure AD 连接 以将其本地目录与 Microsoft 365 或 Office 365 同步，如本文档中所述。  这包括直接从内部部署Skype for Business内部部署迁移Teams。 特别是，使用本地 Skype for Business 的组织必须确保将正确的 msRTCSIP 属性同步到 Azure AD 中。

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 也有本地 Skype for Business 的现有 Teams 用户需要将自己的本地 Skype for Business 帐户迁移到云中，才能使用完整功能，如与 Skype for Business 用户进行互操作，以及与联盟组织中的用户通信。 即使用户只在使用 Teams，基础结构也要求必须有此联机 Skype for Business 帐户，才能提供其他功能。  为了执行此迁移，必须确保已正确配置 Azure AD Connect，这样就可以启用混合了。
 

## <a name="background-information"></a>背景信息

Azure Active Directory 连接保持本地 Active Directory 与 Microsoft 365 或 Office 365 持续同步。  本地目录仍是标识的权威源，且本地环境中的更改会同步到 Azure AD 中。 有关详细信息，请参阅[Azure AD 连接 Sync。](/azure/active-directory/hybrid/how-to-connect-sync-whatis) 即使您不会将所有用户从本地迁移到云，也必须将使用 Teams、Skype for Business 本地或 Skype for Business Online 的所有用户从本地同步到 Azure AD，以确保本地用户和联机用户之间的通信。 *组织中的用户将同时出现在本地目录和联机目录中。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>在有 Skype for Business Server 的情况下配置 Azure AD 

无论你拥有一个本地 Active Directory 林还是多个林，Azure AD 连接 都可以用于各种受支持的拓扑，如[Azure AD](/azure/active-directory/hybrid/plan-connect-topologies)连接 拓扑中所述。  从 Skype for Business Server 角度来看，主要有三种变化情况： 

1. 单个林，其中包含权威用户标识，并托管 Skype for Business Server。 

2. 多个林，其中只有一个林托管 Skype for Business Server，其他一个或多个林（帐户林）包含权威用户标识。 

3. 多个林中有多个 Skype for Business Server 部署。 如果满足某些要求，组织可以将这些多个部署合并为一个Microsoft 365或Office 365部署。

### <a name="single-forest"></a>单个林 

如果用户帐户和 Skype for Business 全都托管在单个林中，你必须确保将 Azure AD Connect 配置为，将此林中的用户同步到 Azure AD 中。  虽然 Azure AD Connect 安装向导有各种选项，但相应属性会自动同步到 Azure Active Directory 中。 建议客户不要修改内置同步规则和/或连接器，这些同步规则和/或连接器管理 (安装向导中无法) 。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>多个林中有一个 Skype for Business 部署 

此方案通常称为“资源林拓扑”。 用户的权威标识托管在一个或多个帐户林中，Skype for Business 单独部署在一个资源林中（其本身可能也会托管权威用户标识）。 一般说来，Skype for Business 用户的权威标识可能与 Skype for Business Server 位于同一林中，也可能位于其他林中，前提是： 

- 一个或多个帐户林中有权威标识的用户在资源林（其中部署了 Skype for Business Server）中表示为禁用的用户对象，且资源林中的 msRTCSIP-OriginatorSID 属性与帐户林中的 SID 一致。 有关更多详细信息，请参阅[Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md)。

- 托管 Skype for Business Server 的资源林信任一个或多个帐户林。  

- 标识（来自帐户林）和 Skype for Business（来自资源林）的所有相关用户对象和属性都通过 Azure AD Connect 同步到 Azure AD 中，且填充有正确的值。  

 若要在多林本地方案中将正确的对象和属性同步到[](configure-a-multi-forest-environment-for-hybrid.md)Azure AD，Microsoft 强烈建议使用 Azure AD 连接 从已启用用户帐户的所有林和包含 Skype for Business 的林进行同步。  假设你从所有林进行同步，必须将 Azure AD Connect 配置为，合并这些标识，并同步到 Azure AD 中。 Azure AD Connect 旨在处理这种情况，它在安装向导中提供了用于进行此设置的内置选项，包括设置用于联接标识的定位标记。  选择以下选项：用户标识存在于多个目录中。 使用 --> ObjectSID 和 msExchangeMasterAccountSID 属性进行匹配。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多个林中有多个 Skype for Business Server 部署 

在此方案中，存在多个林，每个林Skype for Business Server一个Microsoft 365或Office 365林。  每个包含Skype for Business Server林都可以使用 AAD 连接 同步到组织的 Azure AD 中。 在给定时间，最多只能为 Skype for Business 混合配置一个林。 在林中启用混合之前，必须使用 [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)禁用所有其他林的所有 SIP 域。 若要详细了解如何将此类环境合并到 Microsoft 365 或 Office 365，请参阅 cloud consolidation for [Teams and Skype for Business](cloud-consolidation.md)。

## <a name="general-requirements"></a>常规要求 

Teams和 Skype for Business Online 服务都要求存在正确的 Active Directory 属性，并且这些属性填充在 Azure AD 中。  Microsoft 的一般建议是同步包含用户标识的所有林以及包含用户标识Skype for Business Server。

 如果用户的标识存在于多个林中，Azure AD Connect 应进行合并。 遵循本指南后，Azure AD 连接将自动同步正确的属性，只要不修改 Azure AD 服务中的连接器或同步连接。 
  
如果未从包含用户标识和 Skype for Business Server 部署的所有林进行同步，则仍必须确保使用 Teams 或 Skype for Business (（无论是本地还是联机) ）的任何用户，相关标识和 Skype for Business 属性正确填充到 Azure AD 中，这可能需要其他本地目录同步。 有关详细信息，请参阅[Azure AD 连接 sync： Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

在这种情况下，客户有责任确保将属性填充到 Azure AD 的正确配置。 请注意以下几点： 

- 使用非标准配置同步到 Azure AD 是有风险的，因为它可能会导致错误配置，进而导致联机目录中的数据损坏。

- 随着产品发展，Microsoft 将继续验证同步所有相关林的标准同步配置。 如果拥有自定义同步配置，客户负责确保配置将正确的属性和值传递到 Azure AD 中。 

## <a name="related-information"></a>相关信息

- [什么是混合标识](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD 连接同步：了解并自定义同步](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓扑](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 连接同步：同步到 Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)