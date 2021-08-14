---
title: 规划混合连接|Skype for Business Server 和 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: 通过配置混合模式Skype for Business Server Teams实现Skype for Business连接。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 090aab3d376a228915779c8bf55864484cee715d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234047"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>规划 Skype for Business Server 和 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

阅读本主题，了解如何规划 Skype for Business Server 与 Teams 之间的混合连接。 设置混合连接是将本地环境迁移到云的第一步。

如果你的本地 Skype for Business 用户也使用 Teams（并行），则这些用户无法从其 Teams 客户端与 Skype for Business 用户进行交互操作，也无法从 Teams 客户端与联合组织中的用户进行通信。 若要在 Teams 中获得此功能，必须将这些用户从本地 Skype for Business 移动到云，这需要配置 Skype for Business 混合模式。 此外，为了获得最佳体验，这些用户应进入"仅 Teams"模式，这可确保来自任何用户的所有传入呼叫和聊天都登录用户的 Teams 客户端。

在弃用本地 Skype for Business 部署之前，还需要设置混合连接并将所有用户移动到云。  设置混合连接后，你可以选择根据你的计划和业务需求将用户移动到云。 借助直接路由，你可以在迁移到云和完成迁移后，利用本地语音基础结构。

本主题介绍在部署和部署部署环境之间配置混合连接所需的基础结构和系统Skype for Business Server要求Teams。

阅读本主题并准备好配置混合连接后，请参阅配置 Skype for Business Server[和 Teams 之间的混合Teams。](configure-hybrid-connectivity.md) 配置主题提供有关在本地部署和内部部署之间设置混合连接的分Teams。

> [!Important]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持本地环境之间的 PSTN 连接Skype for Business Server云连接器版本与 Skype for Business Online 之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

## <a name="implications-of-the-upcoming-retirement-of-skype-for-business-online"></a>即将停用 Skype for Business Online 的影响
必须记住，在停用 Skype for Business Online 之前和之后，本地 Skype for Business Server 中的用户可以使用 Teams，但他们不能是 TeamsOnly。  (默认情况下，用户为"群岛"模式) 。 用户只有在 TeamsOnly 模式下Teams才能体验其全部优势，尤其是联盟和 PSTN 支持。 

即将停用 Skype for Business Online 不会影响 Skype for Business Server 或 Lync Server 2013 的现有支持生命周期。  但是，Skype for Business Online 即将停用将影响使用本地 Skype for Business Server 或 Lync Server 2013 的客户（包括现有混合组织）如何过渡到云的某些方面。 停用后不会更改的是，将混合用作从本地转换到云的方式保持不变。

目前，在停用 Skype for Business Online 之前，混合组织可以包含三种基本类型的用户： 
- 本地用户 (也可能不使用Teams，但不在"仅Teams模式下)  
- 具有除 TeamsOnly 外的任何共存模式的联机用户
- TeamsOnly 用户。

但是，停用 Skype for Business Online 后，混合组织只能包含两种基本类型的用户： 
- 本地用户可以 (Who也可能不使用Teams TeamsOnly 模式) 
- Teams仅用户。 

若要使组织从 Skype for Business Server 或 Lync Server 2013 移动到 Teams，他们仍必须使用同一工具集设置和配置混合，就像停用之前 *一样*。 更改的是，将用户从本地迁移到 Teams 时，不再需要指定 中的开关以将用户直接从本地移动到 `-MoveToTeams` `Move-CsUser` TeamsOnly。 以前，如果未指定此开关，则用户从本地Skype for Business Server转换为 Skype for Business Online，其模式保持不变。 为准备停用，使用 将用户从本地迁移到云时，现在会自动为用户分配 TeamsOnly 模式，其会议从本地自动转换为 Teams 会议，就像已指定切换一样，无论是否实际指定了交换机。 `Move-CsUser` `-MoveToTeams`  (包括从 Lync Server 2013 迁移，Lync Server 2013 从未具有 `MoveToTeams` switch.)  

同样，如果新用户直接在 Microsoft 365 而非本地创建，则无论租户模式如何，该用户Teams"仅"模式。  (此行为将在即将停用时推出。) 请记住，在混合组织中，应在本地 Active Directory (中创建新用户，然后同步到 Microsoft 365) ，而不是在 Microsoft 365 中直接创建用户，以确保本地用户可以路由到新用户。

停用 Skype for Business Online 后，共存模式将继续存在。 与以前一样，可以将帐户Skype for Business Server本地部署中的用户分配除 TeamsOnly 之外的任何共存模式。 但是，停用后，在线用户只能是 TeamsOnly (TeamsOnly，而目前 Skype for Business Online 用户可以是任何模式) 。  

> [!Important]
> - 拥有位于 Skype for Business Online 中的用户（不是 TeamsOnly）的现有混合组织应专注于尽快将这些用户升级到 Teams Only 模式，但不得晚于 2021 年 7 月 31 日停用。 如果你的组织仍有非 TeamsOnly Skype for Business Online 中的用户，则可能会安排 Microsoft 协助的升级，以将这些用户转换为 TeamsOnly。 这不会影响本地部署中Skype for Business Server用户。 在将在线、非 TeamsOnly 用户升级到 Skype for Business Online 之前，计划通知将提前发送给混合客户Teams。
> - 为准备停用 Skype for Business Online，很快将无法再将 TeamsOnly 模式分配给在线用户。

## <a name="about-shared-sip-address-space-functionality"></a>关于共享 SIP 地址空间功能

<a name="BKMK_Overview"> </a>

 在 Skype for Business Server 和 Teams 本地部署之间设置混合连接后，你可以将一些用户在本地进行管理，而将一些用户设置为联机。

此类配置依赖于共享 SIP 地址空间功能，有时称为"拆分域"，这意味着域（如 contoso.com）的用户在本地使用 Skype for Business Server 和 Teams 之间拆分，如下图所示：

![Skype for Business 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

配置共享 SIP 地址空间时：

- Azure Active Directory 连接用于将本地目录与 Microsoft 365。
- 本地用户与本地服务器交互Skype for Business服务器。
- 联机用户可能会与 Teams交互，直到 2021 年 7 月 31 Skype for Business基于共存模式在线。
- 这两个环境的用户可以相互通信。
- 本地 Active Directory 具有权威性。 所有用户都应首先在本地 Active Directory 中创建，然后同步到 Azure AD。 即使您打算让用户联机，您也必须先在本地环境中创建用户，然后将用户移至联机，以确保本地用户可以发现该用户。

必须先为用户分配一个 Teams 许可证以及计划 2 Skype for Business Online (，然后才能) 。 **即使停用 Skype for Business Online，也要求分配 Skype for Business Online 许可证。** 如果用户想要利用其他联机功能（如音频会议或 电话系统，则需要在 Microsoft 365 中为其分配适当的许可证。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>混合连接基础结构要求

<a name="BKMK_Infrastructure"> </a>

若要在本地环境和 Microsoft 365通信服务之间实现混合连接，您需要满足以下基础结构要求：

- 在支持的拓扑中部署的 Skype for Business Server 或 Lync Server 的单个本地部署。 请参阅 [本主题中的](plan-hybrid-connectivity.md#BKMK_Topology) 拓扑要求。

- 具有Microsoft 365的组织Teams。
    > [!NOTE]
    > 只能将单个租户用于本地部署的混合配置。
    
- Azure Active Directory 连接将本地目录与外部部署Microsoft 365。 有关详细信息，请参阅[Azure AD 连接：帐户和权限](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype for Business Server管理工具。 将用户从本地移动到云需要这些权限。 这些工具必须安装在可以访问本地部署和 Internet 的服务器上。
- 联机管理工具。 可以使用管理中心或Teams管理Windows PowerShell管理Teams。 若要使用 PowerShell 管理 Teams，请下载并安装 Teams PowerShell 模块。  (Skype for Business Online Connector 已停用) 。
- 必须启用共享 SIP 地址空间，并且必须将本地部署配置为将 Microsoft 365用作宿主提供商。 有关配置混合连接所需的步骤详细信息，请参阅配置 [混合连接](configure-hybrid-connectivity.md)。

配置混合连接后，可以将用户移动到Teams。 有关详细信息，请参阅将[用户从本地移动到Teams。](move-users-from-on-premises-to-teams.md)

## <a name="server-version-requirements"></a>服务器版本要求

<a name="BKMK_Topology"> </a>

若要将部署配置为与 Teams **混合，** 您需要具有以下受支持的拓扑之一：

- Skype for Business Server 2019 部署（所有服务器都运行 Skype for Business Server 2019）。
- Skype for Business Server 2015 部署（所有服务器都运行 Skype for Business Server 2015）。
- Lync Server 2013 部署，所有服务器均运行 Lync Server 2013。  但是，如果需要混合语音连接，则必须使用混合版本拓扑，如下所述。
- 最多 2 个不同服务器版本的部署，如下所示：
  - 2015 Skype for Business Server 2019 Skype for Business Server 2019 年
  - Lync Server 2013 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2015

如果 *任何* 拓扑中均需要混合语音，则指定为联盟边缘的边缘服务器以及与 SIP 联盟关联的池都必须在 Skype for Business 2015 或更高版本中运行。 如果存在，用户可以保留在 Lync 2013 池中。 有关详细信息，请参阅 [规划语音解决方案](/MicrosoftTeams/cloud-voice-landing-page.md)。

> [!NOTE]
> Lync Server 2010 不受 Teams。

## <a name="multi-forest-support"></a>多林支持

<a name="BKMK_MultiForest"> </a>

Microsoft 支持以下类型的多林混合方案：

- **资源林拓扑。** 在此类拓扑中，有一个林承载Skype for Business Server (资源林) ，还有一个或多个其他林承载帐户标识，这些林访问资源林中的 Skype for Business Server。 通常，如果满足Skype for Business要求，则用户可以访问另一个林中的功能：
  - 用户正确同步到托管用户Skype for Business。 在混合配置中，这意味着用户必须同步为已禁用的用户对象。
  - 托管用户的Skype for Business必须信任包含用户的林。
    有关资源林混合方案的详细信息，请参阅部署混合部署的资源林[Skype for Business。](configure-a-multi-forest-environment-for-hybrid.md)

- **在多个林中Skype for Business Server部署多个林。** 这种配置可能是合并和收购方案以及更复杂的企业的结果。 对于具有多个 Skype for Business 部署的任何组织，只要满足以下关键要求，就可以在单个 Microsoft 365 组织中将所有用户从本地合并到云：
  - 涉及的组织最多必须Microsoft 365一个。 不支持在具有多个组织的方案中进行合并。
  - 在任何给定时间，只有一个本地Skype for Business林可以处于混合模式， (SIP 地址空间) 。 所有其他本地Skype for Business林必须完全保持本地 (并可能相互联盟) 。 请注意，如果需要，这些其他本地组织可以同步到 AAD，并新增功能以禁用自 2018 年 12 月起可用的联机 [SIP](/powershell/module/skype/disable-csonlinesipdomain) 域。

    在多个林中部署 Skype for Business 的客户必须使用拆分域 (共享 SIP 地址空间) 功能将每个 Skype for Business 林分别迁移到 Microsoft 365 组织中。 林迁移完成后，客户必须禁用与本地部署的混合，然后才能继续迁移下一个本地部署Skype for Business部署。 此外，在迁移到云之前，本地用户与未在同一用户本地目录中表示的任何用户保持联盟状态。 有关详细信息，请参阅 Cloud [consolidation for Teams and Skype for Business](cloud-consolidation.md)。

## <a name="federation-requirements"></a>联合要求

<a name="BKMK_Federation"> </a>

配置混合Skype for Business时，必须确保本地环境和联机环境可以相互联盟。  默认情况下，联机环境具有开放联盟;默认情况下，本地环境通常已关闭联盟。  

要成功配置混合部署，必须满足以下要求：

- 对于本地部署和内部部署组织，域Microsoft 365相同。 如果在本地部署中启用了合作伙伴发现，则必须为联机组织配置开放联盟。 如果未启用合作伙伴发现，则必须为联机组织配置关闭联盟。
- 本地部署中的"阻止的域"列表必须与联机租户的"阻止的域"列表完全匹配。
- 本地部署中的"允许的域"列表必须与联机租户的"允许的域"列表完全匹配。
- 必须为联机租户的外部通信启用联盟。

## <a name="network-considerations"></a>网络注意事项

以下各节介绍以下各项的注意事项：

- DNS 设置
- 防火墙注意事项

### <a name="dns-settings-for-hybrid-deployments"></a>混合部署的 DNS 设置

<a name="BKMK_DNS"> </a>

为混合部署创建 DNS 记录时，Skype for Business外部 DNS 记录应指向内部部署基础结构。 有关所需的 DNS 记录的详细信息，请参阅 dns [requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，还需要确保下表中描述的 DNS 解析在内部部署中正常工作。  (如果已针对本地配置了联盟，则很可能已经拥有这些.) 

|DNS 记录  <br/> |可解决者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\> 解析为访问边缘外部 IP 服务器的所有受支持的 SIP (ip)   <br/> |边缘 (服务器)   <br/> |在混合配置中启用联盟通信。 边缘服务器需要知道在何处路由在内部部署和联机之间拆分的 SIP 域的联合流量。  <br/> 必须在用户名和 SRV 记录中的域之间使用严格的 DNS 名称匹配。  <br/> |
|边缘 Web (FQDN) DNS A 记录，例如 webcon.contoso.com 解析为 Web 会议边缘外部 IP ()   <br/> |内部企业网络连接用户的计算机  <br/> |允许联机用户在本地托管会议中呈现或查看内容。 内容包括PowerPoint、白板、投票和共享笔记。  <br/> |

根据组织中 DNS 的配置方式，您可能需要将这些记录添加到相应 SIP 域 (的内部托管 DNS 区域) 以提供这些记录的内部 DNS 解析。

### <a name="firewall-considerations-for-hybrid-deployments"></a>混合部署的防火墙注意事项

<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据您的 Microsoft Online Services 数据中心的位置，还必须配置网络防火墙设备以接受基于通配符域名的连接 (例如来自 \* .outlook.com) 的所有流量。 如果组织的防火墙不支持通配符名称配置，您必须手动确定要允许的 IP 地址范围和指定的端口。

有关详细信息（包括有关端口和协议要求的详细信息，请参阅 Microsoft 365 [URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)。
