---
title: 规划 Skype for Business 云连接器版本
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: 查找有关 Skype for Business 云连接器版本的信息，云连接器是一组打包的虚拟机 (Vm)，这些虚拟机负责通过 Office 365 中的电话系统（云 PBX）实施本地 PSTN 连接。
ms.openlocfilehash: f69becbd25ad00ca4353c0b287f2abcc43bdecfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>规划 Skype for Business 云连接器版本
 
查找有关 Skype for Business 云连接器版本的信息，云连接器是一组打包的虚拟机 (Vm)，这些虚拟机负责通过 Office 365 中的电话系统（云 PBX）实施本地 PSTN 连接。 
  
如果您没有现有 Lync Server 或 Skype 业务服务器部署云连接器版可能会适合您的组织的解决方案。 如果仍然正在研究 Office 365 提供解决方案中的电话系统适合您的业务，请参阅[规划 Office 365 (云 PBX) 解决方案中的电话系统](plan-your-phone-system-cloud-pbx-solution.md)。 
  
本文档描述云连接器版要求和受支持的拓扑，并可以帮助您计划您的云连接器版部署。 请务必阅读本主题之前配置连接器云环境。 当您准备部署和配置云连接器版本，请参阅[配置和管理商务云连接器版 Skype](configure-skype-for-business-cloud-connector-edition.md)。 
  
现已云连接器版本 2.1。 如果您还没有升级到 2.1 版，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。 您可以找到安装文件的[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。 
  
> [!NOTE]
> 新版本发布后的 60 天内，Microsoft 支持的云连接器版以前的版本。 Microsoft 会在 2.1 版发布后 60 天内继续支持 2.0.1 版，为你预留时间进行升级。 2.0.1 之前的所有版本不再受支持。 
  
云的连接器版是封装虚拟机 (Vm) 在 Office 365 中实现电话系统与内部 PSTN 连接一组组成的混合产品。 通过部署在虚拟化环境中的业务服务器拓扑结构的最小 Skype，在云中托管您的组织中的用户能够接收来自 Microsoft 云的 PBX 服务但 PSTN 连接提供通过现有内部声音基础结构。 
  
![该拓扑图显示云 PBX 网关（用于将云 PBX 连接到 Skype for Business 的内部部署）。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)
  
因为云连接器使你可以将 Office 365 电话系统服务与现有电话环境集成—例如，PBX、模拟设备和呼叫中心—你可以实施从现有电话解决方案到 Office 365 电话系统的分阶段迁移。 
  
例如，假设贵公司有一个复杂的呼叫中心，它具有 Office 365 电话系统无法提供的特定功能。 你可以选择将呼叫中心用户保留在现有解决方案中，而将其他用户迁移到 Office 365 电话系统。 
  
云连接器将在本地托管用户和在线托管用户之间提供路由，你可以选择将自己的 PSTN 提供程序与 Office 365 电话系统结合使用。
  
规划您的云连接器版部署时，请考虑以下： 
  
- 使用云连接器能够利用云语音解决方案，您需要注册 Office 365 租户，其中包括 Office 365 中的电话系统。 如果您还没有 Office 365 租户您可以学习如何在此处注册： [Office 365 的业务](https://products.office.com/en-us/business/office)。 请注意，您需要注册一个包括 Skype 的在线业务的计划。
    
- 要注册的商业在线服务，Skype 云接头装置并运行各个 cmdlet，云连接器 2.0 及更高版本需要商业租户管理员权限 Skype 与 Office 365 专用的帐户。 2.0 之前的云连接器版本需要具有专用的 Office 365 帐户以及租户全局管理员权限。
    
- 云的连接器不需要完全内部 Skype 业务服务器部署。 
    
    目前，云接口不能利用 Lync 共存或 Skype 为企业内部服务器。 如果要将现有 Lync 或 Skype 为商务用户移到 Office 365 提供并保持提供部署到用户的电话，可以考虑在 Office 365 的电话系统具有的业务服务器部署中使用现有的 Skype 的内部连接。 有关详细信息，请参阅[规划您 Office 365 (云 PBX) 解决方案中的电话系统](plan-your-phone-system-cloud-pbx-solution.md)和[计划内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 如果有以前 Skype 业务或 Lync Server 部署和扩展该架构，您不需要清理云连接器部署的架构，只要已经将所有 Skype 业务或 Lync Server 组件都删除从您的环境。 
    
- 您的用户以联机方式驻留。
    
- 如果贵组织已配置目录同步 (DirSync)，则必须先在本地部署中创建已计划混合语音的所有用户帐户，然后再将其同步至云。
    
- 如果需要，您可以继续使用当前 PSTN 运营商。
    
- 如果您想要提供给云连接器上承载的用户拨入会议，您可以从 Microsoft 或音频会议提供商 (ACP) 合作伙伴购买 PSTN 会议。
    
- 现在，云连接器 2.0 版和更高版本支持媒体旁路。 媒体回避允许客户端直接与公共交换电话网络 (PSTN) 的下一跃点发送媒体 — — 网关或会话边框控制器 (SBC) — — 并消除通过媒体路径中的云连接器版组件。 有关详细信息，请参阅[媒体计划绕过云连接器版中](plan-for-media-bypass-in-cloud-connector-edition.md)。
    
- 云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅[使用操作管理套件 (OMS) 的显示器云接头](monitor-cloud-connector-using-operations-management-suite-oms.md)
    
- 所有可用 Office 365 企业 E5 所在的国家/地区中提供了云连接器。 但是，由于各种法规，云连接器无法配置如果租户位置被设置为以下国家之一： 阿尔及利亚、 孟加拉国、 博茨瓦纳、 文莱、 喀麦隆，科特迪瓦，加纳、 黎巴嫩、 澳门，毛里求斯、 纳米比亚、 巴拉圭，塞内加尔。
    
本主题包括以下部分：
  
- [云的连接器版组件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)
    
- [云的连接器版拓扑](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)
    
- [部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)
    
- [您需要在部署之前收集的信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)
    
- [拨号计划注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)
    
- [高可用性注意事项](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)
    
- [云连接器媒体流](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)
    
- [监视和故障排除](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)
    
- [有关详细信息](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)
    
## <a name="cloud-connector-edition-components"></a>云连接器版本组件
<a name="BKMK_Components"> </a>

与云连接器版，您将部署一套包含业务服务器拓扑结构的最小 Skype 的打包 Vm — 边缘组件、 中介组件和一个中央管理存储 (CMS) 角色组成。 您也将安装域控制器来说，这是内部的云连接器正常工作所必需。 这些服务被配置为与您的商业在线服务包括 Skype 的 Office 365 租户的混合。
  
![云连接器版本组件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)
  
云的连接器组件提供以下功能：
  
- **边缘组件**的内部拓扑和在线服务之间的通信经过边缘组件，其中包括以下组件：
    
  - **访问边缘**-提供 SIP 路由到内部部署和 Skype 之间的在线业务。
    
  - **媒体中继**-提供媒体中介组件和其他媒体终结点之间的路由。
    
  - **媒体中继身份验证 / MRAS** -生成媒体中继访问令牌。
    
- **出站路由**-提供负载平衡的网关之间的语音通信或 SBCs 连接到云接口装置。 通话将在连接到云连接器设备的所有网关或 SBC 之间平均拆分。
    
    提供了基于策略的网关路由。 仅基于目标（出站）PSTN 号码的全局策略受支持。
    
- **中央管理存储 (CMS) 角色**-包括配置存储拓扑组件，包括 CMS 文件传输。
    
- **中央管理存储 (CMS) 副本**的同步从全局 CMS DB CMS 角色服务器上的配置信息。
    
- **域控制器**-云连接器 Active Directory 域服务来存储所有的全局设置和部署云连接器组件所需的组。 将为每个云接头装置创建一个目录林。 域控制器不能有任何与生产活动目录的连接。 Active Directory 服务包括：
    
  - Active Directory 域服务
    
  - 可颁发内部证书的 Active Directory 证书服务
    
- **中介组件**的实现 SIP 和媒体网关映射 Skype 业务和 PSTN 网关之间的协议。 包含同步配置全局的 CMS 数据库从一个 CMS 复制副本。
    
## <a name="cloud-connector-edition-topologies"></a>云连接器版本拓扑
<a name="BKMK_Topologies"> </a>

出于讨论目的，我们将提及 PSTN 站点。 PSTN 站点是云接头装置，部署在相同的位置，并与常用的 PSTN 网关连接到它们的组合。 通过 PSTN 站点，你能够：
  
- 提供连接到离用户最近的网关。
    
- 通过部署一个或多个 PSTN 站点内的多个云接头装置允许的可扩展性。
    
- 通过部署单个的 PSTN 站点内的多个云接头装置允许实现高可用性。
    
本主题介绍了 PSTN 网站。 有关规划 PSTN 站点的详细信息，请参阅[规划对于云连接器版 PSTN 的站点](plan-for-cloud-connector-edition-pstn-sites.md)。
  
您可以部署以下云连接器拓扑：
  
- 每个站点 PSTN 单个云连接器版装置。 由于此拓扑不提供高可用性，因此只建议用于评估用途。
    
- 每个 PSTN 站点提供高可用性的多个云连接器版装置。 
    
- 多个 PSTN 站点使用多个云连接器版装置，以提供高可用性的可伸缩性。 最多可部署 200 个站点。
    
当规划拓扑时，请考虑以下事项：
  
- 与云连接器 2.0 及更高版本，一个 PSTN 站点可以有最多 16 个云接头装置。 在之前版本中，每个站点最多支持 4 台设备。 
    
- 有两种类型的硬件配置经云连接器： 
    
  - 大型版本能够处理大量并发呼叫，在所有类型的生产环境中都受支持。
    
  - 小型版本旨在低端硬件上运行，可用于评估目的或者用于呼叫量较低的站点。如果你部署云连接器的小型版本，你仍需要注意生产级别的硬件要求（例如，双电源）。
    
- 如果您有云连接器 2.0 或更高版本，并且部署 16 （具有较大的硬件） 设备的最大配置，PSTN 站点可以处理多达 8000 个呼叫。 如果部署小型版本，支持的限制为 800。 
    
    你还需要将某些设备专用于高可用性。最低建议是应保留一个设备用于高可用性。
    
  - 与第 2 版，如果部署 15 + 1 配置中，PSTN 站点可以处理多达 7500 个呼叫。
    
  - 如果你具有先前版本并且部署最高的 3 + 1 配置（通过较大硬件），你的 PSTN 站点可以处理多达 1500 个并发呼叫。如果你部署小型版本，则支持的限制为 150 个。
    
-  如果您需要每个 PSTN 站点有多个调用时，您可以扩展通过部署更多的 PSTN 站点在同一位置。
    
> [!NOTE]
> 除非另有说明，否则图和下面示例假定使用云连接器更大版本。 
  
### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>单个 PSTN 站点内单台云连接器设备

下图显示了单个 PSTN 站点内一台云连接器版设备。 请注意云连接器包含四个虚拟机安装在一台物理主机计算机位于外围网络中的安全方面的考虑。
  
![具有一个 PSTN 网站的一个云连接器](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)
  
### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>单个 PSTN 站点内多台云连接器设备

 出于可伸缩性和高可用性的目的，您可以选择单个 PSTN 站点内有多个云连接器版，如下面的关系图中所示。 请考虑以下事项：
  
- 呼叫在一个池中的云连接器之间按随机顺序分配。
    
- 出于容量规划目的，必须根据以下计算考虑在一个或多个云连接器离线时处理负载的能力：
    
  - **N+1 配置。** 更大版本的云连接器，N + 1 盒支持 500\*N 并发调用具有 99.8%的可用性。
    
    对于云连接器的较小版本，N + 1 盒支持 50\*N 并发调用具有 99.8%的可用性。
    
  - **N+2 配置。** 更大版本的云连接器，N + 2 盒支持 500\*N 并发呼叫提供 99.9%的可用性。
    
    对于云连接器的较小版本，N + 2 盒支持 50\*N 并发呼叫提供 99.9%的可用性。
    
![具有 1 个 PSTN 网站的两个云连接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)
  
### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>多个 PSTN 网站，每个网站一个或多个云连接器

您还可以选择配置多个 PSTN 网站，并且每个网站具有一个或多个云连接器版本。 如果 PSTN 站点达到同时调用，可以添加另一个 PSTN 站点处理的负载。
  
多个 PSTN 网站也使你能够提供到最靠近你的用户的网关的连接。 例如，假设你在西雅图和阿姆斯特丹都有 PSTN 网关。 你可以部署两个 PSTN 网站（一个位于西雅图，另一个位于阿姆斯特丹），并指定用户使用最靠近他们的 PSTN 网站。 西雅图的用户将路由到西雅图的 PSTN 网站和网关，而阿姆斯特丹的用户将路由到阿姆斯特丹的 PSTN 网站和网关：
  
![2 个 PSTN 网站内的云连接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)
  
## <a name="requirements-for-deployment"></a>部署要求
<a name="BKMK_Requirements"> </a>

部署云连接器版之前，请确保您具有以下针对您的环境：
  
- **主机-**必须将云连接器 Vm 部署在专用硬件上运行 Hyper-V 角色启用 Windows Server 2012 R2 数据中心版 （英文）。
    
    对于版本 2.0 及更高版本，绑定到 Skype for Business Corpnet 交换机的主机计算机网络卡必须在与云连接器公司网络计算机相同的子网中配置 IP 地址。 
    
- 版本 2.1 或更高版本中，对于主机装置必须安装.NET Framework 4.6.1 或更新版本。 
    
- **虚拟机-**Windows Server 2012 R2 ISO （英语） 一个映像 (.iso) 中。 ISO 将转为虚拟机将运行 Skype 业务云连接器版 Vhd。
    
- 若要在部署中每个云连接器版的支持的 4 Vm 安装必要的硬件。 推荐以下配置：
    
  - 64 位双处理器，六个核心 （12 真正核心），2.50 千兆赫 (GHz) 或更高版本
    
  - 64 GB ECC RAM  
    
  - 四个 600 GB（或更高）10K RPM 128M 缓存 SAS 6Gbps 磁盘，在 RAID 5 配置中进行配置
    
  - 三个 1 Gbps RJ45 高吞吐量网络适配器
    
- 如果您选择部署云连接器版本支持多达 50 个呼叫的较小版本，您将需要下列硬件：
    
  - Intel i7 4790 四核处理器，采用 Intel 4600 显卡（不需要高端显卡）
    
  - 32 GB DDR3-1600 非 ECC
    
  - 2：RAID 0 中的 1TB 7200RPM SATA III (6 Gbps)
    
  - 2：1 Gbps 以太网 (RJ45)
    
- 如果在主机上需要代理服务器来浏览 Internet，则必须进行下列配置更改：
    
  - 不使用代理服务器，请指定 WinHTTP 代理设置与您的代理服务器，绕过列表包括"192.168.213。\*"由您的云连接器管理服务和 Skype 业务企业网络子网的 CloudConnector.ini 文件中定义的网络。 否则为管理连接将失败，并禁止部署和云接头的自动恢复。 下面是一个示例 winhttp 配置命令： netsh winhttp 设置"10.10.10.175:8080"代理忽略列表 ="\*.local; 1。\*; 172.20。\*; 192.168.218。\*'\<本地\>"。
    
  - 指定每台计算机，而不是每个用户的代理设置。 否则，云连接器的下载将失败。 您可以指定每台计算机的代理设置，使用注册表更改或使用组策略设置，如下所示：
    
  - **注册表：**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet 设置] ProxySettingsPerUser dword:00000000
    
  - **组策略：**计算机\>管理模板\>Windows 组件\>Internet Explorer： 进行代理设置每台计算机 （而不是每个用户）
    
- 合格的 PBX/Trunk 或合格的 SBC/网络（建议至少使用两个网关）。
    
    云连接器支持经过认证适用于 Skype for Business 的相同会话边界控制器 (SBC)。 有关详细信息，请参阅[有关业务的 Skype 电话基础架构](https://technet.microsoft.com/en-us/office/dn947483.aspx)。 
    
- 使用权限来安装和配置 Hyper-V 主机服务器上的本地服务器管理员帐户。 帐户必须在安装和配置了 Hyper-V 的本地服务器上具有管理员权限。
    
- 部署过程中，需要创建有权限在云连接器域中创建和发布拓扑的域管理员帐户。 
    
- 外部 DNS 记录，这些记录是在安装程序包附带的 CloudConnector.ini 文件中定义的：
    
  - 外部 DNS 记录的访问边缘服务的边缘部分。例如，ap.\<域名\>。 每个 PSTN 网站都需要一个记录。 此记录必须包含该网站的所有边缘的 IP 地址。
    
- 创建的所有必需 DNS 和 SRV 记录与 Office 365 租户。
    
    > [!IMPORTANT]
    > 与云连接器版本，请使用默认的域后缀，集成您的租户时。 onmicrosoft.com，为您的组织的 SIP 域不受支持。 > 不能使用 sip。\<域名\>云接头边缘访问的名称作为代理接口因为此 DNS 记录使用的 Office 365。 
  
- 从公共证书颁发机构 (CA) 获得的用于外部边缘的证书。
    
- 允许通过所需的端口传输流量的防火墙规则已完成。 
    
- 主机计算机和虚拟机的 Internet 连接。 云的连接器下载某些软件从互联网;因此，您必须提供网关和 DNS 服务器信息，以便云连接器宿主机和虚拟机可以连接到 Internet 并下载所需的软件。
    
- 主机计算机上安装了租户远程 PowerShell 模块。
    
- 运行远程 PowerShell 的 Office 365 Skype for Business 管理员凭据。 
    
    > [!IMPORTANT]
    > 管理员帐户不得启用多因素身份验证。 
  
> [!NOTE]
> 在 Microsoft Hyper-V 虚拟化平台只支持云连接器部署。 其他平台（如 Vmware 和 Amazon Web Services）不受支持。 
  
> [!NOTE]
> 运行云连接器的最低硬件配置指南基于基本硬件容量 （核心、 MHz、 千兆字节，等等） 的某一缓冲区容纳埋在体系结构中的任何一台计算机的无形的性能障碍。 Microsoft 已对市场上出售的满足最低指导要求的硬件运行了最坏情况下的负载测试。 介质质量和系统性能都经过验证。 官方云接头装置 Microsoft 合作伙伴有特定云连接器硬件实现依据它们独立地进行测试性能及其硬件以满足负载和质量要求的适用性的代表。 
  
> [!NOTE]
> AudioCodes 和 Sonus 生产的设备已修改了代码，并在 Windows Server Standard Edition 的服务器上运行。这些设备受支持。 
  
## <a name="information-you-need-to-gather-before-deployment"></a>您需要在部署之前收集的信息
<a name="BKMK_PlanDeployment"> </a>

在开始部署之前，您需要确定部署的规模、服务于的 SIP 域以及您计划部署的每个 PSTN 网站的配置信息。若要开始，您将执行以下操作：
  
- 标识将通过此部署基于 SIP Uri 中使用您的公司提供服务的所有 SIP 域。 
    
- 确定需要部署的 PSTN 网站数。
    
- 确保您拥有支持您将每个云连接器版安装四个虚拟机所需的硬件。 
    
对于打算部署每个 PSTN 站点，您需要：
  
- 在每个云接头装置中创建的所有组件的名称 （请参见[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)）。
    
- 确定端口范围（请参阅[端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)）。 
    
- 为边缘组件创建外部 DNS 记录（请参阅[部署要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)）。
    
- 确定边缘组件的证书要求（请参阅[证书要求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)）。
    
### <a name="ports-and-protocols"></a>端口和协议
<a name="BKMB_Ports"> </a>

在定义媒体端口范围时，应注意以下：
  
- 客户端始终使用媒体通信的端口范围 50000 到 50019 — 此范围中 Skype 业务在线预定义，并且无法更改。
    
- 默认情况下，中介组件将使用端口范围 49 152 至 57 500 传输媒体流量。 但是，内部防火墙，通过建立连接，并且出于安全原因，您可以限制此拓扑结构中的端口范围。 每个呼叫最多需要 4 个端口。 如果需要限制中介组件和 PSTN 网关之间的端口数，你还需要在网关上配置对应的端口范围。
    
- 您必须在外围网络中部署云连接器。 这意味着你将有两个防火墙： 
    
  - 第一个防火墙是 Internet 和您的外围网络之间的外部防火墙。
    
  - 第二个防火墙是内部外围网络和内部网络之间。 
    
    您的客户端可以位于 Internet 也可以位于内部网络内： 
    
  - Internet 内的客户端将通过外部防火墙使用边缘组件连接到你的 PSTN。
    
  - 内部网络中的客户端将连接到外围网络中，将连接到的 SBC 或 PSTN 网关的通信中的中介组件内部防火墙通过。 
    
    这意味着您需要在两个防火墙中都打开端口。 
    
下表介绍了外部和内部防火墙的端口和端口范围。
  
此表显示了支持在内部网络中的客户端和中介组件之间进行通信的端口和端口范围：
  
**内部防火墙**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|云的连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |任何  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云的连接器中介组件  <br/> |任何  <br/> |TCP 5068/ TLS 5067  <br/> |
|云的连接器中介组件  <br/> |SBC/PSTN 网关  <br/> |UDP 49 152 57 500  <br/> |任何\*\*\*  <br/> |
|SBC/PSTN 网关  <br/> |云的连接器中介组件  <br/> |任何\*\*\*  <br/> |UDP 49 152 57 500  <br/> |
|云的连接器中介组件  <br/> |内部客户端  <br/> |TCP 49 152 57 500\*  <br/> |TCP 50,000-50,019  <br/> （可选）  <br/> |
|云的连接器中介组件  <br/> |内部客户端  <br/> |UDP 49 152 57 500\*  <br/> |UDP 50,000-50,019  <br/> |
|内部客户端  <br/> |云的连接器中介组件  <br/> |TCP 50,000-50,019  <br/> |TCP 49 152 57 500\*  <br/> |
|内部客户端  <br/> |云的连接器中介组件  <br/> |UDP 50,000-50,019  <br/> |UDP 49 152-57 500\*  <br/> |
   
\*这是中介组件上的默认端口范围。 为获得最佳呼叫流，每个呼叫需要四个端口。
  
\*\*必须将此端口配置 SBC/PSTN 网关;5060 是一个例子。 您可以在 SBC/PSTN 网关上配置其他端口。
  
\*\*\*请注意，还可以限制的端口范围在 SBC/网关是否允许 SBC/网关版制造商。
  
为安全起见，您可以通过[设置 CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) cmdlet 限制中介组件的端口范围。
  
例如，以下命令限制中介组件将使用为 50 000-51 000 音频媒体通信 （入和出） 的端口数。 中介组件使用此配置能够处理 250 个并发呼叫。 请注意，您可能还需要在 SBC/PSTN 网关上限制此范围：
  
```
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

检索并将中介组件的名称，请参阅默认端口，可以按以下方式使用[Get CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) cmdlet:
  
```
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表显示端口并启用云接头边缘外部防火墙组件之间进行通信的端口范围。 此表显示了建议的最低配置。
  
在这种情况下，internet 的所有媒体通讯将通过在线边按如下都顺序： 用户结束点-\>在线边缘-\>云接头边缘：
  
**外部防火墙的最低配置**



|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云接头边缘外部接口  <br/> |任何  <br/> |TCP(MTLS) 5061  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP(MTLS) 5061  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任何  <br/> |云接头边缘外部接口  <br/> |TCP 50,000-59,999  <br/> |TCP 443  <br/> |
|任何  <br/> |云接头边缘外部接口  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |TCP 50,000-59,999  <br/> |TCP 443  <br/> |
   
下表显示端口并启用云接头边缘外部防火墙组件之间进行通信的端口范围。 下表显示了建议的解决方案。
  
在这种情况下直接向云接头边缘组件可以流动，终点，在 internet 中的所有介质流量。 媒体路径将用户结束点-\>云接头边缘。
  
> [!NOTE]
> 如果用户终结点在对称 NAT 后面，此解决方案不适用。 
  
**外部防火墙的建议的配置**


|**源 IP**|**目标 IP**|**源端口**|**目标端口**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |云接头边缘外部接口  <br/> |任何  <br/> |TCP(MTLS) 5061  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP(MTLS) 5061  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |TCP 50,000-59,999  <br/> |任何  <br/> |
|云接头边缘外部接口  <br/> |任何  <br/> |UDP 3478；UDP 50,000-59,999  <br/> |任何  <br/> |
|任何  <br/> |云接头边缘外部接口  <br/> |任何  <br/> |TCP 443；TCP 50,000-59,999  <br/> |
|任何  <br/> |云接头边缘外部接口  <br/> |任何  <br/> |UDP 3478；UDP 50,000 - 59,999  <br/> |
   
### <a name="host-internet-connectivity-requirements"></a>主机 Internet 连接要求
<a name="BKMB_Ports"> </a>

主机必须可以访问外部的资源来成功地安装、 更新和管理云连接器。 下表显示了主机计算机与外部资源之间所需的目标和端口。 
  
||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|方向  <br/> |源 IP  <br/> |目标 IP  <br/> |源端口  <br/> |目标端口  <br/> |协议  <br/> |用途  <br/> |
|出站  <br/> |云的连接器主机 IPs  <br/> |任何  <br/> |任何  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|出站  <br/> |云的连接器主机 IPs  <br/> |任何  <br/> |任何  <br/> |80、 443  <br/> |TCP  <br/> |证书吊销列表 (CRL)  <br/> |
|出站  <br/> |云的 Connectorr 主机 IPs  <br/> |任何  <br/> |任何  <br/> |80、 443  <br/> |TCP  <br/> |云的连接器更新  <br/> Skype for Business Online  <br/> 管理 PowerShell  <br/> Windows 更新  <br/> |
   
如果需要限制性更强的规则，请参阅以下白名单 URL：
  
- 在[Office 365 的 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中的[证书吊销列表的 Url](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- Windows 更新：[如何配置防火墙获取软件更新](https://technet.microsoft.com/en-us/library/bb693717.aspx)
    
- 业务在线管理 PowerShell 的 Skype: \*。 online.lync.com
    
    如果需要为此目标设置代理排除，需要将其添加到 WinHTTP 绕过列表中。
    
- 云的连接器更新：[下载中心](https://aka.ms/CloudConnectorInstaller)， [https://go.microsoft.com](https://go.microsoft.com)，和[http://download.microsoft.com](http://download.microsoft.com)
    
### <a name="dns-name-resolution-for-the-edge-component"></a>边缘组件的 DNS 名称解析
<a name="BKMB_Ports"> </a>

边缘组件需要解决 Office 365 提供服务的外部名称和其他云接头组件的内部名称。 
  
每个边缘组件都是具有面向外部和内部的接口的多宿主计算机。 云的连接器将部署在外围网络中的域控制器组件上的 DNS 服务器。 可以将边缘服务器指向内周边所有的名称解析的 DNS 服务器，但您需要启用云连接器 DNS 服务器来解析外部名称设置 DNS 区域包含外部引用的名称的查询的一个或多个 DNS A 记录查找其他公用 DNS 服务器。 
  
在 .ini 文件中，如果将相同域空间中网关的 FQDN 名称设置为你的 SIP 域，则将在外围网络内的 DNS 服务器中创建此 SIP 域的权威区域。 如果边缘服务器指向这台 DNS 服务器来解析名称，边缘将永远不会解决 _sipfederationtls。\<yourdomain\>呼叫流需要的 DNS 记录。 在这种情况下，Microsoft 建议您在要解决互联网名称查找，边缘外部接口提供 DNS 服务器并边缘的每个组件必须使用主机文件将其他云连接器组件名称解析为 IP 地址。
  
> [!NOTE]
> 出于安全原因，建议不要对内部服务器在生产域的名称解析指向云连接器 DNS 服务器。 
  
### <a name="determine-deployment-parameters"></a>确定部署参数
<a name="BKMK_SiteParams"> </a>

首先需要定义以下常见部署参数：
  

|**项目**|**说明**|**说明**|
|:-----|:-----|:-----|
|SIP 域  <br/> |SIP URI 的公司用户使用。 提供此部署将服务于的所有 SIP 域。 你可以有多个 SIP 域。  <br/> ||
|PSTN 网站数  <br/> |将部署的 PSTN 网站数。  <br/> ||
   
对要计划部署的每个 PSTN 网站，你需要在开始部署之前收集以下信息。 当更新 CloudConnector.ini 文件时，你需要提供此信息。
  
当配置网关信息时，请记住以下事项：
  
- 如果你只有一个网关，请在 .ini 文件中删除第二个网关的该部分。 如果网关超过两个，请按照现有格式添加新网关。
    
- 请确保 IP 地址和网关已安装的端口正确。
    
- 支持 PSTN 网关级别的高可用性、 保留备用网关或添加其它网关。
    
（可选）要将限制出站呼叫号码，LocalRoute 值的更新。
  


|**站点参数**|**说明**|**说明**|
|:-----|:-----|:-----|
|虚拟机域名  <br/> |云的连接器的内部组件的域名。 此域应不同于生产域。 该名称必须在所有云连接器设备上都是相同的。  <br/> 在.ini 文件中的名称:"VirtualMachineDomain"  <br/> |.local 域为首选。  <br/> |
|云的连接器的域控制器名称  <br/> |域控制器的名称。  <br/> 在.ini 文件中的名称:"服务器名"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|云的连接器的域控制器 IP/子网掩码  <br/> |域控制器的 IP 地址。  <br/> 在.ini 文件中的名称:"IP"  <br/> ||
|O365 联机服务 FQDN  <br/> |必须在大多数情况下，世界范围内 O365 实例的默认值。  <br/> 在.ini 文件中的名称:"OnlineSipFederationFqdn"  <br/> ||
|站点名  <br/> |Skype 业务网站的名称;例如，西雅图。  <br/> 在.ini 文件中的名称:"站点名"  <br/> 对于 1.4.1 版及更高版本，各个站点的站点名称不能相同，并且名称必须与 Office 365 中定义的 PSTN 站点（如果存在）匹配。 请注意，在站点中注册第一台设备时，将会自动创建 PSTN 站点。  <br/> ||
|HardwareType  <br/> 1.4.1 版及更高版本  <br/> |硬件类型。 默认值为“Normal”。 你也可以设置为“Minimum”。  <br/> ||
|国家/地区代码  <br/> |拨号的国家/地区代码。  <br/> 在.ini 文件中的名称:"国家/地区代码"  <br/> ||
|城市  <br/> |（可选） 的城市。  <br/> 在.ini 文件中的名称:"市/县"  <br/> ||
|省/市/自治区  <br/> |（可选） 的状态。  <br/> 在.ini 文件中的名称:"状态"  <br/> ||
|基本虚拟机 IP 地址  <br/> |可用于创建云连接器的所有虚拟机的 VHDX 临时基虚拟机的 IP 地址。 此 IP 应位于下一步中定义的相同企业外围网络子网内，需要 Internet 访问。 请务必定义企业默认网关和可路由到 Internet 的 DNS。  <br/> 在.ini 文件中的名称:"BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 1.4.1 版及更高版本  <br/> |Windows Server 更新服务 (WSUS) 的地址 — 用于托管 Microsoft 更新所提供的更新的 Intranet 服务器。  <br/> 如果不需要 WSUS，可以留空。  <br/> ||
|内部网络的子网掩码  <br/> |云的连接器配置 IP 网络云连接器组件之间的内部通信。 边缘也应连接到允许 Internet 连接的另一子网。  <br/> 在.ini 文件中的名称:"池的 VM 网络参数"下的"CorpnetIPPrefixLength"  <br/> ||
|外部网络的子网掩码   <br/> |对于边缘组件的外部网络。  <br/> 在.ini 文件中的名称:"池的 VM 网络参数"下的"InternetIPPrefix"  <br/> ||
|内部网络的交换机名称  <br/> |用于内部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"CorpnetSwitchName"  <br/> ||
|外部网络的交换机名称  <br/> |用于外部云连接器网络的交换机的名称。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"InternetSwitchName"  <br/> ||
|内部网络的默认网关  <br/> |此网关必须提供访问互联网 （互联网也需要设置 DNS 服务器） 并将内部云的连接器组件接口上配置。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"CorpnetDefaultGateway"  <br/> ||
|边缘组件的外部接口的默认网关  <br/> |将边缘组件的外部接口上配置。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"InternetDefaultGateway"  <br/> ||
|内部网络的 DNS 服务器  <br/> |将在临时虚拟机的内部接口上配置。 必须提供名称解析互联网名称。 不提供 DNS 服务器，而互联网连接将会失败，将无法完成部署。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"CorpnetDNSIPAddress"  <br/> ||
|边缘组件的外部接口的 DNS 服务器  <br/> |将边缘的外部接口上配置。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"InternetDNSIPAddress"  <br/> ||
|管理交换机名称。  <br/> |管理开关是一个临时的开关，将自动创建，并将被用于在部署期间云连接器的配置。 部署之后将自动断开连接。 它必须是不同的子网中云连接器使用的任何其他网络。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在.ini 文件中的名称： 虚拟机网络的池参数"下的"ManagementSwitchName"  <br/> ||
|管理子网地址/子网掩码  <br/> |管理子网是一个临时的子网将自动创建，并将被用于在部署期间云连接器的配置。 部署之后将自动删除。 它必须是不同的子网中云连接器使用的任何其他网络。  <br/> 在.ini 文件中的名称:"ManagementIPPrefix"和"虚拟机网络的池参数下的"ManagementIPPrefixLength"  <br/> ||
|中央管理存储 (CMS) 计算机  <br/> |用于中央管理存储 (CMS) 的单个 FQDN。 AD 域名将用于生成 FQDN。  <br/> 在.ini 文件中的名称:"服务器名称"下"参数为主要中央管理服务  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> （CMS 池名称 = 服务器名称）  <br/> |
|CMS 计算机 IP 地址  <br/> |CMS 服务器 （内部外围网络中） 的 IP 地址。  <br/> INI 文件中的名称:"IP"下"参数为主要中央管理服务  <br/> ||
|文件共享名称   <br/> |文件共享名是服务器上创建 CMS 的 Skype 业务复制数据 (例如，CmsFileStore)。  <br/> 在大多数情况下，可以使用建议的值。  <br/> 在.ini 文件中的名称:"CmsFileStore"下"参数为主要中央管理服务  <br/> ||
|中介组件库名称  <br/> |中介组件的池名称。 请仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> 在.ini 文件中的名称:"PoolName"下"参数的中介服务器池"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|中介组件名称  <br/> |中介组件 1 的组件名称。请仅输入 Netbios 名称。AD 域名将用于生成 FQDN。  <br/> 在.ini 文件中的名称:"池的中介服务器的参数"下的"服务器名"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|中介组件的计算机的 IP 地址  <br/> |中介组件 （在外围网络内部） 的内部企业网络 IP。  <br/> 在.ini 文件中的名称:"IP"下"参数的中介服务器池"  <br/> ||
|边缘池内部名称  <br/> |边缘组件的池名称。 请仅输入 Netbios 名称。 AD 域名将用于生成 FQDN。  <br/> 在.ini 文件中的名称:"InternalPoolName"下"参数的边缘服务器池"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|边缘服务器内部名称  <br/> |边缘组件的组件名称。请仅输入 Netbios 名称。AD 域名将用于生成 FQDN。  <br/> 在.ini 文件中的名称:"InternalServerName"下"参数的边缘服务器池"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|边缘服务器内部 IP   <br/> |内部外围网络边缘的 IP 组件与云连接器的其他组件进行通信。  <br/> 在.ini 文件中的名称:"InternalServerIPs"下"参数的边缘服务器池"  <br/> ||
|访问池外部名称  <br/> |访问边缘的名称；例如，AP。 此名称必须与为 SSL 证书提供的名称相匹配。 请仅输入 Netbios 名称。 SIP 域名将用于生成 FQDN。 池中的所有边缘组件将都使用一个外部的池名称。 一个边缘访问池，则需要每个 PSTN 站点。  <br/> 在.ini 文件中的名称:"ExternalSIPPoolName"下"参数的边缘服务器池"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> "sip"保留，并因此不能用作名称。  <br/> 生成的 FQDN 名称必须与为 SSL 证书提供的名称相匹配。  <br/> |
|外部 IP 的访问边缘  <br/> |外部边缘的 IP 组件-如果没有 NAT 可用，或者公用 IP 或转换 IP （请这两个地址如果指定映射）。  <br/> 在.ini 文件中的名称:"ExternalSIPIPs"下"参数的边缘服务器池"  <br/> ||
|媒体中继名称  <br/> |音频视频媒体中继边缘的名称；例如 MR。 一个外部池名称将用于池中的所有边缘组件。 一个边缘媒体中继池，则需要每个 PSTN 站点。  <br/> 在.ini 文件中的名称:"ExternalMRFQDNPoolName"下"参数的边缘服务器池"  <br/> |必须为 15 个字符或更少。请仅输入 Netbios 名称。  <br/> |
|外部媒体中继边缘的 IP  <br/> |当前仅支持一个 IP，因此这将是与访问边缘相同的 IP，为公用 IP 或映射的 IP（如果映射，请同时指定两个地址）。 可以是与访问边缘的边缘组件外部 IP 相同的地址。 请注意，如果边缘服务器位于 NAT 后面，你还需要指定下一个参数的值。  <br/> 在.ini 文件中的名称:"ExternalMRIPs"下"参数的边缘服务器池"  <br/> ||
|外部 IP 的媒体中继边缘 （如果边缘位于 NAT）  <br/> |如果您的边在 NAT 还需要指定公共地址的 NAT 设备后面。  <br/> 在.ini 文件中的名称:"ExternalMRPublicIPs"下"参数的边缘服务器池"  <br/> ||
|语音网关 1 品牌和型号  <br/> |指定 SBC/语音网关的品牌和型号。 请注意您可以从列表的测试设备在连接设备或 SIP 中继[https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)。  <br/> ||
|语音网关 2 使和模型 （如果有 2 个以上的网关，请复制此行）  <br/> |指定语音网关的品牌和型号。 请注意，可以将设备连接测试设备在列表中[https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)。  <br/> ||
|语音网关 1 名  <br/> |用于使用 AD 域生成计算机 FQDN。 如果将在中介组件和语音网关之间使用 TLS，则是必需的。 如果不打算使用 FQDN — — 例如，TLS，则不需要或语音网关不支持使用 FQDN (只有 IP) 连接，请指定。  <br/> ||
|语音网关 2 名 （复制这行如果有 2 个以上的网关）  <br/> |用于使用 AD 域生成计算机 FQDN。 如果将在中介组件和语音网关之间使用 TLS，则是必需的。 如果不打算使用 FQDN — — 例如，TLS，则不需要或语音网关不支持使用 FQDN (只有 IP) 连接，请指定。  <br/> ||
|语音网关 1 的 IP 地址  <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关 2 IP 地址 （如果有 2 个以上的网关这行的副本）  <br/> |语音网关的 IP 地址。  <br/> ||
|语音网关 1 端口 # （复制这行如果有 2 个以上的网关）  <br/> |语音网关的 SIP 中继将侦听，例如 5060 的端口。  <br/> ||
|语音网关 2 端口号  <br/> |语音网关的 SIP 中继将侦听，例如 5060 的端口。  <br/> ||
|语音网关 1 SIP 通信协议  <br/> |TCP 或 TLS。  <br/> ||
|语音网关 2 协议的 SIP 通信流 （复制这行如果有 2 个以上的网关）  <br/> |TCP 或 TLS。  <br/> ||
|与边缘组件之间传输的流量的外部媒体端口范围  <br/> |与边缘的外部接口之间传输的媒体流量的 TCP/UDP 端口范围。 必须始终从 50 000 开始。 有关详细信息，请参阅"端口和协议"。  <br/> |50000-59 999  <br/> |
|端口范围对中介组件通过内部防火墙通信  <br/> |中介组件的客户端和网关 （建议 4 端口每次调用） 通讯时使用的 UDP 端口范围。  <br/> ||
|端口范围对 Skype 业务通过内部防火墙的客户端通信  <br/> |出于规划目的，不可更改。 需要在 Skype 业务客户端在内部网络和与中介组件之间进行通信的内部防火墙中打开端口。  <br/> |50 000 - 50 019  <br/> |
|公用证书密码  <br/> |必须通过脚本提供。  <br/> ||
|安全模式管理员密码  <br/> 仅限于版本 1.4.2  <br/> |内部 CC 域的安全模式管理员密码。  <br/> ||
|云的连接器域管理员密码  <br/> 仅限于版本 1.4.2  <br/> |密码为云连接器的域管理员 （不同于生产域）。 用户名是 Administrator。 你不能更改用户名。  <br/> ||
|虚拟机管理员密码  <br/> 仅限于版本 1.4.2  <br/> |用于在部署过程中配置管理网络。  <br/> 用户名是 Administrator。你不能更改用户名。  <br/> ||
|CABackupFile  <br/> 2.0 版及更高版本  <br/> |用于保存证书颁发机构服务从 Active Directory 服务器到文件时部署云连接器站点中的多个应用装置。 确保要为一个云连接器站点内的所有设备使用相同的密码，以便将 CA 备份文件导入到新添加装置成功。  <br/> ||
|CCEService  <br/> 2.0 版及更高版本  <br/> |用于云连接器管理服务；需要访问云连接器站点目录。务必对一个云连接器站点内的所有设备使用相同密码。  <br/> ||
|Office 365 租户管理员  <br/> | 云连接器使用该帐户来更新和管理云连接器的租户设置： <br/>  2.0 及更高版本： 专用的 Office 365 的凭据与 Skype 业务管理员权限帐户。 <br/>  2.0 之前的版本：具有全局租户管理员权限的专用 Office 365 帐户的凭据。 <br/> ||
|启用 Refer 支持  <br/> |这将定义在你的 IP/PBX 的中继配置上启用还是禁用 SIP REFER 支持。 默认值为 True。 如果你的 IP/PBX 网关提供 REFER 支持，请将此值保留为 true。 否则，需要将此值更改为 False。 如果您不确定是否您的网关支持引用，请参见[限定 IP Pbx 和网关](https://technet.microsoft.com/en-us/office/dn788945)。  <br/> ||
|EnableFastFailoverTimer  <br/> 2.0 版及更高版本  <br/> |使用默认值"真"，如果出站呼叫没有应答由网关在 10 秒内它们将被路由到下一个可用的网关;如果不有任何其他中继然后将自动除去该调用。  <br/> 但是，在网络和网关响应较慢的组织中，或者当建立呼叫的过程超过 10 秒时，这可能会导致不必要的呼叫丢弃。  <br/> 当呼叫一些国家，例如阿拉伯联合酋长国或阿富汗，建立过程的调用可以取得超过 10 秒钟。 您将需要将值更改为 False 如果遇到类似的问题。 请不要忘记更改相应的设置在连接 SBC 或网关。  <br/> 值可以为 True 或 False。默认值为 True。  <br/> ||
|ForwardCallHistory  <br/> 2.0 版及更高版本  <br/> | 此参数用于启用报告同时响铃、呼叫转接和呼叫转移场景中的初始呼叫方的 SIP 头。将此参数设置为 True 将启用两个 SIP 头：<br/>  History-Info <br/>  Referred-By <br/>  历史记录信息标头用于重定向 SIP 请求，"provide(s) 标准的机制，用于捕获请求历史记录信息使各种网络和终端用户服务"([RFC 4244-1.1 节](http://www.ietf.org/rfc/rfc4244.txt))。 对于云连接器中继接口，此头用于同时响铃和呼叫转接场景。  <br/>  值可以为 True 或 False。默认值为 False。<br/> ||
|转发 PAI  <br/> 2.0 版及更高版本  <br/> |PAI 是一个私有扩展启用断言的已验证用户身份的 SIP 服务器的 sip。 SIP 中继提供商，PAI 可能用于寄帐单到目的的历史记录信息和推荐由头都不存在。 中介服务器配置中启用转发 P-断言的标识时，会将转发 PAI 标头包含 SIP &amp; Tel URI 的 SIP 中继到云接线。 中介服务器将转发 PAI 标头包含 tel URI &amp; E.164 号码只能接收 SIP 中继到云连接器上。 中介服务器还将接收两个方向的任何隐私头。 如果 SIP 请求中介服务器发送包含窗体-隐私头"隐私： id"配合 PAI 头，然后断言的标识应保留为私有的网络信任域之外。  <br/> 值可以为 True 或 False。默认值为 False。  <br/> ||
   
### <a name="certificate-requirements"></a>证书要求
<a name="BKMK_Certs"> </a>

每个边缘组件都需要来自公共证书颁发机构的证书。 证书必须具有可在边缘组件之间复制的可导出私钥。 要满足证书要求，你需要在以下选项之间做出选择并为证书提供使用者名称 (SN) 和使用者可选名称 (SAN)。
  
 **如果你有单个 SIP 域：**
  
- **选项 1.** 使用者名称应包含你为边缘组件分配的池名称。 请注意，因为此名称已保留为在线 Skype 业务优势组件，使用者名称不能为 sip.sipdomain.com。 SAN 应包含 sip.sipdomain.com 和访问边缘池名称：
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, 
acessedgepoolnameforsite1.sipdomain.com 

  ```

- 
    
    **选项 2.** 如果您想要使用一个通配符证书所有边缘池服务器部署时，则可以都使用通配符 SAN 项的\*。 而不是证书中的边缘池名称 sipdomain.com。 使用者名称可以是你部署的任何一个边缘池的访问边缘池名称：
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com

  ```

    > [!NOTE]
    > 您必须创建 sip 的外部 DNS 条目。\<sipdomain\>.com 因为此名称所属到 Office 365 的部署。 
  
> [!NOTE]
> 如果你要为你的组织中部署的所有边缘池使用单个证书且不能使用选项 2 中定义的通配符证书，那么你需要在证书的 SAN 名称中包括用于所有部署边缘池的 FQDN。 
  
 **如果你有多个 SIP 域：**
  
你需要为每个 SIP 域添加 sip.sipdomain.com，以及添加每个域的访问边缘池的名称（它可以是一个物理池，但是名称不同）。 下面是多个 sip 域方案中的 SN 和 SAN 条目示例： 
  
- **选项 1.** 使用者名称必须包含您的边缘组件分配的池名称。 请注意，因为此名称已保留为在线 Skype 业务优势组件，使用者名称不能为 sip.sipdomain.com。 SAN 应包含 sip.sipdomain.com 和访问边缘池名称：
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com,
 sip.sipdomain2.com, acessedgepoolnameforsite1.sipdomain1.com 

  ```

- 
    
    **选项 2。**如果您想要使用一个通配符证书所有边缘池服务器部署时，则可以都使用通配符 SAN 项的\*。 而不是证书中的边缘池名称 sipdomain.com。 使用者名称可以是你部署的任何一个边缘池的访问边缘池名称：
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com, SAN = *.sipdomain1.com 
  ```

    > [!NOTE]
    > 您必须创建 sip 的外部 DNS 条目。\<sipdomain\>.com 因为此名称所属到 Office 365 的部署。 
  
出于部署目的，您可以使用下表：
  
|**选项**|**说明**|**说明**|
|:-----|:-----|:-----|
|将对您的部署使用哪个选项？  <br/> |选项 1 或 2  <br/> ||
|SN  <br/> |为您的证书提供 SN  <br/> ||
|SAN  <br/> |为您的证书提供 SAN  <br/> ||
   
如果你要在网关与中介服务器之间使用 TLS，则需要获取分配给网关的证书的根证书或完整证书链。
  
## <a name="dial-plan-considerations"></a>拨号计划注意事项
<a name="BKMK_DailPlan"> </a>

云连接器需要使用在线拨号计划。 有关如何配置联机拨号计划的详细信息，请参阅[调用 PSTN 拨号计划是什么？](https://support.office.com/en-US/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)
  
## <a name="high-availability-considerations"></a>高可用性注意事项
<a name="BKMK_HA"> </a>

针对高可用性部署云连接器版时，您将部署至少两个彼此作为备份的装置。 每个装置由四个部分组成： 边缘、 调解、 中央管理存储 (CMS) 和域控制器。
  
一般情况下，如果在一台装置中的一个组件出现故障，云连接器版可以继续处理请求，但您必须考虑以下：
  
- **中介、CMS 和域控制器组件注意事项**
    
    假设一台设备中的 CMS 或域控制器组件关闭。 该设备仍可以处理入站和出站呼叫，但是如果你在域控制器或 CMS 组件不可访问时重新启动中介组件，中介组件将无法正常工作。 在域控制器关闭时重新启动 CMS 组件，同样存在此问题。 
    
    **建议：**重新启动前组件，检查装置中的其他组件的可用性。
    
- **边缘组件注意事项**
    
    如果一台设备中的边缘组件不可用，则入站和出站呼叫的行为将有所不同，如下所示：
    
  - **出站调用**— — 从您的用户在互联网连接到 PSTN 网络调用。
    
    云中的呼叫分配机制将确定一个边缘组件已关闭，并将所有呼叫都路由到另一台设备，因此出站呼叫将会成功。
    
  - **入站调用**— — 在本地网络或 Internet 的用户从 PSTN 网络调用。
    
     如果不使用接收呼叫装置的边缘部分，对此装置的入站的调用将会失败，因为中介组件无法重定向其他装置的边缘组件的调用。
    
    **建议：**监视系统已经就位。 标识边缘组件故障后，请关闭设备中的所有组件边缘组件不可用。
    
## <a name="cloud-connector-media-flow"></a>云连接器媒体流
<a name="BKMK_MediaFlow"> </a>

下图概述了流云连接器版通过出站和入站调用。 此信息有助于理解连接的建立方式。
  
在第一个图中，内部用户拨打出站呼叫，如下所示：
  
1. Dave，用户驻留在线，但现在在内部网络中，放置到外部 PSTN 用户调用的。
    
2. SIP 通信量路由到 Skype 的在线业务。
    
3. Skype 的在线业务执行数的反转编号查找。 反向编号搜索失败，因为此编号不属于 Skype 业务的组织中的任何人。
    
4. 呼叫被路由到边缘组件 （SIP 和媒体流通过在线边第一次;媒体将转到中介组件通过内部防火墙）。
    
5. 如果路由路径存在，边缘组件中继到中介组件的外围网络中的通信。
    
6. 中介组件将流量发送到 PSTN 网关。
    
![云连接器的出站媒体流](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)
  
在下个图中，内部用户接收入站呼叫，如下所示：
  
1. PSTN 网关接收用户 Dave 主联机，但是现在只是在内部网络中的调用。
    
2. SIP 通信被路由到中介组件。
    
3. 中介组件发送 SIP 通信到边缘组件，然后它将转到 Skype 的在线业务。
    
4. Skype 的在线业务执行数的反转编号查找，并发现这是用户 Dave。
    
5. SIP 信号将转到 Dave 的所有状态点。
    
6. 将在网关和中介组件之间以及中介组件和终结点之间建立媒体流量。
    
![云连接器的入站媒体流](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)
  
## <a name="monitoring-and-troubleshooting"></a>监视和故障排除
<a name="BKMK_Monitor"> </a>

每台云连接器设备都会自动安装监视和故障排除机制。该机制会检测下列事件：
  
- 云连接器设备的一个或多个虚拟机未连接到内部或 Internet 虚拟交换机。
    
- 云连接器设备的一个或多个虚拟机处于已保存或已停止状态。
    
- 未运行的服务。 
    
  如果检测到以下事件之一时，整个云接头装置是将断开，而且标记为脱机，以防止尝试建立对出现故障的装置。 随后，云连接器自动恢复功能将还原服务并将设备标记为在线。 如果由于某种原因失败自动恢复，请参阅[疑难解答云连接器部署](troubleshoot-your-cloud-connector-deployment.md)。
    
  - 在中央管理存储虚拟机上： 
    
     - Skype for Business 主复制器代理
    
     - Skype for Business 备份复制器代理
    
  - 在中介服务器虚拟机上：
    
     - Skype for Business 备份复制器代理
    
     - Skype for Business Server 中介
    
  - 在边缘服务器虚拟机上：
    
     -  Skype for Business 备份复制器代理
    
     -  Skype for Business Server 访问边缘
    
     - Skype for Business Server 音频/视频边缘
    
     - Skype for Business Server 音频/视频验证
    
     - Skype for Business Server Web 会议边缘
    
- 边缘服务器上“CS RTCSRV”的 Windows 防火墙和中介服务器上的“CS RTCMEDSRV”的入站规则已禁用。
    
云连接器 2.1 及更高版本支持使用 Operations Management Suite (OMS) 监视云连接器。 有关详细信息，请参阅[使用操作管理套件 (OMS) 的显示器云接头](monitor-cloud-connector-using-operations-management-suite-oms.md)
  
## <a name="for-more-information"></a>详细信息
<a name="BKMK_MoreInfo"> </a>

有关详细信息，请参阅以下文章：
  
- [规划在 Office 365 (云 PBX) 解决方案电话系统](plan-your-phone-system-cloud-pbx-solution.md)
    
- [配置和管理 Skype 业务云连接器版](configure-skype-for-business-cloud-connector-edition.md)
    
- [计划在云连接器版的媒体跳过](plan-for-media-bypass-in-cloud-connector-edition.md)
    
- [部署云连接器版中的媒体回避](deploy-media-bypass-in-cloud-connector.md)
    

