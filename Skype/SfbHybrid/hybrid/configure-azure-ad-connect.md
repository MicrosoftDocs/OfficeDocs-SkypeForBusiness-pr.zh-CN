---
title: 配置Azure AD 连接
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: 有关在混合Azure AD 连接配置策略的说明。
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887210"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>为 Teams 和 Skype for Business 配置 Azure AD Connect

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
若要Teams，本地部署 Skype for Business Server 或 Lync Server 2013 的组织必须配置 Azure AD 连接 以将其本地目录与 Microsoft 365 同步。 具有本地Skype for Business Server的组织必须确保正确的 msRTCSIP 属性同步到Azure AD。 本文中对"Skype for Business Server"的任何引用也适用于 Lync Server 2013。

> [!NOTE]
> - 若要获得完整功能，Teams本地Skype for Business现有用户需要将 Skype for Business 本地帐户移动到云。 例如，获取功能，如与联盟Skype for Business互操作，以及与联盟组织的用户进行通信的功能。 如果本地用户将仅使用 Teams，你仍必须将用户移动到云，以作为 TeamsOnly Teams完整功能。 若要进行此迁移，必须配置Azure AD 连接，以便启用混合。
> - 如果你不计划很快将用户从本地移动到云，你仍然必须配置 Azure AD 连接，以便 Teams 和 Skype for Business Server 帐户共存。
 

## <a name="background-information"></a>背景信息

Azure Active Directory 连接你的本地 Active Directory 持续与 Microsoft 365。 本地目录仍然是权威标识源，而来自本地环境的更改将同步到Azure AD。 有关详细信息，请参阅 Azure AD 连接 [Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 *你的组织的用户将同时在本地目录和联机目录中表示。*  在本地使用 Teams 或 Skype for Business 所有用户都必须从本地同步到 Azure AD 以确保这些帐户共存。 此外，你可能通过混合连接促进本地用户和在线用户之间的Skype for Business，这也需要配置Azure AD 连接。


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>在有 Skype for Business Server 的情况下配置 Azure AD 

### <a name="general-requirements"></a>常规要求 

若要使 Skype for Business Server 本地部署与 Teams 共存，本地部署中的某些 Active Directory 属性必须使用 Azure AD 连接 同步到 Azure AD 中。 安装程序Azure AD 连接在检测到本地环境中存在自定义项时自动配置Skype for Business Server同步的必需属性。 这些属性包括常规标识属性（如用户主体名称）以及以"msRTCSIP"为前名的属性，这些属性特定于 Skype For Business Server。 完整属性集在"同步：同步Azure AD 连接[属性"中Azure Active Directory。](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)

如果选择自定义用户中的同步Azure AD 连接，必须确保为用户对象同步以下属性：
</br>

|属性|说明|
|---|---|
|msRTCSIP-PrimaryUserAddress| 本地环境中用户的 sip 地址|
|msRTCSIP-DeploymentLocator| 指示用户是托管在本地还是云中|
|msRTCSIP-UserEnabled| 用户是否已启用 SIP 功能|
|||

</br>
</br>
此外，如果要通过本地部署管理电话系统属性，还必须同步以下属性：

|属性|说明|
|:---|:---|
|msRTCSIP-Line| 用户的电话号码|
|msRTCSIP-OptionFlags| 指示用户是否已启用语音功能|
|msRTCSIP-OwnerUrn| 用于标识混合应用程序终结点|
|||

</br>
Microsoft 建议您同步包含用户标识的所有林以及包含用户标识Skype for Business Server。 如果用户的标识存在于多个林中，Azure AD Connect 应进行合并。 遵循本指南后，Azure AD Connect 会自动同步正确的属性，前提是你不修改 Azure AD Connect 中的“连接器”或“同步规则”。 
  
如果未从包含用户标识和 Skype for Business Server 部署的所有林进行同步，必须确保使用 Teams 或 Skype for Business (的任何用户使用 Azure AD（无论是本地还是联机) ）正确填充相关的标识和 Skype for Business 属性。 这可能需要其他本地目录同步。 有关详细信息，请参阅 Azure AD 连接[sync： Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

客户有责任确保正确配置以将属性填充到Azure AD。 请注意以下几点： 

- 使用非标准配置同步到Azure AD存在风险。 非标准配置可能导致联机目录中的数据损坏。

- 随着产品发展，Microsoft 将继续验证同步所有相关林的标准同步配置。 如果拥有自定义同步配置，客户负责确保配置将正确的属性和值传递到 Azure AD 中。 

无论是一个内部部署 Active Directory 林还是多个林，Azure AD 连接可用于各种支持的拓扑，如[Topologies for Azure AD 连接 中所述](/azure/active-directory/hybrid/plan-connect-topologies)。 从企业Skype for Business Server，有三种变体： 

1. 单个林，其中包含权威用户标识，并托管 Skype for Business Server。 

2. 多个林，其中只有一个林托管 Skype for Business Server，其他一个或多个林（帐户林）包含权威用户标识。 

3. 多个林中有多个 Skype for Business Server 部署。 如果满足某些要求，组织可以将这些多个部署合并到一个Microsoft 365组织中。

### <a name="single-forest"></a>单个林 

如果用户帐户和 Skype for Business 全都托管在单个林中，你必须确保将 Azure AD Connect 配置为，将此林中的用户同步到 Azure AD 中。  默认情况下，相应的属性将自动同步到Azure Active Directory。 建议客户不要修改管理配置模板的内置同步规则和/或连接器 (安装向导中无法) 。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>多个林中有一个 Skype for Business 部署 

此方案通常称为“资源林拓扑”。 用户的权威标识托管在一个或多个帐户林中，Skype for Business 单独部署在一个资源林中（其本身可能也会托管权威用户标识）。 一般说来，Skype for Business 用户的权威标识可能与 Skype for Business Server 位于同一林中，也可能位于其他林中，前提是： 

- 帐户林中具有权威标识的用户 () 资源林 (其中 Skype for Business Server 部署为) 用户对象。 资源林中的 msRTCSIP-OriginatorSID 属性必须与帐户林中的 SID 匹配。 有关更多详细信息，请参阅为混合部署配置多林[Skype for Business。](configure-a-multi-forest-environment-for-hybrid.md)

- 托管 Skype for Business Server 的资源林信任一个或多个帐户林。  

- 资源林) 中的标识林 (和资源林) 中的 Skype for Business (的标识对象的所有相关用户对象和属性Azure AD通过 Azure AD 连接 同步到 Azure AD 中。  

  若要在多林本地方案中将正确的对象和属性同步到[](configure-a-multi-forest-environment-for-hybrid.md)Azure AD，Microsoft 强烈建议使用 Azure AD 连接 同步已启用用户帐户的所有林和包含 Skype for Business 的林。 假设你从所有林进行同步，必须将 Azure AD Connect 配置为，合并这些标识，并同步到 Azure AD 中。 Azure AD Connect 旨在处理这种情况，它在安装向导中提供了用于进行此设置的内置选项，包括设置用于联接标识的定位标记。 选择以下选项： **用户标识存在于** 多个目录中，使用 **--> ObjectSID 和 msExchangeMasterAccountSID 属性进行匹配**。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多个林中有多个 Skype for Business Server 部署 

在此方案中，存在多个林，每个林Skype for Business Server一个Microsoft 365组织。 每个包含Skype for Business Server的林都可以使用Azure AD同步到组织的Azure AD 连接。 在给定时间，最多只能为 Skype for Business 混合配置一个林。 在林中启用混合之前，必须使用 [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)禁用所有其他林的所有 SIP 域。 有关详细信息，请参阅 Cloud [consolidation for Teams and Skype for Business](cloud-consolidation.md)。


## <a name="related-information"></a>相关信息

- [什么是混合标识](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect 同步：了解并自定义同步](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓扑](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 连接同步：同步到Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
