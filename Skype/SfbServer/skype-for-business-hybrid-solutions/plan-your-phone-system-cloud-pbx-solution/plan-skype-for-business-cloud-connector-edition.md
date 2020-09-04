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
description: 查找有关 Skype for Business 云连接器版本的信息，这是一组打包的虚拟机，用于实现与电话系统 (云 PBX) 的本地 PSTN 连接 (Vm) 。
ms.openlocfilehash: ec96662e3dbe432ce8cebe7dc59004350124451e
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358988"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>规划 Skype for Business 云连接器版本

> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。

查找有关 Skype for Business 云连接器版本的信息，这是一组打包的虚拟机，用于实现与电话系统 (云 PBX) 的本地 PSTN 连接 (Vm) 。

如果尚不存在现有的 Lync Server 或 Skype for Business Server 部署，则云连接器版本可能是组织的合适解决方案。 如果你仍在调查哪个电话系统解决方案适合你的企业，请参阅 [Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)。

本文档介绍了云连接器版本要求和受支持的拓扑，并帮助您规划云连接器版本部署。 在配置云连接器环境之前，请务必阅读本主题。 当您准备好部署和配置云连接器版本时，请参阅 [configure and Manage Skype For Business Cloud Connector edition](configure-skype-for-business-cloud-connector-edition.md)。

云连接器版本2.1 现已推出。 如果您尚未升级到2.1，请参阅 [升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。 您可以在中找到安装文件 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。

> [!NOTE]
> Microsoft 在发布新版本后的60天内支持云连接器版本的早期版本。 Microsoft 将在2.1 发布后的60天内支持2.0.1 版，以允许你进行升级。 将不再支持2.0.1 之前的所有版本。

云连接器版本是一种混合产品，其中包含一组打包的虚拟机，这些虚拟机 (Vm) ，用于实现与电话系统的本地 PSTN 连接。 通过在虚拟化环境中部署最少的 Skype for Business Server 拓扑，组织中托管的用户可以从 Microsoft 云接收 PBX 服务，但 PSTN 连接是通过现有的内部部署语音基础结构提供的。

![显示将云 PBX 连接到 Skype for business 的本地部署的云 PBX 网关的拓扑图。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

由于云连接器允许您将电话系统服务与现有的电话环境（例如，PBX、模拟设备和呼叫中心）集成，因此您可以从现有电话解决方案到电话系统实施分阶段迁移。

例如，假设您的公司有一个具有电话系统不提供的特定功能的复杂呼叫中心。 您可以选择将呼叫中心用户与现有解决方案一起使用，但要将其他用户移动到电话系统。

云连接器将提供驻留在本地和联机用户之间的路由，你可以选择将自己的 PSTN 提供商与电话系统结合使用。

在规划云连接器版本部署时，请考虑以下事项：

- 若要使用云连接器利用云语音解决方案，你需要注册包含电话系统的 Microsoft 365 或 Office 365 组织。 如果你还没有 Microsoft 365 或 Office 365 组织，你可以了解如何在此处注册： [Microsoft 365 For Business](https://products.office.com/business/office)。 请注意，你需要注册包括 Skype for Business Online 的计划。

- 若要使用 Skype for Business Online 服务注册云连接器设备，并运行各种 cmdlet，云连接器2.0 及更高版本需要具有 Skype for Business 租户管理员权限的专用 Microsoft 365 或 Office 365 帐户。 2.0 之前的云连接器版本需要具有租户全局管理员权限的专用 Microsoft 365 或 Office 365 帐户。

- 云连接器不需要完整的本地 Skype for business Server 部署。

    目前，云连接器不能与 Lync 或 Skype for Business 本地服务器共存。 如果要将现有 Lync 或 Skype for Business 用户移至 Microsoft 365，并为用户持续提供本地电话，请考虑使用现有 Skype for Business Server 部署的使用本地连接的电话系统。 有关详细信息，请参阅在[Skype For Business Server 中使用本地 PSTN 连接](plan-phone-system-with-on-premises-pstn-connectivity.md)[规划电话系统 (云 PBX) 解决方案](plan-your-phone-system-cloud-pbx-solution.md)和规划电话系统。

- 如果您以前使用的是 Skype for Business 或 Lync Server 部署，并且您扩展了架构，则无需清理云连接器部署的架构，只要您从环境中删除了所有 Skype for Business 或 Lync Server 组件。

- 你的用户已联机托管。

- 如果您的组织已将目录同步配置 (DirSync) ，则必须先在本地部署中创建规划其混合语音的所有用户帐户，然后再将其同步到云。

- 如果需要，你可以保留当前的 PSTN 运营商。

- 如果要向托管在云连接器上的用户提供电话拨入式会议，则可以购买来自 Microsoft 的音频会议的 PSTN 会议许可证或付费产品。

- 音频会议许可证 (或按您提供的付费) 也是呼叫升级所必需的。 如果 Skype for Business 用户收到来自外部 PSTN 用户的呼叫，并且想要向该呼叫添加一个更多参与者 (将该呼叫升级到会议) ，将通过 Microsoft 音频会议服务执行升级。

- 云连接器2.0 及更高版本现在支持媒体旁路。 通过媒体旁路，客户端可以将媒体直接发送到公用电话交换网 (PSTN) 下一跃点（网关或会话边界控制器 (SBC) ），并从媒体路径中消除云连接器版本组件。 有关详细信息，请参阅 [在云连接器版本中规划媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。

- 云连接器2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅 [使用 Operations Management Suite 监视云连接器 (OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

- 云连接器在 Office 365 企业版 E5 可用的所有国家/地区可用。

本主题包含以下各部分：

- [云连接器版本组件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [云连接器版本拓扑](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [在部署之前需要收集的信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [拨号计划注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [云连接器媒体流](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [监控和疑难解答](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [详细信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>云连接器版本组件
<a name="BKMK_Components"> </a>

使用云连接器版本，可以部署一组包含最小 Skype for Business Server 拓扑的打包的虚拟机，这些拓扑由边缘组件、中介组件和中央管理存储 (CMS) 角色组成。 您还将安装域控制器，这是云连接器的内部正常运行所必需的。 这些服务配置为与包含 Skype for Business Online 服务的 Microsoft 365 或 Office 365 组织混合使用。

![云连接器版本组件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

云连接器组件提供以下功能：

- **边缘组件** -本地拓扑和联机服务之间的通信通过边缘组件进行，其中包括以下组件：

  - **访问边缘** -在本地部署和 Skype For business Online 之间提供 SIP 路由。

  - **媒体中继** -提供中介组件和其他媒体终结点之间的媒体路由。

  - **Media 中继 Authentication//mras** -生成用于访问媒体中继的令牌。

- **出站路由** -提供连接到云连接器设备的网关或 SBCs 之间语音流量的负载平衡。 呼叫将在连接到云连接器设备的所有网关或 SBCs 之间平均拆分。

    提供基于策略的网关路由。 仅支持基于目标 (出站) PSTN 号码的全局策略。

- **中央管理存储 (CMS) role** -包括拓扑组件的配置存储，其中包括 CMS 文件传输。

- **中央管理存储 (cms) 副本** -从 CMS 角色服务器上的全局 CMS 数据库同步配置信息。

- **域控制器** -云连接器 Active Directory 域服务，用于存储部署云连接器组件所需的所有全局设置和组。 将为每个云连接器设备创建一个林。 域控制器不能与生产 Active Directory 建立任何连接。 Active Directory 服务包括：

  - Active Directory 域服务

  - 用于颁发内部证书的 Active Directory 证书服务

- **中介组件** -在 Skype for BUSINESS 和 PSTN 网关之间实现 SIP 和媒体网关映射协议。 包括从全局 CMS 数据库同步配置的 CMS 副本。

## <a name="cloud-connector-edition-topologies"></a>云连接器版本拓扑
<a name="BKMK_Topologies"> </a>

出于此讨论的目的，我们将参考 PSTN 站点。 PSTN 站点是云连接器设备的组合，在同一位置部署，并与通用 PSTN 网关连接。 PSTN 网站允许您执行以下操作：

- 提供与最接近您的用户的网关的连接。

- 通过在一个或多个 PSTN 站点内部署多个云连接器设备来实现可伸缩性。

- 通过在单个 PSTN 站点内部署多个云连接器设备来实现高可用性。

本主题介绍 PSTN 站点。 有关规划 PSTN 网站的详细信息，请参阅 [Plan For Cloud Connector EDITION PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md)。

您可以部署以下云连接器拓扑：

- 每个 PSTN 站点的单个云连接器版本设备。 出于评估目的，建议使用此拓扑，因为它不提供高可用性。

- 每个 PSTN 站点多个云连接器版本设备，以提供高可用性。

- 具有多个云连接器版设备的多个 PSTN 站点，以提供高可用性的可伸缩性。 最大可部署200个网站。

在规划拓扑时，请考虑以下事项：

- 在云连接器2.0 及更高版本中，一个 PSTN 站点最多可以有16个云连接器设备。 早期版本支持每个站点最高4个设备。

- 有两种类型的硬件配置使用云连接器进行了测试：

  - 较大的版本能够处理大量并发呼叫，并且在所有类型的生产环境中都受支持。

  - 较小的版本用于在低端硬件上运行，可用于评估目的或较低呼叫量的站点。 如果部署较小版本的云连接器，您仍需要注意生产级硬件要求 (如双电源) 。

- 如果你有云连接器版本2.0 或更高版本，并且使用较大的硬件) 部署16台设备 (的最大配置，则 PSTN 站点可以处理多达8000个同时进行的呼叫。 如果部署较小版本，则支持的限制为800。

    您还需要将一些设备专用于高可用性。 最小建议是，应保留一个设备以实现高可用性。

  - 在第2版中，如果部署 15 + 1 配置，PSTN 站点可以处理多达7500个并发呼叫。

  - 如果您具有早期版本，并将最大 3 + 1 配置 (与更大的硬件) 一起部署，则您的 PSTN 站点可以处理多达1500个并发呼叫。 如果部署较小版本，则支持的限制为150。

-  如果每个 PSTN 站点需要进行更多的呼叫，您可以通过在同一位置部署其他 PSTN 站点来进行扩展。

> [!NOTE]
> 除非另行说明，否则下面的图表和示例假定使用较大版本的云连接器。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>单个 PSTN 站点内的单个云连接器设备

下图显示了单个 PSTN 站点内的单个云连接器版本设备。 请注意，云连接器包含在一台物理主机上安装的四个虚拟机，以实现安全目的。

![一个具有一个 PSTN 站点的云连接器](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>单个 PSTN 站点中的多个云连接器设备

 出于可伸缩性和高可用性的目的，可以选择在单个 PSTN 站点中拥有多个云连接器版本，如下图中所示。 请注意以下几点：

- 在一个池中的云连接器之间以随机顺序分发呼叫。

- 出于容量规划目的，您必须考虑在一个或多个云连接器离线时处理负载的能力，具体取决于以下计算：

  - **N + 1 个框。** 对于较大版本的云连接器，N + 1 框支持 500 \* N 个并发呼叫，可用性为99.8%。

    对于云连接器的较小版本，N + 1 框支持 50 \* N 个并发呼叫，可用性为99.8%。

  - **N + 2 个框。** 对于较大版本的云连接器，N + 2 框支持 500 \* N 个并发呼叫，可用性为99.9%。

    对于云连接器的较小版本，N + 2 框支持 50 \* N 个并发呼叫，可用性为99.9%。

![一个 PSTN 站点中的两个云连接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>每个站点有一个或多个云连接器的多个 PSTN 站点

您还可以选择在每个站点中有多个具有一个或多个云连接器版本的 PSTN 站点。 如果你的 PSTN 站点达到并发呼叫限制，你可以添加另一个 PSTN 站点来处理负载。

多个 PSTN 站点还允许你向离你的用户最近的网关提供连接。 例如，假设您在西雅图和阿姆斯特丹中有 PSTN 网关。 您可以部署两个 PSTN 站点（一个在西雅图，一个在阿姆斯特丹中），并将用户分配给用户使用离它们最近的 PSTN 站点。 来自西雅图的用户将被路由到西雅图 PSTN 网站和网关，而阿姆斯特丹中的用户将被路由到阿姆斯特丹 PSTN 网站和网关：

![2个 PSTN 站点内的云连接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>部署要求
<a name="BKMK_Requirements"> </a>

在部署云连接器版本之前，请确保您的环境具有以下各项：

- **对于主机-** 云连接器虚拟机必须部署在运行 Windows Server 2012 R2 Datacenter edition (英语) 且启用了 Hyper-v 角色的专用硬件上。

    对于版本2.0 及更高版本，绑定到 Skype for Business 公司网络交换机的主机计算机网卡必须在与云连接器公司网络计算机相同的子网中配置 IP 地址。

- 对于版本2.1 及更高版本，主机设备必须安装了 .NET Framework 4.6.1 或更高版本。

- **对于虚拟机-** Windows Server 2012 R2 ISO (英语) 映像 ( ISO) 。 ISO 将转换为将运行 Skype for Business 云连接器版本的虚拟机的 Vhd。

- 为部署中的每个云连接器版本支持安装4个虚拟机所需的硬件。 建议使用以下配置：

  - 64位双处理器、六核 (12 个实核) 、2.50 千兆 (GHz) 或更高版本

  - 64 gb (GB) ECC RAM

  - 4 600 GB (或更好) 10K RPM 128M 缓存 SAS 6Gbps 磁盘，在 RAID 5 配置中配置

  - 三个 1 Gbps RJ45 高吞吐量网络适配器

- 如果选择部署支持多达50同时呼叫的较小版本的云连接器版本，将需要以下硬件：

  - Intel i7 4790 四核处理器，带有英特尔4600图形 (无需高端显卡) 

  - 32 GB DDR3-1600 非 ECC

  - 2： 1TB 7200RPM SATA III (6 Gbps) 在 RAID 0 中

  - 2: 1 Gbps 以太网 (RJ45) 

- 如果用于浏览 Internet 的主机上需要代理服务器，则必须进行以下配置更改：

  - 若要绕过代理，请指定使用代理服务器设置的 WinHTTP 代理设置和包含 " \* 192.168.213" 的旁路列表。你的云连接器管理服务和 Skype for Business 网络网络子网使用的网络（如 CloudConnector.ini 文件中所定义）。 否则，管理连接将失败并阻止云连接器的部署和自动恢复。 下面是一个示例 winhttp 配置命令： netsh winhttp set proxy "10.10.10.175： 8080" 旁路-list = " \* local; 1. \* ;172.20. \* ; 192.168.218.。 \* ' \<local\> "。

  - 指定每台计算机的代理设置，而不是每个用户。 否则，云连接器下载将失败。 您可以使用注册表更改或组策略设置来指定每台计算机的代理设置，如下所示：

  - **注册表：** HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword：00000000

  - **组策略：** 计算机 \> 管理模板 \> Windows 组件 \> Internet Explorer：按计算机 (而不是按用户进行代理设置) 

- 合格的 PBX/中继或合格的 SBC/网关 () 建议至少使用两个网关。

    云连接器支持与为 Skype for business 认证 (的同一会话边界控制器 SBCs) 。 有关详细信息，请参阅 [Skype for business 的电话基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。

- 具有在主机服务器上安装和配置 Hyper-v 的权限的本地服务器管理员帐户。 该帐户必须具有在其中安装和配置 Hyper-v 的本地服务器上的管理员权限。

- 在部署过程中，系统将要求您创建一个具有在云连接器域中创建和发布拓扑的权限的域管理员帐户。

- 外部 DNS 记录，在安装程序包附带的 CloudConnector.ini 文件中定义：

  - 边缘组件的访问边缘服务的外部 DNS 记录;例如，"接入点 \<Domain Name\> ..."。 每个 PSTN 站点都需要一个记录。 此记录必须包含该网站所有边缘的 IP 地址。

- Microsoft 365 或 Office 365 组织，其中包含创建的所有必需的 DNS 和 SRV 记录。

    > [!IMPORTANT]
    > 当您将租户与云连接器版本集成时，不支持使用默认域后缀 onmicrosoft.com，作为组织的 SIP 域。 > 无法使用 sip。\<Domain Name\> 作为云连接器边缘访问代理接口的名称，因为此 DNS 记录由 Microsoft 365 和 Office 365 使用。

- 从公共证书颁发机构获取的外部边缘的证书 (CA) 。

- 允许通过所需端口的流量的防火墙规则已完成。

- 主机和虚拟机的 Internet 连接。 云连接器从 Internet 下载一些软件;因此，您必须提供网关和 DNS 服务器信息，以便云连接器主机和虚拟机可以连接到 Internet 并下载所需的软件。

- 在主机计算机上安装的租户远程 PowerShell 模块。

- 用于运行远程 PowerShell 的 Skype for Business 管理员凭据。

    > [!IMPORTANT]
    > 管理员帐户不能启用多重身份验证。

> [!NOTE]
> 云连接器部署仅在 Microsoft Hyper-v 虚拟化平台上受支持。 不支持其他平台（如 VMware 和 Amazon Web 服务）。

> [!NOTE]
> 运行云连接器的最低硬件指南基于基本硬件容量 (内核、MHz、千兆字节等) ，并提供了一些缓冲区以适应任何计算机的体系结构中的无形性能障碍。 Microsoft 已在商业可用硬件上运行最糟糕的事例负载测试，这是最低指导。 验证媒体质量和系统性能。 Microsoft 官方的云连接器设备合作伙伴具有特定的云连接器硬件实施，它们具有独立测试的性能，并且其硬件适用性符合负载和质量要求。

> [!NOTE]
> 由 AudioCodes 和 Sonus 生成的设备已修改代码并在 Windows Server Standard edition 服务器上运行。 支持这些设备。

## <a name="information-you-need-to-gather-before-deployment"></a>在部署之前需要收集的信息
<a name="BKMK_PlanDeployment"> </a>

在开始部署之前，您需要确定部署的大小、正在维护的 SIP 域以及计划部署的每个 PSTN 站点的配置信息。 首先，你将：

- 根据在贵公司中使用的 SIP Uri 确定此部署将提供的所有 SIP 域。

- 确定需要部署的 PSTN 网站数。

- 确保你具有支持为每个云连接器版本安装的四个虚拟机所必需的硬件。

对于计划部署的每个 PSTN 站点，需要执行以下操作：

- 为每个云连接器设备中的所有组件创建名称 (请参阅 [确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)) 。

- 定义端口范围 (参阅) 的 [端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) 。

- 为边缘组件创建外部 DNS 记录 (请参阅 [部署](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)) 的要求。

- 确定边缘组件的证书要求 (请参阅 [证书要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)) 。

### <a name="ports-and-protocols"></a>端口和协议
<a name="BKMB_Ports"> </a>

定义媒体端口范围时，请注意以下事项：

- 客户端始终使用端口范围为50000到50019的媒体流量—此范围是在 Skype for Business Online 中预定义的，不能更改。

- 默认情况下，中介组件将使用端口范围 49 152 到 57 500 进行媒体流量。 但是，连接是通过内部防火墙建立的，因此，出于安全考虑，您可以限制拓扑中的此端口范围。 每次呼叫最高需要4个端口。 如果要限制中介组件和 PSTN 网关之间的端口数，则还需要在网关上配置相应的端口范围。

- 您必须在外围网络中部署云连接器。 这意味着您将拥有两个防火墙：

  - 第一个防火墙在 internet 和您的外围网络之间是外部的。

  - 第二个防火墙在外围网络和内部网络之间是内部的。

    您的客户端可以位于 internet 或内部网络中：

  - Internet 中的客户端将通过外部防火墙通过边缘组件连接到你的 PSTN。

  - 内部网络中的客户端将通过内部防火墙连接到外围网络中的中介组件，这会将流量连接到 SBC 或 PSTN 网关。

    这意味着，您需要在两个防火墙中打开端口。

下表描述了外部和内部防火墙的端口和端口范围。

此表显示了用于在内部网络和中介组件中的客户端之间实现通信的端口和端口范围：

**内部防火墙**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |任何  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |任何  <br/> |TCP 5068/TLS 5067  <br/> |
|云连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |UDP 49 152-57 500  <br/> |各种\*\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云连接器中介组件  <br/> |各种\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/>  (可选)   <br/> |
|云连接器中介组件  <br/> |内部客户端  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|内部客户端  <br/> |云连接器中介组件  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\* 这是中介组件上的默认端口范围。 对于最佳呼叫流，每个呼叫需要四个端口。

\*\* 必须在 SBC/PSTN 网关上配置此端口;5060是一个示例。 您可以在 SBC/PSTN 网关上配置其他端口。

\*\*\* 请注意，如果 SBC/网关制造商允许，您还可以限制您的 SBC/网关上的端口范围。

为安全起见，可以使用 [set-csmediationserver](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) Cmdlet 限制中介组件的端口范围。

例如，以下命令将中介组件为 50 000-51 000 的媒体流量使用的端口数限制为) 的音频 (。 中介组件将能够使用此配置处理250并发呼叫。 请注意，您还可能希望在 SBC/PSTN 网关上限制此范围：

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

若要检索中介组件的名称并查看默认端口，可以使用 [get-csservice](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) cmdlet，如下所示：

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表显示了允许云连接器边缘组件与外部防火墙之间进行通信的端口和端口范围。 此表显示最小建议。

在这种情况下，到 internet 的所有媒体流量都将通过联机边缘流动，如下所示：用户终结点- \> 在线边缘-- \> 云连接器边缘：

**外部防火墙-最低配置**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |

下表显示了允许云连接器边缘组件与外部防火墙之间进行通信的端口和端口范围。 此表显示了推荐的解决方案。

在这种情况下，internet 中的终结点的所有媒体流量都可以直接流向云连接器边缘组件。 媒体路径将为用户终结点- \> 云连接器边缘。

> [!NOTE]
> 如果用户终结点位于对称 NAT 后面，则此解决方案将不起作用。

**外部防火墙-推荐的配置**


|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP (MTLS) 5061  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |TCP 50000-59999  <br/> |任何  <br/> |
|云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478;UDP 50000-59999  <br/> |任何  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |TCP 443;TCP 50000-59999  <br/> |
|任何  <br/> |云连接器边缘外部接口  <br/> |任何  <br/> |UDP 3478;UDP 50000-59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>承载 Internet 连接要求
<a name="BKMB_Ports"> </a>

主机必须能够访问外部资源，才能成功安装、更新和管理云连接器。 下表显示了主机和外部资源之间所需的目标和端口。

|Direction  <br/> |源 IP  <br/> |目标 IP  <br/> |源端口  <br/> |目标端口  <br/> |协议  <br/> |用途  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|出站  <br/> |云连接器主机 Ip  <br/> |任意  <br/> |任意  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|出站  <br/> |云连接器主机 Ip  <br/> |任意  <br/> |任意  <br/> |80、443  <br/> |TCP  <br/> |证书吊销列表 (CRL)   <br/> |
|出站  <br/> |云 Connectorr 主机 Ip  <br/> |任意  <br/> |任意  <br/> |80、443  <br/> |TCP  <br/> |云连接器更新  <br/> Skype for Business Online  <br/> 管理 PowerShell  <br/> Windows 更新  <br/> |

如果需要更多的限制性规则，请参阅以下白名单 Url：

- [Office 365 url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中的[证书吊销列表 url](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Windows Update： [如何为软件更新配置防火墙](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Online 管理 PowerShell： \* online.lync.com

    如果需要对此目标使用代理排除，则需要将其添加到 WinHTTP 旁路列表中。

- 云连接器更新： [下载中心](https://aka.ms/CloudConnectorInstaller)、 [https://go.microsoft.com](https://go.microsoft.com) 和 [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>边缘组件的 DNS 名称解析
<a name="BKMB_Ports"> </a>

边缘组件需要解析 Microsoft 365 或 Office 365 服务的外部名称和其他云连接器组件的内部名称。

每个边缘组件都是具有外部接口和内部接口的多宿主计算机。 云连接器在外围网络中的域控制器组件上部署 DNS 服务器。 您可以将边缘服务器指向外围中的 DNS 服务器，以获取所有名称解析，但您需要使云连接器 DNS 服务器能够解析外部名称，方法是设置一个 DNS 区域，其中包含一个或多个引用名称查找到其他公用 DNS 服务器的外部查询的 DNS A 记录。

在 .ini 文件中，如果将网关的 FQDN 名称设置为来自与 SIP 域相同的域空间，则将在外围环境中的 DNS 服务器中创建此 SIP 域的权威区域。 如果边缘服务器指向此 DNS 服务器以解析名称，则 Edge 将永远不解析 _sipfederationtls。\<yourdomain\> DNS 记录，它是呼叫流所必需的。 在这种情况下，Microsoft 建议您在边缘外部接口上提供一个 DNS 服务器，以解析 Internet 名称查找，并且每个边缘组件都必须使用主机文件将其他云连接器组件名称解析为 IP 地址。

> [!NOTE]
> 出于安全考虑，我们建议您不要将云连接器 DNS 服务器指向生产域中的内部服务器，以便进行名称解析。

### <a name="determine-deployment-parameters"></a>确定部署参数
<a name="BKMK_SiteParams"> </a>

首先，需要定义以下常见部署参数：


|**项**|**说明**|**注释**|
|:-----|:-----|:-----|
|SIP 域  <br/> |公司用户正在使用的 SIP URI。 提供此部署将提供服务的所有 SIP 域。 您可以有多个 SIP 域。  <br/> ||
|PSTN 站点数  <br/> |您将部署的 PSTN 站点的数量。  <br/> ||

对于您计划部署的每个 PSTN 站点，您需要在开始部署之前收集以下信息。 更新 CloudConnector.ini 文件时，将需要提供此信息。

配置网关信息时，请记住以下事项：

- 如果你只有一个网关，请在 .ini 文件中删除第二个网关的部分。 如果有两个以上的网关，请按照现有格式添加新网关。

- 请确保网关 (s) 的 IP 地址和端口正确。

- 若要支持 PSTN 网关级别 HA，请保留辅助网关或添加其他网关。

 (可选) 来限制出站呼叫号码，请更新 LocalRoute 值。



|**网站参数**|**说明**|**注释**|
|:-----|:-----|:-----|
|虚拟机域名  <br/> |云连接器的内部组件的域名。 此域必须不同于生产域。 所有云连接器设备上的名称必须相同。  <br/> .Ini 文件中的名称： "VirtualMachineDomain"  <br/> |。本地域为首选。  <br/> |
|云连接器域控制器名称  <br/> |域控制器的名称。  <br/> .Ini 文件中的名称： "ServerName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|云连接器域控制器 IP/子网掩码  <br/> |域控制器的 IP 地址。  <br/> .Ini 文件中的名称： "IP"  <br/> ||
|Microsoft 365 或 Office 365 Online 服务 Fqdn  <br/> |对于全球范围内的 Microsoft 365 或 Office 365 实例，大多数情况下都必须是默认值。  <br/> .Ini 文件中的名称： "OnlineSipFederationFqdn"  <br/> ||
|名  <br/> |Skype for Business 网站名称;例如，西雅图。  <br/> .Ini 文件中的名称： "SiteName"  <br/> 对于 Release 1.4.1 和更高版本，每个网站的站点名称必须不同，并且名称必须与 PSTN 站点匹配（如果存在），并且在 Microsoft 365 或 Office 365 中定义。 请注意，在站点中注册第一台设备时，将自动创建 PSTN 站点。  <br/> ||
|HardwareType  <br/> 发布1.4.1 和更高版本  <br/> |硬件类型。 默认值为 Normal。 您还可以将设置为 "最小值"。  <br/> ||
|Country Code  <br/> |用于拨号的国家/地区代码。  <br/> .Ini 文件中的名称： "CountryCode"  <br/> ||
|市/县  <br/> |城市 (可选) 。  <br/> .Ini 文件中的名称： "City"  <br/> ||
|状态  <br/> |State (可选) 。  <br/> .Ini 文件中的名称： "State"  <br/> ||
|基本 VM IP 地址  <br/> |将用于为所有云连接器虚拟机创建 VHDX 的临时基虚拟机的 IP 地址。 此 IP 必须位于下一步中定义的外围企业网络子网内，需要 Internet 访问。 确保定义企业默认网关和可路由到 internet 的 DNS。  <br/> .Ini 文件中的名称： "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 发布1.4.1 和更高版本  <br/> | (WSUS) 的 Windows Server Update Services 的地址—即承载来自 Microsoft Update 的更新的 intranet 服务器。  <br/> 如果不需要 WSUS，可以保留为空。  <br/> ||
|内部网络的子网掩码  <br/> |云连接器配置 IP 网络，以便在云连接器组件之间进行内部通信。 边缘也必须连接到允许 Internet 连接的另一个子网。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "CorpnetIPPrefixLength"  <br/> ||
|外部网络的子网掩码  <br/> |对于边缘组件的外部网络。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "InternetIPPrefix"  <br/> ||
|内部网络的交换机名称  <br/> |将用于内部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用默认建议的值。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "CorpnetSwitchName"  <br/> ||
|外部网络的交换机名称  <br/> |将用于外部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用默认建议的值。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "InternetSwitchName"  <br/> ||
|内部网络的默认网关  <br/> |此网关必须提供对 Internet 的访问权限 (Internet 还需要设置 DNS 服务器) 并将在云连接器组件的内部接口上配置。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "CorpnetDefaultGateway"  <br/> ||
|边缘组件的外部接口的默认网关  <br/> |将在边缘组件的外部接口上配置。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "InternetDefaultGateway"  <br/> ||
|内部网络的 DNS 服务器  <br/> |将在临时 VM 的内部接口上配置。 必须为 Internet 名称提供名称解析。 如果不提供 DNS 服务器，Internet 连接将失败，并且不会完成部署。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "CorpnetDNSIPAddress"  <br/> ||
|边缘组件的外部接口的 DNS 服务器  <br/> |将在边缘的外部接口上配置。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "InternetDNSIPAddress"  <br/> ||
|管理交换机名称  <br/> |管理交换机是一个将自动创建的临时开关，它将用于在部署过程中配置云连接器。 在部署后，它将自动断开连接。 它必须是与云连接器中使用的任何其他网络不同的子网。  <br/> 在大多数情况下，可以使用默认建议的值。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "ManagementSwitchName"  <br/> ||
|管理子网地址/子网掩码  <br/> |管理子网是一个将自动创建的临时子网，将用于在部署期间配置云连接器。 部署后将自动删除它。 它必须是与云连接器中使用的任何其他网络不同的子网。  <br/> .Ini 文件中的名称： "虚拟机网络池的参数" 下的 "ManagementIPPrefix" 和 "ManagementIPPrefixLength"  <br/> ||
|中央管理存储 (CMS) 计算机  <br/> |用于中央管理存储 (CMS) 的单个 FQDN。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "主要中央管理服务的参数" 下的 "ServerName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/>  (CMS 池名称 = 服务器名称)   <br/> |
|CMS 计算机 IP 地址  <br/> |在外围网络) 中，CMS 服务器 (内部的 IP 地址。  <br/> INI 文件中的名称： "主要中央管理服务的参数" 下的 "IP"  <br/> ||
|文件共享名称  <br/> |要在 CMS server 上为 Skype for Business 复制数据创建的文件共享名称 (例如，CmsFileStore) 。  <br/> 在大多数情况下，可以使用默认建议的值。  <br/> .Ini 文件中的名称： "主要中央管理服务的参数" 下的 "CmsFileStore"  <br/> ||
|中介组件池名称  <br/> |中介组件的池名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "中介服务器池的参数" 下的 "PoolName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|中介组件名称  <br/> |中介组件1的组件名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "中介服务器池的参数" 下的 "ServerName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|中介组件计算机 IP 地址  <br/> |外围网络) 的内部公司内部公司 IP 用于中介组件 (内部。  <br/> .Ini 文件中的名称： "中介服务器池的参数" 下的 "IP"  <br/> ||
|边缘池内部名称  <br/> |边缘组件的池名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "InternalPoolName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|边缘服务器内部名称  <br/> |边缘组件的组件名称。 仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "InternalServerName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|边缘服务器内部 IP  <br/> |与云连接器的其他组件进行通信的边缘组件的内部外围网络 IP。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "InternalServerIPs"  <br/> ||
|访问池外部名称  <br/> |访问边缘的名称;例如，AP。 此名称必须与为 SSL 证书提供的名称相匹配。 仅输入 Netbios 名称。 SIP 域名将用于生成 FQDN。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点需要一个边缘访问池。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "ExternalSIPPoolName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> "sip" 是保留的，因此不能用作名称。  <br/> 生成的 FQDN 名称必须与为 SSL 证书提供的名称相匹配。  <br/> |
|访问边缘的外部 IP  <br/> |边缘组件（如果没有 NAT 可用，则为公用 IP）的外部 IP; 或者已转换的 IP (请在映射) 的情况下指定这两个地址。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "ExternalSIPIPs"  <br/> ||
|媒体中继名称  <br/> |音频视频媒体中继边缘的名称;例如，MR。 一个外部池名称将用于池中的所有边缘组件。 每个 PSTN 站点需要一个边缘媒体中继池。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "ExternalMRFQDNPoolName"  <br/> |必须为15个字符或更少。 仅输入 Netbios 名称。  <br/> |
|媒体中继边缘的外部 IP  <br/> |目前仅支持一个 IP，因此这将与访问边缘相同（公用或映射的 IP）的 IP (请在映射) 时指定这两个地址。 可以是与访问边缘的边缘组件外部 IP 相同的地址。 注释如果边缘位于 NAT 后面，还需要指定下一个参数的值。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "ExternalMRIPs"  <br/> ||
|如果边缘位于 NAT 之后，则为媒体中继边缘的外部 IP ()   <br/> |如果你的边缘位于 NAT 后面，你还需要指定 NAT 设备的公用地址。  <br/> .Ini 文件中的名称： "边缘服务器池的参数" 下的 "ExternalMRPublicIPs"  <br/> ||
|语音网关1品牌和型号  <br/> |指定 SBC/语音网关的品牌和型号。 请注意，您可以从已测试设备的列表中连接设备或 SIP 中继 [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) 。  <br/> ||
|如果网关数超过2个，则语音网关2品牌和型号 (复制此行)   <br/> |指定语音网关的品牌和型号。 请注意，您可以从的已测试设备列表中连接设备 [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) 。  <br/> ||
|语音网关1名称  <br/> |用于生成 AD 域的计算机 FQDN。 如果在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不打算使用 FQDN，例如，TLS 不是必需的，或者语音网关不支持使用仅限 IP) 的 FQDN (连接—请指定。  <br/> ||
|如果网关数超过2个，则语音网关2名称 (复制此行)   <br/> |用于生成 AD 域的计算机 FQDN。 如果在中介组件和语音网关之间使用 TLS，则是必需的。 如果您不打算使用 FQDN，例如，TLS 不是必需的，或者语音网关不支持使用仅限 IP) 的 FQDN (连接—请指定。  <br/> ||
|语音网关 1 IP 地址  <br/> |语音网关的 IP 地址。  <br/> ||
|如果网关数超过2个，则语音网关 2 IP 地址 (复制此行)   <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关1端口 # (如果网关数超过2个，请复制此行)   <br/> |语音网关 SIP 中继将侦听的端口，例如5060。  <br/> ||
|语音网关2端口#  <br/> |语音网关 SIP 中继将侦听的端口，例如5060。  <br/> ||
|SIP 流量的语音网关1协议  <br/> |TCP 或 TLS。  <br/> ||
|SIP 流量的语音网关2协议 (复制此行（如果网关数超过2个)   <br/> |TCP 或 TLS。  <br/> ||
|进出边缘组件的流量的外部媒体端口范围  <br/> |与边缘的外部接口之间的媒体流量的 TCP/UDP 端口范围。 必须始终从 50 000 开始。 有关详细信息，请参阅 "端口和协议"。  <br/> |50000-59 999  <br/> |
|通过内部防火墙与中介组件进行通信的媒体端口范围  <br/> |中介组件将用来与客户端和网关通信的 UDP 端口范围 (每个呼叫) 推荐4个端口。  <br/> ||
|通过内部防火墙与 Skype for business 客户端通信的媒体端口范围  <br/> |出于规划目的，无法更改。 需要在内部防火墙中打开端口，以便在内部网络中的 Skype for Business 客户端和中介组件之间进行通信。  <br/> |50 000-50 019  <br/> |
|公共证书密码  <br/> |必须在脚本中提供。  <br/> ||
|安全模式管理员密码  <br/> 仅限版本1.4。2  <br/> |内部抄送域的安全模式管理员密码。  <br/> ||
|云连接器域管理员密码  <br/> 仅限版本1.4。2  <br/> |云连接器域管理员的密码 (不同于生产域) 。 User name 为 Administrator。 您不能更改用户名。  <br/> ||
|虚拟机管理员密码  <br/> 仅限版本1.4。2  <br/> |用于在部署过程中配置管理网络。  <br/> User name 为 Administrator。 您不能更改用户名。  <br/> ||
|CABackupFile  <br/> 版本2.0 及更高版本  <br/> |用于在云连接器站点中部署多个设备时将证书颁发机构服务从 Active Directory 服务器保存到文件。 请务必对一个云连接器站点中的所有设备使用相同密码，以便成功将 CA 备份文件导入新添加的设备。  <br/> ||
|CCEService  <br/> 版本2.0 及更高版本  <br/> |用于云连接器管理服务;需要访问云连接器网站目录。 请务必对一个云连接器站点中的所有设备使用相同的密码。  <br/> ||
|Microsoft 365 或 Office 365 租户管理员  <br/> | 云连接器使用该帐户来更新和管理云连接器的租户设置： <br/>  版本2.0 及更高版本：具有 Skype for Business 管理员权限的专用 Microsoft 365 或 Office 365 帐户的凭据。 <br/>  2.0 之前的版本：具有全局租户管理员权限的专用 Microsoft 365 或 Office 365 帐户的凭据。 <br/> ||
|启用参考支持  <br/> |这将定义是否在 IP/PBX 的中继配置上启用或禁用 SIP。 默认值为 True。 如果你的 IP/PBX 网关支持引用支持，请将此设置为 True。 如果不是这样，则需要将此值更改为 False。 如果你不确定你的网关是否支持参考，请参阅 [合格的 IP-pbx 和网关](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。   <br/> ||
|EnableFastFailoverTimer  <br/> 版本2.0 及更高版本  <br/> |默认值为 "True" 的情况下，如果网关在10秒内没有应答出站呼叫，它们将被路由到下一个可用的网关;如果没有其他中继，则将自动丢弃呼叫。  <br/> 但是，在网络和网关响应较慢的组织中，或当建立呼叫的过程超过10秒时，这可能会导致不必要地丢弃呼叫。  <br/> 向某些国家（如 UAE 或阿富汗）发出呼叫时，呼叫建立过程可能需要10秒以上的时间。 如果遇到类似问题，则需要将此值更改为 False。 请勿忘记更改连接的 SBC 或网关上的相应设置。  <br/> 值可以为 True 或 False。 默认值为 True。  <br/> ||
|ForwardCallHistory  <br/> 版本2.0 及更高版本  <br/> | 此参数用于打开用于在同时响铃、呼叫转接和呼叫转移方案中报告初始呼叫者的 SIP 标头。 将此参数设置为 True 将启用两个 SIP 标头： <br/>  历史记录-信息 <br/>  引用者 <br/>  History-Info 标头用于对 SIP 请求进行重新设定，并 "提供 () 一种标准机制，用于捕获请求历史记录信息，从而为网络和最终用户提供多种服务 ([RFC 4244-Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)) 。 对于云连接器中继接口，这在同时和呼叫转发方案中使用。  <br/>  值可以为 True 或 False。 默认值为 False。 <br/> ||
|转发 PAI  <br/> 版本2.0 及更高版本  <br/> |PAI 是 SIP 的专用扩展，它使 SIP 服务器能够断言已通过身份验证的用户的身份。 对于 SIP 中继提供程序，如果历史记录信息和被引用的标头不存在，则 PAI 可用于记帐目的。 如果在配置中启用了前向 P 声明的标识，中介服务器将把带有 SIP &amp; 电话 URI 的 PAI 标头从云连接器转发到 SIP 中继。 中介服务器将转发 PAI 标头，其中电话 URI 的 e.164 &amp; 号码仅在 SIP 中继到云连接器上收到。 中介服务器还将转发任一方向接收到的任何隐私标头。 如果中介服务器发送的 SIP 请求包含表单的隐私标头-"隐私： id" 与 PAI 标头结合使用，则声明的标识应在网络信任域外部保持专用。  <br/> 值可以为 True 或 False。 默认值为 False。  <br/> ||

### <a name="certificate-requirements"></a>证书要求
<a name="BKMK_Certs"> </a>

每个边缘组件都需要来自公共证书颁发机构的证书。 证书必须具有可导出的私钥才能在边缘组件之间进行复制。 若要满足证书要求，您需要在以下选项之间做出决定，并提供证书的使用者名称 (SN) 和使用者备用名称 (SAN) 。

 **如果您有一个 SIP 域：**

- **选项1。** 主题名称必须包含分配给边缘组件的池名称。 请注意，使用者名称不能为 sip.sipdomain.com，因为此名称是为联机 Skype for Business Edge 组件保留的。 SAN 必须包含 sip.sipdomain.com 和访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **选项2。** 如果要在部署的所有边缘池服务器上使用单个通配符证书，则可以使用 sipdomain.com 的通配符 SAN 条目， \* 而不是证书中的边缘池名称。 使用者名称可以是已部署的任何边缘池的访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> 您不得为 sip 创建外部 DNS 条目。 \<sipdomain\> 。com，因为此名称属于 Microsoft 365 或 Office 365 部署。

> [!NOTE]
> 如果要对组织中部署的所有边缘池使用单个证书，但不能使用在选项2中定义的通配符证书，则需要将证书中 SAN 名称中所有已部署的边缘池的 FQDN 包括在内。

 **如果您有多个 SIP 域：**

您将需要为每个 SIP 域添加 sip.sipdomain.com 和每个域的访问边缘池的名称 ( 它可以是一个物理池，但名称不同) 。 下面是一个多 sip 域方案中 SN 和 SAN 条目的示例：

- **选项1。** 主题名称必须包含您为边缘组件分配的池名称。 请注意，使用者名称不能为 sip.sipdomain.com，因为此名称是为联机 Skype for Business Edge 组件保留的。 SAN 必须包含 sip.sipdomain.com 和访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>选项2。</strong>如果要在部署的所有边缘池服务器上使用单个通配符证书，则可以使用 sipdomain.com 的通配符 SAN 条目， \* 而不是证书中的边缘池名称。 使用者名称可以是已部署的任何边缘池的访问边缘池名称：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> 您不得为 sip 创建外部 DNS 条目。 \<sipdomain\> 。com，因为此名称属于 Microsoft 365 或 Office 365 部署。

出于部署目的，您可以使用下表：

|**选项**|**说明**|**注释**|
|:-----|:-----|:-----|
|您将在部署中使用哪种方法？  <br/> |Option 1 或2  <br/> ||
|SN  <br/> |为您的证书提供 SN  <br/> ||
|圣马力诺  <br/> |为您的证书提供 SAN  <br/> ||

如果要在网关和中介服务器之间使用 TLS，则需要获取分配给网关的证书的根证书或完整证书链。

## <a name="dial-plan-considerations"></a>拨号计划注意事项
<a name="BKMK_DailPlan"> </a>

云连接器需要使用联机拨号计划。 有关如何配置在线拨号计划的详细信息，请参阅 [什么是拨号计划？](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>高可用性注意事项
<a name="BKMK_HA"> </a>

部署用于高可用性的云连接器版本时，至少要部署两个充当彼此的备份的设备。 每个设备由四个组件组成： Edge、中介、中央管理存储 (CMS) 和域控制器。

通常，如果设备内的一个组件停止运行，云连接器版本可以继续处理呼叫，但您必须考虑以下事项：

- **中介、CMS 和域控制器组件注意事项**

    假定一个设备中的 CMS 或域控制器组件出现故障。 设备仍可以处理入站和出站呼叫，但如果您在无法访问域控制器或 CMS 组件时重新启动中介组件，则中介将不起作用。 这同样适用于在域控制器关闭时重新启动 CMS 组件的情况。

    **建议：** 在重新启动组件之前，请检查设备中的其他组件是否可用。

- **边缘组件注意事项**

    如果一台设备中的边缘组件不可用，则入站和出站呼叫的行为将有所不同，如下所示：

  - **出站呼叫**—从 Internet 中的用户到 PSTN 网络的呼叫。

    云中的呼叫分布机制将确定一个边缘组件已关闭，并将所有呼叫路由到另一个设备，因此出站呼叫成功。

  - **入站呼叫**—从 PSTN 网络到位于本地网络或 Internet 中的用户的呼叫。

     如果接收呼叫的设备的边缘组件未正常运行，则对此设备的入站呼叫将不会成功，因为中介组件无法将呼叫重定向到其他设备中的边缘组件。

    **建议：** 准备好监控系统。 在确定边缘组件的故障后，请关闭设备中边缘组件不可用的所有组件。

## <a name="cloud-connector-media-flow"></a>云连接器媒体流
<a name="BKMK_MediaFlow"> </a>

下面的关系图概括了通过云连接器版本进行的出站和入站呼叫流。 这是了解如何建立连接的有用信息。

在第一个关系图中，内部用户按如下所示放置出站呼叫：

1. Dave，用户处于联机状态，但现在在内部网络中，将呼叫置于外部 PSTN 用户。

2. 到 Skype for Business Online 的 SIP 通信路由。

3. Skype for Business Online 将对编号执行反向编号查找。 反向号码查找失败，因为此号码不属于 Skype for Business 组织中的任何人。

4. 将呼叫路由到边缘组件 (SIP 和媒体流先通过在线边缘;媒体将通过内部防火墙) 转到中介组件。

5. 如果路由存在，则边缘组件会将流量中继到外围网络中的中介组件。

6. 中介组件将流量发送到 PSTN 网关。

![云连接器的出站媒体流](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

在下图中，内部用户接收入站呼叫，如下所示：

1. PSTN 网关接收到已联机的用户 Dave 的呼叫，但现在在内部网络中。

2. SIP 流量路由到中介组件。

3. 中介组件会将 SIP 流量发送到边缘组件，然后转到 Skype for Business Online。

4. Skype for Business Online 对号码执行反向号码查找，发现这是用户 Dave。

5. SIP 信号转到所有 Dave 的状态点。

6. 将在网关和中介组件之间以及中介组件和终结点之间建立媒体流量。

![云连接器的入站媒体流](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>监控和疑难解答
<a name="BKMK_Monitor"> </a>

监控和故障排除机制随每个云连接器设备自动安装。 该机制将检测以下事件：

- 云连接器设备的一个或多个虚拟机未连接到内部或 internet 虚拟交换机。

- 云连接器设备的一个或多个虚拟机处于 "已保存" 或 "已停止" 状态。

- 未运行的服务。

  如果检测到以下事件之一，将耗尽整个云连接器设备并将其标记为脱机，以防止尝试建立出故障的设备的呼叫。 云连接器自动恢复功能随后将还原服务，并将设备标记为在线。 如果自动恢复由于某些原因失败，请参阅对 [你的云连接器部署进行故障排除](troubleshoot-your-cloud-connector-deployment.md)。

  - 在中央管理存储虚拟机上：

     - Skype for Business 主复制程序代理

     - Skype for Business 副本复制器代理

  - 在中介服务器虚拟机上：

     - Skype for Business 副本复制器代理

     - Skype for Business Server 中介

  - 在边缘服务器虚拟机上

     - Skype for Business 副本复制器代理

     -  Skype for Business Server 访问边缘

     - Skype for Business Server 音频/视频边缘

     - Skype for Business Server 音频/视频身份验证

     - Skype for Business Server Web 会议边缘

- Windows 防火墙的入站规则（针对边缘上的 "cs RTCSRV"）禁用了中介服务器上的 "CS RTCMEDSRV"。

云连接器2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅 [使用 Operations Management Suite 监视云连接器 (OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_MoreInfo"> </a>

有关详细信息，请参阅：

- [Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [配置和管理 Skype for Business 云连接器版本](configure-skype-for-business-cloud-connector-edition.md)

- [云连接器版本中的媒体旁路规划](plan-for-media-bypass-in-cloud-connector-edition.md)

- [在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)


