---
title: Microsoft 团队升级 |环境评估，发现问题
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 使用本指南了解有关正确评估当前环境以便升级到团队的要求。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b7c7910c7c876c01d3192e16f49498e508fcd2c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776729"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>升级到团队之前先评估你的环境

![升级旅行图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段，重点介绍技术准备阶段")

本文是您的升级过程的技术准备阶段的一部分，与用户准备阶段并行完成的活动。 在继续之前，请确认您已完成以前阶段中的这些活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

本文概述了正确评估运营团队的当前环境的要求。 通过评估你的环境，确定将影响你的整体部署的风险和要求。 通过预先确定这些项目，您可以调整计划以推动成功。

## <a name="introduction-to-the-discovery-questionnaire"></a>发现问卷问卷简介

为了实现客观的关键结果（OKRs），您以前已做出关键服务决策。 下一步是执行环境发现以评估与你的 IT 基础结构、网络和操作相关的所有方面，以确认你的组织已准备好实施解决方案。 发现是在为团队进行规划时，首先要执行的关键步骤之一。 环境发现必须包含网络准备情况评估，以确保你的网络可以支持升级到团队。 你可以对你的环境执行详细的发现，以更好地了解其当前状态，并揭示任何困难，甚至更重要的是，在团队推出的执行中可能会发生阻止。

你可以将技术风险标识为环境评估和采纳准备情况评估的一部分，并针对每个确定的风险制定一个缓解计划。 您应将此信息合并到风险注册中。

环境发现问卷问卷中包括与您的现有协作基础结构和 Office 365 组织、网络、终结点、操作以及准备情况和准备情况相关的所有事项。 调查表分为多个部分，用于在几个重要领域确认您的组织准备好团队部署。 与你的项目团队协作，尽可能详细地提供所需的信息，以促进你的规划活动。

> [!TIP]
> 你可以从将调查表复制到 Microsoft Word 文档中开始。 尝试回答所有问题，并在您移动浏览时捕获所有详细信息。

## <a name="project-team"></a>项目团队

确保您已为您的项目团队预定了合适的人员。 验证在[登记项目利益干系人](upgrade-enlist-stakeholders.md)时完成的步骤。

## <a name="office-365-organization-details"></a>Office 365 组织详细信息

我们强烈建议您在使用此调查表时拥有一个活动的 Office 365 组织。 如果尚未激活或配置 Office 365 组织，请参阅[规划 office 365 for business 的设置](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表捕获有关 Office 365 组织的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 注意生产 Office 365 组织 <br>"应答" 列中的名称和 ID <br/>如果你有多个租户 <br>与您的组织相关联， <br>请注意所有 Id。 | 租户名称： <br/>租户 ID：| |
> | 租户是在哪些地区部署的？| | |
> | 这些租户是 Office 365 多租户还是 <br>专用? | <input type="checkbox">多<br/> <input type="checkbox">专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>请注意为每个用户启用的用户数 <br>"评论" 列中的服务。 | <input type="checkbox">Microsoft 团队 <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">之外| |
> | 为 Skype 启用了哪些许可证级别 <br>商业联机用户？ | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">独立 | 用户数 <br>对于每个 SKU： |
> | 什么是当前 Active Directory 林 <br>环境中的功能级别？ <br/>如果有多个林，请注意详细信息 <br>在 "评论" 列中。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 您在目录中使用了什么 <br>今天同步？ |<input type="checkbox">不同步（仅限云） <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox">其他（在中指定 <br>&nbsp;&nbsp; "评论" 列&nbsp;。）| |
> | 当前是否已部署联合标识？ <br/>（Active Directory 联合身份验证服务或 <br>第三方） | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果您使用的是联合身份， <br>联盟基础结构？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 广告 FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 广告 FS <br/> <input type="checkbox">第三方联盟 <br>&nbsp;&nbsp; &nbsp;网关 <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; "评论" 列&nbsp;。） | |
> | 如果您当前维护的是活动的 Office 365 <br>租户，是您的的 SMTP/SIP 域 <br>与租户关联的目标用户？ | <input type="checkbox">N/A –无 Office 365 <br>&nbsp;&nbsp; &nbsp;租户现场 <br/> <input type="checkbox">否，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">是，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域关联 <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; | |
> | 用户 Upn 是否与它们的主 SMTP 地址匹配？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">一致 | |

## <a name="existing-collaboration-platform-summary"></a>现有协作平台摘要

使用下表捕获有关现有协作平台部署的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 是否已部署 Skype for Business？ <br/>对于本地和混合部署，请确保 <br>你注意到版本和累积更新（CU） <br>"评论" 列中的详细信息。 | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合（带 Office 365） <br/> <input type="checkbox">是，本地 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">是、托管、专用 <br>&nbsp;&nbsp; &nbsp;方） <br/> <input type="checkbox">是，托管，共享（第三方） <br/> <input type="checkbox">否，其他 | |
> | 是否已部署 Exchange？ <br/>对于本地和混合部署，请确保 <br>注意注释中的版本和 CU 详细信息 <br>列. | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合（带 Office 365） <br/> <input type="checkbox">是，本地 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">是、托管、专用 <br>&nbsp;&nbsp; &nbsp;方） <br/> <input type="checkbox">是、托管、共享 <br>&nbsp;&nbsp; &nbsp;方） <br/> <input type="checkbox">否，其他 | |
> | 是否已部署 SharePoint？ <br/>对于本地和混合部署，请确保 <br>注意注释中的版本和 CU 详细信息 <br>列. | <input type="checkbox">是，Office 365 <br/> <input type="checkbox">是，混合（带 Office 365） <br/> <input type="checkbox">是，本地 <br/> <input type="checkbox">是，联机，专用 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">是、托管、专用 <br>&nbsp;&nbsp; &nbsp;方） <br/> <input type="checkbox">是、托管、共享 <br>&nbsp;&nbsp; &nbsp;方） <br/> <input type="checkbox">否，其他 | |
> | 是否已部署 Office 365 OneDrive for business？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 是否已部署任何其他第三方平台 <br>目前还在使用？ 如果是，请记下的用户数 <br>这些平台和注释中的用法详细信息 <br>列. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">可宽延 <br/> <input type="checkbox">其他（在批注中指定 <br>&nbsp;&nbsp; &nbsp; | 用户数： <br/>更多信息|
> | 您是否计划从这些第三方移动用户 <br>适用于团队的平台？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 什么是当前电话和会议解决方案 <br>在此计划范围内的用户？ | | |
> | 你的 SBCs 是否支持针对本计划的范围内的你的办事处部署[直接路由](direct-routing-plan.md#supported-session-border-controllers-sbcs)？ <br>如果是，请记下 "评论" 列中的详细信息。| <input type="checkbox">是的 <br/> <input type="checkbox">不 ||

## <a name="collaboration-platform-deployment-details"></a>协作平台部署详细信息

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，请使用下面的示例表捕获团队部署的详细信息。 如果尚未部署团队，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定用户/用户组 <br>&nbsp;&nbsp; （在 "注释" 列中&nbsp;指定） ||
> | 哪些团队功能和形式正在使用？ | <input type="checkbox">基于频道的对话 <br/> <input type="checkbox">私人聊天 <br/> <input type="checkbox">来宾访问 <br/> <input type="checkbox">频道会议 <br/> <input type="checkbox">私人会议 <br/> <input type="checkbox">私人通话 <br/> <input type="checkbox">临时频道聚会 <br/> <input type="checkbox">会议中的视频 <br/> <input type="checkbox">会议中的屏幕共享 <br/> <input type="checkbox">音频会议 <br/><input type="checkbox">应用程序（应用）<br> &nbsp;&nbsp; &nbsp;选项<input type="checkbox">卡<br>&nbsp;&nbsp;机器人&nbsp; <input type="checkbox"> <br>&nbsp;&nbsp;连接线&nbsp; <input type="checkbox"><br><input type="checkbox">自定义云存储集成 <br>&nbsp;&nbsp; （Dropbox、Box、ShareFile、Google Drive、 &nbsp; Egnyte） <br/> <input type="checkbox">频道电子邮件集成 <br/> <input type="checkbox">其他（在 "评论" 列中指定。） | |
> | 你已将哪些应用程序部署到团队？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，请记下 "评论" 列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox">站点 <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">输出 <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | 谁有权创建团队？ | <input type="checkbox">组织中的每个人 <br>&nbsp;&nbsp; （这是默认&nbsp;设置） <br/> <input type="checkbox">特定人员 <br>&nbsp;&nbsp; （在 "注释" 列中指定&nbsp;。） | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，请使用下面的示例表捕获 Skype for Business Online 部署的详细信息。 如果尚未部署 Skype for Business Online 部署，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Skype 启用了哪些类型的用户 <br>for Business Online？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定用户/用户组 <br>&nbsp;&nbsp; （在 "注释" 列中&nbsp;指定） | |
> | 目前的形式和功能 <br>目前在使用中？ | <input type="checkbox">即时消息和状态（IM/P）<br/> <input type="checkbox">有空 <br/> <input type="checkbox">Ws-federation <br/> <input type="checkbox">会议录制 <br/> <input type="checkbox">Microsoft 音频会议 <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; （请注意 "评论" 列中的详细信息&nbsp;。） <br/> <input type="checkbox">通话计划（以前称为 PSTN 呼叫） <br/> <input type="checkbox">组织自动助理 <br/> <input type="checkbox">通话队列 | |
> | 是否已特别阻止任何 Skype for <br>企业联机功能？ <br>如果是，请记下 "评论" 列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 你使用的是哪种方法或计划使用它来 <br>将电话系统（以前称为云 PBX）连接到 <br>PSTN？ <br/>选择所有适用的。 | <input type="checkbox">通话计划（以前称为 PSTN 呼叫） <br/> <input type="checkbox">本地 PSTN 连接（利用现有 <br>&nbsp;&nbsp; Skype for business 2015 或 Lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp;部署） <br/> <input type="checkbox">本地 PSTN 连接（使用云连接器） | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这适用于通话计划和音频 <br>会议功能。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>本地 Skype for Business （如果适用）

如果适用，请使用下面的示例表捕获 Skype for Business 部署的详细信息。 如果尚未在本地部署 Skype for Business，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 当前哪些版本的 Lync 或 Skype for business <br>是在本地部署的？ | <input type="checkbox">Office 通信服务器 2007 "R1" <br/> <input type="checkbox">Office 通信服务器 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business 服务器2015 <br/> <input type="checkbox">Skype for Business 服务器2019 <br/> <input type="checkbox">Skype for Business 云连接器版 | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 此环境是否由第三方托管和管理？ <br/>如果是，请记下 "评论" 列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 目前使用的形式和功能 <br>参加? | <input type="checkbox">即时消息和状态（IM/P） <br/> <input type="checkbox">有空 <br/> <input type="checkbox">Ws-federation <br/> <input type="checkbox">会议录制 <br/> <input type="checkbox">持续聊天/群组聊天 <br/> <input type="checkbox">Microsoft 音频会议 <br>&nbsp;&nbsp; （以前称为电话拨入式&nbsp;会议） <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; （请注意 "注释" 列中的详细&nbsp;信息） <br/> <input type="checkbox">使用本地 PSTN 的企业语音 <br>&nbsp;&nbsp; &nbsp;连接性 <br/> <input type="checkbox">通话计划（以前称为 PSTN 呼叫），通过 <br>&nbsp;&nbsp;与 Skype for business Online &nbsp;的混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox">Office 通信服务器 2007 "R1" <br/> <input type="checkbox">Office 通信服务器 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business 服务器2015 <br/> <input type="checkbox">Skype for Business 服务器2019 | |
> | 您是否已部署 Lync 或 Skype for business Edge <br>合并到多个数据中心？ <br/>如果是，请记下 "评论" 列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 选择你的 Edge 角色今天提供的服务。 | <input type="checkbox">外部用户访问（企业用户） <br/> <input type="checkbox">远程用户访问（匿名外部 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ws-federation <br/> <input type="checkbox">媒体中继 | |
> | 以下哪种语音呼叫功能可供您 <br>当前有依赖关系？ <br/>注意批注中的任何其他依赖项 <br>列. | <input type="checkbox">忙碌选项 <br/> <input type="checkbox">呼叫寄存 <br/> <input type="checkbox">呼叫装货或群组呼叫装货 <br/> <input type="checkbox">常见的区域电话或 "热 desking" <br/> <input type="checkbox">响应组或查寻组 <br/> <input type="checkbox">共享线条外观 <br/> <input type="checkbox">私人线路 <br/> <input type="checkbox">语音邮件 <br/> <input type="checkbox">通过工作通话 <br/> <input type="checkbox">紧急电话或信息 <br>&nbsp;&nbsp; （911、811、 &nbsp;411） <br/> <input type="checkbox">分机号码 <br/> <input type="checkbox">自动助理 <br/> <input type="checkbox">订阅者访问 <br/> <input type="checkbox">模拟设备 <br/> <input type="checkbox">传入 <br/> <input type="checkbox">呼叫方 ID 屏蔽或更改 <br/> <input type="checkbox">基于位置的路由 <br/> <input type="checkbox">最小成本路由 <br/> <input type="checkbox">电梯间电话 | |

## <a name="networking-and-access-to-office-365-services"></a>网络和 Office 365 服务的访问

使用下表捕获你的组织的网络详细信息以及你的用户（或将）连接到 Office 365 服务的方式。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 如何（或如何）迁移范围内的用户 <br>是否在 office 中访问团队？ <br/>选择所有适用的。 | <input type="checkbox">路由 NAT 连接 <br/> <input type="checkbox">代理服务器 <br/> <input type="checkbox">公共 Wi-fi <br/> <input type="checkbox">托管（非公共） Wi-fi <br/> <input type="checkbox">ExpressRoute （Microsoft 对等） ||
> | 如果通过代理服务器访问 Office 365 <br>绕过代理的任何方法？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">否，但正在计划 | |
> | 是否已执行网络准备情况评估？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 用户是否需要使用 VPN 才能连接到 <br>远程公司资源？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果使用 VPN，则可以将团队流量排除在 <br>用于直接访问 Office 365 服务的 VPN？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 你可以确定团队音频和视频流量的优先级 <br>要推动优质体验？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 区域内的所有位置都有 internet 出口， <br>或是否为整个地区集中了 internet 出口？ | <input type="checkbox">对 internet 的区域访问 <br/> <input type="checkbox">对 internet 的集中访问 | |

## <a name="endpoints"></a>终结点

使用下表捕获正在使用的客户端和终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac （在 "评论" 列中指定版本。） <br/> <input type="checkbox">Linux （在 "评论" 列中指定分布。） <br/> <input type="checkbox">其他（请注意 "评论" 列中的详细信息。） | |
> | 部署了哪个版本的 Microsoft Office <br>这些设备？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox">其他（请注意 "评论" 列中的详细信息。） | |
> | 正在使用哪种 Office 部署技术 <br>您的组织中？ | <input type="checkbox">MSI <br/> <input type="checkbox">即点即用 | |
> | 哪些是允许和支持的移动设备 <br>使用的平台？ <br/>选择所有适用的。 | <input type="checkbox">Windows <br/> <input type="checkbox">移动 <br/> <input type="checkbox">输出 <br/> <input type="checkbox">Android <br/> <input type="checkbox">其他（请注意 "评论" 列中的详细信息。） | |
> | 如何提供移动设备？ <br/>选择所有适用的。 | <input type="checkbox">公司设备 <br/> <input type="checkbox">携带自己的设备 | |
> | 用户当前用于访问的设备 <br>语音和会议服务 <br>（话筒、耳机、电话、视频）？ | | |

## <a name="operations"></a>运营

使用下表捕获环境的操作方面的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 您的 Lync 服务器的操作模型是什么？ <br>Skype for Business 服务器或 Office 365 部署 <br>参加? | | |
> | 你可以概括了解当前的支持安排 <br>Lync Server、Skype for Business 服务器还是 Office 365？ | | |
> | 如果您要部署到多个国家或地区， <br>每个国家/地区是否有自己的 IT/电话 <br>要与之协作的职员或是否将集中管理？ | <input type="checkbox">区域操作和支持 <br/> <input type="checkbox">集中操作和支持 | |
> | 您是否关注[通话质量方法](quality-of-experience-review-guide.md)？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 已将个人或团队分配给 <br>协作平台的质量拥护者角色 <br>使用中？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 如何监控 Lync Server、Skype for <br>企业服务器还是 Office 365 部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 如何以及何时向您提供培训 <br>帮助台新服务和功能？ | | |

## <a name="adoption-and-readiness"></a>采纳和准备情况

使用下表并提供组织的当前采用和就绪状态。

>
> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 您当前的活动使用情况 <br>Skype for business？ | **__** % 的活动用户总数与已启用的用户数 | |
> | 您的组织如何使用 <br>Skype for business？ | 一对一对话 <br>&nbsp;&nbsp; IM &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp;通话&nbsp; <input type="checkbox"> <br>&nbsp;&nbsp;共享&nbsp; <input type="checkbox"><br> 会议 <br>&nbsp;&nbsp;会议&nbsp; <input type="checkbox"><br>&nbsp;&nbsp;共享&nbsp; <input type="checkbox"><br>&nbsp;&nbsp;通话&nbsp; <input type="checkbox"> | |
> | 您的组织是否具有用户采纳 <br>并更改管理团队？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 当前如何衡量技术是否成功 <br>Skype for Business 之类的部署？ | | |
> | 你说的你的用户群的百分比是多少 <br>采纳了 Skype for Business？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox">祝 <br/> <input type="checkbox">非 <br/> <input type="checkbox">别有用心 | |
> | 以下哪一项最恰当地描述了推出 <br>用于 Skype for Business 的策略 <br>部署? | <input type="checkbox">广泛访问：电子邮件市场活动 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">已展开：广泛的和一系列 <br>&nbsp;&nbsp; &nbsp;海报） <br>&nbsp;&nbsp; &nbsp;和培训 <br>&nbsp;&nbsp; （视频、用户指南、人员&nbsp;内） <br/> <input type="checkbox">定制：扩展，外加目标 <br>&nbsp;&nbsp;按角色进行消息传递&nbsp;和培训 <br/> <input type="checkbox">之外 <br>&nbsp;&nbsp; （请注意 "评论" 列中的详细信息&nbsp;。） | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul><li>谁将负责完成环境评估？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>后续步骤</td><td><ul><li>记录环境评估的结果。</li></ul></td></tr>
</table>

评估你的环境后，请继续下一步：[准备网络](prepare-network.md)。
