---
title: 团队联系人中心
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: 作为服务的集成联系人中心概述 (CCaaS) Microsoft 团队的解决方案
appliesto:
- Microsoft Teams
ms.openlocfilehash: ccd4456b006d8b27fd0aa2ec88d6467fe86fea8b
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322281"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Microsoft 团队的联系中心集成

将常用的联系人中心解决方案与 Microsoft 团队集成是客户部署团队呼叫功能的一个常见需求。  本文概述了联系中心解决方案如何与 Microsoft 团队集成，以及有关参与 Microsoft 团队连接的合作伙伴解决方案的其他信息。

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>什么是 Microsoft 团队的联系中心集成？

当今的联系人中心不仅提供支持，而且它们充当一种主要机动车，用于与客户的品牌进行交互和未筛选的反馈。 由于今天的客户希望通过电话、电子邮件、文本、社交以及与目前购买过程相关的接触点的扩展量，许多组织已经实现了另外两个现实：

1. 组织的每个成员都有可能参与直接吸引客户，因此需要配备相应的工具。

2. 此扩展的客户交互作用范围需要可帮助推动一致性、持续改进和规模的工具。

Microsoft 团队通过在其通信模式（包括聊天、视频会议和通话）上充当内部和外部客户连接的中心，支持客户交互工作流。 对于某些公司，Microsoft 团队的 [云语音功能](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)（包括 [自动助理](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) 和 [呼叫队列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)）提供功能和配置以满足其需求。

对于需要集成解决方案和工作流以推动客户旅行的其他人而言，Microsoft 团队还会与业界领先的一些联系人中心集成，作为服务 (CCaaS) 解决方案提供商。

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Microsoft 团队认证计划的已连接联系人中心

允许合作伙伴开发和集成 CCaaS 解决方案的 Api 可通过高级通信许可证获得。 此外，我们已经开发了 Microsoft 团队认证计划的已连接联系人中心，让客户能够确保每个参与伙伴的解决方案都经过测试和验证，以提供他们从 Microsoft 解决方案所期望的质量、兼容性和可靠性。

以下合作伙伴正在验证其适用于 Microsoft 团队的解决方案并已准备好参与客户：

| **配偶**                                                                                                                              | **解决方案网站**                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| Competella | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| ContactCenter4All | https://docs.microsoft.com/microsoftteams/teams-contact-center#connected-contact-center-for-microsoft-teams-certification-program |
| Enghouse 交互式 | http://www.enghouseteams.com/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genesys | https://www.genesys.com/microsoft                                                                                   |
| Landis 技术 | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| Luware | https://luware.com/en/solutions/                                                                                       |
| 真 inContact | https://www.niceincontact.com/microsoft-teams                                                            |
| Tendfor | https://www.tendfor.com/en/                                                                                     |

此列表将随着更多合作伙伴加入和满足认证标准而更新。

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>联系人中心解决方案在 Microsoft 团队中是如何工作的？

Microsoft 团队提供了一系列支持第三方语音解决方案开发的功能，包括：

1. [直接路由连接](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [Microsoft Graph 云通信 Api](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. 团队平台和扩展性

4. 团队 Sdk

这些功能共同支持3种集成模型：

  - 通过直接路由) **连接** (

  - **连接和扩展** (直接路由、图形 Api 和团队应用平台) 

  - **扩展和** (将团队 sdk 嵌入到本机团队交互的3p 应用中) 

### <a name="connect"></a>联系

此模型将 CCaaS 合作伙伴与 Microsoft 团队手机系统基础结构联系起来，从而支持增强的路由、配置和系统见解。 在此模型中，联系人中心合作伙伴解决方案还可以为所选号码和用户提供电话服务。

使用在 Connect 模型上构建的解决方案的代理可以 & 见解收集信息，并根据需要直接将呼叫转移到主题专家，从而利用 SME 在团队中的存在以确保其可用性。

组织可以通过设置自动化的虚拟助理和基于技能的路由队列，确保呼叫能够路由到最佳代理。

**功能要点：**

虽然以下内容不是此集成模型的一个完整功能列表，但焦点区域包括：

  - Office 365 authN for agent 允许代理从其集成的 CCaaS 客户端连接到其 Microsoft 租户 

  - 来自团队用户的状态指示 

  - 按测试计划中的指示，通过直接路由 (进行呼叫流程)  

  - 支持与团队用户进行转移和群组通话 

  - 团队图形 Api 和云通信 Api 与团队集成 

  - 能够支持多租户 SIP 中继以支持合作伙伴的 SBC 的多个客户。  

  - 合作伙伴实现[ <span class="underline">Microsoft 认证会话边界控制器 (SBC) </span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>连接和扩展

此模型通过将团队客户端与团队客户端 [平台](https://docs.microsoft.com/microsoftteams/platform/overview)、 [团队图 Api](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和 [云通信 API 与 Microsoft Graph 中](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 的团队客户端集成，并使用团队电话系统进行所有联系人中心通话和通话控制体验，从而延长了联系中心人员和代理体验。 在此模型中，联系人中心合作伙伴作为电话运营商，与 Microsoft 365 一起使用。

利用连接和扩展的解决方案，代理可以从多个系统中的数据与多个系统中的数据相关联，然后在内部协作和外部通信的团队内部工作，从而避免昂贵的上下文切换。

组织可以向个人设计工作流和高级路由配置，并衡量其系统和交互的质量。

**功能要点：**

虽然以下不是此集成模型的功能的完整列表，但它确实突出显示了主要重点领域：

  - 团队图形 Api 和云通信 Api 与团队集成 

  - 针对代理体验的基于团队的应用 

  - 作为代理的主调用终结点的团队 

  - 团队客户端呼叫所有呼叫控件

  - 代理体验应用应该能够同时处理团队 web 和移动客户端

  - 针对团队内 CCaaS 应用中的代理的分析、工作流管理、基于角色的体验

  - 与团队客户集成的聊天和协作体验 

  - 保留团队的性能和质量在所有应用中的客户体验  

### <a name="extend-and-power"></a>延长和增强

此模型使合作伙伴能够利用调用基础结构和客户端平台的团队创建基于本地 Azure 的语音应用程序，为协作客户和代理连接提供新式的智能解决方案。 扩展和功能的目标是 stoke 开发人员创意，推动客户的工作效率。

通过直接在 Azure 上构建，合作伙伴可以在所有团队区域和地域之间快速部署和配置其解决方案，benefitting 来自共享的全球通信网络，同时充分利用 Azure 存储、计算、分析 & 认知服务。

使用 "扩展" 和 "电源集成" 模型，合作伙伴可以提供具有全方位通道通信体验的联系中心代理，同时还可以通过结合人工智能来自定义参与者或其他服务在 [Microsoft Graph 中使用云通信 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的通话方式和时间。

**功能要点：**

虽然以下内容不是此集成模型的功能的完整列表，但除了连接模型和扩展模型提供的功能之外，这些突出显示区域。

  - 正式代理通过团队 SDK 通过 "全频道通信" 体验 

  - 利用团队协作服务进行代理协作和客户交互  

  - 快速调配云服务，随时随地部署 

  - 团队对话期间与用户进行直接对话控制和交互 

### <a name="comparing-connected-contact-center-integration-models"></a>比较连接的联系人中心集成模型

请查看下表，了解 Microsoft 团队支持的集成模型的概述。

<table>
<thead>
<tr class="header">
<th></th>
<th><strong>团队语音应用</strong></th>
<th><strong>联系</strong></th>
<th><strong>Connect + extend</strong></th>
<th><strong>延长 + power</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>云服务模型</td>
<td>Azure</td>
<td>配偶</td>
<td><p>合作伙伴 +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>谁在操作该解决方案？</td>
<td>Microsoft</td>
<td>配偶</td>
<td>配偶</td>
<td>配偶</td>
</tr>
<tr class="odd">
<td>M365 登录</td>
<td>是</td>
<td>是</td>
<td>是</td>
<td>是</td>
</tr>
<tr class="even">
<td>有团队通话的用户？</td>
<td>非正式、SME</td>
<td>非正式、SME</td>
<td>非正式、SME、正式</td>
<td>非正式、SME、正式</td>
</tr>
<tr class="odd">
<td>IW/SME 体验</td>
<td>Teams</td>
<td>Teams</td>
<td><p>团队 +</p>
<p>扩充</p></td>
<td><p>团队 +</p>
<p>扩充</p></td>
</tr>
<tr class="even">
<td>服务连接性</td>
<td>平台<br />
 (通话计划 + DR) </td>
<td>直接路由</td>
<td>直接路由</td>
<td>平台<br />
 (通话计划 + DR) </td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>后续步骤

如果您是希望加入认证计划的供应商，请通过电子邮件发送电子邮件 <Teamscategorypartner@microsoft.com> 。
