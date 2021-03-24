---
title: 规划混合连接|Skype for Business Server 2019 和 Microsoft 365 或 Office 365 集成
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
description: 通过配置 Skype for Business 混合模式，计划实现 Skype for Business Server 与 Teams 或 Skype for Business Online 之间的混合连接。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 1a43243f4b5ce827a7c688c1aad1983466aa6ca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110258"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接

阅读本主题，了解如何规划 Skype for Business Server 与 Teams 或 Skype for Business Online 之间的混合连接。 设置混合连接是将本地环境迁移到云的第一步。

如果你的本地 Skype for Business 用户也使用 Teams（并行），则这些用户无法从其 Teams 客户端与 Skype for Business 用户进行交互操作，也无法从 Teams 客户端与联合组织中的用户进行通信。 若要在 Teams 中获得此功能，必须将这些用户从本地 Skype for Business 移动到云，这需要配置 Skype for Business 混合模式。 此外，为了获得最佳体验，这些用户应进入"仅 Teams"模式，这可确保来自任何用户的所有传入呼叫和聊天都登录用户的 Teams 客户端。

在弃用本地 Skype for Business 部署之前，还需要设置混合连接并将所有用户移动到云。  设置混合连接后，你可以选择根据你的计划和业务需求将用户移动到云。 借助直接路由，你可以在迁移到云和完成迁移后，利用本地语音基础结构。

本主题介绍配置现有本地 Skype for Business Server 部署与 Teams 或 Skype for Business Online 之间的混合连接所需的基础结构和系统要求。

阅读本主题并准备好配置混合连接后，请参阅配置 Skype for Business Server 与 [Microsoft 365 或 Office 365](configure-hybrid-connectivity.md)之间的混合连接。 配置主题提供有关在本地部署和 Teams 或 Skype for Business Online 之间设置混合连接的分步指南。

> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>关于共享 SIP 地址空间功能

<a name="BKMK_Overview"> </a>

 在 Skype for Business Server 和 Teams 或 Skype for Business Online 本地部署之间设置混合连接后，你可以将一些用户在本地进行管理，而将一些用户设置为联机。

此类配置依赖于共享 SIP 地址空间功能，有时称为"拆分域"，这意味着域（如 contoso.com）的用户将拆分为在本地使用 Skype for Business Server 和 Teams 或 Skype for Business Online，如下图所示：

![Skype for Business 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

配置共享 SIP 地址空间时：

- Azure Active Directory Connect 用于将本地目录与 Microsoft 365 或 Office 365 同步。
- 本地用户与本地 Skype for Business 服务器交互。
- 联机用户可能会与 Skype for Business Online 或 Teams 服务交互。
- 这两个环境的用户可以相互通信。
- 本地 Active Directory 具有权威性。 所有用户都应首先在本地 Active Directory 中创建，然后同步到 Azure AD。 即使您打算让用户联机，您也必须先在本地环境中创建用户，然后将用户移至联机状态，以确保本地用户可以发现该用户。

必须先为用户分配 Skype for Business Online 或计划 2 (许可证，然后才能) 用户。 如果用户将使用 Teams，则还必须为该用户分配 Teams 许可证 (Skype for Business 许可证必须保持启用状态) 。 如果用户想要利用其他联机功能（如音频会议或电话系统），则需要在 Microsoft 365 或 Office 365 中为其分配适当的许可证。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>混合连接基础结构要求

<a name="BKMK_Infrastructure"> </a>

若要在本地环境与 Microsoft 365 或 Office 365 通信服务之间实现混合连接，您需要满足以下基础结构要求：

- 在支持的拓扑中部署的 Skype for Business Server 或 Lync Server 的单个本地部署。 请参阅 [本主题中的](plan-hybrid-connectivity.md#BKMK_Topology) 拓扑要求。

- 启用了 Skype for Business Online 的 Microsoft 365 或 Office 365 组织。
    > [!NOTE]
    > 只能将单个租户用于本地部署的混合配置。
    
- Azure Active Directory Connect，用于将本地目录与 Microsoft 365 或 Office 365 同步。 有关详细信息，请参阅 [Azure AD Connect：帐户和权限](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype for Business Server 管理工具。 将用户从本地移动到云需要这些权限。 这些工具必须安装在可以访问本地部署和 Internet 的服务器上。
- 联机管理工具。 可以使用 Teams 管理中心或 Windows PowerShell管理 Teams 和 Skype for Business Online。 若要使用 PowerShell 管理 Teams 或 Skype for Business Online，请下载并安装 Skype for Business Online 连接器。
- 必须启用共享 SIP 地址空间，并且必须将本地部署配置为将 Microsoft 365 或 Office 365 用作宿主提供商。 有关配置混合连接所需的步骤详细信息，请参阅配置 [混合连接](configure-hybrid-connectivity.md)。

配置混合连接后，可以将用户移至 Teams 或 Skype for Business Online。 有关详细信息，请参阅将用户[从](move-users-from-on-premises-to-teams.md)本地移动到 Teams 和将用户从本地移动到[Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md)

## <a name="server-version-requirements"></a>服务器版本要求

<a name="BKMK_Topology"> </a>

若要配置与 Teams 或 **Skype for Business Online** 的混合部署，你需要具有以下受支持的拓扑之一：

- Skype for Business Server 2019 部署（所有服务器都运行 Skype for Business Server 2019）。
- Skype for Business Server 2015 部署（所有服务器都运行 Skype for Business Server 2015）。
- Lync Server 2013 部署，所有服务器均运行 Lync Server 2013。  但是，如果需要混合语音连接，则必须使用混合版本拓扑，如下所述。
- 最多 2 个不同服务器版本的部署，如下所示：
  - Skype for Business Server 2015 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2015

如果 *任何* 拓扑中均需要混合语音，则指定为联盟边缘的边缘服务器以及与 SIP 联盟关联的池都必须运行 Skype for Business 2015 或更高版本。 如果存在，用户可以保留在 Lync 2013 池中。 有关更多详细信息，请参阅在 Skype for Business Server 中使用 [PSTN 连接规划电话系统](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。

Skype for Business Online 支持以下包含 **Lync Server 2010** 的拓扑，用于即时消息和会议。 混合语音和 Teams 不支持包含 **Lync Server 2010** 的拓扑。

- 混合 Lync Server 2010 和 Skype for Business Server 2015 部署
- 混合 Lync Server 2010 和 Lync Server 2013 部署
- Lync Server 2010 部署，所有服务器运行 Lync Server 2010，具有最新的累积更新。

联盟边缘服务器和联合边缘服务器的下一个跃点服务器必须运行具有最新累积更新的 Lync Server 2010。 Skype for Business Server 2015 或 Lync Server 2013 管理工具必须安装在至少一台服务器或管理工作站上。

## <a name="multi-forest-support"></a>多林支持

<a name="BKMK_MultiForest"> </a>

Microsoft 支持以下类型的多林混合方案：

- **资源林拓扑。** 在此类型的拓扑中，有一个林承载 Skype for Business Server (资源林) ，还有一个或多个其他林承载帐户标识，这些林访问资源林中的 Skype for Business Server。 通常，如果满足以下要求，用户可以访问另一个林中的 Skype for Business 功能：
  - 用户正确同步到托管 Skype for Business 的林中。 在混合配置中，这意味着用户必须同步为禁用的用户对象。
  - 托管 Skype for Business 的林必须信任包含用户的林。
    有关资源林混合方案的详细信息，请参阅部署混合 Skype for Business 的资源 [林拓扑](configure-a-multi-forest-environment-for-hybrid.md)。

- **多个林中有多个 Skype for Business Server 部署。** 这种配置可能是合并和收购方案以及更复杂的企业的结果。 对于具有多个 Skype for Business 部署的任何组织，只要满足以下关键要求，就可以将所有用户从本地合并到单个 Microsoft 365 或 Office 365 组织中云：
  - 最多必须涉及一个 Microsoft 365 或 Office 365 组织。 不支持在具有多个组织的方案中进行合并。
  - 在任何给定时间，只有一个本地 Skype for Business 林可以处于混合模式 (共享 SIP 地址空间) 。 所有其他本地 Skype for Business 林必须完全保留在本地 (并可能相互联盟) 。 请注意，如果需要，这些其他本地组织可以同步到 AAD，并新增功能以禁用自 2018 年 12 月起可用的联机 [SIP](/powershell/module/skype/disable-csonlinesipdomain) 域。

    在多个林中部署 Skype for Business 的客户必须使用拆分域 (共享 SIP 地址空间) 功能将每个 Skype for Business 林分别完全迁移到 Microsoft 365 或 Office 365 组织，然后禁用与本地部署的混合，然后再继续迁移下一个本地 Skype for Business 部署。 此外，在迁移到云之前，本地用户与未在同一用户本地目录中表示的任何用户保持联盟状态。 有关详细信息，请参阅 Teams [和 Skype for Business 的云合并](cloud-consolidation.md)。

## <a name="federation-requirements"></a>联合要求

<a name="BKMK_Federation"> </a>

配置 Skype for Business 混合模式时，必须确保本地环境和联机环境可以相互联盟。  默认情况下，联机环境具有开放联盟;默认情况下，本地环境通常已关闭联盟。  

要成功配置混合部署，必须满足以下要求：

- 必须为本地部署和 Microsoft 365 或 Office 365 组织配置相同的域匹配。 如果在本地部署中启用了合作伙伴发现，则必须为联机组织配置开放联盟。 如果未启用合作伙伴发现，则必须为联机组织配置关闭联盟。
- 本地部署中的"阻止的域"列表必须与联机租户的"阻止的域"列表完全匹配。
- 本地部署中的"允许的域"列表必须与联机租户的"允许的域"列表完全匹配。
- 必须为联机租户的外部通信启用联盟。

## <a name="network-considerations"></a>网络注意事项

以下各节介绍以下各项的注意事项：

- DNS 设置
- 防火墙注意事项

### <a name="dns-settings-for-hybrid-deployments"></a>混合部署的 DNS 设置

<a name="BKMK_DNS"> </a>

为混合部署创建 DNS 记录时，所有 Skype for Business 外部 DNS 记录都应指向本地基础结构。 有关所需的 DNS 记录的详细信息，请参阅 [DNS requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，还需要确保下表中描述的 DNS 解析在内部部署中正常工作。  (如果已针对本地配置了联盟，则很可能已经拥有这些.) 

|DNS 记录  <br/> |可解决者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\> 解析为访问边缘外部 IP 服务器的所有受支持的 SIP ()   <br/> |边缘 (服务器)   <br/> |在混合配置中启用联盟通信。 边缘服务器需要知道在何处路由在内部部署和联机之间拆分的 SIP 域的联合流量。  <br/> 必须在用户名和 SRV 记录中的域之间使用严格的 DNS 名称匹配。  <br/> |
|边缘 Web (FQDN) DNS A 记录，例如 webcon.contoso.com 解析为 Web 会议边缘外部 IP (服务器)   <br/> |内部企业网络连接用户的计算机  <br/> |允许联机用户在本地托管会议中呈现或查看内容。 内容包括 PowerPoint 文件、白板、投票和共享笔记。  <br/> |

根据 DNS 在组织中配置方式，您可能需要将这些记录添加到相应 SIP 域 () 的内部托管 DNS 区域，以针对这些记录提供内部 DNS 解析。

### <a name="firewall-considerations-for-hybrid-deployments"></a>混合部署的防火墙注意事项

<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据您的 Microsoft Online Services 数据中心的位置，还必须配置网络防火墙设备以接受基于通配符域名的连接 (例如来自 \* .outlook.com) 的所有流量。 如果组织的防火墙不支持通配符名称配置，您必须手动确定要允许的 IP 地址范围和指定的端口。

有关详细信息，包括有关端口和协议要求的详细信息，请参阅 [Microsoft 365 和 Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)。