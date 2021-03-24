---
title: Microsoft 电话解决方案
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
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
description: 了解 Microsoft 的电话解决方案：电话系统 (专用交换机 - PBX) 和 PSTN 连接选项 (通话套餐和直接路由) 。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 4fa6b04fba5b9dbea30cfeeb9e347cf542f07d38
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110588"
---
# <a name="microsoft-telephony-solutions"></a>Microsoft 电话解决方案

当你开始在 Microsoft 云中开始使用 Teams 时，Microsoft 支持多个选项。 本文帮助您决定哪种 Microsoft 电话解决方案 (Phone System in the cloud 或 企业语音 on-premises) 适合您组织的用户，以及您的组织如何连接到公用电话交换网 (PSTN) 。

您应该将本文与关联的技术图表一同使用，该图表为贵组织做出正确的决策提供了视觉帮助：

- [Microsoft 电话解决方案 - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Microsoft 电话解决方案 - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>专用交换机 (PBX) 选项

### <a name="phone-system-microsoft-365-or-office-365"></a>Microsoft 365 (Office 365 电话系统) 
  
电话系统是 Microsoft 的技术，用于通过 Microsoft Teams 和/或 Skype for Business Online 在 Microsoft 365 或 Office 365 云中启用呼叫控制和专用交换机 (PBX) 功能。

电话系统适用于 Teams 或 Skype for Business Online 客户端和认证设备。 电话系统允许你将现有 PBX 系统替换为直接从 Microsoft 365 或 Office 365 提供的一组功能，并紧密集成到公司的云生产力体验中。 若要将电话系统连接到 PSTN (公用电话) ，可以选择 Microsoft 的呼叫计划或您自己的电话运营商。

有关详细信息，请参阅什么是 [Microsoft 365 或 Office 365 中的电话系统](/MicrosoftTeams/what-is-phone-system-in-office-365)。

### <a name="enterprise-voice-skype-for-business-server"></a>企业语音 (Skype for Business Server) 

企业语音是 Microsoft 用于在本地 Skype for Business Server 中启用呼叫控制和专用交换机 (PBX) 功能的技术。 此 Skype for Business 选项只能使用你自己的电话运营商连接到公用电话交换网。

有关详细信息，请参阅[Plan for 企业语音 in Skype for Business Server。](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>PSTN 呼叫选项 (公用电话) 的连接

可以选择通过以下方式连接到 PSTN (公用电话) 网络：

- 在 Microsoft 365 或 Office 365 中使用 Microsoft 通话套餐 
- 连接您自己的电话运营商

### <a name="calling-plan-microsoft-365-or-office-365"></a>通话套餐 (Microsoft 365 或 Office 365) 

此选项将 Microsoft 365 或 Office 365 电话系统连接到公用电话交换网 (PSTN) 以允许呼叫世界各地的座机和移动电话。 借助通话套餐，Microsoft 是 PSTN 运营商。

有关详细信息，请参阅 [Microsoft 365 或 Office 365](/MicrosoftTeams/calling-plans-for-office-365)通话套餐。

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>将你自己的电话运营商 (Microsoft 365 或 Office 365 和 Skype for Business 本地) 

此选项可将 Microsoft 365 电话系统或 Office 365 或本地 Skype for Business 企业语音电话系统连接到电话网络。 此选项要求支持 SBC (会话) 。 在某些情况下，此选项可能需要本地部署的其他 Microsoft 软件。

## <a name="which-solution-is-right-for-your-organization"></a>哪种解决方案适合你的组织？

可以选择全云解决方案、连接你自己的运营商解决方案，或全云和第三方运营商之间的混合解决方案：

- 具有通话套餐的电话 (云中) 

- 通过直接路由使用自己的运营商的电话系统

- 通过 Skype for Business Server 或云连接器版本使用自己的运营商的电话系统

- 企业语音运营商在 Skype for Business Server 中运行

您选择的解决方案取决于您当前和未来的需求，例如：

- 是希望保留本地部署提供的功能，还是需要保留该功能。
- 要为用户部署哪个客户端。
- 你的计划是将用户迁移到云。
- 是否需要与第三方 PBX 和其他电话设备进行互操作。

请考虑以下问题以确定最适合贵组织的解决方案：

- 你是否具有现有的 Skype for Business Server 部署？
- 你的用户是托管在本地 Skype for Business 中，还是托管在 Skype for Business Online 上的云中，还是同时托管在两者中？ 
- 是否要将本地用户移动到云？
- Microsoft 的 PSTN 呼叫计划在你的地区是否可用？
- 您是否希望或需要保留当前的电话运营商？  例如，由于现有合同，是否需要保留当前运营商？
- 您是否具有需要或需要保留的现有本地旧版 PBX？
- 您当前的旧版 PBX 是否提供对您的业务至关重要的独特功能？
- 您的任何或所有用户是否需要电话系统中当前未提供的功能？

请注意以下事项：

- 这四个选项可以共存，以防您需要为复杂环境设计解决方案或管理多步骤迁移。
- 通过 Skype for Business Server 或云连接器版本具有自己运营商的电话系统只能与 Skype for Business Server 或云连接器一起部署。 单个公司不支持共存 Skype for Business Server 和云连接器。

## <a name="phone-system-with-calling-plan"></a>具有通话套餐的电话系统


具有通话套餐的电话系统是 Teams 或 Skype for Business Online 用户的全云选项，如下图所示：

![具有通话套餐的电话系统](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Microsoft Phone System 添加了国内或国际通话套餐，允许呼叫世界各地的电话 (具体取决于许可的呼叫) 。 
- 由于 PSTN 呼叫计划在 Microsoft 365 或 Office 365 中运行，因此此选项不需要部署或维护任何本地部署。
- 客户可以通过直接路由连接受支持的 SBC，实现与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备的互操作性。

| 基础结构要求                   | 是否必需？|
| :----------------------------------------------------| ---------:|
| 需要不间断地连接到 Microsoft 365 或 Office 365 | 是 |
| 在全球可用*                            | 否  |
| 要求在 SBC 服务器中部署和维护 (会话边界)  | 否 |
| 需要和第三方运营商签订合同      | 否   |
| 需要部署和维护 Skype for Business Server 或云连接器版本 | 否 |

\* 有关提供通话套餐的国家/地区详细信息，请参阅音频会议和通话套餐的 [国家和地区可用性](/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。


如果您对以下问题回答"是"，则这是适合您的解决方案：

- 通话套餐在你的地区可用。
- 无需保留当前的 PSTN 运营商。
- 您希望使用 Microsoft 管理的对 PSTN 电话交换网或 PSTN (访问) 。
- 你不希望自己管理会话边界控制器。
- Teams 和/或 Skype for Business Online 具有组织所需的全部功能。

有关详细信息，请参阅什么是 [Microsoft 365 和 Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) 中的电话系统以及 [Microsoft 365 或 Office 365](/MicrosoftTeams/calling-plans-for-office-365)通话套餐。

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>通过直接路由使用自己的运营商的电话系统

此选项为云中的 Microsoft Phone System 提供了几乎任何适用于 Teams 用户的电话运营商。

![通过直接路由使用运营商的电话系统](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- 无需其他本地软件，即可将自己支持的 SBC 直接连接到 Microsoft Phone System。  
- 将几乎任何电话运营商与 Microsoft Phone System 一同使用。
- 客户或运营商或合作伙伴可以配置和管理 (询问你的运营商或合作伙伴是否提供此选项) 。
- 配置电话设备（如第三方 PBX 和模拟设备）与 Microsoft Phone System 之间的互操作性。

| 基础结构要求                   | 是否必需？|
| :----------------------------------------------------| ---------:|
| 需要不间断地连接到 Microsoft 365 或 Office 365 | 是 |
| 在全球可用                            | 是  |
| 要求在 SBC 服务器中部署和维护 (会话边界)  | 是 |
| 需要和第三方运营商签订合同*      | 是   |
| 需要部署和维护 Skype for Business Server 或云连接器版本 | 否 |

\* 除非部署为具有通话套餐的电话系统上的用户提供连接到第三方 PBX、模拟设备或其他电话设备的选项。

如果您对以下问题回答"是"，则这是适合您的解决方案：

- 你想要将 Teams 与电话系统一同使用。
- 你需要保留当前的 PSTN 运营商。
- 你想要混合路由，一些呼叫通过通话套餐进行，一些通过你的运营商
- 您需要与第三方 PBX 和/或设备（例如开销寻呼机、模拟设备）进行互操作
- Teams 具有组织所需的全部功能。

有关详细信息，请参阅什么是 [Microsoft 365 和 Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) 中的电话系统和 [规划直接路由](/MicrosoftTeams/direct-routing-plan)。


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>通过 Skype for Business Server 或云连接器版本使用自己的运营商的电话系统

> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

此选项为云中的 Microsoft Phone System 提供与 Skype for Business Online 用户本地电话网络的连接。

![通过 Skype for Business Server 或云连接器版本使用运营商的电话系统](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - 通过本地部署的 Skype for Business Server 或 Skype for Business 云连接器版本，将你自己的支持的 SBC 连接到 Microsoft Phone 系统。 
- 将几乎任何电话运营商与 Microsoft Phone System 一同使用。 
- 如果你已拥有本地 Skype for Business Server，你可以利用它; 如果不部署，可以部署更浅的版本 – 云连接器版本。


| 基础结构要求                   | 是否必需？|
| :----------------------------------------------------| ---------:|
| 需要不间断地连接到 Microsoft 365 或 Office 365 | 是 |
| 在全球可用                            | 是  |
| 要求在 SBC 服务器中部署和维护 (会话边界)  | 是 |
| 需要和第三方运营商签订合同      | 是   |
| 需要部署和维护 Skype for Business Server 或云连接器版本 | 是 |



如果您对以下问题回答"是"，则这是适合您的解决方案：

- 你想要为用户使用 Skype for Business Online。
- PSTN 呼叫计划在你的区域不可用。
- 你需要保留当前的 PSTN 运营商。

有关详细信息，请参阅什么是 [Microsoft 365 和 Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365)中的电话系统 [、Skype for Business Server 2019](../../SfBServer2019/skype-for-business-server-2019.yml)和 [Plan for Skype for Business 云连接器版本](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)。

建议：当业务条件发生变化（例如，不再需要保留 PSTN 运营商）时，请考虑使用选项 1 或 2 移动到 Microsoft Teams，以：
- 最大程度地降低维护成本
- 有权访问 Microsoft 发布的最新功能

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>企业语音运营商在 Skype for Business Server 中运行

此选项企业语音本地用户连接到本地 Skype for Business 电话网络。

![企业语音运营商在 Skype for Business Server 中运行](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- 将你自己的支持的 SBC 企业语音 Skype for Business 本地服务器中的系统。
- 如果您需要本地生存能力，请使用 。
- 将几乎任何电话运营商与 Microsoft Phone System 一同使用。 
- 部署和维护的最复杂选项。

| 基础结构要求                   | 是否必需？|
| :----------------------------------------------------| ---------:|
| 需要不间断地连接到 Microsoft 365 或 Office 365 | 否 |
| 在全球可用                            | 是  |
| 要求在 SBC 服务器中部署和维护 (会话边界)  | 是 |
| 需要和第三方运营商签订合同      | 是   |
| 需要部署和维护 Skype for Business Server | 是 |

有关详细信息，请参阅[Plan for 企业语音 in Skype for Business Server。](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

建议：当业务条件发生变化（例如，不再需要保留 PSTN 运营商）时，请考虑使用选项 1 或 2 移动到 Microsoft Teams，以：
- 最大程度地降低维护成本
- 有权访问 Microsoft 发布的最新功能