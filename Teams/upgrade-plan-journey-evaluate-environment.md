---
title: 升级团队的 Microsoft 团队到之前评估环境
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指南可了解有关正确评估当前环境升级到团队的要求。
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b33f85faf0bc5a4d29afddb3b047a4cb2275462e
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853628"
---
![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")

本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。 在继续之前，确认您已完成从以前的阶段的这些活动：

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>升级到团队之前评估环境

本文概述了正确的运营团队评估当前环境的要求。 通过评估您的环境，您可以确定风险和将影响整个部署的要求。 通过预先确定这些项，您可以调整驱动器成功进行规划。

## <a name="introduction-to-the-discovery-questionnaire"></a>发现调查表简介

若要获得目标关键结果 (OKRs)，以前所作关键服务决策。 下一步是执行环境发现评估与您的 IT 基础结构、 网络和操作，以确认您的组织准备好实施解决方案相关的所有方面。 发现是第一次，关键步骤时采取的规划的您旅程向工作组之一。 环境发现必须包括以确保您的网络可支持升级到团队网络准备情况评估。 执行更好地了解其当前状态并揭示任何困难您环境的详细的发现或 — 甚至更重要 — 团队推出执行可能阻止程序。

标识为环境评估和采用准备情况评估的一部分的技术风险和制定针对每个确定风险缓解计划。 还应该采用风险注册中的此信息。

与您现有协作基础结构和 Office 365 租户、 网络、 终结点、 操作和应用和准备相关的所有方面都是作为环境发现调查表的一部分包含。 调查表分为多个节，以确认您的组织准备团队部署多个主要区域中。 使用您的项目团队提供的详尽尽可能便于您规划活动请求的信息。

> [!TIP]
> 您可以开始通过将调查表复制到 Microsoft Word 文档。 尝试回答所有问题，移动时捕获所有的详细信息。

## <a name="project-team"></a>项目工作组

确保，您已为您的项目团队进行适当的人员。 确认您已完成[登记项目 stakekholders](upgrade-enlist-stakeholders.md)中的步骤。

## <a name="office-365-tenant-details"></a>Office 365 租户的详细信息

我们强烈建议您具有活动的 Office 365 租户，当您使用此信息的问卷。 如果尚未激活或尚未配置 Office 365 租户，请参阅[规划业务的 Office 365 的安装程序](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

下表用于捕获有关 Office 365 租户的信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 请注意生产 Office 365 租户 <br>名称和应答列中的 ID <br/>如果您有多个租户 <br>您的组织，与相关联 <br>注意所有 Id。  | 租户名称： <br/>租户 ID:| |
> | 在哪些区域租户部署？| | |
> | 将 Office 365 Multitenant 这些租户或 <br>专用？ | <input type="checkbox">Multitenant<br/> <input type="checkbox">专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>请注意每个已启用的用户数 <br>在注释列中的服务。 | <input type="checkbox">Microsoft 团队 <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">其他|                                   |
> | 哪些许可证级别启用的 Skype <br>业务 Online 用户？ | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">独立 | 用户数 <br>为每个 SKU 中： |
> | 什么是当前的 Active Directory 林 <br>在环境中的功能级别？ <br/>如果有多个林中，请注意详细信息 <br>在注释列中。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 您使用什么目录 <br>立即同步？ |<input type="checkbox">没有同步 （仅限云） <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox">其他 (中指定 <br>&nbsp;&nbsp; &nbsp;注释列。)| |
> | 当前是否已部署联合标识？ <br/>(Active Directory 联合身份验证服务或 <br>第三方) | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果您使用的联合的身份，是什么 <br>联合身份验证基础结构？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">第三方联合身份验证 <br>&nbsp;&nbsp; &nbsp;网关 <br>&nbsp;&nbsp; &nbsp;(请注意中的详细信息 <br>&nbsp;&nbsp; &nbsp;注释列。) | |
> | 如果当前维护活动的 Office 365 <br>租户的 SMTP/SIP 域，您 <br>租户相关联的目标的用户？ | <input type="checkbox">N/A – 没有 Office 365 <br>&nbsp;&nbsp; &nbsp;就地租户 <br/> <input type="checkbox">否，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域不关联 <br>&nbsp;&nbsp; &nbsp;与任何位于中国数据中心的租户 <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">是，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域相关联 <br>&nbsp;&nbsp; &nbsp;与现有租户 <br>&nbsp;&nbsp; &nbsp;Office 365 中 | |
> | 用户的 Upn 匹配其主 SMTP 地址？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">规章 | |

## <a name="existing-collaboration-platform-summary"></a>协作平台的现有摘要

下表用于捕获现有协作平台部署有关的信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 是否已部署 Skype for Business？ <br/>内部部署和混合部署中，确保 <br>注意的版本和累积更新 (CU) <br>在注释列的详细信息。 | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合 （与 Office 365) <br/> <input type="checkbox">是，在部署 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是，承载，专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是，承载共享 （第三方） <br/> <input type="checkbox">无其他 | |
> | 是否已部署 Exchange？ <br/>内部部署和混合部署中，确保 <br>注意的版本和注释的 CU 详细信息 <br>列。 | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合 （与 Office 365) <br/> <input type="checkbox">是，在部署 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是，承载，专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是，承载，共享 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">无其他 | |
> | 是否已部署 SharePoint？ <br/>内部部署和混合部署中，确保 <br>注意的版本和注释的 CU 详细信息 <br>列。 | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合 （与 Office 365) <br/> <input type="checkbox">是，在部署 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是，承载，专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是，承载，共享 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">无其他 | |
> | 是 Office 365 OneDrive for Business 部署？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 您必须部署的任何其他第三方平台 <br>在使用今天？ 如果是这样，记下的用户数量 <br>这些平台和使用率的详细信息的注释 <br>列。 | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">可宽延时间 <br/> <input type="checkbox">其他 （指定的注释 <br>&nbsp;&nbsp; &nbsp;列。) | 用户的数量： <br/>详细信息：|
> | 您计划将用户从这些第三方移动 <br>向工作组平台？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 什么是当前的电话和会议解决方案 <br>此计划作用域中的用户？ | | |
> | 您必须为您的办公室的这一计划作用域中部署的[Sbc 支持直接路由](direct-routing-plan.md#supported-session-border-controllers-sbcs)？ <br>如果是，注意注释列中的详细信息。| <input type="checkbox">是的 <br/> <input type="checkbox">不 ||

## <a name="collaboration-platform-deployment-details"></a>协作平台部署详细信息

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，请使用下面的示例表捕获团队部署的详细信息。 如果尚未部署团队，跳过本节。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定的用户/用户组 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定） ||
> | 正在使用哪个团队功能和形式？ | <input type="checkbox">基于通道的对话 <br/> <input type="checkbox">私人聊天 <br/> <input type="checkbox">来宾访问 <br/> <input type="checkbox">通道会议 <br/> <input type="checkbox">专用的会议 <br/> <input type="checkbox">专用电话 <br/> <input type="checkbox">即席通道 meetup <br/> <input type="checkbox">在会议中的视频 <br/> <input type="checkbox">在会议中共享的屏幕 <br/> <input type="checkbox">音频会议 <br/><input type="checkbox">应用程序 （应用程序）<br> &nbsp;&nbsp; &nbsp; <input type="checkbox">选项卡<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Bot <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">连接器<br><input type="checkbox">自定义云存储集成 <br>&nbsp;&nbsp; &nbsp; （框、 收存箱、 ShareFile、 Google 驱动器） <br/> <input type="checkbox">通道电子邮件集成 <br/> <input type="checkbox">其他 （注释列中的指定）。 | |
> | 到团队已部署哪些应用程序？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，注意注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | 谁有权创建团队？ | <input type="checkbox">组织中所有人 <br>&nbsp;&nbsp; &nbsp;（这是默认设置） <br/> <input type="checkbox">特定的某个人 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定）。 | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，请使用下面的示例表捕获业务 Online 部署您 Skype 的详细信息。 如果尚未部署 Skype 业务 Online 部署，跳过本节。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Skype 为启用了哪些类型的用户 <br>for Online Business？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定的用户/用户组 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定） | |
> | 哪些形式和功能目前 <br>在目前使用？ | <input type="checkbox">即时消息和状态 (IM/P)<br/> <input type="checkbox">会议 <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">会议录制 <br/> <input type="checkbox">Microsoft 音频会议 <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息。） <br/> <input type="checkbox">调用计划 (以前称为 PSTN 呼叫) <br/> <input type="checkbox">组织的自动助理 <br/> <input type="checkbox">呼叫队列 | |
> | 特别是已阻止任何的 Skype <br>业务 Online 功能？ <br>如果是，注意注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 哪种方法是您使用或要使用的计划 <br>连接到电话系统 (以前称为云 PBX) <br>PSTN？ <br/>选择所有适用项。 | <input type="checkbox">调用计划 (以前称为 PSTN 呼叫) <br/> <input type="checkbox">（利用现有的内部部署 PSTN 连接 <br>&nbsp;&nbsp; &nbsp;Skype 业务 2015年或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;部署) <br/> <input type="checkbox">内部部署 PSTN 连接 （使用云连接器） | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这是适用于调用计划和音频 <br>会议功能。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business 的本地 （如果适用）

如果适用，请使用下面的示例表捕获您 Skype 业务部署的详细信息。 如果您没有为业务本地部署 Skype，跳过本节。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 哪些版本的 Lync 或 for Business 的 Skype 当前 <br>在本地部署？ | <input type="checkbox">Office Communications Server 2007"R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype 业务服务器 2015 <br/> <input type="checkbox">Skype 商业云连接器 edition | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 此环境承载以及由第三方管理？ <br/>如果是，注意注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 哪些形式和功能当前正在使用 <br>今天？ | <input type="checkbox">即时消息和状态 (IM/P) <br/> <input type="checkbox">会议 <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">会议录制 <br/> <input type="checkbox">持久聊天 / 群聊 <br/> <input type="checkbox">Microsoft 音频会议 <br>&nbsp;&nbsp; &nbsp;（以前称为电话拨入式会议） 上您 <br>&nbsp;&nbsp; &nbsp;内部部署 Lync Server 或 <br>&nbsp;&nbsp; &nbsp;Skype 业务部署 <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息） <br/> <input type="checkbox">使用企业语音部署 PSTN <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox">调用计划 (以前称为 PSTN 呼叫) 通过 <br>&nbsp;&nbsp; &nbsp;与 Skype 的业务 Online 的混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox">Office Communications Server 2007"R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype 业务服务器 2015 | |
> | 您必须 Lync 或 Skype 的业务边缘部署 <br>到多个数据中心？ <br/>如果是，注意注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 选择边缘角色立即提供的服务。 | <input type="checkbox">外部用户访问 （企业用户） <br/> <input type="checkbox">远程用户访问 （匿名外部 <br>&nbsp;&nbsp; &nbsp;会议参与者) <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">媒体中继 | |
> | 您其以下语音呼叫功能 <br>对当前具有依赖项？ <br/>请注意任何附加依赖项的注释 <br>列。 | <input type="checkbox">忙选项 <br/> <input type="checkbox">呼叫寄存 <br/> <input type="checkbox">呼叫应答或组呼叫应答 <br/> <input type="checkbox">公用区域电话或者"热办公" <br/> <input type="checkbox">响应组或智能寻线组 <br/> <input type="checkbox">共享的行外观 <br/> <input type="checkbox">Private line-专线 <br/> <input type="checkbox">语音邮件 <br/> <input type="checkbox">用单位电话呼叫 <br/> <input type="checkbox">紧急或信息号码 <br>&nbsp;&nbsp; &nbsp;（911、 811 411） <br/> <input type="checkbox">扩展拨号 <br/> <input type="checkbox">自动助理 <br/> <input type="checkbox">订阅者访问 <br/> <input type="checkbox">模拟设备 <br/> <input type="checkbox">传真 <br/> <input type="checkbox">呼叫者 ID 遮蔽或更改 <br/> <input type="checkbox">基于位置的路由 <br/> <input type="checkbox">最低成本路由 <br/> <input type="checkbox">简要电话 | |

## <a name="networking-and-access-to-office-365-services"></a>网络和访问 Office 365 服务

下表用于捕获贵组织的网络的详细信息和您的用户是如何 （或将） 连接到 Office 365 服务。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 如何实现 （或将如何） 的迁移范围中的用户 <br>访问团队时在办公室？ <br/>选择所有适用项。 | <input type="checkbox">路由的 NAT 连接 <br/> <input type="checkbox">代理服务器 <br/> <input type="checkbox">公共 Wi-fi <br/> <input type="checkbox">托管 Wi-fi （不是公共） <br/> <input type="checkbox">ExpressRoute （Microsoft 对等） ||
> | 如果通过代理服务器到 Office 365 的访问，则存在 <br>若要绕过代理任何方式？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">否，但在计划 | |
> | 您已执行网络准备情况评估？ <br/>有关详细信息，请参阅[网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 使用 VPN 连接到时所需的用户 <br>企业资源远程？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果使用 VPN，则可以团队流量从排除 <br>VPN 以直接访问 Office 365 服务？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 您可以设置了团队音频和视频流量的优先级 <br>到驱动器的高质量体验？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 区域内的所有位置都有 internet 出口吗 <br>或为整个区域集中是 internet 出口？ | <input type="checkbox">到 internet 区域的访问 <br/> <input type="checkbox">到 internet 的集中的访问 | |

> [!TIP]
> 要计算的带宽和其他网络要求的云语音量部署，具体取决于组织的详细信息和估计的使用率，请访问[网络规划器](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)中[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)。

## <a name="endpoints"></a>终结点

下表用于捕获的客户端和中使用的终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac （指定注释列中的版本。） <br/> <input type="checkbox">其他 （请注意注释列中的详细信息。） | |
> | 部署哪些版本的 Microsoft Office <br>到这些设备？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox">其他 （请注意注释列中的详细信息。） | |
> | 正在使用中的 Office 部署技术 <br>在您的组织？ | <input type="checkbox">MSI <br/> <input type="checkbox">单击即点即用 | |
> | 什么是允许和支持移动 <br>使用平台？ <br/>选择所有适用项。 | <input type="checkbox">Windows <br/> <input type="checkbox"> 手机 <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">其他 （请注意注释列中的详细信息。） | |
> | 如何提供移动设备？ <br/>选择所有适用项。 | <input type="checkbox">企业设备 <br/> <input type="checkbox">使您自己的设备 | |
> | 哪些设备当前执行用户用于访问 <br>语音和会议服务 <br>（话筒、 耳机、 电话、 视频）？ | | |

## <a name="operations"></a>运营

下表用于捕获您的环境的运营方面的详细信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 什么是 Lync 服务器，您操作模型 <br>Skype Business Server 或 Office 365 部署 <br>今天？ | | |
> | 您可以分级显示的当前支持排列 <br>Lync Server，Skype 业务服务器或 Office 365？ | | |
> | 如果您正在部署到多个国家或地区， <br>每个国家/地区具有自己 IT / 电话 <br>人员能够使用，或将此进行集中管理？ | <input type="checkbox">区域的操作和支持 <br/> <input type="checkbox">集中式的操作和支持 | |
> | 是您执行了[呼叫质量方法](quality-of-experience-review-guide.md)？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 已分配个人或团队添加到 <br>协作平台的质量推广人角色 <br>使用？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 您如何监视您的 Lync Server，Skype 的 <br>业务 Server 或 Office 365 部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 如何以及何时执行您提供培训对您 <br>在新的服务和功能的帮助台？ | | |

## <a name="adoption-and-readiness"></a>应用和准备

使用下表并提供组织的当前采用和就绪状态。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 您当前的活动使用的是什么 <br>Skype for Business？ | 与启用的用户的 ___ %总活动用户 | |
> | 如何使用您的组织 <br>Skype for Business？ | 一对一对话 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">调用 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">共享<br> 会议 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">会议<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">共享<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">调用| |
> | 您的组织有用户应用 <br>和变更管理团队？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 如何当前测量成功技术 <br>推出采用 Skype for Business？ | | |
> | 用户群的比例您认为具有 <br>采用 Skype for Business？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox">良好 <br/> <input type="checkbox">非特定语言 <br/> <input type="checkbox">错误 | |
> | 它以下最佳介绍了推出 <br>用于业务您 Skype 的策略 <br>部署？ | <input type="checkbox">广泛的通： 电子邮件与市场活动 <br>&nbsp;&nbsp; &nbsp;培训的链接 <br/> <input type="checkbox">扩展： 广泛通以及各类 <br>&nbsp;&nbsp; &nbsp;的认知活动 （海报、 <br>&nbsp;&nbsp; &nbsp;事件、 拥护者) 和培训 <br>&nbsp;&nbsp; &nbsp;（视频、 用户指南、 面对面） <br/> <input type="checkbox">定制： 展开，以及目标 <br>&nbsp;&nbsp; &nbsp;消息和个人培训 <br/> <input type="checkbox">其他 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息。） | |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责完成环境评估？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>下一步</td><td><ul><li>文档环境评估的结果。</li></ul></td></tr>
</table>

评估环境后，继续执行下一步：[准备您的网络](upgrade-prepare-environment-prepare-network.md)。