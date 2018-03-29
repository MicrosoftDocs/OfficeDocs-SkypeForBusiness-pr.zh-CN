---
title: Skype 业务混合解决方案
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0b038686-ed36-4867-9653-14cc08c919cb
description: 查找有关规划业务混合部署 Skype。
ms.openlocfilehash: c2ed5a488bae74e1756ca02b0b28e9770efe0160
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-hybrid-solutions"></a>Skype 业务混合解决方案
 
查找有关规划业务混合部署 Skype。 
  
本主题介绍几种混合配置，以帮助确定哪种配置最适合你的企业。 然后，你可以通过使用本主题中的链接阅读有关感兴趣的配置的详细信息。 本主题包含以下部分：
  
- [Skype for Business 混合配置](skype-for-business-hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [添加到您现有的在线业务 Skype 内部 Skype 的业务环境](skype-for-business-hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [在 Office 365 (云 PBX) 中利用电话系统](skype-for-business-hybrid-solutions.md#BKMK_CloudPBX)
    
- [与 Exchange 和 SharePoint 集成](skype-for-business-hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [规划和配置混合环境的任务](skype-for-business-hybrid-solutions.md#BKMK_Tasks)
    
- [有关详细信息](skype-for-business-hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Skype for Business 混合配置
<a name="BKMK_HybridConfigurations"> </a>

Skype 的业务支持几种混合配置。 您可以添加 Skype，到您现有的在线业务内部 Skype 的业务环境中的、 集成您的业务部署的 Exchange 联机和 SharePoint Online，Skype 和利用 Office 365 (云 PBX) 中的电话系统 — — 微软启用在线业务的呼叫控制和 Skype 与 Office 365 云中的专用分组交换机 (PBX) 功能的技术。 
  
与业务混合部署 Skype，您组合业务服务您内部 Skype 与 Skype 业务在线预订的。 您可以开始构建您的组织中的软件作为服务管理技能并将您适用于业务用户的 Skype 在您自己的节奏移动到云。 您在云中托管的用户可以利用电话系统的 Office 365 中同时保留内部公共交换电话网络 (PSTN) 连接。
  
与业务混合配置的 Skype，记住以下：
  
- 部分用户可能驻留在本地，而其他用户可能驻留在线上，但这些用户共享同一个会话初始协议 (Session Initiation Protocol, SIP) 域（例如 contoso.com）。
    
- 您可以将用户迁移从 Skype 为内部部署的业务到 Skype 的在线业务随着时间的推移在日程上。
    
- 可以与其他 Microsoft Office 365 应用程序集成，包括 Exchange Online 和 SharePoint Online。
    
- 可以与 Exchange 和 SharePoint 集成。
    
- 可以利用 Skype 会议直播。
    
- 可以利用 PSTN 会议。
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>添加到您现有的在线业务 Skype 内部 Skype 的业务环境
<a name="BKMK_HybridConnectivity"> </a>

Skype 业务服务器和 Skype 的在线业务之间的混合连接意味着用户的域，如 contoso.com，都分为使用 Skype 业务服务器上部署和 Skype 的在线业务。 部分域用户驻留在本地，而另一部分用户驻留在线上。 可以配置内部部署的混合与 Skype 在线业务，并使用活动目录同步来保证您的内部部署和联机同步的用户。 
  
下图显示了如何添加 Skype 的在线业务到允许您将用户移动到您自己的节奏在云中您现有的业务环境中，内部 Skype:
  
![Skype for Business 混合配置](../media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](plan-hybrid-connectivity.md)和[部署混合来临 Skype 业务服务器和 Skype 的在线业务](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>利用 Office 365 中的电话系统（云 PBX）
<a name="BKMK_CloudPBX"> </a>

 在 Office 365 (云 PBX) 的电话系统是微软技术启用在线业务的呼叫控制和 Skype 与 Office 365 云中的专用分组交换机 (PBX) 功能。 Office 365 中的电话系统允许您替换现有的 PBX 系统一套功能从 Office 365 提供并紧密地集成到微软云生产力的经验。
  
除了两个电话系统在 Office 365 的混合产品，Microsoft 提供了调用计划与 Office 365 中的电话系统 — — PSTN 呼叫服务 — — 不需要内部服务器部署全云解决方案。 决定如果调用计划与 Office 365 中的电话系统可能适合您的组织的解决方案，请参阅[在 Office 365 提供解决方案的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)。
  
Office 365 混合产品中有两个电话系统： 
  
- [在 Office 365 提供您 Skype 业务服务器部署的内部连接的电话系统](skype-for-business-hybrid-solutions.md#BKMK_Server)
    
- [在 Office 365 商务服务器云连接器版 Skype 所提供的内部连接的电话系统](skype-for-business-hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>由 Skype for Business Server 部署提供本地连接的 Office 365 电话系统
<a name="BKMK_Server"> </a>

此配置包括修改了混合 PSTN 的业务服务器内部部署 Skype。 在云中托管您的组织中的用户能够接收来自 Microsoft 云的 PBX 服务但 PSTN 连接通过内部部署 Skype 上的企业语音提供业务服务器部署。 
  
![云 PBX 与 Skype for Business Server 部署](../media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
此配置最适用于以下情况： 
  
- PBX 未提供你需要保留的独特功能。
    
- 呼叫计划即 Office 365 PSTN 呼叫服务在你的区域中不可用。
    
- 您具有现有 Lync 或 Skype 业务服务器部署。
    
有关详细信息，请参阅[规划与 Office 365 中的电话系统部署 Skype 业务服务器中的 PSTN 连接](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)并[使用户具有内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统](plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md)。
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>由 Skype for Business Server 云连接器版本提供本地连接的 Office 365 电话系统
<a name="BKMK_CCE"> </a>

此配置包含一组实施本地 PSTN 连接的已打包虚拟机 (VM)。 通过部署在虚拟化环境中的业务服务器拓扑结构的最小 Skype，在云中托管您的组织中的用户能够接收来自 Microsoft 云的 PBX 服务但 PSTN 连接提供通过现有内部声音基础结构。 
  
![CloudPBXCloudConnectorEdition](../media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
此配置最适用于以下情况：
  
- PBX 未提供你需要保留的独特功能。
    
- 呼叫计划即 Office 365 PSTN 呼叫服务在你的区域中不可用。
    
- 您没有现有 Lync 或 Skype 业务服务器部署。
    
有关详细信息，请参阅[规划业务云连接器版 Skype](plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)。
  
## <a name="integrate-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Skype 业务混合配置，可与其他 Microsoft Office 365 提供应用程序，包括 Exchange 联机和 SharePoint Online 集成。
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype for Business Server 与 Exchange Online 和 SharePoint Online

下面的关系图中所示，您可以将 Skype 集成为 Exchange 联机和 SharePoint Online 具有的业务服务器：
  
![Skype for Business Server 与 Exchange Online 和 SharePoint Online](../media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
集成业务服务器与 Exchange 联机和 SharePoint Online Skype 有几个优点。 您可以：
  
- 为业务服务器使用 Skype 的完整功能集。
    
- 利用现有的本地电话设备，例如 PBX。
    
- 使用 Exchange Online 来处理电子邮件，从而卸载本地电子邮件服务器和存储的负担。
    
- 使用 SharePoint Online 进行协作，从而卸载维护本地 SharePoint 服务器的负担。
    
- 使用 Skype 业务、 交换和 SharePoint 集成功能，包括统一邮件 (UM) Office 365 中。
    
有关详细信息，请参阅[计划集成 Skype 业务和交换](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server 与 Skype for Business Online

您可以集成 Exchange Server 使用 Skype 的在线业务如下图中所示：
  
![将 Exchange 与 Skype for Business Online 集成](../media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
与 Skype 的 Exchange Server 集成的在线业务有下列优点：
  
- 利用现有的 Exchange 基础结构。
    
- 使用 Skype 业务联机状态、 IM 和会议功能。 
    
有关详细信息，请参阅[计划集成 Skype 业务和交换](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>规划和配置混合环境的任务
<a name="BKMK_Tasks"> </a>

Skype 为业务提供了一组丰富的功能无论您构建您的部署体系结构。 所选架构将决定你应承担的 IT 职责，以及你通过订阅雇用 Microsoft 为哪些职责提供支持。 无论哪个架构最适合你的组织，你始终都应承担以下五项核心职责：
  
- **网络连接和连接**-确保网络容量和可用性通过防火墙、 代理服务器、 网关和跨越广域网链路，通过执行网络评估或与合作伙伴进行评估。
    
- **数据治理&amp;权限管理**-分类您的敏感数据，并确保它是受保护并监视无论它存储和传输中时。
    
- **客户端终结点**的建立、 测量，并实施现代安全标准用于访问数据和资产的设备上。
    
- **的帐户&amp;访问管理**-建立"正常"的帐户活动的配置文件，并通知关于不寻常的活动。
    
- **标识** - 对所有标识使用受硬件保护的凭据或多重身份验证 (Multi-Factor Authentication, MFA)。
    
除了为本地环境执行的架构任务之外，你还需要执行以下任务：
  
- 规划和设计标识管理要求，包括将本地标识与 Office 365 集成。
    
- 确保网络容量和可用性。
    
- 获取第三方 SSL 证书，以便为 Office 365 服务产品提供企业安全。
    
- 确定是否要使用 Internet 协议版本 6 (IPv6) 连接到 Office 365。
    
- 确定需要与内部部署和联机版本的 Skype 业务、 交换和 SharePoint 多少功能集成。 
    
- 确定哪个代理服务器设备将用于处理来自 Office 365 的请求。
    
您还需要执行以下 IT 专业人员的任务，以实现您的业务混合环境 Skype:
  
- 确保您具有 Microsoft Office 365 承租人与 Skype 业务在线启用。
    
- 实施标识管理计划。 
    
- 规划并实施内部和外部 DNS 记录与路由。
    
- 针对 Office 365 IP 地址和 URL 要求对代理或防火墙进行配置。
    
- 管理用户帐户和 Skype 的在线业务设置。 
    
- 根据需要配置代理服务器服务。 
    
- 配置与 Exchange Server 和 SharePoint 的本地版本和联机版本的功能集成。
    
## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_MoreInfo"> </a>

有关详细信息，请参阅以下资源：
  
- [Microsoft 云 IT 体系结构资源](https://aka.ms/clouditarch)
    
- [企业架构师的 Microsoft 云标识](https://aka.ms/cloudidarch)
    
- [做好组织准备为 Office 365 的企业](https://aka.ms/O365EntPrep)
    
- [计划 Skype for Business Server 与 Skype for Business Online 之间的混合连接](plan-hybrid-connectivity.md)
    
- [部署企业服务器的 Skype 和 Skype 的在线业务之间的混合连接](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- [在 Office 365 提供解决方案的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [计划以落实 Skype 业务和交换](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
如果要下载本主题的海报版本，请访问以下网址：
  
- [Skype 的业务体系结构模式 (pdf)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype for Business Architectural Models.pdf)
    
- [Skype 的业务体系结构模式 (Visio)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype for Business Architectural Models.vsd)
    

