---
title: 规划混合连接 |Skype for Business Server 2019 Microsoft 365 和 Office 365 集成
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
description: 规划在 Skype for business Server 和 Skype for business Online 或团队之间实施混合连接的注意事项。
ms.openlocfilehash: ff0ac03d0f93eaa509badb4462d179b41f77ab21
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779749"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接

## <a name="overview"></a>概述

阅读本主题，了解如何规划 Skype for Business Server 和团队或 Skype for business Online 之间的混合连接。 设置混合连接是将本地环境迁移到云的第一步。

如果你的本地 Skype for Business 用户也使用 Teams（并行），则这些用户无法从其 Teams 客户端与 Skype for Business 用户进行交互操作，也无法从 Teams 客户端与联合组织中的用户进行通信。 若要在 Teams 中获得此功能，必须将这些用户从本地 Skype for Business 移动到云，这需要配置 Skype for Business 混合模式。 此外，为了获得最佳体验，这些用户应处于 "仅团队" 模式，以确保来自用户团队客户端中的任何用户土地的所有传入呼叫和聊天。

在弃用本地 Skype for Business 部署之前，还需要设置混合连接并将所有用户移动到云。  设置混合连接后，你可以选择根据你的计划和业务需求将用户移动到云。 借助直接路由，你可以在迁移到云和完成迁移后，利用本地语音基础结构。

本主题介绍在现有的本地 Skype for business Server 部署和团队或 Skype for business Online 之间配置混合连接时所需的基础结构和系统要求。

阅读本主题并准备好配置混合连接后，请参阅在[Skype For Business Server 和 Office 365 之间配置混合连接](configure-hybrid-connectivity.md)。 配置主题提供了有关在本地部署和团队或 Skype for business Online 之间设置混合连接的分步指南。

## <a name="about-shared-sip-address-space-functionality"></a>关于共享 SIP 地址空间功能

<a name="BKMK_Overview"> </a>

 在 Skype for business Server 和团队或 Skype for business Online 的本地部署之间设置混合连接，可以让一些用户驻留在本地，而某些用户驻留在网上。

此类型的配置依赖于共享的 SIP 地址空间功能，有时也称为 "拆分域"--即域的用户（如 contoso.com）在使用 Skype for Business Server on on-premises and team 或 Skype for business Online 之间进行拆分，如下图所示：

![SfB 混合连接-拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

配置共享 SIP 地址空间时：

- Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。
- 驻留在本地的用户与本地 Skype for Business 服务器交互。
- 联机驻留的用户可能与 Skype for Business Online 或团队服务进行交互。
- 这两个环境中的用户可以相互通信。
- 内部部署 Active Directory 是权威的。 所有用户应首先在本地 Active Directory 中创建，然后同步到 Azure AD。 即使您打算将用户置于联机状态，您也必须先在本地环境中创建用户，然后将该用户移到 "联机"，以确保本地用户可以发现该用户。

在用户可以联机移动之前，必须为用户分配 Skype for Business Online （计划2）许可证。 如果用户将使用团队，则还必须为该用户分配团队许可证（并且 Skype for Business 许可证必须保持启用状态）。 如果您的用户想要利用其他在线功能（如音频会议或电话系统），您需要在 Office 365 中为他们分配适当的许可证。

## <a name="infrastructure-requirements"></a>基础结构要求

<a name="BKMK_Infrastructure"> </a>

若要在本地环境和 Office 365 通信服务之间实现混合连接，需要满足以下基础结构要求：

- 在受支持的拓扑中部署的 Skype for Business Server 或 Lync Server 的单个本地部署。 请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。
- 启用了 Skype for Business Online 的 Microsoft Office 365 组织。
    > [!NOTE]
    > 您可以仅将一个租户用于与本地部署的混合配置。
- Azure Active Directory Connect，用于将本地目录与 Office 365 同步。 有关详细信息，请参阅[AZURE AD Connect：帐户和权限](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。
- Skype for Business Server 管理工具。  这是将用户从本地迁移到云所必需的。 必须在具有本地部署和 internet 访问权限的服务器上安装这些工具。
- 联机管理工具。  您可以使用团队管理员中心或 Windows PowerShell 管理团队和 Skype for Business Online。 若要使用 PowerShell 管理团队或 Skype for business Online，请下载并安装 Skype for Business Online 连接器。
- 必须启用共享 SIP 地址空间，并且必须将本地部署配置为使用 Office 365 作为托管提供程序。 有关配置混合连接所需步骤的详细信息，请参阅[配置混合连接](configure-hybrid-connectivity.md)。

配置混合连接后，可以将用户移动到团队或 Skype for Business Online。 有关详细信息，请参阅[将用户从本地移动到团队](move-users-from-on-premises-to-teams.md)和[将用户从本地移动到 Skype for business Online](move-users-from-on-premises-to-skype-for-business-online.md)。

## <a name="server-version-requirements"></a>服务器版本要求

<a name="BKMK_Topology"> </a>

若要配置与**团队或 Skype For Business Online**的混合部署，您需要具有以下受支持的拓扑之一：

- 一个 Skype for business Server 2019 部署，其中包含运行 Skype for Business Server 2019 的所有服务器。
- 一个 Skype for business Server 2015 部署，其中包含运行 Skype for Business Server 2015 的所有服务器。
- Lync Server 2013 部署，其中包含运行 Lync Server 2013 的所有服务器。  但是，如果需要混合语音连接，则必须使用混合版本拓扑，如下所述。
- 一种部署，其中最多包含2个不同的服务器版本，如下所示：
  - Skype for business Server 2015 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2015

*如果任何拓扑中都需要混合语音*，则被指定为联盟边缘的边缘服务器以及与 SIP 联合关联的池必须运行 Skype for business 2015 或更高版本。 用户可以保留在 Lync 2013 池（如果存在）。 有关更多详细信息，请参阅[在 Skype For Business Server 中规划带有 PSTN 连接的电话系统](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。

包含 Lync Server 2010 的以下拓扑支持用于即时消息和会议的**Skype For Business Online** 。  **混合语音和团队不支持包含 Lync Server 2010**的拓扑。

- 混合 Lync Server 2010 和 Skype for Business Server 2015 部署
- 混合 Lync Server 2010 和 Lync Server 2013 部署
- Lync Server 2010 部署，其中包含运行 Lync Server 2010 的所有服务器以及最新的累积更新。

联合边缘服务器和联合边缘服务器中的下一个跃点服务器必须使用最新的累积更新运行 Lync Server 2010。 Skype for Business Server 2015 或 Lync Server 2013 管理工具必须至少安装在一台服务器或管理工作站上。

## <a name="multi-forest-support"></a>多林支持

<a name="BKMK_MultiForest"> </a>

Microsoft 支持以下类型的多林混合方案：

- **资源林拓扑。** 在这种拓扑中，有一个承载 Skype for Business Server （资源林）的林，还有一个或多个其他林，它们托管帐户标识，可访问资源林中的 Skype for Business Server。 通常，如果满足以下要求，用户可以在另一个林中访问 Skype for Business 功能：
  - 将用户正确同步到承载 Skype for Business 的林中。 在混合配置中，这意味着用户必须同步为禁用的用户对象。
  - 托管 Skype for Business 的林必须信任包含用户的林。
    有关资源林混合方案的详细信息，请参阅[为混合 Skype For Business 部署资源林拓扑](configure-a-multi-forest-environment-for-hybrid.md)。
- **多个林中的 Skype for Business Server 的多个部署。** 这种配置可因合并和收购方案以及在更复杂的企业中而产生。  将所有用户从本地部署到单个 Office 365 组织中的云的合并可为具有多个 Skype for Business 部署的任何组织实现，前提是满足以下关键要求：

  - 至少必须有一个 Office 365 组织。 不支持在具有多个 Office 365 组织的方案中进行合并。
  - 在任何给定时间，只有一个本地 Skype for Business 林可以处于混合模式（共享 SIP 地址空间）。 所有其他本地 Skype for business 林必须在内部部署中保持完全（且大概相互联合）。 请注意，如果需要，可通过新功能将这些其他内部部署组织同步到 AAD，以禁用2018年12月提供的[联机 SIP 域](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain)。

    在多个林中部署 Skype for business 的客户必须使用拆分域（共享 SIP 地址空间）功能将每个 Skype for Business 林单独完全迁移到 Office 365 组织中，然后在迁移到迁移下一个本地 Skype for Business 部署之前，先在本地部署中禁用混合。 此外，在迁移到云之前，本地用户仍将与在同一用户的本地目录中未表示的任何用户保持联合状态。 有关更多详细信息，请参阅[适用于团队和 Skype For business 的云合并](cloud-consolidation.md)。

## <a name="federation-requirements"></a>联合身份验证要求

<a name="BKMK_Federation"> </a>

在配置混合时，您必须确保您的内部部署和联机环境可以相互联盟。  默认情况下，联机环境具有开放联盟;默认情况下，内部部署环境通常具有关闭的联合身份验证。  

若要成功配置混合部署，必须满足以下要求：

- 为本地部署和 Office 365 组织配置的域匹配必须相同。 如果在本地部署上启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。 如果未启用合作伙伴发现，则必须为您的联机租户配置关闭的联合身份验证。
- 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。
- 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。
- 必须为联机租户的外部通信启用联合。

## <a name="network-considerations"></a>网络注意事项

以下各节介绍了以下方面的注意事项：

- DNS 设置
- 防火墙注意事项

### <a name="dns-settings"></a>DNS 设置

<a name="BKMK_DNS"> </a>

在为混合部署创建 DNS 记录时，所有 Skype for business 外部 DNS 记录都应指向内部部署基础结构。 有关所需 DNS 记录的详细信息，请参阅[Skype For Business Server 的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，还需要确保下表中所述的 DNS 解析在本地部署中运行。 （如果已将联合身份验证配置为本地，则很可能已经具有这些。）

|DNS 记录  <br/> |可解析者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls _tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有受支持的 SIP 域解析为访问边缘外部 IP （s）  <br/> |边缘服务器  <br/> |在混合配置中启用联合通信。 边缘服务器需要知道为在本地和联机之间拆分的 SIP 域路由联盟流量的位置。  <br/> 必须在用户名和 SRV 记录中使用域之间的严格 DNS 名称匹配。  <br/> |
|用于边缘 Web 会议服务 FQDN 的 DNS A 记录，例如，webcon.contoso.com 解析为 Web 会议边缘外部 IP （s）  <br/> |连接到用户计算机的内部公司网络  <br/> |使联机用户能够在本地托管会议中显示或查看内容。 内容包括 PowerPoint 文件、白板、投票和共享便笺。  <br/> |

根据组织中配置 DNS 的方式，您可能需要将这些记录添加到相应 SIP 域的内部托管 DNS 区域中，以提供对这些记录的内部 DNS 解析。

### <a name="firewall-considerations"></a>防火墙注意事项

<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据 Microsoft Online Services 数据中心的位置，您还必须将网络防火墙设备配置为根据通配符域名（例如，所有来自\*outlook.com 的流量）接受连接。 如果组织的防火墙不支持通配符名称配置，则必须手动确定要允许和指定端口的 IP 地址范围。

有关详细信息，包括有关端口和协议要求的详细信息，请参阅[Office 365 url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。
