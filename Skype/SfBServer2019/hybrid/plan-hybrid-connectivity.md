---
title: 规划混合连接性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 规划业务联机或团队实现业务服务器 Skype 和 Skype 之间的混合连接性注意事项。
ms.openlocfilehash: 825057f84300d9e47427eea5b27117d168b4126f
ms.sourcegitcommit: d1672a9070668a0d9304296dbca29f7dd2a8daee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "26625687"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>规划业务服务器 Skype 和 Office 365 之间的混合连接性

## <a name="overview"></a>概述

阅读本主题可了解如何规划 Skype Business Server 和团队或 Skype 业务 online 之间的混合连接性。 设置混合连接性是内部部署环境迁移到云的第一步。

如果您有还使用团队 （并行） 的业务用户的内部部署 Skype，这些用户没有与 Skype 互操作的业务用户从其团队客户端，也不能与联盟组织中的用户通信的功能及其团队客户端。 若要获得此团队中的功能，这些用户必须从移 Skype 业务本地到云，这需要配置的业务混合模式的 Skype。 此外，获得最佳体验，这些用户应仅团队模式，它可确保所有传入呼叫并从用户的工作组客户端中的任何用户园地聊天。

设置混合连接性和所有用户都迁移到云也是需要先停用业务部署您的本地 Skype。  混合连接设置，您可以选择将用户移动到云根据日程安排和业务需求。 使用直接路由时，您可以利用本地语音基础结构，移动到云中和完成迁移后时。

本主题介绍基础结构和系统要求您需要配置混合连接之间您现有的内部部署 Skype 业务服务器部署和团队或 Skype 业务 online。

您已阅读本主题，并准备好配置混合连接后，请参阅[Business Server 和 Office 365 的 Skype 之间配置混合连接性](configure-hybrid-connectivity.md)。 配置主题提供业务 online 设置您的本地部署和团队或 Skype 之间的混合连接性的分步指导。


## <a name="about-split-domain-functionality"></a>有关拆分域功能
<a name="BKMK_Overview"> </a>

 在本地部署的 Business Server 和团队的 Skype 或 Skype 业务 online 之间设置混合连接，您可以将一些用户驻留在本地和联机驻留的一些用户。

这种配置依赖于共享 SIP 地址空间功能，并有时称为"拆分域"— 这意味着用户的域名，例如，contoso.com，分别使用 Skype 业务服务器上部署和团队或 for Business 的 Skype 之间联机，如下图中所示： 

![SfB 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

当配置共享的 SIP 地址空间：

- Azure Active Directory 连接用于与 Office 365 同步您的本地目录。

- 用户驻留在本地与业务服务器的内部部署 Skype 进行交互。 

- 联机驻留用户可能交互 Skype 业务联机或团队服务。

- 这两种环境中的用户可以相互通信。 

- 内部部署 Active Directory 是权威。 所有用户应首先，在内部部署 Active Directory 中创建，然后同步到 Azure AD。 即使您打算联机驻留用户，必须首先在内部部署环境中，创建用户，然后将用户移动到 online 以确保用户是内部部署用户可供搜索。 

用户可以联机移动之前，必须为用户分配业务 Online (计划 2) 许可证 Skype。 如果用户将使用团队，还必须为用户分配的工作组许可证 （和业务许可证 Skype 必须保持启用状态）。 如果您的用户想要充分利用附加的联机功能，如要进行音频会议或电话系统，您需要将其分配 Office 365 中的适当许可。


## <a name="infrastructure-requirements"></a>基础结构要求
<a name="BKMK_Infrastructure"> </a>

若要实现您的内部部署环境与 Office 365 通信服务之间的混合连接，您需要满足以下基础结构要求：

- 一个本地部署的 Skype 业务服务器或受支持的拓扑中部署 Lync Server。 请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。

- Skype 业务 Online 启用的 Microsoft Office 365 租户。

    > [!NOTE]
    > 只能将混合配置的单个租户与你的本地部署结合使用。

- Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。 有关详细信息，请参阅[Azure AD 连接： 帐户和权限](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype Business Server 管理工具。  需要将用户从内部部署移动到云。 必须有权在本地部署和 internet 服务器上安装这些工具。 

- Online 管理工具。  可以使用的团队和 Skype 业务管理中心或 Windows PowerShell 来管理工作组和 Skype 业务 online。 若要使用 PowerShell 管理团队或 Skype 业务 online，下载并安装 Business Online Connector Skype。 

- 必须启用共享的 SIP 地址空间，并且必须配置内部部署 Office 365 用作宿主提供商。 有关配置混合连接所需的步骤的详细信息，请参阅[配置混合连接性](configure-hybrid-connectivity.md)。

配置混合连接后，您可以将用户移至团队或 Skype 业务 online。 有关详细信息，请参阅[移动用户从内部部署到团队](move-users-from-on-premises-to-teams.md)和[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。


## <a name="topology-requirements"></a>拓扑要求
<a name="BKMK_Topology"> </a>

**工作组**或业务 online Skype 配置混合部署，您需要具备以下支持的拓扑结构之一：

- 包含业务服务器 2019年运行 Skype 的所有服务器的业务服务器 2019年部署 Skype。 
- 包含业务服务器 2015年运行 Skype 的所有服务器的业务服务器 2015年部署 Skype。
- 运行 Lync Server 2013 的所有服务器与 Lync Server 2013 部署。  但是，如果不需要混合语音连接，您必须使用混合的版本拓扑如下所述。
- 具有两个不同的服务器版本，如下所示的最大部署：
  - Skype 业务服务器 2015年和 Skype 业务服务器 2019
  - Lync Server 2013 和 Skype 业务服务器 2019
  - Lync Server 2013 和 Skype 业务服务器 2015

*如果在任何拓扑中需要混合语音*，这两个被指定为联合身份验证边缘，以及与 SIP 联盟关联的池的边缘服务器必须运行 Skype 的业务 2015年或更高版本。 如果存在，则用户可以在 Lync 2013 池上保留。 有关详细信息，请参阅[规划中的业务服务器 Skype 的 PSTN 连接电话系统](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。

以下拓扑，包括即时消息和会议的**Lync Server 2010 支持与业务 online Skype** 。  包含**混合语音也团队不支持 Lync Server 2010**的拓扑。

- 混合的 Lync Server 2010 和 Skype 业务服务器 2015年部署
- Lync Server 2010 和 Lync Server 2013 混合的部署
-   运行 Lync Server 2010 通过最新累积更新的所有服务器与 Lync Server 2010 部署。
联合身份验证边缘服务器和从联合身份验证边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新累积更新。 必须至少一台服务器或管理工作站上安装 Skype 业务服务器 2015年或 Lync Server 2013 管理工具。



 ## <a name="multi-forest-support"></a>多林支持
<a name="BKMK_MultiForest"> </a>

如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：

- 用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。

- 托管 Skype for Business 的林必须信任包含用户的林。

有关多林混合方案的详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](configure-a-multi-forest-environment-for-hybrid.md)。


## <a name="federation-requirements"></a>联合身份验证要求
<a name="BKMK_Federation"> </a>

在配置混合时，必须确保您在本地和联机环境可以与每个其他联盟。  Online 环境具有开放联盟默认设置。通常，在本地环境具有默认情况下关闭联合身份验证。  

必须满足以下要求才能成功配置混合部署：

- 为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。

- 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。

- 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。

- Online 租户的外部通信，必须启用联盟。


## <a name="network-considerations"></a>网络注意事项

以下各节介绍的注意事项： 

- DNS 设置 
- 防火墙注意事项 


### <a name="dns-settings"></a>DNS 设置
<a name="BKMK_DNS"> </a>

创建混合部署的 DNS 记录时，所有业务外部 DNS 记录的 Skype 应都指向的内部部署基础结构。 有关所需的 DNS 记录的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，您需要确保 DNS 解析下表中所述的本地部署中。 （如果已配置为在本地联盟，然后您很可能已具有这些。）

|DNS 记录  <br/> |解析者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有支持的 SIP 域解析为访问边缘外部 IP(s)  <br/> |边缘服务器  <br/> |在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。  <br/> 必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。  <br/> |
|边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com  <br/> |内部企业网络连接的用户的计算机  <br/> |让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。  <br/> |

根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。 

### <a name="firewall-considerations"></a>防火墙注意事项
<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受连接基于通配符域名 (例如，来自所有通讯\*。 outlook.com)。 如果贵组织的防火墙不支持通配符名称配置，您将需要手动确定您希望允许的 IP 地址范围和指定的端口。

有关详细信息，包括有关端口和协议要求的详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。
