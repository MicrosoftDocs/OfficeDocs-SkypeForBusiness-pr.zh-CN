---
title: 规划混合连接|Skype for Business Server和 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: 计划通过配置Skype for Business混合模式实现Skype for Business Server和 Teams 之间的混合连接。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695045"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>规划Skype for Business Server和 Teams 之间的混合连接

> [!Important]
> 尽管自 2021 年以来已停用 Skype for Business Online，但仍支持本地产品Skype for Business Server 2019、Skype for Business Server 2015 和 Lync Server 2013。 此外，Microsoft 支持这些本地产品与 Microsoft Teams 之间的混合环境。 这允许具有这些本地部署的组织将其用户迁移到 TeamsOnly。  最后，不再支持云连接器版Skype for Business Server。 需要本地 PSTN 连接的客户应使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)。


阅读本主题，了解如何规划 Skype for Business Server 或 Lync Server 2013 与 Teams 之间的混合连接。 设置混合连接是将本地环境移到云中仅限 Microsoft Teams 环境的第一步。

在本地部署Skype for Business Server中，Skype for Business用户也可以使用 Teams，但并非所有 Teams 功能都可供此类用户使用，只要这些用户配置为使用本地Skype for Business Server部署。 这些用户据说是本地的“主页”，某些 Teams 功能在本地托运时不可用，例如：

- 通过用户的 Teams 客户端与其他组织中的用户进行联合呼叫和聊天不可用
- 通过用户的 Teams 客户端与组织中使用Skype for Business客户端的其他用户进行互操作通信。
- 如果为用户分配了电话系统许可证) ，则 PSTN 呼叫功能 (。

若要获得完整的 Teams 功能，必须将这些用户从本地Skype for Business移动到云，此时用户将变为 TeamsOnly。 将用户从本地移动到云的行为会将用户的共存模式设置为 TeamsOnly。 将用户移动到云和 TeamsOnly 后，所有传入聊天和呼叫都会进入其 Teams 客户端 (不同于 Teams) 的并行使用情况。  有关详细信息，请参阅 [Teams 共存与Skype for Business和迁移](/microsoftteams/coexistence-chat-calls-presence)以及组织[使用 Teams 和Skype for Business的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

在云中的本地和 TeamsOnly 之间移动用户需要配置Skype for Business混合模式。 此外，在解除本地部署之前Skype for Business部署会将所有用户从本地移动到云。   设置混合连接后，你可以选择根据你的计划和业务需求将用户移动到云。  借助直接路由，你可以在迁移到云和完成迁移后，利用本地语音基础结构。

本主题介绍在现有本地Skype for Business Server部署和 Teams 之间配置混合连接所需的基础结构和系统要求。

阅读本主题并准备好配置混合连接后，请参阅配置 [Skype for Business Server 和 Teams 之间的混合连接](configure-hybrid-connectivity.md)。 配置主题提供有关在本地部署和 Teams 之间设置混合连接的分步指导。


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Skype for Business联机停用的影响
请务必记住，Skype for Business Online 停用前后，本地Skype for Business Server的用户都可以使用 Teams，但他们不能是 TeamsOnly。  (默认情况下，本地用户处于 Islands 模式，并分配 TeamsOnly) 以外的任何模式。 用户只能体验 Teams 的全部优势，尤其是联合身份验证、PSTN 支持，并保证所有入站聊天和通话在 Teams 中处于 TeamsOnly 模式后才会进入 Teams。 

Skype for Business Online 的停用不会影响 Skype for Business Server 或 Lync Server 2013 的现有支持生命周期。  但是，Skype for Business Online 的停用确实影响了用户 **如何** 过渡到云并在具有本地Skype for Business Server或 Lync Server 2013 的组织（包括现有混合组织）中 *成为 TeamsOnly* 的某些方面。 将混合用作从本地过渡到云的先决条件配置 (如 TeamsOnly) 保持不变。

在停用 Skype for Business Online 之前，混合组织可以包含三种基本类型的用户： 
- 本地用户 (可能使用或不使用 Teams，但不能在仅限 Teams 模式下)  
- 具有 TeamsOnly 以外的任何共存模式的联机用户
- TeamsOnly 用户。

但是，Skype for Business联机停用后，混合组织只能由两种基本类型的用户组成： 
- 本地用户 (谁可能或可能不会使用 Teams，但不使用 TeamsOnly 模式) 
- 仅 Teams 用户。 

若要使组织从 Skype for Business Server 或 Lync Server 2013 迁移到 Teams，仍必须使用相同的工具集设置和配置混合，*与停用前完全相同*。 将用户从本地移动到 TeamsOnly 时，不再需要指定 `-MoveToTeams` 开关 `Move-CsUser`。 以前，如果未指定此开关，则用户将从本地Skype for Business Server主机转换为 Skype for Business Online，并且其模式保持不变。 但是，由于 Skype Business Online 已停用，因此将用户从本地迁移到云 `Move-CsUser` ，并 *会自动* 分配 TeamsOnly 模式，并启动其会议从本地到 Teams 会议的转换，而不管是否指定了 `-MoveToTeams` 切换。 这也意味着具有 Lync Server 2013 的组织（从未进行过 `MoveToTeams` 切换）可以将用户直接从本地移动到 TeamsOnly。 

同样，如果新用户是直接在 Microsoft 365 而不是本地创建的，则无论租户的模式如何，该用户都将自动采用仅限 Teams 模式。 请记住，在至少有一个本地用户的混合组织中，应在本地 Active Directory (中创建新用户，然后同步到 Microsoft 365) ，而不是直接在 Microsoft 365 中创建用户，以确保本地用户可以路由到新用户，*即使你希望新用户成为云用户*。 在本地目录中创建后，必须在本地Skype for Business部署 *中* 启用这些新用户，然后根据需要迁移到云以成为 TeamsOnly。 

Skype for Business Online 停用后，共存模式仍然存在。 与以前一样，在本地Skype for Business Server拥有帐户的用户可以分配除 TeamsOnly 以外的任何共存模式。 但是，退休后，联机用户只能是 TeamsOnly。 不再可以将 TeamsOnly 以外的模式分配给联机用户。


> [!Important]
> 现有混合组织（用户驻留在 Skype for Business Online（不是 TeamsOnly）应专注于尽快将这些用户升级到仅限 Teams 模式。 如果你的组织仍有用户驻留在 Skype for Business *Online* 中，而这些用户不是 TeamsOnly，则你将计划进行 Microsoft 辅助升级，以便将这些用户过渡到 TeamsOnly。 **Microsoft 辅助升级不会影响本地Skype for Business Server的用户。** 在这些联机的非 TeamsOnly 用户升级到 Teams 之前，计划通知将提前发送到混合客户，其中用户驻留在 Skype for Business Online 中。

## <a name="about-shared-sip-address-space-functionality"></a>关于共享 SIP 地址空间功能

<a name="BKMK_Overview"> </a>

在本地部署的 Skype for Business Server 和 Teams 之间设置混合连接后，可以让一些用户驻留在本地，某些用户可以联机居住。

这种类型的配置依赖于共享 SIP 地址空间功能，有时称为“拆分域”，这意味着域的用户（如 contoso.com）在使用本地Skype for Business Server和 Teams 之间进行拆分，如下图所示：

![Skype for Business 混合连接 - 拆分域。](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

配置共享 SIP 地址空间时：

- Azure Active Directory Connect 用于将本地目录与 Microsoft 365 同步。
- 本地用户与本地Skype for Business服务器交互。
- 联机用户与 Teams 进行交互。
- 来自这两个环境的用户可以相互通信。
- 本地 Active Directory是权威的。 应先在本地 Active Directory中创建所有用户，然后同步到 Azure AD。 即使你打算让用户处于联机状态，也必须先在本地环境中创建用户，然后将用户移动到联机，以确保本地用户能够发现该用户。

在用户可以联机移动之前，必须为用户分配 Teams 许可证以及Skype for Business联机 (计划 2) 。 **即使在 Skype for Business Online 停用后，也需要分配 Skype for Business Online 许可证。** 如果你的用户想要利用其他联机功能（如音频会议或电话系统），则需要在 Microsoft 365 中为他们分配相应的许可证。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>混合连接基础结构要求

<a name="BKMK_Infrastructure"> </a>

若要在本地环境与 Microsoft 365 通信服务之间实现混合连接，需要满足以下基础结构要求：

- 部署在受支持拓扑中的Skype for Business Server或 Lync Server 的单个本地部署。 请参阅本主题中的 [拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology) 。

- 具有 Teams 的 Microsoft 365 组织。
    > [!NOTE]
    > 在本地部署中，只能将单个租户用于混合配置。
    
- 部署了 Azure Active Directory Connect，用于同步本地目录与 Microsoft 365。 有关详细信息，请参阅 [Azure AD Connect：帐户和权限](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype for Business Server管理工具。 这些是将用户从本地移动到云所必需的。 这些工具必须安装在可访问本地部署和 Internet 的服务器上。
- 联机管理工具。 可以使用 Teams 管理中心或Windows PowerShell来管理 Teams。 若要使用 PowerShell 管理 Teams，请下载并安装 Teams PowerShell 模块。  (Skype for Business联机连接器已停用) 。
- 必须启用共享 SIP 地址空间，并且本地部署必须配置为使用 Microsoft 365 作为托管提供程序。 有关配置混合连接所需的步骤的详细信息，请参阅 [配置混合连接](configure-hybrid-connectivity.md)。

配置混合连接后，可以将用户移动到 Teams。 有关详细信息，请参阅 [将用户从本地移动到 Teams](move-users-from-on-premises-to-teams.md)。

## <a name="server-version-requirements"></a>服务器版本要求

<a name="BKMK_Topology"> </a>

若要配置混合与 **Teams** 的部署，需要具有以下支持的拓扑之一：

- Skype for Business Server 2019 部署（所有服务器都运行 Skype for Business Server 2019）。
- Skype for Business Server 2015 部署（所有服务器都运行 Skype for Business Server 2015）。
- 所有服务器都运行 Lync Server 2013 的 Lync Server 2013 部署。  但是，如果需要混合语音连接，则必须使用混合版本拓扑，如下所述。
- 部署最多包含 2 个不同的服务器版本，如下所示：
  - Skype for Business Server 2015 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2019
  - Lync Server 2013 和 Skype for Business Server 2015
- 从 2022 年 7 月 31 日起，若要在本地部署和云之间移动用户，必须使用以下最低版本的 Skype for Business Server 或 Lync Server：
</br>

|本地产品|所需的最低版本|所需的最小版本|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| 带有修补程序 7 的 CU10|5.0.8308.1182|

</br>

> [!NOTE] 
> Teams 不支持 Lync Server 2010。


## <a name="multi-forest-support"></a>多林支持

<a name="BKMK_MultiForest"> </a>

Microsoft 支持以下类型的多林混合方案：

- **资源林拓扑。** 在此类拓扑中，有一个林托管Skype for Business Server (资源林) ，还有一个或多个托管帐户标识的其他林，这些林访问资源林中的Skype for Business Server。 通常，如果满足以下要求，用户可以访问另一林中的 Skype for Business 功能：
  - 用户已正确同步到托管 Skype for Business 的林中。 在混合配置中，这意味着必须将用户同步为已禁用的用户对象。
  - 托管 Skype for Business 的林必须信任包含用户的林。
    有关资源林混合方案的详细信息，请参阅[部署用于混合Skype for Business的资源林拓扑](configure-a-multi-forest-environment-for-hybrid.md)。

- **在多个林中多次部署Skype for Business Server。** 这种配置可能是由于合并和收购方案，以及更复杂的企业。 对于具有多个Skype for Business部署的任何组织，只要满足以下关键要求，就可以在单个 Microsoft 365 组织中将所有用户从本地合并到云：
  - 最多必须涉及一个 Microsoft 365 组织。 不支持在具有多个组织的方案中进行合并。
  - 在任意给定时间，仅有一个本地 Skype for Business 林可处于混合模式（共享 SIP 地址空间）。 所有其他本地Skype for Business林必须完全保留在本地 (，并大概彼此联合) 。 请注意，如果需要使用新的功能，这些其他本地组织可以同步到 AAD，以禁用截至 2018 年 12 月的 [联机 SIP 域](/powershell/module/skype/disable-csonlinesipdomain) 。

    在多个林中部署Skype for Business的客户必须使用拆分域 (共享 SIP 地址空间) 功能将每个Skype for Business林单独迁移到 Microsoft 365 组织。 完成林迁移后，客户必须先禁用与本地部署的混合，然后再继续迁移下一个本地Skype for Business部署。 此外，在迁移到云之前，本地用户仍与同一用户的本地目录中未表示的任何用户保持联合状态。 有关详细信息，请参阅 [Teams 和 Skype for Business 的云合并](cloud-consolidation.md)。

## <a name="federation-requirements"></a>联合身份验证要求

<a name="BKMK_Federation"> </a>

配置Skype for Business混合模式时，必须确保本地环境和联机环境可以相互联合。  默认情况下，联机环境具有开放联合身份验证;默认情况下，本地环境通常已关闭联合身份验证。  

必须满足以下要求才能成功配置混合部署：

- 必须为本地部署和 Microsoft 365 组织配置相同的域匹配。 如果在本地部署上启用了合作伙伴发现，则必须为联机组织配置开放联合身份验证。 如果未启用合作伙伴发现，则必须为联机组织配置已关闭的联合身份验证。
- 本地部署中的“阻止的域”列表必须与联机租户的“已阻止的域”列表完全匹配。
- 本地部署中的“允许的域”列表必须与联机租户的“允许的域”列表完全匹配。
- 必须为联机租户的外部通信启用联合身份验证。

## <a name="network-considerations"></a>网络注意事项

以下部分介绍了以下注意事项：

- DNS 设置
- 防火墙注意事项

### <a name="dns-settings-for-hybrid-deployments"></a>混合部署的 DNS 设置

<a name="BKMK_DNS"> </a>

为混合部署创建 DNS 记录时，所有 Skype for Business 外部 DNS 记录都应指向本地基础结构。 有关所需 DNS 记录的详细信息，请参阅[Skype for Business Server的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，还需要确保下表中所述的 DNS 解析在本地部署中有效。 （如果已为本地配置了联合身份验证，则很可能已经拥有了这些。)

|DNS 记录  <br/> |解析者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\> 对于解析为 Access Edge 外部 IP () 的所有受支持的 SIP 域  <br/> |边缘服务器  <br/> |在混合配置中启用联合通信。 边缘服务器需要知道在何处路由本地和联机之间拆分的 SIP 域的联合流量。  <br/> 必须在用户名和 SRV 记录中的域之间使用严格的 DNS 名称匹配。  <br/> |
|适用于 Edge Web 会议服务 FQDN 的 DNS A 记录 () ，例如 webcon.contoso.com 解析为 Web 会议边缘外部 IP (的)   <br/> |连接内部企业网络的用户计算机  <br/> |使在线用户能够在本地托管会议中呈现或查看内容。 内容包括 PowerPoint 文件、白板、投票和共享笔记。  <br/> |

根据组织中 DNS 的配置方式，可能需要将这些记录添加到相应 SIP 域的内部托管 DNS 区域，以便为这些记录提供内部 DNS 解析。

### <a name="firewall-considerations-for-hybrid-deployments"></a>混合部署的防火墙注意事项

<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据 Microsoft Online Services 数据中心的位置，还必须将网络防火墙设备配置为接受基于通配符域名 (连接，例如，来自 \*.outlook.com) 的所有流量。 如果组织的防火墙不支持通配符名称配置，则必须手动确定要允许的 IP 地址范围和指定的端口。

有关详细信息，包括有关端口和协议要求的详细信息， [请参阅 Microsoft 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)。
