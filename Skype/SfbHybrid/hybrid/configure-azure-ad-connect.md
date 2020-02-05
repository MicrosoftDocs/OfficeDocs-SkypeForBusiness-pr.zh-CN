---
title: 配置 Azure AD Connect
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
description: 在混合环境中配置 Azure AD Connect 的说明。
ms.openlocfilehash: 3060ef443fd2ee57157c2590441c5fe04b1d8739
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726932"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>为团队和 Skype for business 配置 Azure AD Connect
 
具有本地 Skype for Business Server （或 Lync Server）以及计划使用团队或 Skype for business Online 的组织必须将 Azure AD Connect 配置为将其本地目录与 Office 365 同步，如以下所述：证明.  这包括直接从 Skype for Business 从本地迁移到团队的组织。 特别是，在本地 Skype for business 的组织必须确保将正确的 msRTCSIP 属性同步到 Azure AD 中。 

> [!NOTE]
> 如果现有团队还具有 Skype for business 内部部署的用户，则需要将其 Skype for Business 内部部署帐户移动到云，以获得完整功能，例如与 Skype for business 用户进行互操作的能力，以及与联合组织中的用户进行通信。 即使用户只是使用团队，基础结构也需要此联机 Skype for Business 帐户来提供其他功能。  若要进行此迁移，必须确保正确配置了 Azure AD Connect，以便能够启用混合。
 

## <a name="background-information"></a>背景信息

Azure Active Directory Connect 保持您的本地 Active Directory 持续与 Office 365 保持同步。  您的本地目录仍是身份的权威源，并且您的本地环境中的更改将同步到 Azure AD 中。 有关详细信息，请参阅[AZURE AD Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 即使您不将所有用户从本地迁移到云，使用团队、Skype for Business 本地或 Skype for business Online 的所有用户都必须从内部部署同步到 Azure AD，以确保本地用户和联机用户之间的通信。 *您的组织中的用户将在本地目录和联机目录中进行表示。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>在拥有 Skype for Business Server 时配置 Azure AD 

无论您是否具有一个本地 Active Directory 林或多个林，都可以在各种受支持的拓扑中使用 Azure AD Connect，如[AZURE Ad connect 的拓扑](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)中所述。  从 Skype for Business Server 的角度来看，有三种主要变化： 

1. 一个包含权威用户标识和主机 Skype for Business Server 的林。 

2. 多个林，其中只有一个承载 Skype for Business Server 以及包含权威用户标识（帐户林）的一个或多个其他林。 

3. 多个林中的 Skype for Business Server 的多个部署。 如果满足某些要求，组织可以将这些多个部署合并到一个 Office 365 租户中。

### <a name="single-forest"></a>单林 

如果用户帐户和 Skype for Business 都托管在单个林中，则必须确保将 Azure AD Connect 配置为将此林的用户同步到 Azure AD。  虽然 Azure AD Connect 安装向导具有多种选项，但相应的属性将自动同步到 Azure Active Directory 中。 建议客户不要修改用于管理配置的内置同步规则和/或连接器（无法通过安装向导）。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>具有一个 Skype for Business 部署的多个林 

此方案通常称为资源林拓扑。 用户的权威标识托管在一个或多个帐户林中，Skype for Business 部署在单独的资源林中（本身也可能承载权威用户身份）。 通常情况下，Skype for business 用户的权威身份与 Skype for Business Server 和/或另一个林中的林（如果有）： 

- 具有帐户林的权威标识的用户在资源林（其中部署了 Skype for Business 服务器）中表示为禁用的用户对象，并且资源林中的 msRTCSIP 属性与 OriginatorSID 中的 SID 匹配帐户林。 有关详细信息，请参阅为[混合 Skype For Business 配置多林环境](configure-a-multi-forest-environment-for-hybrid.md)。

- 托管 Skype for Business Server 的资源林信任帐户林。  

- 所有有关 identity （from account 林）和 Skype for Business （来自资源林）的相关用户对象和属性都将通过 Azure AD Connect 以正确的值同步到 Azure AD。  

 若要在[多林本地方案](configure-a-multi-forest-environment-for-hybrid.md)中在 Azure ad 中实现正确的对象和属性同步，Microsoft 强烈建议使用 Azure ad Connect 从已启用用户帐户和包含 Skype for business 的林的所有林同步。  如果您从所有林同步，则必须将 Azure AD Connect 配置为合并这些标识并将其同步到 Azure AD。 Azure AD Connect 旨在处理这种情况，并在安装向导中提供内置选项以进行设置，包括设置指向加入标识的定位。  选择以下内容：多个目录之间存在用户标识。 使用--> ObjectSID 和 msExchangeMasterAccountSID 属性进行匹配。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多个林中的多个 Skype for Business Server 部署 

在这种情况下，有多个林，每个林都包含 Skype for Business Server 和一个 Office 365 租户。  可以使用 AAD Connect 将每个包含 Skype for Business Server 的林同步到该租户的 Azure AD 中。 在给定时间，最多只能为 Skype for business 混合配置一个林。 在林中启用混合功能之前，必须使用[csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)禁用所有其他林的所有 SIP 域。 有关如何将此类环境合并到 Office 365 的更多详细信息，请参阅[云整合（针对团队和 Skype For business](cloud-consolidation.md)）。

## <a name="general-requirements"></a>一般要求 

团队和 Skype for business Online 服务都要求正确的 Active Directory 属性存在，并在 Azure AD 中进行了填充。  Microsoft 的一般建议是同步所有包含用户标识的林，以及包含 Skype for Business Server 的任何林。

 如果多个林之间存在用户的标识，Azure AD Connect 应执行合并。 当遵循本指南时，Azure AD Connect 将自动同步正确的属性，前提是您不修改 Azure AD Connect 中的连接器或同步规则。 
  
如果您不从包含用户标识和 Skype for Business Server 部署的所有林同步，您仍必须确保将相关身份和 Skype for business 属性正确地填充到使用团队或 Skype 的任何用户的 Azure AD 中for Business （无论是本地还是联机）--这可能需要其他本地目录同步。 有关详细信息，请参阅[AZURE AD Connect sync：属性同步到 Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

在这种情况下，客户有责任确保将属性填充到 Azure AD 中的正确配置。 请注意下列事项： 

- 将非标准配置用于同步到 Azure AD 的风险很大，因为这可能会导致错误配置，这可能导致联机目录中的数据损坏。

- 随着产品的发展，Microsoft 将继续验证所有相关林同步的标准同步配置。 具有自定义同步配置的客户负责确保其配置将正确的属性和值传递到 Azure AD。 

## <a name="related-information"></a>相关信息

- [什么是混合标识](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 同步：了解和自定义同步](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓扑](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect sync：属性已同步到 Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
