---
title: 环境兼容性 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 规划从环境到环境的过程时，如何执行详细的Skype for Business Microsoft Teams。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fdaafeb9042f8b76b40c797109740af5c93ef077
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635046"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>用于实施环境Microsoft Teams发现

发现是规划用户旅程时首先执行的关键步骤Microsoft Teams。

可以针对环境执行详细发现，以更好地了解其当前状态，并揭示任何困难，或者（甚至进一步）可能阻止用户实施Teams操作。

## <a name="discovery-questionnaire"></a>发现调查问卷

下面的示例调查问卷将指导你完成一组问题，以确认你的组织已准备好成功推出音频会议，并电话系统呼叫计划功能在 Teams。

与现有协作基础结构以及组织或Microsoft 365 Office 365、网络、终结点、操作、采用和准备相关的所有事项均包含在环境发现调查问卷中。

调查问卷分为多个部分，以确认组织是否准备好在多个主要Teams部署。 与项目团队合作，尽可能详细地提供请求的信息，促进规划活动。

> [!TIP]
> 首先，可以将调查问卷复制到文档Microsoft Word文档。 尝试回答所有问题，在浏览时捕获所有详细信息。

### <a name="project-team"></a>Project团队

捕获有关项目推出项目的关键利益干系Teams的详细信息。 请注意，一个人可以在整个项目中扮演多个角色。

> | 角色 | 姓名、电子邮件地址、电话号码 | 位置、时区 | 备注 |
> |---|---|---|---|
> | 执行发起人 | | | |
> | 项目主管 | | | |
> | 协作主管/架构师 | | | |
> | 顾问 | | | |
> | 项目经理 | | | |
> | 变更管理/采用专业人员 | | | |
> | 网络主管 | | | |
> | 安全主管 | | | |
> | 电话服务主管 | | | |
> | 桌面主管 | | | |
> | 支持主管 | | | |
> | 部署主管 | | | |
> | 服务所有者 | | | |
> | 设施主管 | | | |
> | 语音团队主管 | | | |
> | 业务部门潜在顾客 | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365或Office 365组织详细信息

强烈建议你在处理此调查问卷时Microsoft 365或Office 365组织。 如果尚未激活或配置组织或Microsoft 365 Office 365，请参阅规划企业Microsoft 365[设置](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表捕获有关组织或Microsoft 365 Office 365的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 请注意生产Microsoft 365<br/>或Office 365组织名称和 ID<br/>。 如果拥有更多<br/>多个与之关联的租户<br/>请记下组织的所有 ID。 | 租户名称： <br/>租户 ID：| |
> | 租户部署在哪些区域？| | |
> | 请注意这些类型Microsoft 365或 <br/>Office 365租户。 它们是否多租户 <br/>还是专用？ | <input type="checkbox"> 多租户<br/> <input type="checkbox"> 专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>请注意为每个用户启用的用户数 <br/>服务。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint联机 <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 其他| |
> | 为哪些用户启用了Skype级别 <br/>Business Online 用户？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | 用户数 <br/>对于每个 SKU： |
> | 当前 Active Directory 林是什么 <br/>环境中的功能级别？ <br/>如果多个林，请记下详细信息 <br/>。 | <input type="checkbox">WindowsServer 2000 <br/> <input type="checkbox">WindowsServer 2003 <br/> <input type="checkbox">WindowsServer 2008<br/> <input type="checkbox">WindowsServer 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 用于目录的是什么 <br/>今天同步？ |<input type="checkbox"> 只有云 (同步)  <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; 连接 <br/> <input type="checkbox"> 其他 (在 <br/>&nbsp;&nbsp; &nbsp;Comments column.) | |
> | 当前是否已部署联合标识？ <br/> (Active Directory 联合身份验证服务或 <br/>第三方)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用联合标识，则 <br/>联合基础结构？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> 第三方联合 <br/>&nbsp;&nbsp; &nbsp; 网关 (记下详细信息 <br/>&nbsp;&nbsp; &nbsp; 在"批注"列中)  | |
> | 如果当前保持活动Microsoft 365<br/>或 Office 365 租户， 是 的 SMTP/SIP 域 <br/>与租户关联的目标用户？ | <input type="checkbox">N/A – 无Microsoft 365或<br/>&nbsp;&nbsp; &nbsp; Office 365租户就位 <br/> <input type="checkbox"> 否，用户的 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; 域未关联 <br/>&nbsp;&nbsp; &nbsp; 中具有任何租户 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或Office 365<br/> <input type="checkbox"> 是，用户的 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; 域已关联 <br/>&nbsp;&nbsp; &nbsp; 中的现有租户 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或Office 365 | |
> | 用户 UPN 是否匹配其主 SMTP 地址？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>现有协作平台摘要

使用下表捕获有关现有协作平台部署的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否已部署 Skype for Business？ <br/>对于本地和混合部署，请确保 <br/>请注意 CU 版本和累积 (更新)  <br/>"批注"列中的详细信息。 | <input type="checkbox">是，Microsoft 365或 <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> 是，混合 (与 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管，共享 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Exchange？ <br/>对于本地和混合部署，请确保 <br/>请注意注释中的版本和 CU 详细信息 <br/>列。 | <input type="checkbox">是，Microsoft 365 <br/> <input type="checkbox"> 是，混合 (与 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管，共享 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 SharePoint？ <br/>对于本地和混合部署，请确保 <br/>请注意注释中的版本和 CU 详细信息 <br/>列。 | <input type="checkbox">是，Microsoft 365 <br/> <input type="checkbox"> 是，混合 (与 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管，共享 <br/>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否OneDrive for Business部署？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否部署了任何其他第三方平台 <br/>和当前使用中？ 如果是这样，请记下 <br/>这些平台以及 <br/>"批注"列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> 其他 (在 <br/>&nbsp;&nbsp; &nbsp;Comments column.)  | 用户数： <br/>详细信息：|
> | 是否计划从这些第三方移动用户 <br/>要Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 当前电话和会议解决方案是什么 <br/>此计划范围内的用户数？ | | |
> | 是否部署了支持直接路由[的 SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs) <br/>适用于此计划范围内办公室？ 如果是，<br/>记下"批注"列中的详细信息。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>协作平台部署详细信息

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，使用下面的示例Teams捕获部署的详细信息。 如果尚未部署Teams，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox"> 组织中所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br/>&nbsp;&nbsp; &nbsp; ("批注"列中指定。)  ||
> | 哪些Teams功能和形式？ | <input type="checkbox"> 基于频道的对话 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 来宾访问 <br/> <input type="checkbox"> 频道会议 <br/> <input type="checkbox"> 私人会议 <br/> <input type="checkbox"> 私人通话 <br/> <input type="checkbox"> 临时频道会面 <br/> <input type="checkbox"> 会议中的视频 <br/> <input type="checkbox"> 会议中屏幕共享 <br/> <input type="checkbox"> 音频会议 <br/><input type="checkbox"> 应用程序 (应用) <br/> &nbsp;&nbsp; &nbsp;<input type="checkbox">选项卡<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">机器人 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">连接器<br/><input type="checkbox"> 自定义云存储集成 <br/>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google <br/>&nbsp;&nbsp; &nbsp;驱动器，Egnyte <br/> <input type="checkbox"> 频道电子邮件集成 <br/> <input type="checkbox"> 其他 ("批注"列中的"指定")  | |
> | 哪些应用程序已部署到 Teams？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows移动版 | |
> | 谁有权创建团队？ | <input type="checkbox"> 组织中的每个人 <br/>&nbsp;&nbsp; &nbsp; (这是默认设置)  <br/> <input type="checkbox"> 特定人员 <br/>&nbsp;&nbsp; &nbsp; ("批注"列中指定。)  | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，使用下面的示例Skype for Business捕获联机部署的详细信息。 如果尚未部署联机Skype for Business，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为哪些类型的用户启用了Skype <br/>for Business Online？ | <input type="checkbox"> 组织中所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br/>&nbsp;&nbsp; &nbsp; ("批注"列中指定。)  | |
> | 当前包含哪些形式和功能 <br/>今天使用？ | <input type="checkbox"> 即时消息和状态 (IM/P) <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> Microsoft 音频会议 <br/> <input type="checkbox"> 第三方音频会议 (注意<br/>&nbsp;&nbsp; &nbsp; "批注"列中的详细信息)  <br/> <input type="checkbox"> 呼叫计划 (以前称为 PSTN 呼叫)  <br/> <input type="checkbox"> 组织自动助理 <br/> <input type="checkbox"> 呼叫队列 | |
> | 你明确阻止了Skype的任何 <br/>Business Online 功能？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 你使用或计划使用什么方法 <br/>将电话系统 (云 PBX) 连接到 <br/>PSTN？ <br/>选择所有适用项。 | <input type="checkbox"> 呼叫计划 (以前称为 PSTN 呼叫)  <br/> <input type="checkbox"> 本地 PSTN 连接 <br/>&nbsp;&nbsp; &nbsp; (利用现有Skype <br/>&nbsp;&nbsp; &nbsp;Business 2015 或 Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013 部署)  <br/> <input type="checkbox"> 本地 PSTN 连接 <br/>&nbsp;&nbsp; &nbsp; (Cloud Connector)  | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这适用于通话计划和音频 <br/>会议功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business本地 (（如果适用) 

如果适用，使用下面的示例Skype for Business捕获部署的详细信息。 如果尚未在本地部署Skype for Business，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 哪些版本的 Lync 或 Skype for Business <br/> 当前部署在本地？ | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">2015 Skype for Business Server 2015 年 1 月 <br/> <input type="checkbox">2019 Skype for Business Server 2019 年 1 月 <br/><input type="checkbox">Skype for Business云连接器 <br/>&nbsp;&nbsp; &nbsp;版本 | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 此环境是否由第三方托管和管理 <br/>party？ 如果是，请记下 <br/>"批注"列。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 当前使用哪些形式和功能 <br/>今天？ | <input type="checkbox"> 即时消息和状态 (IM/P)  <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> 持久聊天/群组聊天 <br/> <input type="checkbox"> Microsoft 音频会议 <br/>&nbsp;&nbsp; &nbsp; ("电话拨入式会议") 您的 <br/>&nbsp;&nbsp; &nbsp; 本地 Lync Server 或 <br/>&nbsp;&nbsp; &nbsp; Skype for Business部署 <br/> <input type="checkbox"> 第三方音频会议 <br/>&nbsp;&nbsp; &nbsp; (注释中的详细信息 <br/>&nbsp;&nbsp; &nbsp; column.)  <br/> <input type="checkbox">企业语音本地部署 <br/>&nbsp; &nbsp; &nbsp;PSTN 连接 <br/> <input type="checkbox"> 呼叫计划 (PSTN 呼叫) 通过 <br/>&nbsp;&nbsp; &nbsp;与 Skype for Business Online 的混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox">OfficeCommunications Server 2007 "R1" <br/> <input type="checkbox">OfficeCommunications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">2015 Skype for Business Server 2015 年 1 月 <br/> <input type="checkbox">2019 Skype for Business Server 2019 年 1 月| |
> | 您是否拥有 Lync 或 Skype for Business Edge <br/>部署到多个数据中心？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 选择 Edge 角色目前提供的服务。 | <input type="checkbox"> 企业用户 (外部)  <br/> <input type="checkbox"> 远程用户访问 (匿名 <br/>&nbsp;&nbsp; &nbsp; 外部会议参与者)  <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 媒体中继 | |
> | 你具有以下语音呼叫功能中的哪一项 <br/>当前是否依赖于？ <br/>请注意注释中任何其他依赖项 <br/>列。 | <input type="checkbox"> 繁忙选项 <br/> <input type="checkbox"> 呼叫公园 <br/> <input type="checkbox"> 呼叫取件或群组呼叫取件 <br/> <input type="checkbox"> 常用区域电话或"热桌面" <br/> <input type="checkbox"> 响应组或寻线组 <br/> <input type="checkbox"> 共享线条外观 <br/> <input type="checkbox"> 专用线 <br/> <input type="checkbox"> 语音邮件 <br/> <input type="checkbox"> 通过工作呼叫 <br/> <input type="checkbox"> 紧急号码或信息号码 <br/>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 分机拨号 <br/> <input type="checkbox"> 自动助理 <br/> <input type="checkbox"> 订户访问权限 <br/> <input type="checkbox"> 模拟设备 <br/> <input type="checkbox"> 传真 <br/> <input type="checkbox"> 来电显示屏蔽或更改 <br/> <input type="checkbox"> 基于位置的路由 <br/> <input type="checkbox"> 成本最低路由 <br/> <input type="checkbox"> 电梯电话 | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>网络和访问Microsoft 365 Office 365服务

使用下表捕获组织的网络详细信息，以及用户如何 (或) 连接到Microsoft 365 Office 365服务。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 如何 (或如何) 迁移范围内的用户 <br/>Teams办公室时访问？ <br/>选择所有适用项。 | <input type="checkbox"> 路由 NAT 连接 <br/> <input type="checkbox"> 代理服务器 <br/> <input type="checkbox"> 公共Wi-Fi <br/> <input type="checkbox"> 托管 (公共) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft 对等互连)  ||
> | 如果对 Microsoft 365 或 Office 365的访问是通过<br/>代理服务器，是否可以通过任何方式绕过代理？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 否，但正在计划中 | |
> | 是否执行了网络就绪性评估？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 连接到 时，用户是否需使用 VPN <br/>远程企业资源？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用 VPN，则Teams流量排除 <br/>用于直接访问服务Microsoft 365 Office 365 VPN？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 能否优先Teams音频和视频流量 <br/>推动高质量的体验？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否一个区域内的所有位置都有 Internet 出口， <br/>或者 Internet 出口是否针对整个区域集中？ | <input type="checkbox"> 对 Internet 的区域访问 <br/> <input type="checkbox"> 集中访问 <br/>&nbsp;&nbsp; &nbsp; Internet | |

## <a name="endpoints"></a>终结点

使用下表捕获使用的客户端和终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox">WindowsXP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac ("批注"列中指定版本)  <br/> <input type="checkbox"> Linux (在 Comments 列中指定分布)  <br/><input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 部署Microsoft Office版本 <br/>到这些设备？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">2010 Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">2016 Office 2016 年 1 月 <br/> <input type="checkbox">Office for Mac 2011 年 1 月 <br/> <input type="checkbox">2016 Office for Mac 2016 年 1 月 <br/> <input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 使用Office部署技术 <br/>在你的组织中？ | <input type="checkbox"> MSI <br/> <input type="checkbox"> 单击运行 | |
> | 允许和支持的移动设备是什么 <br/>使用中的平台？ <br/>选择所有适用项。 | <input type="checkbox">Windows <br/> <input type="checkbox"> 移动版 <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 如何提供移动设备？ <br/>选择所有适用项。 | <input type="checkbox"> 企业设备 <br/> <input type="checkbox"> 自带设备 | |
> | 用户当前用于访问的设备 <br/>语音和会议服务 <br/> (手机、耳机、电话、视频) ？ | | |

## <a name="operations"></a>运营

使用下表捕获环境的操作方面的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 您的 Lync Server 的操作模型是什么， <br/>Skype for Business Server、Microsoft 365部署、 <br/>或Office 365部署？ | | |
> | 能否概述当前的支持安排 <br/>Lync Server、Skype for Business Server、Microsoft 365、 <br/>还是Office 365？ | | |
> | 如果要部署到多个国家/地区， <br/>每个国家/地区是否都有自己的 IT/电话 <br/>要与员工合作，或者这将集中管理吗？ | <input type="checkbox"> 区域操作和支持 <br/> <input type="checkbox"> 集中式操作和支持 | |
> | 是否遵循通话质量方法？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否将个人或团队分配到 <br/>协作平台的质量冠军角色 <br/>使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何监视 Lync Server，Skype <br/>Business Server、Microsoft 365部署，或 <br/>Office 365部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 如何以及何时向 <br/>有关新服务和功能的技术支持？ | | |

## <a name="adoption-and-readiness"></a>采用和准备情况

使用下表并提供组织的当前采用和就绪状态。

>
> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 你当前的活动使用情况是什么 <br/>Skype for Business？ | **__** 活动用户总数与启用的用户的百分比 | |
> | 你的组织如何使用 <br/>Skype for Business？ | 一对一对话 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">通话 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br/> 会议 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">会议<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">通话 | |
> | 组织是否采用用户 <br/>和更改管理团队？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 当前如何衡量技术成功 <br/>推出，例如 Skype for Business？ | | |
> | 用户群的百分比 <br/>已Skype for Business？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox"> 很好 <br/> <input type="checkbox"> 中性 <br/> <input type="checkbox"> 错误 | |
> | 下列哪一项最能描述推出 <br/>策略用于Skype for Business <br/>部署？ | <input type="checkbox"> 广泛宣传：电子邮件市场活动 <br/>&nbsp;&nbsp; &nbsp; 培训链接 <br/> <input type="checkbox"> 扩展：广泛覆盖以及各种 <br/>&nbsp;&nbsp; &nbsp; 通过海报 (意识活动; <br/>&nbsp;&nbsp; &nbsp; 活动、冠军) 和培训 <br/>&nbsp;&nbsp; &nbsp; (视频、用户指南、个人)  <br/> <input type="checkbox"> 定制：扩展的，以及有针对性的 <br/>&nbsp;&nbsp; &nbsp; 按人员发送消息和培训 <br/> <input type="checkbox"> 其他 <br/>&nbsp;&nbsp; &nbsp; ("注释"列中的详细信息。)  | |
