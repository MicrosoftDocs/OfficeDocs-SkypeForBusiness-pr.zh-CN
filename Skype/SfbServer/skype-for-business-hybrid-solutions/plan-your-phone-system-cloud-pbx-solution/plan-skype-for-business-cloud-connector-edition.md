---
title: Plan for Skype for Business Cloud Connector Edition
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
description: 查找有关 Skype for Business 云连接器版本的信息，该版本是一组打包的虚拟机 (VM) ，使用电话系统 (云 PBX) 实现本地 PSTN 连接。
ms.openlocfilehash: 75abeba6c97b59b4795fc3399ff6a983db57bbff
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064708"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Plan for Skype for Business Cloud Connector Edition

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

查找有关 Skype for Business 云连接器版本的信息，该版本是一组打包的虚拟机 (VM) ，使用电话系统 (云 PBX) 实现本地 PSTN 连接。

如果你还没有 Lync Server 或 Skype for Business Server 部署，云连接器版本可能是适合你的组织的解决方案。 如果仍在调查哪种电话系统解决方案适合你的企业，请参阅 [Microsoft 电话解决方案](/microsoftteams/cloud-voice-landing-page)。

本文档介绍云连接器版本要求和支持的拓扑，并帮助你规划云连接器版本部署。 在配置云连接器环境之前，请务必阅读本主题。 当你准备好部署和配置云连接器版本时，请参阅配置 [和管理 Skype for Business 云连接器版本](configure-skype-for-business-cloud-connector-edition.md)。

云连接器版本 2.1 现已可用。 如果尚未升级到 2.1，请参阅升级到云连接器 [的新版本](upgrade-to-a-new-version-of-cloud-connector.md)。 可在 上找到安装文件 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。

> [!NOTE]
> Microsoft 在新版本发布后的 60 天内支持云连接器版本的早期版本。 Microsoft 将在 2.1 版本发布后的 60 天内支持版本 2.0.1，以便你有时间进行升级。 2.0.1 之前的所有版本都不再受支持。

云连接器版本是一种混合产品，包含一组打包的虚拟机 (VM) 实现与电话系统的本地 PSTN 连接。 通过部署虚拟化环境中最少的 Skype for Business Server 拓扑，你组织中托管在云中的用户可以从 Microsoft 云接收 PBX 服务，但 PSTN 连接通过现有的本地语音基础结构提供。

![显示云 PBX 网关将云 PBX 连接到 Skype for Business 本地部署的拓扑图。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

由于云连接器使您能够将电话系统服务与现有电话环境（例如，PBX、模拟设备和呼叫中心）集成，因此您可以实施从现有电话解决方案到电话系统的分阶段迁移。

例如，假设贵公司有一个复杂的呼叫中心，具有电话系统未提供的特定功能。 你可以选择将呼叫中心用户保留为现有解决方案，但将其他用户移至电话系统。

云连接器将提供本地和在线托管用户之间的路由，你可以选择将你自己的 PSTN 提供商与电话系统一同使用。

规划云连接器版本部署时，请考虑以下事项：

- 若要使用云连接器利用云语音解决方案，你需要注册包含电话系统的 Microsoft 365 或 Office 365 组织。 如果还没有 Microsoft 365 或 Office 365 组织，可以在此处了解如何注册 [：Microsoft 365 商业版](https://products.office.com/business/office)。 请注意，你需要注册包含 Skype for Business Online 的计划。

- 若要向 Skype for Business Online 服务注册云连接器设备并运行各种 cmdlet，云连接器 2.0 及更高版本需要具有 Skype for Business 租户管理员权限的专用 Microsoft 365 或 Office 365 帐户。 2.0 之前的云连接器版本需要具有租户全局管理员权限的专用 Microsoft 365 或 Office 365 帐户。

- 云连接器不需要完整的本地 Skype for Business Server 部署。

    目前，云连接器无法与 Lync 或 Skype for Business 本地服务器共存。 如果要将现有 Lync 或 Skype for Business 用户移动到 Microsoft 365，并不断为用户提供本地电话服务，请考虑使用现有 Skype for Business Server 部署使用具有本地连接的电话系统。 有关详细信息，请参阅 Plan [your Phone System (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page.md)和 Plan Phone System with [on-premises PSTN connectivity in Skype for Business Server。](plan-phone-system-with-on-premises-pstn-connectivity.md)

- 如果你之前已部署 Skype for Business 或 Lync Server，并且扩展了架构，则无需清理云连接器部署的架构，只要从环境中删除了所有 Skype for Business 或 Lync Server 组件。

- 你的用户是联机的。

- 如果组织已配置目录同步 (DirSync) ，则必须先在本地部署中创建计划混合语音的所有用户帐户，然后同步到云。

- 如果需要，你可以保留当前的 PSTN 运营商。

- 如果要向在云连接器上托管的用户提供电话拨入式会议，可以购买 PSTN 会议许可证，也可以按从 Microsoft 获取音频会议产品/服务一样付费。

- 音频会议许可证 (提供时付费，) 升级也是必需的。 如果 Skype for Business 用户收到来自外部 PSTN 用户的呼叫，并且希望向该呼叫添加一个参与者 (将呼叫升级为会议) ，则升级将通过 Microsoft 音频会议服务执行。

- 云连接器 2.0 及更高版本现在支持媒体旁路。 媒体旁路允许客户端将媒体直接发送到公用电话交换网 (PSTN) 下一个跃点（网关或会话边界控制器 (SBC) ）并消除媒体路径中的云连接器版本组件。 有关详细信息，请参阅在云 [连接器版本中规划媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。

- 云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 。 有关详细信息，请参阅使用 Operations Management Suite ([OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

- 云连接器适用于提供 Office 365 企业版 E5 的所有国家/地区。

本主题包含以下各部分：

- [云连接器版本组件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [云连接器版本拓扑](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [部署之前需要收集的信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [拨号计划注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [云连接器媒体流](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [监控和疑难解答](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [详细信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>云连接器版本组件
<a name="BKMK_Components"> </a>

使用云连接器版本，你可以部署一组包含最低 Skype for Business Server 拓扑的打包的 VM，该拓扑由边缘组件、中介组件和中央管理存储 (CMS) 角色组成。 您还将安装域控制器，这是云连接器内部运行所需的。 这些服务配置为与包含 Skype for Business Online 服务的 Microsoft 365 或 Office 365 组织进行混合。

![云连接器版本组件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

云连接器组件提供以下功能：

- **边缘组件** - 本地拓扑和联机服务之间的通信通过边缘组件进行，其中包括以下组件：

  - **访问边缘** - 在本地部署和 Skype for Business Online 之间提供 SIP 路由。

  - **媒体中继** - 在中介组件和其他媒体终结点之间提供媒体路由。

  - **媒体中继身份验证/MRAS** - 生成访问媒体中继的令牌。

- **出站路由** - 在连接到云连接器设备的网关或 SDC 之间提供语音流量的负载平衡。 呼叫将在连接到云连接器设备的所有网关或 SDC 之间均匀拆分。

    根据策略提供到网关的路由。 仅支持基于目标号码和出 (PSTN) 全局策略。

- **中央管理 (CMS)** 角色 - 包括拓扑组件的配置存储，包括 CMS 文件传输。

- **中央管理存储 (CMS**) 副本 - 从 CMS 角色服务器上全局 CMS DB 同步配置信息。

- **域控制器** - 云连接器 Active Directory 域服务，用于存储部署云连接器组件所需的所有全局设置和组。 将针对每个云连接器设备创建一个林。 域控制器不能与生产 Active Directory 有任何连接。 Active Directory 服务包括：

  - Active Directory 域服务

  - 用于颁发内部证书的 Active Directory 证书服务

- **中介组件** - 在 Skype for Business 和 PSTN 网关之间实施 SIP 和媒体网关映射协议。 包含从全局 CMS 数据库同步配置的 CMS 副本。

## <a name="cloud-connector-edition-topologies"></a>云连接器版本拓扑
<a name="BKMK_Topologies"> </a>

出于此讨论的目的，我们将参考 PSTN 站点。 PSTN 站点是云连接器设备的组合，部署在同一位置，并连接了常见的 PSTN 网关。 PSTN 站点允许你：

- 提供与离您的用户最近的网关的连接。

- 在一个或多个 PSTN 站点中部署多个云连接器设备，实现可伸缩性。

- 在单个 PSTN 站点中部署多个云连接器设备，实现高可用性。

本主题介绍 PSTN 站点。 有关规划 PSTN 站点的信息，请参阅规划 [云连接器版本 PSTN 站点](plan-for-cloud-connector-edition-pstn-sites.md)。

可以部署以下云连接器拓扑：

- 每个 PSTN 站点一台云连接器版本设备。 建议仅出于评估目的使用此拓扑，因为它不提供高可用性。

- 每个 PSTN 站点多个云连接器版本设备，以提供高可用性。

- 具有多个云连接器版本设备的多个 PSTN 站点，以提供高可用性的可伸缩性。 您最多可以部署 200 个网站。

规划拓扑时，请考虑以下事项：

- 使用云连接器 2.0 及更高版本，一个 PSTN 站点可以拥有最多 16 个云连接器设备。 以前版本支持每个站点最多 4 个设备。

- 有两种类型的硬件配置通过云连接器测试：

  - 较大版本能够处理大量并发呼叫，并且在所有类型的生产环境中都受支持。

  - 较小的版本旨在运行在低端硬件上，可用于评估目的或低呼叫量的网站。 如果部署云连接器的较小版本，你仍然需要注意生产级硬件要求 (如双电源) 。

- 如果你拥有云连接器版本 2.0 或更高版本，并且你部署了具有较大硬件) 的 16 个设备 (的最大配置，则 PSTN 站点最多可处理 8，000 个并发呼叫。 如果部署较小的版本，则支持的限制是 800。

    你还需要将某些设备专用于高可用性。 最低建议是应保留一个设备以用于高可用性。

  - 在版本 2 中，如果部署 15+1 配置，PSTN 站点可以同时处理多达 7，500 个呼叫。

  - 如果你拥有较早版本，并且使用较大的硬件 (部署最大 3 + 1 配置) ，则 PSTN 站点最多可以处理 1500 个并发呼叫。 如果部署较小的版本，则支持的限制是 150。

-  如果需要每个 PSTN 站点具有更多呼叫，可以通过在同一位置部署其他 PSTN 站点来向上扩展。

> [!NOTE]
> 除非另有说明，否则下面的图表和示例假定使用云连接器的较大版本。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>单个 PSTN 站点内的单个云连接器设备

下图显示了单个 PSTN 站点中的单个云连接器版本设备。 请注意，出于安全目的，云连接器由安装在外围网络内的一台物理主机上的四个 VM 组成。

![具有一个 PSTN 站点的一个云连接器](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>单个 PSTN 站点内的多个云连接器设备

 出于可伸缩性和高可用性目的，您可以选择在单个 PSTN 站点中具有多个云连接器版本，如下图所示。 比如以下几种情况：

- 呼叫在一个池中的云连接器之间随机分布。

- 出于容量规划目的，您必须根据以下计算考虑在一个或多个云连接器脱机时处理负载的能力：

  - **N+1 个框。** 对于云连接器的较大版本，N+1 框支持 500 N 个并发呼叫，可用性为 \* 99.8%。

    对于云连接器的较小版本，N+1 框支持 50 N 个并发呼叫，可用性为 \* 99.8%。

  - **N+2 个框。** 对于云连接器的较大版本，N+2 框支持 500 N 个并发呼叫，可用性 \* 为 99.9%。

    对于云连接器的较小版本，N+2 框支持 50 N 个并发呼叫，可用性为 \* 99.9%。

![1 个 PSTN 站点内的两个云连接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>每个站点具有一个或多个云连接器的多个 PSTN 站点

还可以选择让多个 PSTN 站点在每个站点中具有一个或多个云连接器版本。 如果 PSTN 站点达到同时呼叫的限制，可以添加另一个 PSTN 站点来处理负载。

多个 PSTN 站点还允许您提供与离您的用户最近的网关的连接。 例如，假设你在西雅图和阿姆斯特丹有 PSTN 网关。 你可以部署两个 PSTN 站点（一个位于西雅图，一个位于阿姆斯特丹）并分配用户使用最靠近他们的 PSTN 网站。 西雅图的用户将被路由到西雅图 PSTN 站点和网关，而阿姆斯特丹的用户将路由到阿姆斯特丹的 PSTN 站点和网关：

![2 个 PSTN 站点内的云连接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>部署要求
<a name="BKMK_Requirements"> </a>

部署云连接器版本之前，请确保你的环境具有以下各项：

- **对于主机 -** 云连接器 VM 必须部署在运行 Windows Server 2012 R2 Datacenter 版本 (English) 并且启用了 Hyper-V 角色的专用硬件上。

    对于版本 2.0 及更高版本，绑定到 Skype for Business Corpnet 交换机的主机计算机网卡必须在与云连接器企业网络计算机相同的子网中配置 IP 地址。

- 对于版本 2.1 和更高版本，主机设备必须.NET Framework 4.6.1 或更高版本。

- **对于虚拟机 -** A Windows Server 2012 R2 ISO (English) image (.iso) . ISO 将转换为运行 Skype for Business 云连接器版本的虚拟机的 VHD。

- 支持为部署中每个云连接器版本安装 4 个 VM 的必要硬件。 建议使用以下配置：

  - 64 位双处理器、六核 (12 实) 、2.50 GHz (GHz) 或更高

  - 64 GB (GB) ECC RAM

  - 四个 600 GB (或) 10K RPM 128M 缓存 SAS 6Gbps 磁盘，在 RAID 5 配置中配置

  - 三个 1 Gbps RJ45 高吞吐量网络适配器

- 如果选择部署支持最多 50 个并发呼叫的云连接器版本的较小版本，则需要以下硬件：

  - Intel i7 4790 四核和 Intel 4600 图形 (无需使用高端) 

  - 32 GB 版第 3 版、1600 级非 ECC

  - 2：RAID 0 中的 1TB 7200RPM SATA III (6 Gbps) 0

  - 2：1 Gbps 以太网 (RJ45) 

- 如果在主机上需要代理服务器才能浏览 Internet，则必须进行以下配置更改：

  - 若要绕过代理，请指定使用代理服务器设置的 WinHTTP 代理设置和包含"192.168.213"的绕过 \* 列表。云连接器管理服务和 Skype for Business Corpnet 子网使用的网络，如你的 CloudConnector.ini 文件中定义。 否则，管理连接将失败，并阻止部署和自动恢复云连接器。 下面是一个示例 winhttp 配置命令：netsh winhttp set proxy "10.10.10.175：8080" bypass-list=" \* .local;1. \*172.20. \* ;192.168.218. \* ' \<local\> "。

  - 指定每台计算机而不是每个用户的代理设置。 否则云连接器下载将失败。 可以使用注册表更改或组策略设置指定每台计算机的代理设置，如下所示：

  - **注册表：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings]** ProxySettingsPerUser dword：00000000

  - **组策略：** 计算机 \> 管理模板 \> Windows \> 组件Internet Explorer：按计算机而不是 (用户设置代理) 

- 建议至少使用两个网关 (合格的 PBX/中继或合格的 SBC/网关) 。

    云连接器支持与经 Skype for Business (认证的) SDC 相同的会话边界控制器。 有关详细信息，请参阅[Telephony Infrastructure for Skype for Business。](../../../SfbPartnerCertification/certification/infra-gateways.md)

- 具有在主机服务器上安装和配置 Hyper-V权限的本地服务器管理员帐户。 该帐户必须在安装和配置帐户的本地服务器上Hyper-V管理员权限。

- 在部署过程中，将要求您创建一个域管理员帐户，该帐户具有在云连接器域中创建和发布拓扑的权限。

- 外部 DNS 记录，在安装CloudConnector.ini中包含的外部 DNS 文件中定义：

  - 边缘组件的访问边缘服务的外部 DNS 记录;例如，ap. \<Domain Name\> 。 每个 PSTN 站点需要一条记录。 此记录必须包含该站点的所有边缘的 IP 地址。

- 创建了所有必需的 DNS 和 SRV 记录的 Microsoft 365 或 Office 365 组织。

    > [!IMPORTANT]
    > 将租户与云连接器版本集成时，不支持将默认域后缀 .onmicrosoft.com 用作组织的 SIP 域。 >不能使用 sip。\<Domain Name\> 作为云连接器边缘访问代理接口的名称，因为此 DNS 记录由 Microsoft 365 和 Office 365 使用。

- 从 CA 公共证书颁发机构获取的外部边缘 (证书) 。

- 允许通过所需端口通信的防火墙规则已完成。

- 主机和 VM 的 Internet 连接。 云连接器从 Internet 下载一些软件;因此，必须提供网关和 DNS 服务器信息，以便云连接器主机计算机和 VM 可以连接到 Internet 并下载必要的软件。

- 安装在主机上的租户远程 PowerShell 模块。

- 用于运行远程 PowerShell 的 Skype for Business 管理员凭据。

    > [!IMPORTANT]
    > 管理员帐户不得启用多重身份验证。

> [!NOTE]
> 云连接器部署仅在 Microsoft Hyper-V平台上受支持。 其他平台（如 VMware 和 Amazon Web Services）不受支持。

> [!NOTE]
> 运行云连接器的最低硬件指南基于基本硬件容量 (内核、MHz、千兆字节等) 以及一些缓冲区，以适应任何计算机的体系结构中隐藏着无形的性能障碍。 Microsoft 对商业上提供的硬件运行最差情况负载测试，满足最低指导要求。 已验证媒体质量和系统性能。 Microsoft 的官方云连接器设备合作伙伴具有特定的云连接器硬件实施，他们已针对这些硬件实现独立测试性能，并且其硬件适合满足负载和质量要求。

> [!NOTE]
> AudioCodes 和 Sonus 生成的设备已修改代码，并运行在 Windows Server Standard 版本的服务器上。 这些设备受支持。

## <a name="information-you-need-to-gather-before-deployment"></a>部署之前需要收集的信息
<a name="BKMK_PlanDeployment"> </a>

开始部署之前，需要确定部署的大小、要服务的 SIP 域以及计划部署的每个 PSTN 站点的配置信息。 首先，您将：

- 根据公司中使用的 SIP URI 确定此部署将服务的所有 SIP 域。

- 确定需要部署的 PSTN 站点数。

- 确保你拥有支持要针对每个云连接器版本安装的四个 VM 所需的硬件。

对于您计划部署的每个 PSTN 站点，您需要：

- 为每个云连接器设备的所有组件创建 (请参阅确定 [部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)) 。

- 定义端口范围 ([端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)) 。

- Create external DNS records for the Edge component (see [Requirements for deployment) .](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- 确定边缘组件的证书要求 (请参阅 [证书要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)) 。

### <a name="ports-and-protocols"></a>端口和协议
<a name="BKMB_Ports"> </a>

定义媒体端口范围时，请注意以下事项：

- 客户端始终对媒体流量使用端口范围 50000 到 50019- 此范围在 Skype for Business Online 中预定义，无法更改。

- 默认情况下，中介组件将为媒体流量使用端口范围 49 152 到 57 500。 但是，连接是通过内部防火墙建立的，出于安全原因，可以在拓扑中限制此端口范围。 每个呼叫最多需要 4 个端口。 如果要限制中介组件和 PSTN 网关之间的端口数，则还需要在网关上配置相应的端口范围。

- 必须在外围网络中部署云连接器。 这意味着你将有两个防火墙：

  - 第一个防火墙是 Internet 和外围网络之间的外部防火墙。

  - 第二个防火墙位于外围网络和内部网络之间。

    客户端可以在 Internet 或内部网络中：

  - Internet 中的客户端通过边缘组件通过外部防火墙连接到 PSTN。

  - 内部网络的客户端将通过内部防火墙连接到外围网络中中介组件，这将将流量连接到 SBC 或 PSTN 网关。

    这意味着您需要在两个防火墙中打开端口。

下表介绍了外部和内部防火墙的端口和端口范围。

此表显示了用于启用内部网络和中介组件中的客户端之间的通信的端口和端口范围：

**内部防火墙**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |任何  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |任何  <br/> |TCP 5068/ TLS 5067  <br/> |
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |UDP 49 152 - 57 500  <br/> |任意\*\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |任意\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50，000-50，019  <br/> （可选）  <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50，000-50，019  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |TCP 50，000-50，019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |UDP 50，000-50，019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* 这是中介组件上的默认端口范围。 为获得最佳呼叫流，每个呼叫需要四个端口。

\*\* 必须在 SBC/PSTN 网关上配置此端口;5060 就是一个示例。 可以在 SBC/PSTN 网关上配置其他端口。

\*\*\* 请注意，如果 SBC/网关制造商允许，您还可以限制 SBC/Gateway 上的端口范围。

出于安全目的，可以使用 [Set-CsMediationServer](/powershell/module/skype/set-csmediationserver?view=skype-ps) cmdlet 限制中介组件的端口范围。

例如，以下命令将中介组件用于媒体流量的端口数限制为 50 000 - 51 000（用于音频 (和) ）。 中介组件将能够通过此配置处理 250 个并发呼叫。 请注意，您可能还需要在 SBC/PSTN 网关上限制此范围：

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

若要检索中介组件的名称并查看默认端口，可以使用 [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps) cmdlet，如下所示：

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表显示了用于启用云连接器边缘组件与外部防火墙之间的通信的端口和端口范围。 此表显示了最低建议。

在这种情况下，到 Internet 的所有媒体流量都将通过联机边缘流动，如下所示：用户结束点-- 联机边缘 \> -- \> 云连接器边缘：

**外部防火墙 - 最低配置**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |TCP 50，000-59，999  <br/> |TCP 443  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |TCP 50，000-59，999  <br/> |TCP 443  <br/> |

下表显示了用于启用云连接器边缘组件与外部防火墙之间的通信的端口和端口范围。 此表显示了建议的解决方案。

在这种情况下，Internet 中终点的所有媒体流量都可以直接流向云连接器边缘组件。 媒体路径将为用户结束点 - \> 云连接器边缘。

> [!NOTE]
> 如果用户终点位于对称 NAT 后面，此解决方案将不起作用。

**外部防火墙 - 建议的配置**


|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |TCP 50，000-59，999  <br/> |任何  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478;UDP 50，000-59，999  <br/> |任何  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP 443;TCP 50，000-59，999  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478;UDP 50，000 - 59，999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>主机 Internet 连接要求
<a name="BKMB_Ports"> </a>

主机必须能够访问外部资源才能成功安装、更新和管理云连接器。 下表显示了主机计算机和外部资源之间所需的目标及端口。

|Direction  <br/> |源 IP  <br/> |目标 IP  <br/> |源端口  <br/> |目标端口  <br/> |协议  <br/> |用途  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|出站  <br/> |云连接器主机 IP  <br/> |任意  <br/> |任意  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|出站  <br/> |云连接器主机 IP  <br/> |任意  <br/> |任意  <br/> |80, 443  <br/> |TCP  <br/> |CRL (证书吊销)   <br/> |
|出站  <br/> |云连接器主机 IP  <br/> |任意  <br/> |任意  <br/> |80, 443  <br/> |TCP  <br/> |云连接器更新  <br/> Skype for Business Online  <br/> 管理 PowerShell  <br/> Windows 更新  <br/> |

如果需要更严格的规则，请参阅以下允许列表 URL：

- [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) [URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)和 IP 地址范围中的证书吊销列表 URL

- Windows 更新 [：如何为软件更新配置防火墙](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Online 管理员 \* PowerShell：.online.lync.com

    如果需要对此目标进行代理排除，则需要将其添加到 WinHTTP 绕过列表。

- 云连接器更新： [下载中心](https://aka.ms/CloudConnectorInstaller)、 [https://go.microsoft.com](https://go.microsoft.com) 和 [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>边缘组件的 DNS 名称解析
<a name="BKMB_Ports"> </a>

边缘组件需要解析 Microsoft 365 或 Office 365 服务的外部名称以及其他云连接器组件的内部名称。

每个边缘组件都是一台具有面向外部和内部的接口的多主计算机。 云连接器在外围网络内的域控制器组件上部署 DNS 服务器。 可以将边缘服务器指向外围的 DNS 服务器，以实现所有名称解析，但需要启用云连接器 DNS 服务器来解析外部名称，只需为引用名称查找的其他公共 DNS 服务器的外部查询设置包含一个或多个 DNS A 记录的 DNS 区域。

在 .ini 文件中，如果为来自 SIP 域的相同域空间的网关设置 FQDN 名称，将在外围 DNS 服务器中创建此 SIP 域的权威区域。 如果边缘服务器指向此 DNS 服务器来解析名称，边缘永远不会解析_sipfederationtls。\<yourdomain\> DNS 记录，呼叫流需要此记录。 在这种情况下，Microsoft 建议您在边缘外部接口上提供 DNS 服务器来解析 Internet 名称查找，并且每个边缘组件必须使用 HOST 文件将其他云连接器组件名称解析为 IP 地址。

> [!NOTE]
> 出于安全考虑，建议不要将云连接器 DNS 服务器指向生产域中的内部服务器进行名称解析。

### <a name="determine-deployment-parameters"></a>确定部署参数
<a name="BKMK_SiteParams"> </a>

首先，需要定义以下常见部署参数：


|**项目**|**说明**|**注释**|
|:-----|:-----|:-----|
|SIP 域  <br/> |公司用户使用的 SIP URI。 提供此部署将服务的所有 SIP 域。 可以具有多个 SIP 域。  <br/> ||
|PSTN 站点数  <br/> |要部署的 PSTN 站点数。  <br/> ||

对于您计划部署的每个 PSTN 站点，在开始部署之前，您需要收集以下信息。 更新更新文件时，需要CloudConnector.ini此信息。

配置网关信息时，请记住以下事项：

- 如果只有一个网关，请删除第二个网关的 .ini 文件部分。 如果网关超过两个，请按照现有格式添加新网关。

- 请确保网关的 IP 地址和端口 (正确的) 地址。

- 要支持 PSTN 网关级别 HA，请保留辅助网关或添加其他网关。

 (可选) 要限制出站呼叫号码，请更新 LocalRoute 值。



|**网站参数**|**说明**|**注释**|
|:-----|:-----|:-----|
|虚拟机域名  <br/> |云连接器内部组件的域名。 此域必须与生产域不同。 名称在所有云连接器设备中必须相同。  <br/> .ini 文件中的名称："VirtualMachineDomain"  <br/> |首选 .local 域。  <br/> |
|云连接器域控制器名称  <br/> |域控制器的名称。  <br/> .ini 文件中的名称："ServerName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|云连接器域控制器 IP/子网掩码  <br/> |域控制器的 IP 地址。  <br/> .ini 文件中的名称："IP"  <br/> ||
|Microsoft 365 或 Office 365 Online 服务 FQDN  <br/> |在大多数情况下，必须是全球 Microsoft 365 或 Office 365 实例的默认值。  <br/> .ini 文件中的名称："OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business 站点名称;例如，西雅图。  <br/> .ini 文件中的名称："SiteName"  <br/> 对于版本 1.4.1 及更高版本，每个站点的网站名称必须不同，并且名称必须与 MICROSOFT 365 或 Office 365 中定义的 PSTN 站点（如果存在）匹配。 请注意，在站点中注册第一个设备时，会自动创建 PSTN 站点。  <br/> ||
|HardwareType  <br/> 版本 1.4.1 及更高版本  <br/> |硬件类型。 默认值为 Normal。 还可以设置为"最小"。  <br/> ||
|Country Code  <br/> |拨号的国家/地区代码。  <br/> .ini 文件中的名称："CountryCode"  <br/> ||
|市/县  <br/> |城市 (可选) 。  <br/> .ini 文件中的名称："City"  <br/> ||
|状态  <br/> |状态 (可选) 。  <br/> .ini 文件中的名称："State"  <br/> ||
|基本 VM IP 地址  <br/> |将用于创建所有云连接器虚拟机的 VHDX 的临时基本虚拟机的 IP 地址。 此 IP 必须在同一步中定义的外围企业网络子网中，并且需要 Internet 访问。 请务必定义公司默认网关和可路由到 Internet 的 DNS。  <br/> .ini 文件中的名称："BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 版本 1.4.1 及更高版本  <br/> |WSUS (Windows Server Update Services) 一台用于托管来自 Microsoft 更新的更新的 Intranet 服务器。  <br/> 如果不需要 WSUS，可以保留为空。  <br/> ||
|内部网络的子网掩码  <br/> |云连接器为云连接器组件之间的内部通信配置 IP 网络。 边缘还必须连接到允许 Internet 连接的另一子网。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"CorpnetIPPrefixLength"  <br/> ||
|外部网络的子网掩码  <br/> |对于边缘组件的外部网络。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"InternetIPPrefix"  <br/> ||
|内部网络的交换机名称  <br/> |将用于内部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用默认的建议值。  <br/> .ini 文件中的名称："VM 网络池的参数"下的"CorpnetSwitchName"  <br/> ||
|外部网络的交换机名称  <br/> |将用于外部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用默认的建议值。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"InternetSwitchName"  <br/> ||
|内部网络的默认网关  <br/> |此网关必须提供对 Internet (还需要设置 DNS 服务器) ，并且将在云连接器组件的内部接口上配置。  <br/> .ini 文件中的名称："VM 网络池的参数"下的"CorpnetDefaultGateway"  <br/> ||
|边缘组件外部接口的默认网关  <br/> |将在边缘组件的外部接口上配置。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"InternetDefaultGateway"  <br/> ||
|内部网络的 DNS 服务器  <br/> |将在临时 VM 的内部接口上配置。 必须为 Internet 名称提供名称解析。 如果不提供 DNS 服务器，Internet 连接将失败，部署将无法完成。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"CorpnetDNSIPAddress"  <br/> ||
|边缘组件的外部接口的 DNS 服务器  <br/> |将在边缘的外部接口上配置。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"InternetDNSIPAddress"  <br/> ||
|管理交换机名称  <br/> |管理交换机是一个将自动创建的临时交换机，它将用于在部署期间配置云连接器。 部署后，它将自动断开连接。 它必须是不同于云连接器中使用的任何其他网络的子网。  <br/> 在大多数情况下，可以使用默认的建议值。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"ManagementSwitchName"  <br/> ||
|管理子网地址/子网掩码  <br/> |管理子网是一个将自动创建的临时子网，用于在部署期间配置云连接器。 部署后将自动删除它。 它必须是不同于云连接器中使用的任何其他网络的子网。  <br/> .ini 文件中的名称："虚拟机网络池的参数"下的"ManagementIPPrefix"和"ManagementIPPrefixLength"  <br/> ||
|中央管理存储 (CMS) 计算机  <br/> |用于中央管理存储的单个 FQDN (CMS) 。 AD 域名将用于生成 FQDN。  <br/> .ini 文件中的名称："Primary Central Management Service 的参数"下的"ServerName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/>  (CMS 池名称 = 服务器)   <br/> |
|CMS 计算机 IP 地址  <br/> |外围网络中内部 CMS (的 IP) 。  <br/> INI 文件中的名称："主中央管理服务的参数"下的"IP"  <br/> ||
|文件共享名称  <br/> |在 CMS 服务器上为 Skype for Business 复制数据创建的文件共享 (例如，CmsFileStore) 。  <br/> 在大多数情况下，可以使用默认的建议值。  <br/> .ini 文件中的名称："主中央管理服务的参数"下的"CmsFileStore"  <br/> ||
|中介组件池名称  <br/> |中介组件的池名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .ini 文件中的名称："中介服务器池的参数"下的"PoolName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|中介组件名称  <br/> |中介组件 1 的组件名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .ini 文件中的名称："中介服务器池的参数"下的"ServerName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|中介组件计算机 IP 地址  <br/> |中介组件的内部企业网络 IP (外围网络内部) 。  <br/> .ini 文件中的名称："中介服务器池的参数"下的"IP"  <br/> ||
|边缘池内部名称  <br/> |边缘组件的池名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"InternalPoolName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|边缘服务器内部名称  <br/> |边缘组件的组件名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"InternalServerName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|边缘服务器内部 IP  <br/> |用于与云连接器的其他组件通信的边缘组件的内部外围网络 IP。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"InternalServerIPs"  <br/> ||
|访问池外部名称  <br/> |访问边缘的名称;例如，AP。 此名称必须与为 SSL 证书提供的名称匹配。 仅输入 Netbios 名称。 SIP 域名将用于生成 FQDN。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点都需要一个边缘访问池。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"ExternalSIPPoolName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> 保留"sip"，因此不能用作名称。  <br/> 生成的 FQDN 名称必须与为 SSL 证书提供的名称相匹配。  <br/> |
|访问边缘的外部 IP  <br/> |边缘组件的外部 IP - 如果没有可用的 NAT，则公用 IP，或转换的 IP (映射后，请同时指定两个) 。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"ExternalSIPIPs"  <br/> ||
|媒体中继名称  <br/> |音频视频媒体中继边缘的名称;例如 MR。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点需要一个边缘媒体中继池。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"ExternalMRFQDNPoolName"  <br/> |必须是 15 个字符或更少。 仅输入 Netbios 名称。  <br/> |
|媒体中继边缘的外部 IP  <br/> |目前仅支持一个 IP，因此这将是与访问边缘相同的 IP，可以是公用 IP 或映射的 IP (请指定两个地址（如果映射) ）。 可以是与访问边缘的边缘组件外部 IP 相同的地址。 请注意，如果 Edge 位于 NAT 后面，则还需要为下一个参数指定值。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"ExternalMRIPs"  <br/> ||
|如果边缘位于 NAT (，则媒体中继边缘的外部 IP)   <br/> |如果你的边缘位于 NAT 后面，你还需要指定 NAT 设备的公用地址。  <br/> .ini 文件中的名称："边缘服务器池的参数"下的"ExternalMRPublicIPs"  <br/> ||
|语音网关 1 制造和型号  <br/> |指定 SBC/语音网关的型号和型号。 请注意，你可以从 位于 的已测试设备列表中连接设备或 SIP 中继 [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) 。  <br/> ||
|语音网关 2 make and Model (copy this row if you have more than 2 gateways)   <br/> |指定语音网关的型号和型号。 请注意，你可以从 位于 的已测试设备列表中连接设备 [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) 。  <br/> ||
|语音网关 1 名称  <br/> |用于使用 AD 域生成计算机 FQDN。 如果在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不计划使用 FQDN（例如，TLS 不是必需的，或者语音网关不支持使用 FQDN 或仅 IP (IP) ，请指定。  <br/> ||
|语音网关 2 (网关数超过 2 时复制此行)   <br/> |用于使用 AD 域生成计算机 FQDN。 如果在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不计划使用 FQDN（例如，TLS 不是必需的，或者语音网关不支持使用 FQDN 或仅 IP (IP) ，请指定。  <br/> ||
|语音网关 1 IP 地址  <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关 2 IP 地址 (网关数超过 2 个时复制此)   <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关 1 端口 # (如果网关数超过 2 个，请复制)   <br/> |语音网关 SIP 中继将侦听的端口，例如 5060。  <br/> ||
|语音网关 2 端口#  <br/> |语音网关 SIP 中继将侦听的端口，例如 5060。  <br/> ||
|SIP 流量的语音网关 1 协议  <br/> |TCP 或 TLS。  <br/> ||
|SIP 流量的语音网关 2 协议 (如果网关数超过 2 个，请复制)   <br/> |TCP 或 TLS。  <br/> ||
|与边缘组件之间的流量的外部媒体端口范围  <br/> |与边缘的外部接口之间传输的媒体流量的 TCP/UDP 端口范围。 必须始终从 50 000 开始。 有关详细信息，请参阅"端口和协议"。  <br/> |50000 - 59 999  <br/> |
|通过内部防火墙与中介组件通信的媒体端口范围  <br/> |中介组件用于与客户端和网关通信的 UDP 端口范围 (每个呼叫路由建议 4 个) 。  <br/> ||
|通过内部防火墙与 Skype for Business 客户端进行通信的媒体端口范围  <br/> |出于规划目的，无法更改。 需要在内部防火墙中打开端口，以在内部网络内的 Skype for Business 客户端和中介组件之间进行通信。  <br/> |50 000- 50 019  <br/> |
|公共证书密码  <br/> |必须在脚本中提供。  <br/> ||
|安全模式管理员密码  <br/> 仅版本 1.4.2  <br/> |内部抄送域的安全模式管理员密码。  <br/> ||
|云连接器域管理员密码  <br/> 仅版本 1.4.2  <br/> |云连接器域管理员密码 (不同于生产域) 。 用户名为管理员。 无法更改用户名。  <br/> ||
|虚拟机管理员密码  <br/> 仅版本 1.4.2  <br/> |用于在部署期间配置管理网络。  <br/> 用户名为管理员。 无法更改用户名。  <br/> ||
|CABackupFile  <br/> 版本 2.0 及更高版本  <br/> |用于在云连接器站点中部署多个设备时将证书颁发机构服务从 Active Directory 服务器保存为文件。 确保对一个云连接器站点内的所有设备使用相同的密码，以便成功将 CA 备份文件导入新添加的设备。  <br/> ||
|CCEService  <br/> 版本 2.0 及更高版本  <br/> |用于云连接器管理服务;需要访问云连接器站点目录。 请确保对一个云连接器站点内的所有设备使用相同的密码。  <br/> ||
|Microsoft 365 或 Office 365 租户管理员  <br/> | 云连接器使用该帐户更新和管理云连接器的租户设置： <br/>  版本 2.0 及更高版本：具有 Skype for Business 管理员权限的专用 Microsoft 365 或 Office 365 帐户的凭据。 <br/>  2.0 以前的版本：具有全局租户管理员权限的专用 Microsoft 365 或 Office 365 帐户的凭据。 <br/> ||
|启用 REFER 支持  <br/> |这将定义在 IP/PBX 的中继配置上是启用还是禁用 SIP REFER 支持。 默认值为 True。 如果 IP/PBX 网关支持 REFER 支持，请保留为 True。 如果没有，需要将此值更改为 False。 如果不确定网关是否支持 REFER，请参阅 Qualified [IP-PBXs and Gateways](../../../SfbPartnerCertification/certification/infra-gateways.md)。   <br/> ||
|EnableFastFailoverTimer  <br/> 版本 2.0 及更高版本  <br/> |如果网关在 10 秒钟内未应答出站呼叫，则这些出站呼叫将路由到下一个可用网关;如果没有其他中继，则会自动放弃呼叫。  <br/> 但是，在网络和网关响应较慢的组织中，或者建立呼叫的过程需要 10 秒以上的时间时，这可能会导致不必要地丢弃呼叫。  <br/> 呼叫其他国家/地区（例如，阿拉伯联合酋长国或巴基斯坦）时，呼叫建立过程可能需要 10 秒以上。 如果遇到类似问题，则需要将该值更改为 False。 不要忘记更改连接的 SBC 或网关上的相应设置。  <br/> 该值可以是 True 或 False。 默认值为 True。  <br/> ||
|ForwardCallHistory  <br/> 版本 2.0 及更高版本  <br/> | 此参数用于打开用于报告同时响铃、呼叫转接和呼叫转移方案中的初始呼叫者的 SIP 标头。 将参数设置为 True 将打开两个 SIP 标头： <br/>  History-Info <br/>  Referred-By <br/>  History-Info 标头用于重新定向 SIP 请求和"为 () 提供用于捕获请求历史记录信息的标准机制，以便为网络和最终用户启用各种服务" ([RFC 4244 - 第 1.1](http://www.ietf.org/rfc/rfc4244.txt)) 节。 对于云连接器中继接口，这用于模拟和呼叫转发方案。  <br/>  该值可以是 True 或 False。 默认值为 False。 <br/> ||
|转发 PAI  <br/> 版本 2.0 及更高版本  <br/> |PAI 是 SIP 的专用扩展，使 SIP 服务器能够断言经过身份验证的用户的身份。 对于 SIP 中继提供商，如果不存在 History-Info 和 Referred-By，PAI 可用于计费目的。 在配置中启用 Forward P-Asserted-Identity 时，中介服务器将具有 SIP Tel URI 的 PAI 标头从云连接器转发到 &amp; SIP 中继。 中介服务器将仅在 SIP 中继上收到的具有 tel URI E.164 号码的 PAI 头转发 &amp; 到云连接器。 中介服务器还将转发在任一方向上接收的任何隐私标头。 如果中介服务器发送的 SIP 请求包含格式为"Privacy： id"的隐私标头与 PAI 标头，则断言的标识应在网络信任域外部保持私有。  <br/> 该值可以是 True 或 False。 默认值为 False。  <br/> ||

### <a name="certificate-requirements"></a>证书要求
<a name="BKMK_Certs"> </a>

每个边缘组件都需要来自公共证书颁发机构的证书。 证书必须具有可导出的私钥，以在边缘组件之间复制。 若要满足证书要求，您需要在下列选项之间做出决定，并为证书提供主题名称 (SN) 和主题备用名称 (SAN) 。

 **如果您具有单个 SIP 域：**

- **选项 1.** 主题名称必须包含分配给边缘组件的池名称。 请注意，无法将主题名称 sip.sipdomain.com，因为此名称保留用于联机 Skype for Business 边缘组件。 SAN 必须包含 sip.sipdomain.com 和访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **选项 2.** 如果要在部署的所有边缘池服务器上使用单个通配符证书，可以使用 .sipdomain.com 通配符 SAN 条目，而不是证书中的边缘 \* 池名称。 主题名称可以是已部署的任何边缘池的访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> 不得为 sip 创建外部 DNS 条目 \<sipdomain\> 。com，因为此名称属于 Microsoft 365 或 Office 365 部署。

> [!NOTE]
> 如果要对组织中部署的所有边缘池使用单个证书，但无法使用选项 2 中定义的通配符证书，则需要在证书的 SAN 名称中包括所有部署的边缘池的 FQDN。

 **如果您有多个 SIP 域：**

您需要添加每个 SIP 域 sip.sipdomain.com 每个 SIP 域的访问边缘池的名称 (该池可以是一个物理池，但名称) 。 下面是多个 sip 域方案中的 SN 和 SAN 条目的示例：

- **选项 1.** 主题名称必须包含为边缘组件分配的池名称。 请注意，无法将主题名称 sip.sipdomain.com，因为此名称保留用于联机 Skype for Business 边缘组件。 SAN 必须包含 sip.sipdomain.com 和访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>选项 2.</strong>如果要在部署的所有边缘池服务器上使用单个通配符证书，可以使用 .sipdomain.com 通配符 SAN 条目，而不是证书中的边缘 \* 池名称。 主题名称可以是已部署的任何边缘池的访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> 不得为 sip 创建外部 DNS 条目 \<sipdomain\> 。com，因为此名称属于 Microsoft 365 或 Office 365 部署。

出于部署目的，可以使用下表：

|**选项**|**说明**|**注释**|
|:-----|:-----|:-----|
|您将使用哪个选项进行部署？  <br/> |选项 1 或 2  <br/> ||
|SN  <br/> |为证书提供 SN  <br/> ||
|SAN  <br/> |为证书提供 SAN  <br/> ||

如果在网关和中介服务器之间使用 TLS，则需要获取分配给网关的证书的根证书或完整证书链。

## <a name="dial-plan-considerations"></a>拨号计划注意事项
<a name="BKMK_DailPlan"> </a>

云连接器需要使用联机拨号计划。 若要详细了解如何配置在线拨号计划，请参阅 [什么是拨号计划？](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>高可用性注意事项
<a name="BKMK_HA"> </a>

部署云连接器版本实现高可用性时，你至少部署两个设备来充当彼此的备份。 每个设备由四个组件组成：边缘、中介、中央管理存储 (CMS) 和域控制器。

通常，如果设备中的一个组件关闭，云连接器版本可以继续处理呼叫，但必须考虑以下事项：

- **中介、CMS 和域控制器组件注意事项**

    假定一个设备中的 CMS 或域控制器组件关闭。 该设备仍可处理入站和出站呼叫，但如果在域控制器或 CMS 组件不可访问时重新启动中介组件，则中介将不起作用。 这同样适用于域控制器关闭时重新启动 CMS 组件。

    **建议：** 重新启动组件之前，请检查设备中其他组件的可用性。

- **边缘组件注意事项**

    如果一个设备中的边缘组件不可用，入站和出站呼叫的行为将有所不同，如下所示：

  - **出站** 呼叫 — 从 Internet 中的用户到 PSTN 网络的呼叫。

    云中的呼叫分发机制将确定一个边缘组件已关闭，并且将所有呼叫路由到另一个设备，以便出站呼叫成功。

  - **入站** 呼叫 — 从 PSTN 网络向本地网络或 Internet 中的用户发送的呼叫。

     如果接收呼叫的设备的边缘组件未正常工作，则此设备的入站呼叫将不会成功，因为中介组件无法将呼叫重定向到其他设备中的边缘组件。

    **建议：** 具有一个监视系统。 确定边缘组件故障后，关闭设备中边缘组件不可用的所有组件。

## <a name="cloud-connector-media-flow"></a>云连接器媒体流
<a name="BKMK_MediaFlow"> </a>

下图概述了通过云连接器版本的出站和入站呼叫流。 这是一些有用的信息，有助于了解如何建立连接。

第一个图表中，内部用户拨打出站呼叫，如下所示：

1. Dave 是一名在线用户，但现在在内部网络中，他向外部 PSTN 用户呼叫。

2. SIP 流量路由到 Skype for Business Online。

3. Skype for Business Online 对号码执行反向号码查找。 反向号码查找失败，因为此号码不属于 Skype for Business 组织的任何人员。

4. 呼叫首先通过联机边缘 (SIP 和媒体流的边缘组件;媒体将转到中介组件，通过内部防火墙) 。

5. 如果路由存在，边缘组件将流量中继到外围网络中中介组件。

6. 中介组件将流量发送到 PSTN 网关。

![云连接器的出站媒体流](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

在下图中，内部用户接收入站呼叫，如下所示：

1. PSTN 网关接收用户 Dave 的呼叫，该用户在线工作，但现在位于内部网络中。

2. SIP 流量将路由到中介组件。

3. 中介组件将 SIP 流量发送到边缘组件，然后发送到 Skype for Business Online。

4. Skype for Business Online 对号码执行反向号码查找，并发现这是用户 Dave。

5. SIP 信号转到 Dave 的所有状态点。

6. 将在网关和中介组件之间以及中介组件和结束点之间建立媒体流量。

![云连接器的入站媒体流](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>监控和疑难解答
<a name="BKMK_Monitor"> </a>

监控和疑难解答机制随每个云连接器设备自动安装。 该机制将检测以下事件：

- 云连接器设备的一个或多个虚拟机未连接到内部或 Internet 虚拟交换机。

- 云连接器设备的一个或多个虚拟机已保存或已停止状态。

- 未运行的服务。

  如果检测到以下事件之一，整个云连接器设备将排出并标记为脱机，以防止尝试建立对故障设备的呼叫。 云连接器自动恢复功能随后将还原服务，将设备标记为联机。 如果由于某种原因自动恢复失败，请参阅 [云连接器部署疑难解答](troubleshoot-your-cloud-connector-deployment.md)。

  - 在中央管理存储虚拟机上：

     - Skype for Business 主复制程序代理

     - Skype for Business 副本复制程序代理

  - 在中介服务器虚拟机上：

     - Skype for Business 副本复制程序代理

     - Skype for Business Server 中介

  - 在边缘服务器虚拟机上

     - Skype for Business 副本复制程序代理

     -  Skype for Business Server 访问边缘

     - Skype for Business Server 音频/视频边缘

     - Skype for Business Server 音频/视频身份验证

     - Skype for Business Server Web 会议边缘

- 边缘上的"CS RTCSRV"和中介服务器上"CS RTCMEDSRV"的 Windows 防火墙的入站规则处于禁用状态。

云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 。 有关详细信息，请参阅使用 Operations Management Suite ([OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_MoreInfo"> </a>

有关详细信息，请参阅：

- [Microsoft 电话解决方案](/microsoftteams/cloud-voice-landing-page)

- [配置和管理 Skype for Business 云连接器版本](configure-skype-for-business-cloud-connector-edition.md)

- [云连接器版本中的媒体旁路规划](plan-for-media-bypass-in-cloud-connector-edition.md)

- [在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)