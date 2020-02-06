---
title: 规划 Skype for Business 云连接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: 查找有关 Skype for Business 云连接器版本的信息，云连接器是一组打包的虚拟机 (Vm)，这些虚拟机负责通过 Office 365 中的电话系统（云 PBX）实施本地 PSTN 连接。
ms.openlocfilehash: 20ea88b230fe0fd9a590c489cb6f0017a2c27209
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814460"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>规划 Skype for Business 云连接器版本

查找有关 Skype for Business 云连接器版本的信息，云连接器是一组打包的虚拟机 (Vm)，这些虚拟机负责通过 Office 365 中的电话系统（云 PBX）实施本地 PSTN 连接。

如果尚未安装现有 Lync 服务器或 Skype for Business Server 部署，则云连接器版本可能是你的组织的合适解决方案。 如果您仍在调查 Office 365 解决方案中的哪些电话系统适合您的企业，请参阅[Microsoft 电话解决方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)。

本文档介绍了云连接器版本要求和受支持的拓扑，并帮助你规划云连接器版本部署。 请务必阅读本主题，然后再配置你的云连接器环境。 准备好部署和配置云连接器版本时，请参阅[配置和管理 Skype For Business 云连接器版本](configure-skype-for-business-cloud-connector-edition.md)。

云连接器版本2.1 现已推出。 如果你尚未升级到 2.1，请参阅[Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md)。 你可以在上[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)找到安装文件。

> [!NOTE]
> 发布新版本后，Microsoft 支持以前版本的云连接器版本60天。 Microsoft 会在 2.1 版发布后 60 天内继续支持 2.0.1 版，为你预留时间进行升级。 2.0.1 之前的所有版本不再受支持。

云连接器版是一种混合服务，它包含一组打包的虚拟机（Vm），用于在 Office 365 中与电话系统实现本地 PSTN 连接。 通过在虚拟化环境中部署最小的 Skype for Business 服务器拓扑，组织中托管的用户可以从 Microsoft 云中接收 PBX 服务，但 PSTN 连接通过现有的本地语音提供实现.

![该拓扑图显示云 PBX 网关（用于将云 PBX 连接到 Skype for Business 的内部部署）。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

因为云连接器使你可以将 Office 365 电话系统服务与现有电话环境集成—例如，PBX、模拟设备和呼叫中心—你可以实施从现有电话解决方案到 Office 365 电话系统的分阶段迁移。

例如，假设贵公司有一个复杂的呼叫中心，它具有 Office 365 电话系统无法提供的特定功能。 你可以选择将呼叫中心用户保留在现有解决方案中，而将其他用户迁移到 Office 365 电话系统。

云连接器将在本地托管用户和在线托管用户之间提供路由，你可以选择将自己的 PSTN 提供程序与 Office 365 电话系统结合使用。

规划云连接器版本部署时，请考虑以下事项：

- 若要使用云连接器利用云语音解决方案，你需要在 Office 365 中注册包含电话系统的 Office 365 租户。 如果你还没有 Office 365 租户，则可以了解如何在此处注册： [Office 365 For Business](https://products.office.com/en-us/business/office)。 请注意，你需要注册包括 Skype for Business Online 的计划。

- 若要使用 Skype for Business Online 服务注册云连接器装置，并运行各种 cmdlet，云连接器2.0 和更高版本需要具有 Skype for Business 租户管理员权限的专用 Office 365 帐户。 2.0 之前的云连接器版本需要具有专用的 Office 365 帐户以及租户全局管理员权限。

- 云连接器不需要完整的本地 Skype for business 服务器部署。

    当前，云连接器不能与 Lync 或 Skype for business 本地服务器共存。 如果你想要将现有 Lync 或 Skype for business 用户移动到 Office 365 并持续为你的用户提供本地电话，请考虑使用现有 Skype for Business Server 部署的 Office 365 中的电话系统与本地连接。 有关详细信息，请参阅[在 office 365 （云 PBX）解决方案中规划电话系统](plan-your-phone-system-cloud-pbx-solution.md)和在[Office 365 中计划电话系统和 Skype for business 服务器中的本地 PSTN 连接](plan-phone-system-with-on-premises-pstn-connectivity.md)。

- 如果您有以前的 Skype for Business 或 Lync Server 部署，并且您扩展了架构，则无需清理云连接器部署的架构，只要已删除环境中的所有 Skype for business 或 Lync Server 组件。

- 您的用户以联机方式驻留。

- 如果贵组织已配置目录同步 (DirSync)，则必须先在本地部署中创建已计划混合语音的所有用户帐户，然后再将其同步至云。

- 如果需要，您可以继续使用当前 PSTN 运营商。

- 如果您想要向在云连接器上托管的用户提供电话拨入式会议，您可以从 Microsoft 购买 PSTN 会议许可证或购买音频会议。

- "音频会议许可证" （或 "即付即用" 优惠）也是通话升级所必需的。 如果 Skype for Business 用户从外部 PSTN 用户接收呼叫，并且想要向该呼叫添加一个参与者（将通话升级到会议），则将通过 Microsoft 音频会议服务执行升级。

- 现在，云连接器 2.0 版和更高版本支持媒体旁路。 媒体绕过允许客户将媒体直接发送到公共交换式电话网络（PSTN）下一跃点（即网关或会话边界控制器（SBC）），并从媒体路径中删除云连接器版本组件。 有关详细信息，请参阅[在云连接器版本中规划媒体绕过](plan-for-media-bypass-in-cloud-connector-edition.md)。

- 云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅[Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- 云连接器可在 Office 365 企业版 E5 可用的所有国家/地区使用。

本主题包括以下部分：

- [云连接器版本组件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [云连接器版本拓扑](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [在部署之前需要收集的信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [拨号计划注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [云连接器媒体流](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [监视和故障排除](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [有关详细信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>云连接器版本组件
<a name="BKMK_Components"> </a>

借助云连接器版本，你可以部署一组打包的 Vm，其中包含最少的 Skype for Business 服务器拓扑-包括一个边缘组件、中介组件和一个中央管理应用商店（CMS）角色。 你还将安装一个域控制器，这是云连接器内部功能所必需的。 这些服务配置为与包含 Skype for Business Online 服务的 Office 365 租户混合。

![云连接器版本组件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

云连接器组件提供以下功能：

- **边缘组件**-本地拓扑和联机服务之间的通信将经历 Edge 组件，其中包括以下组件：

  - **Access Edge** -提供本地部署和 Skype For business Online 之间的 SIP 路由。

  - **媒体中继**-提供中介组件和其他媒体终结点之间的媒体路由。

  - **媒体中继身份验证/MRAS** -生成用于访问媒体中继的令牌。

- **出站路由**-提供与云连接器装置连接的网关或 SBCs 之间的语音流量的负载平衡。 通话将在连接到云连接器设备的所有网关或 SBC 之间平均拆分。

    根据策略实现向网关路由。 仅支持基于目标（出站）PSTN 号码的全局策略。

- **中央管理存储（CMS）角色**-包括拓扑组件的配置存储，包括 CMS 文件传输。

- **中央管理存储（CMS）副本**-从 CMS 角色服务器上的全局 CMS 数据库同步配置信息。

- **域控制器**-云连接器 Active Directory 域服务用于存储部署云连接器组件所需的所有全局设置和组。 将为每个云连接器装置创建一个目录林。 域控制器不能与生产 Active Directory 建立任何连接。 Active Directory 服务包括：

  - Active Directory 域服务

  - 可颁发内部证书的 Active Directory 证书服务

- **采集转送组件**-在 Skype for BUSINESS 和 PSTN 网关之间实现 SIP 和媒体网关映射协议。 包含从全局 CMS 数据库同步配置的 CMS 副本。

## <a name="cloud-connector-edition-topologies"></a>云连接器版本拓扑
<a name="BKMK_Topologies"> </a>

出于讨论目的，我们将提及 PSTN 站点。 PSTN 站点是云连接器装置的组合，可在同一位置部署，并与公用 PSTN 网关连接。 通过 PSTN 站点，你能够：

- 提供到最靠近您的用户的网关的连接。

- 通过在一个或多个 PSTN 站点内部署多个云连接器装置来实现可伸缩性。

- 通过在单个 PSTN 站点内部署多个云连接器装置，允许高可用性。

本主题介绍了 PSTN 网站。 有关规划 PSTN 网站的详细信息，请参阅[Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md)。

你可以部署以下云连接器拓扑：

- 每个 PSTN 站点的单个云连接器 Edition 装置。 由于此拓扑不提供高可用性，因此只建议用于评估用途。

- 每个 PSTN 站点多个云连接器 Edition 装置以提供高可用性。

- 具有多个云连接器版设备的多个 PSTN 站点，提供高可用性的可伸缩性。 最多可部署 200 个站点。

当规划拓扑时，请考虑以下事项：

- 使用云连接器2.0 及更高版本，一个 PSTN 站点最多可以有16个云连接器装置。 在之前版本中，每个站点最多支持 4 台设备。

- 有两种类型的硬件配置可通过云连接器进行测试：

  - 大型版本能够处理大量并发呼叫，在所有类型的生产环境中都受支持。

  - 小型版本旨在低端硬件上运行，可用于评估目的或者用于呼叫量较低的站点。如果你部署云连接器的小型版本，你仍需要注意生产级别的硬件要求（例如，双电源）。

- 如果你有云连接器版本2.0 或更高版本，并且你部署16个装置的最高配置（使用较大的硬件），则你的 PSTN 网站可以同时处理多达8000个通话。 如果部署小型版本，支持的限制为 800。

    你还需要将某些设备专用于高可用性。 最低建议是应保留一个设备用于高可用性。

  - 对于版本2，如果你部署 15 + 1 配置，则你的 PSTN 网站可以同时处理多达7500的通话。

  - 如果你具有先前版本并且部署最高的 3 + 1 配置（通过较大硬件），你的 PSTN 站点可以处理多达 1500 个并发呼叫。如果你部署小型版本，则支持的限制为 150 个。

-  如果每个 PSTN 网站需要更多呼叫，您可以通过在同一位置部署额外的 PSTN 网站来实现向上扩展。

> [!NOTE]
> 除非另行说明，否则下面的图表和示例假定使用较大版本的云连接器。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>单个 PSTN 站点内单台云连接器设备

下图显示了单个 PSTN 站点内的单个云连接器 Edition 设备。 请注意，云连接器包含四个虚拟机在外围网络中安装的虚拟机，用于安全用途。

![具有一个 PSTN 网站的一个云连接器](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>单个 PSTN 站点内多台云连接器设备

 出于可伸缩性和高可用性的目的，你可以选择在单个 PSTN 站点中拥有多个云连接器版本，如下图所示。 请考虑以下事项：

- 呼叫在一个池中的云连接器之间按随机顺序分配。

- 出于容量规划目的，必须根据以下计算考虑在一个或多个云连接器离线时处理负载的能力：

  - **N+1 配置。** 对于较大版本的云连接器，N + 1 个框支持\*500 N 个并发通话，其中有99.8% 的可用性。

    对于较小版本的云连接器，N + 1 个框支持\*50 N 个并发通话，可用性为99.8%。

  - **N+2 配置。** 对于较大版本的云连接器，N + 2 个框支持\*500 N 个并发通话，可用性为99.9%。

    对于较小版本的云连接器，N + 2 个框支持\*50 N 个并发通话，其可用性为99.9%。

![具有 1 个 PSTN 网站的两个云连接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>多个 PSTN 网站，每个网站一个或多个云连接器

你还可以选择配置多个 PSTN 站点，并且每个站点具有一个或多个云连接器版本。 如果 PSTN 站点达到并发呼叫限制，你可以添加另一个 PSTN 站点来处理负载。

多个 PSTN 网站也使你能够提供到最靠近你的用户的网关的连接。 例如，假设你在西雅图和阿姆斯特丹都有 PSTN 网关。 你可以部署两个 PSTN 网站（一个位于西雅图，另一个位于阿姆斯特丹），并指定用户使用最靠近他们的 PSTN 网站。 西雅图的用户将路由到西雅图的 PSTN 网站和网关，而阿姆斯特丹的用户将路由到阿姆斯特丹的 PSTN 网站和网关：

![2 个 PSTN 网站内的云连接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>部署要求
<a name="BKMK_Requirements"> </a>

在部署云连接器版本之前，请确保你的环境具有下列内容：

- **对于主计算机-** 云连接器 Vm 必须部署在运行 Windows Server 2012 R2 Datacenter edition （英语）且启用了 Hyper-v 角色的专用硬件上。

    对于版本 2.0 及更高版本，绑定到 Skype for Business Corpnet 交换机的主机计算机网络卡必须在与云连接器公司网络计算机相同的子网中配置 IP 地址。

- 对于版本2.1 和更高版本，主机装置必须安装 .NET Framework 4.6.1 或更高版本。

- **对于虚拟机-** Windows Server 2012 R2 ISO （英语）映像（.iso）。 ISO 将被转换为将运行 Skype for Business Cloud Connector Edition 的虚拟机的 Vhd。

- 支持安装部署中每个云连接器版本的4个 Vm 的必要硬件。 推荐以下配置：

  - 64位双处理器、六核（12核）、2.50 千兆位（GHz）或更高版本

  - 64 GB ECC RAM 

  - 四个 600 GB（或更高）10K RPM 128M 缓存 SAS 6Gbps 磁盘，在 RAID 5 配置中进行配置

  - 三个 1 Gbps RJ45 高吞吐量网络适配器

- 如果你选择部署支持多达50同时通话的较小版本的云连接器版本，你将需要以下硬件：

  - Intel i7 4790 四核处理器，采用 Intel 4600 显卡（不需要高端显卡）

  - 32 GB DDR3-1600 非 ECC

  - 2：RAID 0 中的 1TB 7200RPM SATA III (6 Gbps)

  - 2：1 Gbps 以太网 (RJ45)

- 如果在主机上需要代理服务器来浏览 Internet，则必须进行下列配置更改：

  - 若要绕过代理，请指定使用代理服务器设置的 WinHTTP 代理设置和回避列表（包括 "192.168.213"）。\*由您的云连接器 Managements 服务和 Skype for business 网络网络子网使用的网络，如 CloudConnector 文件中所定义。 否则，管理连接将失败，并将阻止部署和自动恢复 CloudConnector_shortest。 以下是 winhttp 配置命令示例： netsh winhttp set proxy "10.10.10.175： 8080" 旁路-list = "\*local; 1。\*; 172.20。\*; 192.168.218。\*"\<本地\>"。

  - 指定每台计算机的代理服务器设置，而不是每用户。 否则，云连接器下载将失败。 你可以使用注册表更改或组策略设置来指定每台计算机的代理设置，如下所示：

  - **注册表：** HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet 设置] ProxySettingsPerUser dword：00000000

  - **组策略：** 计算机\>管理模板\>Windows 组件\> Internet Explorer：针对每台计算机（而不是每用户）进行代理设置

- 合格的 PBX/Trunk 或合格的 SBC/网络（建议至少使用两个网关）。

    云连接器支持经过认证适用于 Skype for Business 的相同会话边界控制器 (SBC)。 有关详细信息，请参阅[Skype for business 的电话服务基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。

- 具有在主机服务器上安装和配置 Hyper-v 的权限的本地服务器管理员帐户。 帐户必须在安装和配置了 Hyper-V 的本地服务器上具有管理员权限。

- 部署过程中，需要创建有权限在云连接器域中创建和发布拓扑的域管理员帐户。

- 外部 DNS 记录，这些记录是在安装程序包附带的 CloudConnector.ini 文件中定义的：

  - 适用于 Edge 组件的访问边缘服务的外部 DNS 记录;例如，"接入点\<域名"\>。 每个 PSTN 站点都需要一个记录。 此记录必须包含该网站所有边缘的 IP 地址。

- 已创建所有所需的 DNS 和 SRV 记录的 Office 365 租户。

    > [!IMPORTANT]
    > 将租户与云连接器版本集成时，不支持将默认域后缀 onmicrosoft.com 用作组织的 SIP 域。 > 您不能使用 sip。\<域名\>作为云连接器 Edge 访问代理接口的名称，因为此 DNS 记录由 Office 365 使用。

- 从公共证书颁发机构 (CA) 获得的用于外部边缘的证书。

- 允许通过所需的端口传输流量的防火墙规则已完成。

- 主机计算机和虚拟机的 Internet 连接。 云连接器从 Internet 下载某些软件;因此，您必须提供网关和 DNS 服务器信息，以便云连接器主机和虚拟机可以连接到 Internet 并下载必要的软件。

- 主机计算机上安装了租户远程 PowerShell 模块。

- 运行远程 PowerShell 的 Office 365 Skype for Business 管理员凭据。

    > [!IMPORTANT]
    > 管理员帐户不得启用多因素身份验证。

> [!NOTE]
> 仅 Microsoft Hyper-v 虚拟化平台支持云连接器部署。 其他平台（如 Vmware 和 Amazon Web Services）不受支持。

> [!NOTE]
> 运行云连接器的最低硬件指南基于基本硬件容量（内核、MHz、千兆字节等），其中提供了一些缓冲区来满足任何计算机的体系结构中的无形性能障碍。 Microsoft 已对市场上出售的满足最低指导要求的硬件运行了最坏情况下的负载测试。 介质质量和系统性能都经过验证。 适用于 Microsoft 的官方云连接器设备合作伙伴具有特定的云连接器硬件实现，它们分别测试了性能，其硬件适用性满足负载和质量要求。

> [!NOTE]
> AudioCodes 和 Sonus 生产的设备已修改了代码，并在 Windows Server Standard Edition 的服务器上运行。 这些设备受支持。

## <a name="information-you-need-to-gather-before-deployment"></a>在部署之前需要收集的信息
<a name="BKMK_PlanDeployment"> </a>

在开始部署之前，您需要确定部署的规模、服务于的 SIP 域以及您计划部署的每个 PSTN 网站的配置信息。若要开始，您将执行以下操作：

- 根据公司中使用的 SIP Uri 标识将由此部署提供服务的所有 SIP 域。

- 确定需要部署的 PSTN 网站数。

- 确保你有必要硬件支持你将为每个云连接器版本安装的四个 Vm。

对于你计划部署的每个 PSTN 网站，你需要：

- 为每个云连接器装置中的所有组件创建名称（请参阅[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)）。

- 确定端口范围（请参阅[端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)）。

- 为边缘组件创建外部 DNS 记录（请参阅[部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)）。

- 确定边缘组件的证书要求（请参阅[证书要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)）。

### <a name="ports-and-protocols"></a>端口和协议
<a name="BKMB_Ports"> </a>

当确定媒体端口范围时，请注意以下事项：

- 客户端始终使用端口范围50000到50019进行媒体流量-此范围是在 Skype for Business Online 中预定义的，不能更改。

- 默认情况下，中介组件将使用端口范围 49 152 至 57 500 传输媒体流量。 但是，连接是通过内部防火墙建立的，并且出于安全考虑，您可以限制拓扑中的此端口范围。 每个呼叫最多需要 4 个端口。 如果需要限制中介组件和 PSTN 网关之间的端口数，你还需要在网关上配置对应的端口范围。

- 必须在外围网络中部署云连接器。 这意味着你将有两个防火墙：

  - 第一个防火墙是 Internet 和您的外围网络之间的外部防火墙。

  - 第二个防火墙在外围网络和内部网络之间是内部的。

    您的客户端可以位于 Internet 也可以位于内部网络内：

  - Internet 内的客户端将通过外部防火墙使用边缘组件连接到你的 PSTN。

  - 内部网络中的客户端将通过内部防火墙连接到外围网络中的中介组件，后者将流量连接到 SBC 或 PSTN 网关。

    这意味着您需要在两个防火墙中都打开端口。

下表介绍了外部和内部防火墙的端口和端口范围。

此表显示了支持在内部网络中的客户端和中介组件之间进行通信的端口和端口范围：

**内部防火墙**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |任意  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |任意  <br/> |TCP 5068/ TLS 5067  <br/> |
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |UDP 49 152-57 500  <br/> |所有\*\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |所有\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50,000-50,019  <br/> （可选）  <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50,000-50,019  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |TCP 50,000-50,019  <br/> |TCP 49 152-57 500\*  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |UDP 50,000-50,019  <br/> |UDP 49 152-57 500\*  <br/> |

\*这是中介组件上的默认端口范围。 为获得最佳呼叫流，每个呼叫需要四个端口。

\*\*必须在 SBC/PSTN 网关配置此端口;5060是一个示例。 你可以在 SBC/PSTN 网关上配置其他端口。

\*\*\*请注意，如果 SBC/网关制造商允许，你也可以限制你的 SBC/网关的端口范围。

出于安全考虑，你可以使用[CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) Cmdlet 限制中介组件的端口范围。

例如，以下命令限制了将用于音频的媒体流量为 50 000-51 000 （入和出）的端口数。 中介组件使用此配置能够处理 250 个并发呼叫。 请注意，您可能还需要在 SBC/PSTN 网关上限制此范围：

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

若要检索中介组件的名称并查看默认端口，可以使用[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) cmdlet，如下所示：

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表显示了允许云连接器边缘组件与外部防火墙之间通信的端口和端口范围。 此表显示了建议的最低配置。

在这种情况下，internet 上的所有媒体流量将通过在线边缘传递，如下所示：用户终结\>点-在线边缘\>--云连接线边缘：

**外部防火墙 - 最低配置**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任意  <br/> |云连接线边缘外部接口  <br/> |任意  <br/> |TCP(MTLS) 5061  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP(MTLS) 5061  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP 80  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |UDP 53  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP 53  <br/> |
|云连接线边缘外部接口  <br/> |任何  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任意  <br/> |云连接线边缘外部接口  <br/> |TCP 50,000-59,999  <br/> |TCP 443  <br/> |
|任何  <br/> |云连接线边缘外部接口  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |TCP 50,000-59,999  <br/> |TCP 443  <br/> |

下表显示了端口和端口范围，以便在云连接器 Edge 组件之间实现与外部防火墙之间的通信。 下表显示了推荐的解决方案。

在这种情况下，internet 中的终点的所有媒体流量都可以直接流向 Cloud Connector Edge 组件。 媒体路径将为用户终结点-\>云连接线边缘。

> [!NOTE]
> 如果用户终结点在对称 NAT 后面，此解决方案不适用。

**外部防火墙 - 推荐的配置**


|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任意  <br/> |云连接线边缘外部接口  <br/> |任意  <br/> |TCP(MTLS) 5061  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP(MTLS) 5061  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP 80  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |UDP 53  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |任意  <br/> |TCP 53  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |TCP 50,000-59,999  <br/> |任意  <br/> |
|云连接线边缘外部接口  <br/> |任意  <br/> |UDP 3478；UDP 50,000-59,999  <br/> |任意  <br/> |
|任意  <br/> |云连接线边缘外部接口  <br/> |任意  <br/> |TCP 443；TCP 50,000-59,999  <br/> |
|任何  <br/> |云连接线边缘外部接口  <br/> |任何  <br/> |UDP 3478；UDP 50,000 - 59,999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>主机 Internet 连接要求
<a name="BKMB_Ports"> </a>

主机必须能够访问外部资源才能成功安装、更新和管理云连接器。 下表显示了主机计算机与外部资源之间所需的目标和端口。

|方向  <br/> |源 IP  <br/> |目标 IP  <br/> |源端口  <br/> |目标端口  <br/> |协议  <br/> |用途  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|出站  <br/> |云连接器主机 IPs  <br/> |任何  <br/> |任何  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|出站  <br/> |云连接器主机 IPs  <br/> |任何  <br/> |任何  <br/> |80, 443  <br/> |TCP  <br/> |证书吊销列表 (CRL)  <br/> |
|出站  <br/> |云 Connectorr 主机 IPs  <br/> |任何  <br/> |任何  <br/> |80, 443  <br/> |TCP  <br/> |云连接器更新  <br/> Skype for Business Online  <br/> 管理 PowerShell  <br/> Windows 更新  <br/> |

如果需要限制性更强的规则，请参阅以下白名单 URL：

- [Office 365 url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中的[证书吊销列表 url](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Windows 更新：[如何为软件更新配置防火墙](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- Skype for Business Online 管理员 PowerShell： \*online.lync.com

    如果需要为此目标设置代理排除，需要将其添加到 WinHTTP 绕过列表中。

- 云连接器更新： "[下载中心](https://aka.ms/CloudConnectorInstaller)" [https://go.microsoft.com](https://go.microsoft.com)、"和"[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>边缘组件的 DNS 名称解析
<a name="BKMB_Ports"> </a>

Edge 组件需要解析 Office 365 服务的外部名称以及其他云连接器组件的内部名称。

每个边缘组件都是具有面向外部和内部的接口的多宿主计算机。 云连接器在外围网络中的域控制器组件上部署 DNS 服务器。 你可以将 Edge 服务器指向周边中的 DNS 服务器，以使用所有名称解析，但你需要启用云连接器 DNS 服务器解析外部名称，方法是为外部查询设置包含一个或多个 DNS A 记录的 DNS 区域，引用名称对其他公共 DNS 服务器的查找。

在 .ini 文件中，如果将相同域空间中网关的 FQDN 名称设置为你的 SIP 域，则将在外围网络内的 DNS 服务器中创建此 SIP 域的权威区域。 如果 Edge 服务器指向此 DNS 服务器以解析名称，则 Edge 从不解析 _sipfederationtls。\<您\> DNS 记录，它是调用流所必需的。 在这种情况下，Microsoft 建议你在 Edge 外部接口上提供 DNS 服务器以解析 Internet 名称查找，并且每个 Edge 组件必须使用主机文件将其他云连接器组件名称解析为 IP 地址。

> [!NOTE]
> 出于安全考虑，我们建议你不要将云连接器 DNS 服务器指向生产域中的内部服务器以进行名称解析。

### <a name="determine-deployment-parameters"></a>确定部署参数
<a name="BKMK_SiteParams"> </a>

首先需要定义以下常见部署参数：


|**项目**|**说明**|**注释**|
|:-----|:-----|:-----|
|SIP 域  <br/> |公司用户正在使用 SIP URI。 提供此部署将服务于的所有 SIP 域。 你可以有多个 SIP 域。  <br/> ||
|PSTN 网站数  <br/> |将部署的 PSTN 网站数。  <br/> ||

对要计划部署的每个 PSTN 网站，你需要在开始部署之前收集以下信息。 当更新 CloudConnector.ini 文件时，你需要提供此信息。

当配置网关信息时，请记住以下事项：

- 如果你只有一个网关，请在 .ini 文件中删除第二个网关的该部分。 如果网关超过两个，请按照现有格式添加新网关。

- 请确保网关的 IP 地址和端口正确。

- 要支持 PSTN 网关级别 HA，请保留辅助网关或添加其他网关。

（可选）要限制出站呼叫号码，请更新 LocalRoute 值。



|**网站参数**|**说明**|**备注**|
|:-----|:-----|:-----|
|虚拟机域名  <br/> |云连接器的内部组件的域名。 此域应不同于生产域。 该名称必须在所有云连接器设备上都是相同的。  <br/> 在 .ini 文件中的名称： "VirtualMachineDomain"  <br/> |.local 域为首选。  <br/> |
|云连接器域控制器名称  <br/> |域控制器的名称。  <br/> 在 .ini 文件中的名称： "服务器名"  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> |
|云连接器域控制器 IP/子网掩码  <br/> |域控制器的 IP 地址。  <br/> 在 .ini 文件中的名称： "IP"  <br/> ||
|O365 联机服务 FQDN  <br/> |对于世界范围的 O365 实例，大多数情况下都必须是默认值。  <br/> 在 .ini 文件中的名称： "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for business 网站名称;例如，西雅图。  <br/> .Ini 文件中的名称： "SiteName"  <br/> 对于 1.4.1 版及更高版本，各个站点的站点名称不能相同，并且名称必须与 Office 365 中定义的 PSTN 站点（如果存在）匹配。 请注意，在站点中注册第一台设备时，将会自动创建 PSTN 站点。  <br/> ||
|HardwareType  <br/> 1.4.1 版及更高版本  <br/> |硬件类型。 默认值为“Normal”。 你也可以设置为“Minimum”。  <br/> ||
|国家/地区代码  <br/> |用于拨号的国家/地区代码。  <br/> 在 .ini 文件中的名称： "CountryCode"  <br/> ||
|城市  <br/> |城市（可选）。  <br/> .Ini 文件中的名称： "City"  <br/> ||
|省/市/自治区  <br/> |省/市/自治区（可选）。  <br/> .Ini 文件中的名称： "State"  <br/> ||
|基本虚拟机 IP 地址  <br/> |将用于为所有云连接器虚拟机创建 VHDX 的临时基 VM 的 IP 地址。 此 IP 应位于下一步中定义的相同企业外围网络子网内，需要 Internet 访问。 请务必定义企业默认网关和可路由到 Internet 的 DNS。  <br/> 在 .ini 文件中的名称： "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 1.4.1 版及更高版本  <br/> |Windows Server 更新服务 (WSUS) 的地址 — 用于托管 Microsoft 更新所提供的更新的 Intranet 服务器。  <br/> 如果不需要 WSUS，可以留空。  <br/> ||
|内部网络的子网掩码  <br/> |云连接器为云连接器组件之间的内部通信配置 IP 网络。 边缘也应连接到允许 Internet 连接的另一子网。  <br/> 在 .ini 文件中的名称： "CorpnetIPPrefixLength" 下的 "VM 网络池的参数" 下的 "  <br/> ||
|外部网络的子网掩码   <br/> |对于边缘组件的外部网络。  <br/> 在 .ini 文件中的名称： "InternetIPPrefix" 下的 "VM 网络池的参数" 下的 "  <br/> ||
|内部网络的交换机名称  <br/> |将用于内部云连接器网络的开关的名称。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在 .ini 文件中的名称： "CorpnetSwitchName" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|外部网络的交换机名称  <br/> |将用于外部云连接器网络的开关的名称。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在 .ini 文件中的名称： "InternetSwitchName" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|内部网络的默认网关  <br/> |此网关必须提供对 Internet 的访问权限（Internet 也需要设置 DNS 服务器），并且将在云连接器组件的内部接口上配置。  <br/> 在 .ini 文件中的名称： "CorpnetDefaultGateway" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|边缘组件的外部接口的默认网关  <br/> |将在边缘组件的外部接口上配置。  <br/> 在 .ini 文件中的名称： "InternetDefaultGateway" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|内部网络的 DNS 服务器  <br/> |将在临时虚拟机的内部接口上配置。 必须为 Internet 名称提供名称解析。 如果不提供 DNS 服务器，Internet 连接将失败，部署无法完成。  <br/> 在 .ini 文件中的名称： "CorpnetDNSIPAddress" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|边缘组件的外部接口的 DNS 服务器  <br/> |将在边缘的外部接口上配置。  <br/> 在 .ini 文件中的名称： "InternetDNSIPAddress" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|管理交换机名称。  <br/> |管理开关是将自动创建的临时开关，它将用于在部署期间配置云连接器。 部署之后将自动断开连接。 它必须是与云连接器中使用的任何其他网络不同的子网。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在 .ini 文件中的名称： "ManagementSwitchName" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|管理子网地址/子网掩码  <br/> |管理子网是将自动创建的临时子网，并且将在部署期间用于配置云连接器。 部署之后将自动删除。 它必须是与云连接器中使用的任何其他网络不同的子网。  <br/> 在 .ini 文件中的名称： "ManagementIPPrefix" 和 "ManagementIPPrefixLength" 下的 "VM 网络池的参数" 下的 "参数"  <br/> ||
|中央管理存储（CMS）计算机  <br/> |用于中央管理存储 (CMS) 的单个 FQDN。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "主中心管理服务的参数" 下的 "服务器名"  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> （CMS 池名称 = 服务器名称）  <br/> |
|CMS 计算机 IP 地址  <br/> |CMS 服务器的 IP 地址（在外围网络内部）。  <br/> INI 文件中的名称： "IP" 位于 "主要管理中心管理服务的参数" 下  <br/> ||
|文件共享名称   <br/> |要在 CMS 服务器上为 Skype for Business 复制数据创建的文件共享名称（例如，CmsFileStore）。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在 .ini 文件中的名称： "CmsFileStore" 下的 "主要管理中心管理服务的参数" 下  <br/> ||
|采集转送组件池名称  <br/> |中介组件的池名称。 请仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> 在 .ini 文件中的名称： "PoolName" 下的 "中介服务器池的参数" 下的 "  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> |
|中介组件名称  <br/> |中介组件 1 的组件名称。 请仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> 在 .ini 文件中的名称： "服务器名" 下的 "中介服务器池的参数" 下的 "服务器名"  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> |
|中介组件计算机 IP 地址  <br/> |用于中介组件的内部公司内部公司 IP （在外围网络内部）。  <br/> .Ini 文件中的名称： "IP" 在 "中介服务器池的参数" 下  <br/> ||
|边缘池内部名称  <br/> |边缘组件的池名称。 请仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> 在 .ini 文件中的名称： "InternalPoolName" 下的 "边缘服务器池的参数" 下的 "  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> |
|边缘服务器内部名称  <br/> |边缘组件的组件名称。请仅输入 Netbios 名称。AD 域名将用于生成 FQDN。  <br/> 在 .ini 文件中的名称： "InternalServerName" 下的 "边缘服务器池的参数" 下的 "  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|边缘服务器内部 IP   <br/> |与云连接器的其他组件通信的边缘组件的内部外围网络 IP。  <br/> 在 .ini 文件中的名称： "InternalServerIPs" 下的 "边缘服务器池的参数" 下的 "  <br/> ||
|访问池外部名称  <br/> |访问边缘的名称；例如，AP。 此名称必须与为 SSL 证书提供的名称相匹配。 请仅输入 Netbios 名称。 SIP 域名将用于生成 FQDN。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点需要一个 Edge 访问池。  <br/> 在 .ini 文件中的名称： "ExternalSIPPoolName" 下的 "边缘服务器池的参数" 下的 "  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> "sip" 已保留，因此不能用作名称。  <br/> 生成的 FQDN 名称必须与为 SSL 证书提供的名称相匹配。  <br/> |
|访问边缘的外部 IP  <br/> |Edge 组件的外部 IP （如果没有可用的 NAT，则为公共 IP），或者是已翻译的 IP （如果已映射，请指定两个地址）。  <br/> 在 .ini 文件中的名称： "ExternalSIPIPs" 下的 "边缘服务器池的参数" 下的 "  <br/> ||
|媒体中继名称  <br/> |音频视频媒体中继边缘的名称；例如 MR。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点需要一个 Edge 媒体中继池。  <br/> 在 .ini 文件中的名称： "ExternalMRFQDNPoolName" 下的 "边缘服务器池的参数" 下的 "  <br/> |必须为 15 个字符或更少。 请仅输入 Netbios 名称。  <br/> |
|媒体中继边缘的外部 IP  <br/> |当前仅支持一个 IP，因此这将是与访问边缘相同的 IP，为公用 IP 或映射的 IP（如果映射，请同时指定两个地址）。 可以是与访问边缘的边缘组件外部 IP 相同的地址。 请注意，如果边缘服务器位于 NAT 后面，你还需要指定下一个参数的值。  <br/> 在 .ini 文件中的名称： "ExternalMRIPs" 下的 "边缘服务器池的参数" 下的 "  <br/> ||
|媒体中继边缘的外部 IP （如果边缘位于 NAT 下方）  <br/> |如果你的边缘位于 NAT 后面，你还可以指定 NAT 设备的公共地址。  <br/> 在 .ini 文件中的名称： "ExternalMRPublicIPs" 下的 "边缘服务器池的参数" 下的 "  <br/> ||
|语音网关1制作和型号  <br/> |指定 SBC/语音网关的品牌和型号。 请注意，您可以从已测试的设备列表中连接设备或 SIP 干线[https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)。  <br/> ||
|语音网关2型和型号（如果您有2个以上的网关，请复制此行）  <br/> |指定语音网关的品牌和型号。 请注意，您可以从的已测试设备列表中连接设备[https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)。  <br/> ||
|语音网关1名称  <br/> |用于使用 AD 域生成计算机 FQDN。 如果将在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不打算使用 FQDN （例如，TLS 不是必需的，或者语音网关不支持使用 FQDN （仅 IP）的连接，请指定。  <br/> ||
|语音网关2名称（如果您有2个以上的网关，请复制此行）  <br/> |用于使用 AD 域生成计算机 FQDN。 如果将在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不打算使用 FQDN （例如，TLS 不是必需的，或者语音网关不支持使用 FQDN （仅 IP）的连接，请指定。  <br/> ||
|语音网关 1 IP 地址  <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关 2 IP 地址（如果您有2个以上的网关，请复制此行）  <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关1端口 # （如果您有2个以上的网关，请复制此行）  <br/> |语音网关 SIP 中继将侦听的端口，例如 5060。  <br/> ||
|语音网关2端口#  <br/> |语音网关 SIP 中继将侦听的端口，例如 5060。  <br/> ||
|用于 SIP 流量的语音网关1协议  <br/> |TCP 或 TLS。  <br/> ||
|用于 SIP 流量的语音网关2协议（如果您有2个以上的网关，请复制此行）  <br/> |TCP 或 TLS。  <br/> ||
|与边缘组件之间传输的流量的外部媒体端口范围  <br/> |与边缘的外部接口之间传输的媒体流量的 TCP/UDP 端口范围。 必须始终从 50 000 开始。 有关详细信息，请参阅 "端口和协议"。  <br/> |50000 - 59 999  <br/> |
|通过内部防火墙与/从中介组件进行通信的媒体端口范围  <br/> |中介组件将用于与客户端和网关通信的 UDP 端口范围（建议每个呼叫4个端口）。  <br/> ||
|用于通过内部防火墙与 Skype for Business 客户端通信的媒体端口范围  <br/> |出于规划目的，不可更改。 需要在内部防火墙中打开端口，以便在内部网络中的 Skype for Business 客户端与中介组件之间进行通信。  <br/> |50 000 - 50 019  <br/> |
|公用证书密码  <br/> |必须通过脚本提供。  <br/> ||
|安全模式管理员密码  <br/> 仅限于版本 1.4.2  <br/> |内部 CC 域的安全模式管理员密码。  <br/> ||
|云连接器域管理员密码  <br/> 仅限于版本 1.4.2  <br/> |Cloud Connector 域管理员的密码（不同于生产域）。 用户名是 Administrator。 你不能更改用户名。  <br/> ||
|虚拟机管理员密码  <br/> 仅限于版本 1.4.2  <br/> |用于在部署过程中配置管理网络。  <br/> 用户名是 Administrator。你不能更改用户名。  <br/> ||
|CABackupFile  <br/> 2.0 版及更高版本  <br/> |在云连接器网站中部署多个设备时，用于将证书颁发机构服务从 Active Directory 服务器保存到文件。 请务必对一个云连接器内的所有设备使用相同密码，以确保成功地将 CA 备份文件导入到新添加的设备。  <br/> ||
|CCEService  <br/> 2.0 版及更高版本  <br/> |用于云连接器管理服务；需要访问云连接器站点目录。务必对一个云连接器站点内的所有设备使用相同密码。  <br/> ||
|Office 365 租户管理员  <br/> | 云连接器使用该帐户来更新和管理云连接器的租户设置： <br/>  版本2.0 和更高版本：具有 Skype for business 管理员权限的专用 Office 365 帐户的凭据。 <br/>  2.0 之前的版本：具有全局租户管理员权限的专用 Office 365 帐户的凭据。 <br/> ||
|启用 Refer 支持  <br/> |这将定义在你的 IP/PBX 的中继配置上启用还是禁用 SIP REFER 支持。 默认值为 True。 如果你的 IP/PBX 网关提供 REFER 支持，请将此值保留为 true。 否则，需要将此值更改为 False。 如果您不确定您的网关是否支持引用，请参阅[合格的 IP-pbx 和网关](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。   <br/> ||
|EnableFastFailoverTimer  <br/> 2.0 版及更高版本  <br/> |使用默认值 "True" 时，如果网关在10秒内未接听出站通话，它们将路由到下一个可用网关;如果没有其他中继，将自动丢弃呼叫。  <br/> 但是，在网络和网关响应较慢的组织中，或者当建立呼叫的过程超过 10 秒时，这可能会导致不必要的呼叫丢弃。  <br/> 拨打某些国家/地区（例如阿联酋或阿富汗）的电话时，呼叫建立过程可能需要 10 秒以上。 如果遇到类似问题，则需将值更改为 False。 记得在连接的 SBC 或网关上更改相应的设置。  <br/> 值可以为 True 或 False。默认值为 True。  <br/> ||
|ForwardCallHistory  <br/> 2.0 版及更高版本  <br/> | 此参数用于启用报告同时响铃、呼叫转接和呼叫转移场景中的初始呼叫方的 SIP 头。将此参数设置为 True 将启用两个 SIP 头：<br/>  History-Info <br/>  Referred-By <br/>  历史记录信息标头用于重新定向 SIP 请求和 "提供（s）一种标准机制来捕获请求历史记录信息，以便为网络和最终用户提供多种服务" （[RFC 4244-Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)）。 对于云连接器中继接口，此头用于同时响铃和呼叫转接场景。  <br/>  值可以为 True 或 False。默认值为 False。<br/> ||
|转发 PAI  <br/> 2.0 版及更高版本  <br/> |PAI 是 SIP 的专用扩展，使 SIP 服务器可以断定已经过身份验证的用户的身份。 对于 SIP 中继提供程序，PAI 可用于 History-Info 和 Referred-By 头不存在的事件中的计费目的。 在配置中启用转发 P 声明的标识时，中介服务器会将具有 SIP &amp;电话 URI 的 PAI 标头从 Cloud Connector 转发到 SIP 主干。 中介服务器将转发 PAI 标头，其中电话 URI &amp;的 E.I 数字仅在 SIP 主干和云连接器上收到。 中介服务器还会转发在任一方向收到的任何 Privacy 头。 如果中介服务器发送的 SIP 请求包含表单的隐私标头-"隐私： id" 与 PAI 标头结合，则声明的标识应保留在网络信任域外部的专用。  <br/> 值可以为 True 或 False。默认值为 False。  <br/> ||

### <a name="certificate-requirements"></a>证书要求
<a name="BKMK_Certs"> </a>

每个边缘组件都需要来自公共证书颁发机构的证书。 证书必须具有可在边缘组件之间复制的可导出私钥。 要满足证书要求，你需要在以下选项之间做出选择并为证书提供使用者名称 (SN) 和使用者可选名称 (SAN)。

 **如果你有单个 SIP 域：**

- **选项 1.** 使用者名称应包含你为边缘组件分配的池名称。 请注意，由于此名称已保留给联机 Skype for Business Edge 组件，因此无法 sip.sipdomain.com 使用者名称。 SAN 应包含 sip.sipdomain.com 和访问边缘池名称：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **选项 2.** 如果想要在部署的所有边缘池服务器上使用单个通配符证书，则可以使用 sipdomain.com 中的通配符 SAN 条目\*，而不是证书中的边缘池名称。 使用者名称可以是你部署的任何一个边缘池的访问边缘池名称：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> 您不得为 sip 创建外部 DNS 条目。\<sipdomain\>，因为此名称属于 Office 365 部署。

> [!NOTE]
> 如果你要为你的组织中部署的所有边缘池使用单个证书且不能使用选项 2 中定义的通配符证书，那么你需要在证书的 SAN 名称中包括用于所有部署边缘池的 FQDN。

 **如果你有多个 SIP 域：**

你需要为每个 SIP 域添加 sip.sipdomain.com，以及添加每个域的访问边缘池的名称（它可以是一个物理池，但是名称不同）。 下面是多个 sip 域方案中的 SN 和 SAN 条目示例：

- **选项 1.** 主题名称必须包含你为 Edge 组件分配的池名称。 请注意，由于此名称已保留给联机 Skype for Business Edge 组件，因此无法 sip.sipdomain.com 使用者名称。 SAN 应包含 sip.sipdomain.com 和访问边缘池名称：

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>选项2。</strong>如果想要在部署的所有边缘池服务器上使用单个通配符证书，则可以使用 sipdomain.com 中的通配符 SAN 条目\*，而不是证书中的边缘池名称。 使用者名称可以是你部署的任何一个边缘池的访问边缘池名称：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> 您不得为 sip 创建外部 DNS 条目。\<sipdomain\>，因为此名称属于 Office 365 部署。

出于部署目的，您可以使用下表：

|**选项**|**说明**|**备注**|
|:-----|:-----|:-----|
|将对您的部署使用哪个选项？  <br/> |选项 1 或 2  <br/> ||
|SN  <br/> |为您的证书提供 SN  <br/> ||
|SAN  <br/> |为您的证书提供 SAN  <br/> ||

如果你要在网关与中介服务器之间使用 TLS，则需要获取分配给网关的证书的根证书或完整证书链。

## <a name="dial-plan-considerations"></a>拨号计划注意事项
<a name="BKMK_DailPlan"> </a>

云连接器需要使用在线拨号计划。 有关如何配置联机拨号计划的详细信息，请参阅[什么是拨号计划？](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>高可用性注意事项
<a name="BKMK_HA"> </a>

部署云连接器版本以获得高可用性时，至少要部署两个充当彼此备份的装置。 每个装置包含四个组件： Edge、中介、中央管理存储（CMS）和域控制器。

通常，如果装置中的一个组件出现故障，云连接器版本可以继续处理呼叫，但必须考虑以下事项：

- **中介、CMS 和域控制器组件注意事项**

    假设一台设备中的 CMS 或域控制器组件关闭。 该设备仍可以处理入站和出站呼叫，但是如果你在域控制器或 CMS 组件不可访问时重新启动中介组件，中介组件将无法正常工作。 在域控制器关闭时重新启动 CMS 组件，同样存在此问题。

    **建议：** 重新启动组件之前，请检查装置中的其他组件的可用性。

- **边缘组件注意事项**

    如果一台设备中的边缘组件不可用，则入站和出站呼叫的行为将有所不同，如下所示：

  - **出站呼叫**——从 INTERNET 到 PSTN 网络的呼叫。

    云中的呼叫分配机制将确定一个边缘组件已关闭，并将所有呼叫都路由到另一台设备，因此出站呼叫将会成功。

  - **入站呼叫**——从 PSTN 网络到本地网络或 Internet 中的用户的呼叫。

     如果接收呼叫的设备的边缘组件未正常工作，则发往此设备的入站呼叫不会成功，因为中介组件无法将该呼叫重定向到其他设备中的边缘组件。

    **建议：** 准备好监控系统。 确定 Edge 组件的故障后，请关闭装置中 Edge 组件不可用的所有组件。

## <a name="cloud-connector-media-flow"></a>云连接器媒体流
<a name="BKMK_MediaFlow"> </a>

下图概括了通过云连接器版本进行出站和入站呼叫的流程。 此信息有助于理解连接的建立方式。

在第一个图中，内部用户拨打出站呼叫，如下所示：

1. Dave 是一个以联机方式驻留的用户，但是现在位于内部网络中，他向外部 PSTN 用户发出呼叫。

2. SIP 流量路由到 Skype for Business Online。

3. Skype for business Online 对该号码执行反向数字查找。 反向号码查找失败，因为此号码不属于 Skype for Business 组织中的任何人。

4. 呼叫将路由到边缘组件（SIP 和媒体流首先通过联机边缘；媒体将通过内部防火墙转到中介组件）。

5. 如果路由存在，边缘组件会将流量中继到外围网络中的中介组件。

6. 中介组件将流量发送到 PSTN 网关。

![云连接器的出站媒体流](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

在下个图中，内部用户接收入站呼叫，如下所示：

1. PSTN 网关为以联机方式驻留但现在位于内部网络中的用户 Dave 接收呼叫。

2. SIP 流量将路由到中介组件。

3. 中介组件将 SIP 流量发送到边缘组件，然后转到 Skype for business Online。

4. Skype for Business Online 对该号码执行反向号码查找，发现这是用户 Dave。

5. SIP 信号将转到 Dave 的所有状态点。

6. 将在网关和中介组件之间以及中介组件和终结点之间建立媒体流量。

![云连接器的入站媒体流](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>监视和故障排除
<a name="BKMK_Monitor"> </a>

每台云连接器设备都会自动安装监视和故障排除机制。该机制会检测下列事件：

- 云连接器设备的一个或多个虚拟机未连接到内部或 Internet 虚拟交换机。

- 云连接器设备的一个或多个虚拟机处于已保存或已停止状态。

- 未运行的服务。

  如果检测到以下事件之一，则整个云连接器装置将被排出并标记为 "脱机"，以防止尝试建立无法正常工作的装置的呼叫。 随后，云连接器自动恢复功能将还原服务并将设备标记为在线。 如果自动恢复由于某些原因失败，请参阅[Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md)。

  - 在中央管理存储虚拟机上：

     - Skype for Business 主复制器代理

     -  Skype for Business 备份复制器代理

  - 在中介服务器虚拟机上：

     -  Skype for Business 备份复制器代理

     - Skype for Business Server 中介

  - 在边缘服务器虚拟机上：

     -  Skype for Business 备份复制器代理

     -  Skype for Business Server 访问边缘

     - Skype for Business Server 音频/视频边缘

     - Skype for Business Server 音频/视频验证

     - Skype for Business Server Web 会议边缘

- 边缘服务器上“CS RTCSRV”的 Windows 防火墙和中介服务器上的“CS RTCMEDSRV”的入站规则已禁用。

云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅[Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_MoreInfo"> </a>

有关详细信息，请参阅：

- [Microsoft 电话解决方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [配置和管理 Skype for Business 云连接器版本](configure-skype-for-business-cloud-connector-edition.md)

- [云连接器版本中的媒体旁路规划](plan-for-media-bypass-in-cloud-connector-edition.md)

- [在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)


