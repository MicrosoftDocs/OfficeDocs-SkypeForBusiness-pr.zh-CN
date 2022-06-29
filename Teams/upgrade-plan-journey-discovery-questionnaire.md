---
title: Microsoft Teams 升级|环境评估、发现问题
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 使用本指南了解正确评估当前环境以升级到 Teams 的要求。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca3233f2dd0dde20f887378520049023ab82cbb7
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529704"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>发现问卷 - 评估环境

以下一组表列出了在 [升级到 Teams 之前](upgrade-plan-journey-evaluate-environment.md)可帮助你评估环境的问题：

- [Microsoft 365 或Office 365组织详细信息](#microsoft-365-or-office-365-organization-details)
- [现有协作平台摘要](#existing-collaboration-platform-summary)
- [协作平台部署详细信息](#collaboration-platform-deployment-details)
- [Microsoft 365 或 Office 365 服务的网络和访问权限](#networking-and-access-to-microsoft-365-or-office-365-services)
- [终结点](#endpoints)
- [运营](#operations)
- [采用和就绪情况](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 或Office 365组织详细信息

强烈建议你在处理问卷时有一个活跃的 Microsoft 365 或Office 365组织。 如果尚未激活或配置 Microsoft 365 或Office 365组织，请参阅[规划 Microsoft 365 商业版的设置](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表捕获有关 Microsoft 365 或Office 365组织的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 请注意生产 Microsoft 365 或Office 365组织 <br>“答案”列中的名称和 ID <br/>如果你有多个租户 <br>与组织相关联， <br>记下所有 ID。 | 租户名称： <br/>租户 ID：| |
> | 在哪些区域部署了租户？| | |
> | 这些租户是 Microsoft 365 还是Office 365多租户或 <br>专用？ | <input type="checkbox"> 多租户<br/> <input type="checkbox"> 专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>请注意为每个用户启用的用户数 <br>“注释”列中的服务。 | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> 其他| |
> | 为 Skype for 启用了哪些许可证级别 <br>Business Online 用户？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 独立 | 用户数 <br>对于每个 SKU： |
> | 当前 Active Directory 林是什么 <br>环境中的功能级别？ <br/>如果有多个林，请注意详细信息 <br>在“注释”列中。 | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 用于目录的内容 <br>今天同步？ |<input type="checkbox"> 仅) 云没有同步 ( <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox"> 其他 (在 <br>&nbsp;&nbsp; &nbsp;Comments column.) | |
> | 当前是否已部署联合标识？ <br/> (Active Directory 联合身份验证服务或 <br>第三方)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用的是联合标识，什么是 <br>联合身份验证基础结构？ | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> 第三方联合 <br>&nbsp;&nbsp; &nbsp;网关 <br>&nbsp;&nbsp; &nbsp; (记下其中的详细信息 <br>&nbsp;&nbsp; &nbsp;Comments column.)  | |
> | 如果当前维护有效的 Microsoft 365 或Office 365 <br>租户是你的 SMTP/SIP 域 <br>与租户关联的目标用户？ | <input type="checkbox">N/A - 无 Microsoft 365 或 Office 365 <br>&nbsp;&nbsp; &nbsp;租户就位 <br/> <input type="checkbox"> 否，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域未关联 <br>&nbsp;&nbsp; &nbsp;中包含任何租户 <br>&nbsp;&nbsp; &nbsp;Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域已关联 <br>&nbsp;&nbsp; &nbsp;具有现有租户 <br>&nbsp;&nbsp; &nbsp;在 Microsoft 365 或 Office 365 | |
> | 用户 UPN 是否与其主要 SMTP 地址匹配？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>现有协作平台摘要

使用下表捕获有关现有协作平台部署的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否已部署 Skype for Business？ <br/>对于本地部署和混合部署，请确保 <br>请记下 CU (版本和累积更新)  <br>“注释”列中的详细信息。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，将混合 (与 Microsoft 365 或 Office 365)  <br/> <input type="checkbox"> 是，本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管、共享 (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Exchange？ <br/>对于本地部署和混合部署，请确保 <br>记下批注中的版本和 CU 详细信息 <br>列。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，将混合 (与 Microsoft 365 或 Office 365)  <br/> <input type="checkbox"> 是，本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是、托管、共享 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 SharePoint？ <br/>对于本地部署和混合部署，请确保 <br>记下批注中的版本和 CU 详细信息 <br>列。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，将混合 (与 Microsoft 365 或 Office 365)  <br/> <input type="checkbox"> 是，本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是、托管、共享 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Microsoft 365 或Office 365 OneDrive for Business？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否部署了任何其他第三方平台 <br>现在正在使用？ 如果是，请记下用户数 <br>批注中的这些平台和使用情况详细信息 <br>列。 | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> 松弛 <br/> <input type="checkbox"> 其他 (在注释中指定 <br>&nbsp;&nbsp; &nbsp;column.)  | 用户数： <br/>细节：|
> | 是否计划将用户从这些第三方移动 <br>平台到 Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 什么是当前的电话和会议解决方案 <br>属于此计划范围的用户？ | | |
> | 是否已为处于此计划范围内的办公室部署 [支持直接路由的 SBC](direct-routing-plan.md#supported-session-border-controllers-sbcs) ？ <br>如果是，请记下“注释”列中的详细信息。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>协作平台部署详细信息

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，请使用下面的示例表捕获 Teams 部署的详细信息。 如果尚未部署 Teams，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox"> 组织中的所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br>&nbsp;&nbsp; &nbsp; (注释列中指定)  ||
> | 正在使用哪些 Teams 功能和方式？ | <input type="checkbox"> 基于频道的对话 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 来宾访问 <br/> <input type="checkbox"> 频道会议 <br/> <input type="checkbox"> 私人会议 <br/> <input type="checkbox"> 专用呼叫 <br/> <input type="checkbox"> 临时通道会议 <br/> <input type="checkbox"> 会议中的视频 <br/> <input type="checkbox"> 会议中的屏幕共享 <br/> <input type="checkbox"> 音频会议 <br/><input type="checkbox"> 应用程序 (应用) <br> &nbsp;&nbsp; &nbsp;<input type="checkbox">标签<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">机器人 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">连接<br><input type="checkbox"> 自定义云存储集成 <br>&nbsp;&nbsp; &nbsp;Dropbox、Box、ShareFile、Google Drive、Egnyte <br/> <input type="checkbox"> 频道电子邮件集成 <br/> <input type="checkbox"> 其他 (在“注释”列中指定。)  | |
> | 你已将哪些应用程序部署到 Teams？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，请记下“注释”列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox"> Web <br/> <input type="checkbox"> 窗户 <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | 谁有权创建团队？ | <input type="checkbox"> 组织中的每个人 <br>&nbsp;&nbsp; &nbsp; (这是默认设置)  <br/> <input type="checkbox"> 特定人员 <br>&nbsp;&nbsp; &nbsp; (注释列中指定)  | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，请使用下面的示例表捕获Skype for Business联机部署的详细信息。 如果尚未部署Skype for Business联机部署，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Skype 启用了哪些类型的用户 <br>for Business Online？ | <input type="checkbox"> 组织中的所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br>&nbsp;&nbsp; &nbsp; (注释列中指定)  | |
> | 当前采用何种模式和功能 <br>当前正在使用？ | <input type="checkbox"> 即时消息和状态 (即时消息/P) <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合会 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> Microsoft 音频会议 <br/> <input type="checkbox"> 第三方音频会议 <br>&nbsp;&nbsp; &nbsp; (注释列中的详细信息。)  <br/> <input type="checkbox"> 调用计划 (以前的 PSTN 呼叫)  <br/> <input type="checkbox"> 组织自动助理 <br/> <input type="checkbox"> 呼叫队列 | |
> | 是否已专门阻止任何 Skype for <br>Business Online 功能？ <br>如果是，请记下“注释”列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 使用或计划使用哪种方法 <br>将电话系统 (以前的云 PBX) 连接到 <br>PSTN？ <br/>选择所有适用项。 | <input type="checkbox"> 调用计划 (以前的 PSTN 呼叫)  <br/> <input type="checkbox"> 利用现有 PSTN 连接 (本地 PSTN <br>&nbsp;&nbsp; &nbsp;Skype for Business 2015 或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;部署)  <br/> <input type="checkbox"> 使用云连接器 (本地 PSTN 连接)  | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这适用于通话套餐和音频 <br>会议功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business本地 (（如果适用）) 

如果适用，请使用下面的示例表捕获Skype for Business部署的详细信息。 如果尚未在本地部署Skype for Business，请跳过此部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | Lync 或 Skype for Business 当前的版本 <br>是否部署在本地？ | <input type="checkbox"> Office Communications Server 2007“R1” <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Skype for Business 云连接器版本 | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 此环境是否由第三方托管和管理？ <br/>如果是，请记下“注释”列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 当前正在使用的模式和功能 <br>今天？ | <input type="checkbox"> 即时消息和状态 (即时消息/P)  <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合会 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> 持久聊天/群聊 <br/> <input type="checkbox"> Microsoft 音频会议 <br>&nbsp;&nbsp; &nbsp; (以前在会议) 拨号 <br>&nbsp;&nbsp; &nbsp;本地 Lync Server 或 <br>&nbsp;&nbsp; &nbsp;Skype for Business部署 <br/> <input type="checkbox"> 第三方音频会议 <br>&nbsp;&nbsp; &nbsp; (记下“批注”列中的详细信息)  <br/> <input type="checkbox">企业语音使用本地 PSTN <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox"> 呼叫计划 (以前通过 PSTN 呼叫)  <br>&nbsp;&nbsp; &nbsp;与 Skype for Business Online 混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox"> Office Communications Server 2007“R1” <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | 是否已部署 Lync 或 Skype for Business Edge <br>进入多个数据中心？ <br/>如果是，请记下“注释”列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 选择 Edge 角色当前提供的服务。 | <input type="checkbox"> 外部用户访问 (企业用户)  <br/> <input type="checkbox"> 远程用户访问 (匿名外部 <br>&nbsp;&nbsp; &nbsp;会议参与者)  <br/> <input type="checkbox"> 联合会 <br/> <input type="checkbox"> 媒体中继 | |
> | 以下哪些语音呼叫功能可以使用 <br>当前是否依赖？ <br/>记下注释中任何其他依赖项 <br>列。 | <input type="checkbox"> 忙碌选项 <br/> <input type="checkbox"> 呼叫寄存 <br/> <input type="checkbox"> 呼叫取件或组呼叫取件 <br/> <input type="checkbox"> 公共区域电话或“热桌面” <br/> <input type="checkbox"> 响应组或搜寻组 <br/> <input type="checkbox"> 共享行外观 <br/> <input type="checkbox"> 专用行 <br/> <input type="checkbox"> 语音 信箱 <br/> <input type="checkbox"> 通过工作呼叫 <br/> <input type="checkbox"> 紧急或信息编号 <br>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 扩展拨号 <br/> <input type="checkbox"> 自动助理 <br/> <input type="checkbox"> 订阅服务器访问权限 <br/> <input type="checkbox"> 模拟设备 <br/> <input type="checkbox"> 传真 <br/> <input type="checkbox"> 调用方 ID 掩码或更改 <br/> <input type="checkbox"> 基于位置的路由 <br/> <input type="checkbox"> 成本最低的路由 <br/> <input type="checkbox"> 电梯电话 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Microsoft 365 或 Office 365 服务的网络和访问权限

使用下表捕获组织的网络详细信息，以及用户 (或将) 连接到 Microsoft 365 或Office 365服务的方式。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 如何 (或如何) 迁移范围内的用户 <br>访问 Teams 时，他们在办公室？ <br/>选择所有适用项。 | <input type="checkbox"> 路由 NAT 连接 <br/> <input type="checkbox"> 代理服务器 <br/> <input type="checkbox"> 公共Wi-Fi <br/> <input type="checkbox"> 托管 (不是公共) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (Microsoft 对等互连)  ||
> | 如果通过代理服务器访问 Microsoft 365 或 Office 365，则存在 <br>以任何方式绕过代理？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不， 但它正在计划中 | |
> | 是否已执行网络就绪评估？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 连接到 VPN 时，用户是否需要使用 VPN <br>企业资源远程？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用 VPN，可以从中排除 Teams 流量 <br>要直接访问 Microsoft 365 或Office 365服务的 VPN？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否可以确定 Teams 音频和视频流量的优先级 <br>推动高质量体验？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 在区域内的所有位置都具有 Internet 出口， <br>还是整个区域的 Internet 出口集中？ | <input type="checkbox"> 对 Internet 的区域访问 <br/> <input type="checkbox"> 对 Internet 的集中访问 | |

## <a name="endpoints"></a>终结点

使用下表捕获正在使用的客户端和终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox"> Windowsxp <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (在“注释”列中指定版本。)  <br/> <input type="checkbox"> Linux (在“注释”列中指定分布。)  <br/> <input type="checkbox"> 其他 (记下“注释”列中的详细信息)  | |
> | 部署了哪个版本的 Microsoft Office <br>到这些设备？ | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox"> 其他 (记下“注释”列中的详细信息)  | |
> | 正在使用哪个 Office 部署技术 <br>在组织中？ | <input type="checkbox"> 微星 <br/> <input type="checkbox"> 即点即用 | |
> | 什么是允许和支持的移动设备 <br>正在使用的平台？ <br/>选择所有适用项。 | <input type="checkbox"> 窗户 <br/> <input type="checkbox"> 移动 <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (记下“注释”列中的详细信息)  | |
> | 如何提供移动设备？ <br/>选择所有适用项。 | <input type="checkbox"> 企业设备 <br/> <input type="checkbox"> 自带设备 | |
> | 用户当前用于访问哪些设备 <br>语音和会议服务 <br> (手机、耳机、手机、视频) ？ | | |

## <a name="operations"></a>运营

使用下表捕获环境操作方面的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | Lync Server 的操作模型是什么， <br>Skype for Business Server、Microsoft 365 或 Office 365 部署 <br>今天？ | | |
> | 是否可以概述当前支持安排 <br>Lync Server、Skype for Business Server、Microsoft 365 或Office 365？ | | |
> | 如果要部署到多个国家或地区， <br>每个国家/地区是否都有自己的 IT/电话 <br>要与之协作的员工，还是将集中管理此功能？ | <input type="checkbox"> 区域运营和支持 <br/> <input type="checkbox"> 集中式操作和支持 | |
> | 是否遵循 [呼叫质量方法](quality-of-experience-review-guide.md)？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否已将个人或团队分配到 <br>协作平台的质量冠军角色 <br>正在使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何监视 Lync Server、Skype for <br>Business Server、Microsoft 365 或Office 365部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 如何以及何时向你提供培训 <br>有关新服务和功能的帮助？ | | |

## <a name="adoption-and-readiness"></a>采用和就绪情况

使用下表并提供组织的当前采用和就绪状态。

>
> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 当前的活动使用情况 <br>Skype for Business？ | **__** 活动用户总数与已启用用户的百分比 | |
> | 组织如何使用 <br>Skype for Business？ | 一对一对话 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">我 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br> 会议 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">会议<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 | |
> | 你的组织是否具有用户采用 <br>和更改管理团队？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 当前如何衡量技术的成功 <br>像Skype for Business这样的推出？ | | |
> | 你会说你的用户群的百分比 <br>采用Skype for Business？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox"> 好 <br/> <input type="checkbox"> 中性 <br/> <input type="checkbox"> 坏 | |
> | 以下哪项最能说明推出 <br>用于Skype for Business的策略 <br>部署？ | <input type="checkbox"> 广泛覆盖：使用电子邮件活动 <br>&nbsp;&nbsp; &nbsp;指向训练的链接 <br/> <input type="checkbox"> 展开：广泛覆盖以及各种范围 <br>&nbsp;&nbsp; &nbsp;宣传活动 (海报， <br>&nbsp;&nbsp; &nbsp;事件，冠军) 和训练 <br>&nbsp;&nbsp; &nbsp; (视频、用户指南、亲自)  <br/> <input type="checkbox"> 量身定制：展开，外加有针对性 <br>&nbsp;&nbsp; &nbsp;按角色传递和训练 <br/> <input type="checkbox"> 其他 <br>&nbsp;&nbsp; &nbsp; (注释列中的详细信息。)  | |


