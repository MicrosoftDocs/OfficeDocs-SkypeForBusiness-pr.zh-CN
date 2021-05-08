---
title: Microsoft Teams升级|环境评估、发现问题
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 使用本指南了解正确评估当前环境以升级到 Teams。
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
ms.openlocfilehash: f3d1349cf32e652cc308bb85c187db90303aa959
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808952"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>发现调查问卷 - 评估环境

下表列出了一组问题，这些问题有助于在升级到 Teams 之前[评估环境](upgrade-plan-journey-evaluate-environment.md)：

- [Microsoft 365或Office 365组织详细信息](#microsoft-365-or-office-365-organization-details)
- [现有协作平台摘要](#existing-collaboration-platform-summary)
- [协作平台部署详细信息](#collaboration-platform-deployment-details)
- [网络和访问Microsoft 365 Office 365服务](#networking-and-access-to-microsoft-365-or-office-365-services)
- [终结点](#endpoints)
- [运营](#operations)
- [采用和准备情况](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365或Office 365组织详细信息

强烈建议你在处理调查问卷时Microsoft 365或Office 365组织。 如果尚未激活或配置组织或Microsoft 365 Office 365，请参阅规划企业Microsoft 365[设置](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表捕获有关组织或Microsoft 365 Office 365的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 记下生产Microsoft 365或Office 365组织 <br>"答案"列中的名称和 ID <br/>如果拥有多个租户 <br>与组织关联， <br>记下所有 ID。 | 租户名称： <br/>租户 ID：| |
> | 租户部署在哪些区域？| | |
> | 这些租户是多租户Microsoft 365还是Office 365租户或 <br>专用？ | <input type="checkbox"> 多租户<br/> <input type="checkbox"> 专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>请注意为每个用户启用的用户数 <br>服务。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint联机 <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 其他| |
> | 为哪些用户启用了Skype级别 <br>Business Online 用户？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 独立 | 用户数 <br>对于每个 SKU： |
> | 当前 Active Directory 林是什么 <br>环境中的功能级别？ <br/>如果多个林，请记下详细信息 <br>。 | <input type="checkbox">WindowsServer 2000 <br/> <input type="checkbox">WindowsServer 2003 <br/> <input type="checkbox">WindowsServer 2008<br/> <input type="checkbox">WindowsServer 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 用于目录的是什么 <br>今天同步？ |<input type="checkbox"> 只有云 (同步)  <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp; 连接 <br/> <input type="checkbox"> 其他 (在 <br>&nbsp;&nbsp; &nbsp;Comments column.) | |
> | 当前是否已部署联合标识？ <br/> (Active Directory 联合身份验证服务或 <br>第三方)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用联合标识，则 <br>联合基础结构？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> 第三方联合 <br>&nbsp;&nbsp; &nbsp; 网关 <br>&nbsp;&nbsp; &nbsp; (请注意 <br>&nbsp;&nbsp; &nbsp;Comments column.)  | |
> | 如果当前保持活动Microsoft 365或Office 365 <br>租户， 是 <br>与租户关联的目标用户？ | <input type="checkbox">N/A – 无Microsoft 365或Office 365 <br>&nbsp;&nbsp; &nbsp; 租户就地 <br/> <input type="checkbox"> 否，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 域未关联 <br>&nbsp;&nbsp; &nbsp; 中具有任何租户 <br>&nbsp;&nbsp; &nbsp; Microsoft 365或Office 365 <br/> <input type="checkbox"> 是，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 域已关联 <br>&nbsp;&nbsp; &nbsp; 使用现有租户 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 或 Office 365 | |
> | 用户 UPN 是否匹配其主 SMTP 地址？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>现有协作平台摘要

使用下表捕获有关现有协作平台部署的信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否已部署 Skype for Business？ <br/>对于本地和混合部署，请确保 <br>请注意 CU 版本和累积更新 (CU)  <br>"批注"列中的详细信息。 | <input type="checkbox">是，Microsoft 365或Office 365 <br/> <input type="checkbox">是， (混合Microsoft 365或Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管的共享 (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Exchange？ <br/>对于本地和混合部署，请确保 <br>请注意注释中的版本和 CU 详细信息 <br>列。 | <input type="checkbox">是，Microsoft 365或Office 365 <br/> <input type="checkbox">是， (混合Microsoft 365或Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管，共享 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 SharePoint？ <br/>对于本地和混合部署，请确保 <br>请注意注释中的版本和 CU 详细信息 <br>列。 | <input type="checkbox">是，Microsoft 365或Office 365 <br/> <input type="checkbox">是， (混合Microsoft 365或Office 365)  <br/> <input type="checkbox"> 是，在本地 <br/> <input type="checkbox"> 是，联机，专用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，托管，专用 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 是，托管，共享 <br>&nbsp;&nbsp; &nbsp; (第三方)  <br/> <input type="checkbox"> 否，其他 | |
> | 是Microsoft 365还是Office 365 OneDrive for Business部署？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否部署了任何其他第三方平台 <br>和当前使用中？ 如果是这样，请记下 <br>这些平台和注释中的使用情况详细信息 <br>列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> 其他 (批注中的"指定" <br>&nbsp;&nbsp; &nbsp; column.)  | 用户数： <br/>详细信息：|
> | 是否计划从这些第三方移动用户 <br>要Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 当前电话和会议解决方案是什么 <br>此计划范围内的用户数？ | | |
> | 是否针对此计划范围内办公室部署了支持直接路由的[SDC？](direct-routing-plan.md#supported-session-border-controllers-sbcs) <br>如果是，请记下"批注"列中的详细信息。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>协作平台部署详细信息

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，使用下面的示例Teams捕获部署的详细信息。 如果尚未部署Teams，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox"> 组织中所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br>&nbsp;&nbsp; &nbsp; ("批注"列中指定)  ||
> | 哪些Teams功能和形式正在使用？ | <input type="checkbox"> 基于频道的对话 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 来宾访问 <br/> <input type="checkbox"> 频道会议 <br/> <input type="checkbox"> 私人会议 <br/> <input type="checkbox"> 私人通话 <br/> <input type="checkbox"> 临时频道会面 <br/> <input type="checkbox"> 会议中的视频 <br/> <input type="checkbox"> 会议中屏幕共享 <br/> <input type="checkbox"> 音频会议 <br/><input type="checkbox"> 应用程序 (应用) <br> &nbsp;&nbsp; &nbsp;<input type="checkbox">选项卡<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">机器人 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">连接器<br><input type="checkbox"> 自定义云存储集成 <br>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google 云端硬盘、Egnyte <br/> <input type="checkbox"> 频道电子邮件集成 <br/> <input type="checkbox"> 其他 ("批注"列中的"指定")  | |
> | 哪些应用程序已部署到 Teams？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows移动版 | |
> | 谁有权创建团队？ | <input type="checkbox"> 组织中的每个人 <br>&nbsp;&nbsp; &nbsp; (这是默认设置)  <br/> <input type="checkbox"> 特定人员 <br>&nbsp;&nbsp; &nbsp; ("批注"列中指定。)  | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，使用下面的示例Skype for Business捕获联机部署的详细信息。 如果尚未部署联机Skype for Business，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 为哪些类型的用户启用了Skype <br>for Business Online？ | <input type="checkbox"> 组织中所有用户 <br/> <input type="checkbox"> 特定用户/用户组 <br>&nbsp;&nbsp; &nbsp; ("批注"列中指定)  | |
> | 当前包含哪些形式和功能 <br>今天使用？ | <input type="checkbox"> 即时消息和状态 (IM/P) <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> Microsoft 音频会议 <br/> <input type="checkbox"> 第三方音频会议 <br>&nbsp;&nbsp; &nbsp; ("注释"列中的详细信息。)  <br/> <input type="checkbox"> 呼叫计划 (以前称为 PSTN 呼叫)  <br/> <input type="checkbox"> 组织自动助理 <br/> <input type="checkbox"> 呼叫队列 | |
> | 是否明确阻止了任何Skype <br>Business Online 功能？ <br>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 你使用或计划使用什么方法 <br>将电话系统 (以前为云 PBX) 连接到 <br>PSTN？ <br/>选择所有适用项。 | <input type="checkbox"> 呼叫计划 (以前称为 PSTN 呼叫)  <br/> <input type="checkbox"> 本地 PSTN 连接 (现有 <br>&nbsp;&nbsp; &nbsp; Skype for Business 2015 或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 部署)  <br/> <input type="checkbox"> 使用 Cloud Connector (本地 PSTN 连接)  | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这适用于通话计划和音频 <br>会议功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business本地 (（如果适用) 

如果适用，使用下面的示例Skype for Business捕获部署的详细信息。 如果尚未在本地部署Skype for Business，请跳过本部分。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 当前 Lync 或 Skype for Business的版本 <br>是否部署在本地？ | <input type="checkbox">OfficeCommunications Server 2007 "R1" <br/> <input type="checkbox">OfficeCommunications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">2015 Skype for Business Server 2015 年 1 月 <br/> <input type="checkbox">Skype for Business Server 2019 年 1 月 <br/> <input type="checkbox">Skype for Business 云连接器版本 | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 此环境是否由第三方托管和管理？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 当前使用哪些形式和功能 <br>今天？ | <input type="checkbox"> 即时消息和状态 (IM/P)  <br/> <input type="checkbox"> 会议 <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 会议录制 <br/> <input type="checkbox"> 持久聊天/群组聊天 <br/> <input type="checkbox"> Microsoft 音频会议 <br>&nbsp;&nbsp; &nbsp; (电话拨入式会议) 您的 <br>&nbsp;&nbsp; &nbsp; 本地 Lync Server 或 <br>&nbsp;&nbsp; &nbsp; Skype for Business部署 <br/> <input type="checkbox"> 第三方音频会议 <br>&nbsp;&nbsp; &nbsp; ("批注"列中的详细信息)  <br/> <input type="checkbox">企业语音本地 PSTN <br>&nbsp;&nbsp; &nbsp; 连接 <br/> <input type="checkbox"> 呼叫计划 (以前称为 PSTN 呼叫) 通过 <br>&nbsp;&nbsp; &nbsp;与 Skype for Business Online 的混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox">OfficeCommunications Server 2007 "R1" <br/> <input type="checkbox">OfficeCommunications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">2015 Skype for Business Server 2015 年 1 月 <br/> <input type="checkbox">Skype for Business Server 2019 年 1 月 | |
> | 是否部署了 Lync 或 Skype for Business Edge <br>进入多个数据中心？ <br/>如果是，请记下"批注"列中的详细信息。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 选择 Edge 角色目前提供的服务。 | <input type="checkbox"> 企业用户 (外部)  <br/> <input type="checkbox"> 远程用户访问 (匿名外部 <br>&nbsp;&nbsp; &nbsp; 会议参与者)  <br/> <input type="checkbox"> 联合身份验证 <br/> <input type="checkbox"> 媒体中继 | |
> | 你具有以下语音呼叫功能中的哪一项 <br>当前是否依赖于？ <br/>请注意注释中任何其他依赖项 <br>列。 | <input type="checkbox"> 繁忙选项 <br/> <input type="checkbox"> 呼叫公园 <br/> <input type="checkbox"> 呼叫取件或群组呼叫取件 <br/> <input type="checkbox"> 常用区域电话或"热桌面" <br/> <input type="checkbox"> 响应组或寻线组 <br/> <input type="checkbox"> 共享线条外观 <br/> <input type="checkbox"> 专用线 <br/> <input type="checkbox"> 语音邮件 <br/> <input type="checkbox"> 通过工作呼叫 <br/> <input type="checkbox"> 紧急号码或信息号码 <br>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 分机拨号 <br/> <input type="checkbox"> 自动助理 <br/> <input type="checkbox"> 订户访问权限 <br/> <input type="checkbox"> 模拟设备 <br/> <input type="checkbox"> 传真 <br/> <input type="checkbox"> 来电显示屏蔽或更改 <br/> <input type="checkbox"> 基于位置的路由 <br/> <input type="checkbox"> 成本最低路由 <br/> <input type="checkbox"> 电梯电话 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>网络和访问Microsoft 365 Office 365服务

使用下表捕获组织的网络详细信息，以及用户如何 (或) 连接到Microsoft 365 Office 365服务。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 如何 (或如何) 迁移范围内的用户 <br>Teams办公室时访问？ <br/>选择所有适用项。 | <input type="checkbox"> 路由 NAT 连接 <br/> <input type="checkbox"> 代理服务器 <br/> <input type="checkbox"> 公共Wi-Fi <br/> <input type="checkbox"> 托管 (公共) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (Microsoft 对等互连)  ||
> | 如果对 Microsoft 365 或 Office 365 的访问权限是通过代理服务器访问的，则是否有 <br>绕过代理的任何方式？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 否，但正在计划中 | |
> | 是否执行了网络就绪性评估？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 连接到 时，用户是否需使用 VPN <br>远程企业资源？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用 VPN，则Teams流量排除 <br>用于直接访问服务Microsoft 365 Office 365 VPN？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 能否优先Teams音频和视频流量 <br>推动高质量的体验？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否一个区域内的所有位置都有 Internet 出口， <br>或者 Internet 出口是否针对整个区域集中？ | <input type="checkbox"> 对 Internet 的区域访问 <br/> <input type="checkbox"> 集中访问 Internet | |

## <a name="endpoints"></a>终结点

使用下表捕获使用的客户端和终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox">WindowsXP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac ("批注"列中指定版本。)  <br/> <input type="checkbox"> Linux (在 Comments 列中指定分布)  <br/> <input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 部署Microsoft Office版本 <br>到这些设备？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">2007 Office 2007 年 1 月 <br/> <input type="checkbox">Office 2010 年 10 月 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 年 1 月 <br/> <input type="checkbox">2011 Office for Mac 2011 <br/> <input type="checkbox">2016 Office for Mac 2016 年 1 月 <br/> <input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 哪些Office部署技术 <br>在你的组织中？ | <input type="checkbox"> MSI <br/> <input type="checkbox"> 单击运行 | |
> | 允许和支持的移动设备是什么 <br>使用中的平台？ <br/>选择所有适用项。 | <input type="checkbox">Windows <br/> <input type="checkbox"> 移动版 <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (请注意"批注"列中的详细信息。)  | |
> | 如何提供移动设备？ <br/>选择所有适用项。 | <input type="checkbox"> 企业设备 <br/> <input type="checkbox"> 自带设备 | |
> | 用户当前用于访问的设备 <br>语音和会议服务 <br> (手机、耳机、电话、视频) ？ | | |

## <a name="operations"></a>运营

使用下表捕获环境的操作方面的详细信息。

> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 您的 Lync Server 的操作模型是什么， <br>Skype for Business Server、Microsoft 365 或 Office 365 部署 <br>今天？ | | |
> | 能否概述当前的支持安排 <br>Lync Server、Skype for Business Server、Microsoft 365 或 Office 365？ | | |
> | 如果要部署到多个国家/地区， <br>每个国家/地区是否都有自己的 IT/电话 <br>要与员工合作，或者这将集中管理吗？ | <input type="checkbox"> 区域操作和支持 <br/> <input type="checkbox"> 集中式操作和支持 | |
> | 是否遵循呼叫 [质量方法](quality-of-experience-review-guide.md)？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否将个人或团队分配到 <br>协作平台的质量冠军角色 <br>使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何监视 Lync Server，Skype <br>Business Server、Microsoft 365或 Office 365 部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 如何以及何时向 <br>有关新服务和功能的技术支持？ | | |

## <a name="adoption-and-readiness"></a>采用和准备情况

使用下表并提供组织的当前采用和就绪状态。

>
> | 问题 | 回答 | 备注 |
> |---|---|---|
> | 你当前的活动使用情况是什么 <br>Skype for Business？ | **__** 活动用户总数与启用的用户的百分比 | |
> | 你的组织如何使用 <br>Skype for Business？ | 一对一对话 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">通话 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br> 会议 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">会议<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共享<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">通话 | |
> | 组织是否采用用户 <br>和更改管理团队？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 当前如何衡量技术成功 <br>推出，如 Skype for Business？ | | |
> | 用户群的百分比 <br>已Skype for Business？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox"> 很好 <br/> <input type="checkbox"> 中性 <br/> <input type="checkbox"> 错误 | |
> | 下列哪一项最能描述推出 <br>策略用于Skype for Business <br>部署？ | <input type="checkbox"> 广泛宣传：电子邮件市场活动 <br>&nbsp;&nbsp; &nbsp; 培训链接 <br/> <input type="checkbox"> 扩展：广泛覆盖以及各种 <br>&nbsp;&nbsp; &nbsp; 通过海报 (意识活动; <br>&nbsp;&nbsp; &nbsp; 小项、) 和培训 <br>&nbsp;&nbsp; &nbsp; (视频、用户指南、个人)  <br/> <input type="checkbox"> 定制：扩展的，以及有针对性的 <br>&nbsp;&nbsp; &nbsp; 按人员发送消息和培训 <br/> <input type="checkbox"> 其他 <br>&nbsp;&nbsp; &nbsp; ("注释"列中的详细信息。)  | |


