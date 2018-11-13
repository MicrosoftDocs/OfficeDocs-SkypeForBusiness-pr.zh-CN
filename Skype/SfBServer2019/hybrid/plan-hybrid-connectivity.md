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
ms.openlocfilehash: 34df2639ed57376549b2a8bde2e4b0e071d08957
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295271"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>规划业务服务器 Skype 和 Office 365 之间的混合连接性

## <a name="overview"></a>概述

阅读本主题可了解如何规划业务联机或团队的 Skype 业务服务器和 Skype 之间的混合连接性。 设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。

混合解决方案，使您能够同时还利用 Microsoft 云中提供的在线服务保留某些本地控件。 使用混合连接性设置和各种云服务供您在线和本地用户，您可以选择将用户移动到云根据日程安排和业务需求。

例如，您可能选择呼叫控制通过获得 Microsoft 电话系统在云中同时保留您的本地 PSTN 连接。 您还可以选择充分利用其他云服务，例如云语音邮件和呼叫数据连接器。

本主题介绍您需要配置混合部署的 Business Server-与在您的内部部署 Active Directory-中创建的用户您现有的本地 Skype 和 Skype 之间的连接的基础结构和系统要求适用于在线商务或团队。

您已阅读本主题，并准备好配置混合连接后，请参阅[Business Server 和 Office 365 的 Skype 之间配置混合连接性](configure-hybrid-connectivity.md)。 配置主题提供业务 online 设置您的本地部署和 Skype 之间的混合连接性的分步指导。

（有关配置 Lync Server 2013 或 Lync Server 2010 混合部署的信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）

## <a name="split-domain-functionality"></a>拆分域功能
<a name="BKMK_Overview"> </a>

 Skype 业务服务器的内部部署和 Skype 之间设置业务联机或团队的混合连接，您可以将一些用户驻留在本地和联机驻留的一些用户。

此类型的配置有时称为"拆分域"— 这意味着用户的域名，例如，contoso.com，分别驻留在本地的企业服务器和 Skype 业务联机或团队使用 Skype，如下图中所示：

![SfB 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

使用拆分域环境中：

- 用户驻留在本地与业务服务器的内部部署 Skype 进行交互。 他们还可能有权访问在线服务，例如云语音邮件。

- 联机驻留用户可能交互 Skype 业务或团队的联机服务。

- 这两种环境中的用户可以使用即时消息、 参加会议呼叫或 VoIP 呼叫、 进行相互协作，依此类推。

- Azure Active Directory 连接用于与 Office 365 同步您的本地目录。

本地 Active Directory 是权威性的，即你必须执行下列操作以确保本地和在线用户可以相互发现：

- 所有用户应首先，在内部部署 Active Directory 中创建，然后同步到 Azure AD。

- 迁移到云中的用户必须具有业务计划 2 或团队许可证的任一 Skype。

- 如果您的用户想要充分利用附加的联机功能，如 Skype 会议广播或云语音邮件，您需要将其分配 Office 365 中的适当许可。

- 为 Skype for Business Online 用户分配许可证后，你需要为 Skype for Business 或本地 Enterprise Voice 启用这些用户。 有关详细信息，请参阅[启用本地的企业语音的用户](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)。 有关混合语音要求的详细信息，请参阅[Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。


## <a name="infrastructure-requirements"></a>基础结构要求
<a name="BKMK_Infrastructure"> </a>

若要实现您的内部部署环境与 Office 365 通信服务之间的混合连接，您需要满足以下基础结构要求。

- 一个本地部署的 Skype 业务服务器或受支持的拓扑中部署 Lync Server。 请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。

- Skype 业务 Online 启用的 Microsoft Office 365 租户。

    > [!NOTE]
    > 只能将混合配置的单个租户与你的本地部署结合使用。

- Skype Business Server 管理工具。 （如果您使用 Lync Server 2013 或 Lync Server 2010，可以使用 Lync Server 2013 管理工具。 有关详细信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）

- Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。 有关详细信息，请参阅[Azure AD 连接： 帐户和权限](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

    若要支持 Office 365 的单一登录，使用户能使用在本地所用的同一登录凭据，可以使用 Azure Active Directory (AAD) Connect 的密码同步功能。 还可以使用 Active Directory 联合身份验证服务 (AD FS) 来进行 Office 365 单一登录。 

若要配置混合连接，还需要设置您的本地和联机环境之间的联盟和配置您的业务 Online 租户中为共享的会话初始协议 (SIP) 地址空间 Skype 上。 有关配置混合连接所需的步骤的详细信息，请参阅[配置混合连接性](configure-hybrid-connectivity.md)。

配置混合连接后，可以业务联机或团队中将用户移动到 Skype。 有关详细信息，请参阅[移动到业务 online Skype 本地用户](move-users-from-on-premises-to-skype-for-business-online.md)和[移动用户从内部部署到团队](move-users-from-on-premises-to-teams.md)。

## <a name="multi-forest-support"></a>多林支持
<a name="BKMK_MultiForest"> </a>

如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：

- 用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。

- 托管 Skype for Business 的林必须信任包含用户的林。

有关多林混合方案的详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](configure-a-multi-forest-environment-for-hybrid.md)。

## <a name="administrator-credentials"></a>管理员凭据
<a name="BKMK_Credentials"> </a>

当要求您提供您的管理员凭据时，使用的用户名和密码的管理员帐户为您的 Office 365 租户。 Azure Active Directory 联合身份验证、 目录同步、 单一登录，和将用户迁移到 Skype 配置业务 online 时，您还将使用这些凭据。

## <a name="skype-for-business-online-powershell"></a>Skype for Business Online PowerShell
<a name="BKMK_PowerShell"> </a>

管理员现在可以使用 Windows PowerShell 管理 Skype 业务联机和其 Skype 业务联机用户帐户。 若要执行此操作，您必须首先下载和安装的业务 Online 连接器模块从 Microsoft 下载中心下载 Skype。 下载、 安装和使用 Skype 对业务联机连接器模块和 using Windows PowerShell to manage Skype 业务 online 的详细信息的详细信息，请参阅[Windows PowerShell 将计算机设置](https://technet.microsoft.com/library/dn362831.aspx)。

## <a name="skype-for-business-client-support"></a>Skype for Business 客户端支持
<a name="BKMK_ClientSupport"> </a>

客户端中支持的功能与本地和联机环境中提供的功能一样，存在一些差异。 以下客户端支持与 Skype 业务 Online 混合部署中：

- Skype for Business

- Lync 2013

- Lync 2010

- Lync Windows 应用商店应用

- Lync Web App

- Lync Mobile

- Lync for Mac 2011

- Lync 会议室系统和 Skype 的业务会议室系统

- Lync Basic 2013

- Microsoft Surface Hub

在决定要在其中家庭用户在组织中之前，您应当查看[for Business 的 Skype 的桌面客户端功能比较](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)以确定 Business Server Skype 的各种配置客户端支持。 另请参阅：

- [规划客户端和设备](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Skype for Business 的移动客户端功能比较](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>拓扑要求
<a name="BKMK_Topology"> </a>

业务 online 与 Skype 配置混合部署，您需要具备以下支持的拓扑结构之一：

- 包含业务服务器 2015年运行 Skype 的所有服务器的业务服务器 2015年部署 Skype。

- 运行 Lync Server 2013 的所有服务器与 Lync Server 2013 部署。

    混合语音连接，必须业务 2015; 的 Skype 被指定为联合身份验证边缘边缘服务器。边缘还需要 Skype 针对 Business Server 后端。 你可能有一个池中没有任何用户。

- 运行 Lync Server 2010 通过最新累积更新的所有服务器与 Lync Server 2010 部署。

  - 联合身份验证边缘服务器和从联合身份验证边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新累积更新。

  - 必须至少一台服务器或管理工作站上安装 Skype 业务服务器 2015年或 Lync Server 2013 管理工具。

- 混合的 Lync Server 2013 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：

  - 至少一个企业版池或 Standard Edition 服务器 

  - 与 SIP 联盟关联的控制器池（如果存在）

  - 与 SIP 联盟关联的边缘池

- 混合的 Lync Server 2010 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：

  - 至少一个企业版池或 Standard Edition 服务器 

  - 与 SIP 联盟关联的控制器池（如果存在）

  - 与站点的 SIP 联盟关联的边缘池

- 混合的 Lync Server 2010 和 Lync Server 2013 部署与至少一个站点运行 Lync Server 2013 中的以下服务器角色：

  - 站点中至少一个企业版池或 Standard Edition 服务器

  - 与 SIP 联盟关联的控制器池（如果站点中存在）

  - 与站点的 SIP 联盟关联的边缘池

## <a name="federation-allowedblocked-lists-requirements"></a>联盟允许/阻止列表的要求
<a name="BKMK_Federation"> </a>

允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。 这些域有时也称允许的合作伙伴服务器 或直接联盟合作伙伴。 您应熟悉开放联盟和封闭联盟（在本地部署中分别称为合作伙伴发现 和允许的合作伙伴域列表）之间的差异。

必须满足以下要求才能成功配置混合部署：

- 为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。

- 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。

- 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。

- Online 租户，使用适用于业务 Online 控制面板 Skype 配置的外部通信，必须启用联盟。

## <a name="dns-settings"></a>DNS 设置
<a name="BKMK_DNS"> </a>

创建混合部署的 DNS 记录时，所有业务外部 DNS 记录的 Skype 应都指向的内部部署基础结构。 有关所需的 DNS 记录的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外，您需要以确保 DNS 解析下表中所述的本地部署中：

|DNS 记录  <br/> |解析者  <br/> |DNS 要求  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有支持的 SIP 域解析为访问边缘外部 IP(s)  <br/> |边缘服务器  <br/> |在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。  <br/> 必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。  <br/> |
|边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com  <br/> |内部企业网络连接的用户的计算机  <br/> |让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。  <br/> |

根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。

## <a name="firewall-considerations"></a>防火墙注意事项
<a name="BKMK_Firewall"> </a>

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受连接基于通配符域名 (例如，来自所有通讯\*。 outlook.com)。 如果贵组织的防火墙不支持通配符名称配置，您将需要手动确定您希望允许的 IP 地址范围和指定的端口。

有关详细信息，请参阅 [Office 365 URL 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。

## <a name="port-and-protocol-requirements"></a>端口和协议要求
<a name="BKMK_Ports"> </a>

除了内部通信的端口要求，还必须配置以下端口以启用混合连接：


|**协议**|**TCP 或 UDP**|**源 IP**|**目标 IP**|**源端口**|**目标端口**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |访问边缘  <br/> |Office 365  <br/> |任何  <br/> |5061  <br/> |信号  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |访问边缘  <br/> |任何  <br/> |5061  <br/> |信号  <br/> |
|STUN  <br/> |TCP  <br/> |A/V 边缘  <br/> |Office 365  <br/> |50000-59999  <br/> |443，50000-59999  <br/> |为音频、视频、应用程序共享会话打开  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |A/V 边缘  <br/> |443  <br/> |50000-59999  <br/> |为音频、视频、应用程序共享会话打开  <br/> |
|STUN  <br/> |UDP  <br/> |A/V 边缘  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |为音频、视频会话打开  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |A/V 边缘  <br/> |3478  <br/> |3478  <br/> |为音频、视频会话打开  <br/> |

有关端口和防火墙的边缘服务器规划的详细信息，请参阅[Skype 业务服务器中的边缘服务器环境要求](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)。 另请参阅[Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md)和[协议工作负荷图](https://go.microsoft.com/fwlink/p/?LinkId=550989)。

## <a name="user-accounts-and-data"></a>用户帐户和数据
<a name="BKMK_UserAccounts"> </a>

在混合部署中，您想要联机承载任何用户必须先创建在本地部署中，以便在 Active Directory 域服务中创建的用户帐户。 然后，您可以将用户移动到 Skype 业务 online，其中将移动用户的联系人列表。

在同步您的本地部署和使用 AAD 连接的 online 租户之间的用户帐户时，您需要同步的 AD 帐户为在组织中的业务或 Lync 用户的所有 Skype 即使用户未联机移动到。 如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。

> [!IMPORTANT]
> 所有用户管理，包括用户的本地和 Skype 之间移动业务 online，都必须使用最新的安装管理工具版本。 必须具有对现有的内部部署和 Internet 连接访问的单独服务器上安装管理工具。 此 cmdlet 将用户从您的本地部署迁移到 Skype 业务 online， [Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)，必须从管理工具连接到内部部署运行。 有关移动用户的详细信息，请参阅[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。

规划混合部署时，您还应考虑与用户相关的以下问题：

- **用户联系人**为 Lync Online 用户的联系人的限制为 250 个字符。 当帐户移至 Lync Online，超出该号码的任何联系人将从用户的联系人列表中删除。

- **即时消息和状态**使用用户帐户都将迁移的用户联系人列表、 组和访问控制列表 (Acl)。

- **会议数据、 会议内容和计划的会议**此内容不会迁移用户帐户。 用户必须在其帐户迁移到 Lync Online 之后重新安排会议。

## <a name="user-policies-and-features"></a>用户策略和功能
<a name="BKMK_UserPolicies"> </a>

- 在混合环境中，可以为本地或联机用户（但不是同时）启用即时消息和会议。

- **客户端支持**他们会移动到 Skype 业务 online 时，某些用户可能需要新的客户端版本。 为 Office Communications Server 2007 R2，用户必须将移动到 Skype 之前迁移到 Skype 业务 online 业务服务器或 Lync Server 2013 的池。

- **在本地策略和配置 （非用户）** 联机和本地策略要求单独的配置。 无法设置适用于二者的全局策略。
