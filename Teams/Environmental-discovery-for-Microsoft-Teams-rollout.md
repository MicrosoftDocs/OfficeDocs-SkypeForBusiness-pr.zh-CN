---
title: Microsoft 小组部署的环境的发现
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 如何规划从 Skype 业务您迁移到 Microsoft 小组执行详细的环境发现。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5fde916c4fe9ece9ad80ec63dad1618fa0d1ae5
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Microsoft 小组部署的环境的发现
===================================================

发现是时采取计划为您的旅程到 Microsoft 小组第一，关键步骤之一。

执行详细的发现您的环境以更好地了解其当前状态并显示任何困难或 — — 更进一步 — — 可能阻止程序执行团队展示。

<a name="discovery-questionnaire"></a>发现调查表
=======================

下面的示例调查表将引导您完成一组问题，以确认您的组织已准备好的音频会议和电话系统调用计划在团队中的能力与成功地展示。

您现有协作基础结构和 Office 365 租户、 联网、 终结点、 操作以及采用和准备工作相关的所有事宜都的环境发现调查表的一部分。

调查表分为多个部分，以确认您所在组织的团队部署主要体现在几个方面的准备工作。 项目团队以提供请求的信息尽可能详细的信息，以帮助您规划的活动与合作。

> [!TIP]
> 您可以通过复制到 Word 文档的调查表。 尝试回答所有的问题中, 移动时捕获的所有详细信息。

<a name="project-team"></a>项目团队
------------

捕获关键利益相关者团队展示项目的详细的信息。 请注意，一个人可以扮演多个角色在整个项目。

> | 角色                                  | 姓名、 电子邮件地址、 电话号码 | 时区的位置 | 备注      |
> |---------------------------------------|-----------------------------------|---------------------|---------------|
> | 执行发起人                     |                                   |                     |               |
> | 项目主管                          |                                   |                     |               |
> | 协作主管/架构师          |                                   |                     |               |
> | 顾问                            |                                   |                     |               |
> | 项目经理                       |                                   |                     |               |
> | 变更管理/采用专业人员 |                                   |                     |               |
> | 网络主管                          |                                   |                     |               |
> | 安全主管                         |                                   |                     |               |
> | 电话服务主管                        |                                   |                     |               |
> | 桌面主管                          |                                   |                     |               |
> | 支持主管                |                                   |                     |               |
> | 部署主管                       |                                   |                     |               |
> | 服务所有者                         |                                   |                     |               |
> | 设施主管                       |                                   |                     |               |
> | 语音团队主管                       |                                   |                     |               |
> | 业务部门的潜在顾客                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Office 365 租户详细信息
-------------------------

我们强烈建议您有当前的 Office 365 租户，当您使用此调查表。 如果尚未激活或尚未配置 Office 365 租户，请参阅[规划业务的 Office 365 的安装程序](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表来捕获 Office 365 租户有关的信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 请注意生产 Office 365 租户 <br>名称和 ID 在答案列 <br/>如果您有多个租户 <br>与您的组织， <br>请注意所有 Id。  | 租户名称： <br/>租户 ID:| |
> | 在哪些区域中承租人部署？| | |
> | 是这些租户 Office 365 Multitenant 或 <br>专用？ | <input type="checkbox">Multitenant<br/> <input type="checkbox">专用 | |
> | 目前使用哪些 Microsoft Online 产品？ <br/>注意对于每个启用的用户的数量 <br>在注释列中的服务。 | <input type="checkbox">Microsoft 的小组 <br/> <input type="checkbox">Skype 的业务 <br>&nbsp;&nbsp; &nbsp;在线 <br/> <input type="checkbox">联机交换 <br/> <input type="checkbox">SharePoint 在线 <br/> <input type="checkbox">OneDrive 为公司的 <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">其他|                                   |
> | 对 Skype 的启用许可证级别 <br>业务联机用户吗？ | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | 用户数 <br>对于每个 SKU: |
> | 什么是当前的活动目录林中 <br>在环境中的功能级别？ <br/>如果有多个林，注意细节 <br>在注释列中。 | <input type="checkbox">Windows 2000 服务器 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 您使用什么目录 <br>今天同步？ |<input type="checkbox">没有同步 （仅云） <br/> <input type="checkbox">Azure 的活动目录 <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox">其他 (在中指定 <br>&nbsp;&nbsp; &nbsp;注释列。)| |
> | 当前是否已部署联合标识？ <br/>(Active Directory 联合身份验证服务或 <br>第三方) | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果您正在使用联合的身份，是什么 <br>联合身份验证基础结构？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">第三方联盟 <br>&nbsp;&nbsp; &nbsp;网关 <br>&nbsp;&nbsp; &nbsp;(请注意中的详细信息 <br>&nbsp;&nbsp; &nbsp;注释列。) | |
> | 如果当前维护活动的 Office 365 <br>租户的 SMTP/SIP 域，您 <br>与租户相关的目标的用户吗？ | <input type="checkbox">N/A--没有 Office 365 <br>&nbsp;&nbsp; &nbsp;租户在的地方 <br/> <input type="checkbox">否，用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域无关 <br>&nbsp;&nbsp; &nbsp;在任何承租人与 <br>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox">是的用户的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp;域关联时 <br>&nbsp;&nbsp; &nbsp;与现有租户 <br>&nbsp;&nbsp; &nbsp;Office 365 中 | |
> | 用户的 Upn 与他们的主要 SMTP 地址？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">一致 | |

<a name="existing-collaboration-platform-summary"></a>摘要现有协作平台
---------------------------------------

使用下表来获取有关您现有的协作平台的部署信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 是否已部署 Skype for Business？ <br/>对于内部部署和混合部署，请确保 <br>记下您的版本和累积更新 (CU) <br>在注释列中的详细信息。 | <input type="checkbox">是的 Office 365 <br/> <input type="checkbox">是的 （与 Office 365) 的混合 <br/> <input type="checkbox">是的在部署 <br/> <input type="checkbox">是的在线的专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是的承载、 专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是的承载共享 （第三方） <br/> <input type="checkbox">没有其他 | |
> | 是否已部署 Exchange？ <br/>对于内部部署和混合部署，请确保 <br>您注意到的版本和注释中的 CU 详细信息 <br>列。 | <input type="checkbox">是的 Office 365 <br/> <input type="checkbox">是的 （与 Office 365) 的混合 <br/> <input type="checkbox">是的在部署 <br/> <input type="checkbox">是的在线的专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是的承载、 专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是的承载、 共享 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">没有其他 | |
> | 是否已部署 SharePoint？ <br/>对于内部部署和混合部署，请确保 <br>您注意到的版本和注释中的 CU 详细信息 <br>列。 | <input type="checkbox">是的 Office 365 <br/> <input type="checkbox">是的 （与 Office 365) 的混合 <br/> <input type="checkbox">是的在部署 <br/> <input type="checkbox">是的在线的专用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">是的承载、 专用 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">是的承载、 共享 <br>&nbsp;&nbsp; &nbsp;（第三方） <br/> <input type="checkbox">没有其他 | |
> | 为部署的业务是 Office 365 OneDrive？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 您部署的任何其他第三方平台 <br>和目前在使用？ 如果是这样，请注意用户的数量 <br>这些平台和注释中的使用率详细信息 <br>列。 | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">可宽延时间 <br/> <input type="checkbox">其他 （指定注释中 <br>&nbsp;&nbsp; &nbsp;列。) | 用户数： <br/>详细信息：|
> | 您打算移动用户从这些第三方 <br>对团队的平台？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 当前的电话和会议解决方案是什么 <br>这计划的作用域中的用户？ | | |

<a name="collaboration-platform-deployment-details"></a>协作平台的部署详细信息
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams（如果适用）

如果适用，请使用下面的示例表捕获您的团队部署的详细信息。 如果您尚未部署团队，跳过此部分。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 为 Teams 启用了哪些类型的用户？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定的用户/用户组 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定） ||
> | 在使用哪些团队功能和形式？ | <input type="checkbox">基于通道的对话 <br/> <input type="checkbox">私人聊天 <br/> <input type="checkbox">来宾访问 <br/> <input type="checkbox">通道会议 <br/> <input type="checkbox">专用的会议 <br/> <input type="checkbox">私人电话 <br/> <input type="checkbox">Ad hoc 通道 meetup <br/> <input type="checkbox">在会议中的视频 <br/> <input type="checkbox">在会议中共享的屏幕 <br/> <input type="checkbox">音频会议 <br/><input type="checkbox">应用程序 （应用程序）<br> &nbsp;&nbsp; &nbsp; <input type="checkbox">选项卡<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">机器人 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">连接器<br><input type="checkbox">自定义云存储集成 <br>&nbsp;&nbsp; &nbsp;框、 收存、 ShareFile (Google 驱动器） <br/> <input type="checkbox">通道电子邮件集成 <br/> <input type="checkbox">其他 （注释列中指定）。 | |
> | 向团队已部署哪些应用程序？ | | |
> | 你是否专门阻止过任何 Teams 功能？ <br/>如果是，请注意在注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 目前使用哪些 Teams 客户端？ | <input type="checkbox">网站 <br/> <input type="checkbox">窗口 <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | 谁有权创建团队？ | <input type="checkbox">组织中的每个人 <br>&nbsp;&nbsp; &nbsp;（这是默认设置） <br/> <input type="checkbox">特定人员 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定）。 | |
> | 你在 Teams 中是否使用安全与合规性功能？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online（如果适用）

如果适用，请使用下面的示例表捕获您 Skype 的在线业务部署的详细信息。 如果您没有联机业务部署的部署 Skype，跳过此部分。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 哪种类型的用户启用了 Skype <br>对于在线业务吗？ | <input type="checkbox">组织中的所有用户 <br/> <input type="checkbox">特定的用户/用户组 <br>&nbsp;&nbsp; &nbsp;（注释列中的指定） | |
> | 什么形式和功能是当前 <br>在目前使用？ | <input type="checkbox">即时消息和状态 (IM/P)<br/> <input type="checkbox">会议 <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">会议记录 <br/> <input type="checkbox">Microsoft 的音频会议 <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息）。 <br/> <input type="checkbox">调用计划 (以前称为 PSTN 调用) <br/> <input type="checkbox">组织的自动助理 <br/> <input type="checkbox">电话队列 | |
> | 已明确禁止任何 Skype 的吗 <br>在线的业务能力？ <br>如果是，请注意在注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 哪种方法是使用或打算使用的 <br>连接到电话系统 (以前称为云 PBX) <br>PSTN 吗？ <br/>请选择所有适用。 | <input type="checkbox">调用计划 (以前称为 PSTN 调用) <br/> <input type="checkbox">内部 （利用现有的 PSTN 连接性 <br>&nbsp;&nbsp; &nbsp;Skype 业务 2015年或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;部署) <br/> <input type="checkbox">内部部署的 PSTN 连接 （使用云连接器） | |
> | 是否已将任何电话号码转网到 Microsoft？ <br/>这是适用于调用计划和音频 <br>会议功能。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype 业务内部 （如果适用）

如果适用，请使用下面的示例表捕获您 Skype 业务部署的详细信息。 如果您还没有为业务场所部署 Skype，跳过此部分。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Lync 或业务的 Skype 的哪些版本当前 <br>已部署的内部部署？ | <input type="checkbox">2007"R1"的办公通信服务器 <br/> <input type="checkbox">办公通信服务器 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype 业务服务器 2015 <br/> <input type="checkbox">Skype 的商务云连接器版 | |
> | 是否配置了与 Skype for Business Online 混合？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 为此环境承载和由第三方管理吗？ <br/>如果是，请注意在注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 哪种形式和功能正在使用中 <br>今天吗？ | <input type="checkbox">即时消息和状态 (IM/P) <br/> <input type="checkbox">会议 <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">会议记录 <br/> <input type="checkbox">持续聊天 / 组聊天 <br/> <input type="checkbox">Microsoft 的音频会议 <br>&nbsp;&nbsp; &nbsp;（以前称为拨入会议） 上您 <br>&nbsp;&nbsp; &nbsp;内部 Lync Server 或 <br>&nbsp;&nbsp; &nbsp;Skype 业务部署 <br/> <input type="checkbox">第三方音频会议 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息） <br/> <input type="checkbox">企业语音使用场所 PSTN <br>&nbsp;&nbsp; &nbsp;连接 <br/> <input type="checkbox">调用计划 (以前称为 PSTN 调用) 通过 <br>&nbsp;&nbsp; &nbsp;与 Skype 的在线业务的混合 | |
> | 你已部署 Edge Server 的哪个/哪些版本？ | <input type="checkbox">2007"R1"的办公通信服务器 <br/> <input type="checkbox">办公通信服务器 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype 业务服务器 2015 | |
> | 您有 Lync 或 Skype 业务部署的边缘 <br>到多个数据中心？ <br/>如果是，请注意在注释列中的详细信息。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 请选择边缘角色目前提供的服务。 | <input type="checkbox">外部用户访问 （企业用户） <br/> <input type="checkbox">远程用户访问 （匿名外部 <br>&nbsp;&nbsp; &nbsp;会议参与者) <br/> <input type="checkbox">联合身份验证 <br/> <input type="checkbox">媒体中继 | |
> | 其中以下调用功能的声音 <br>目前对有依赖关系？ <br/>请注意在注释任何附加依赖项 <br>列。 | <input type="checkbox">繁忙的选项 <br/> <input type="checkbox">挂断电话 <br/> <input type="checkbox">调用装货或组调用装货 <br/> <input type="checkbox">公共区域电话或者"热办公" <br/> <input type="checkbox">响应组或查寻组 <br/> <input type="checkbox">共享的行的外观 <br/> <input type="checkbox">专用线路 <br/> <input type="checkbox">语音邮件 <br/> <input type="checkbox">工作通过调用 <br/> <input type="checkbox">紧急情况或信息的数字 <br>&nbsp;&nbsp; &nbsp;911、 811 (411） <br/> <input type="checkbox">扩展拨号 <br/> <input type="checkbox">自动助理 <br/> <input type="checkbox">订阅者访问 <br/> <input type="checkbox">模拟设备 <br/> <input type="checkbox">传真 <br/> <input type="checkbox">呼叫方 ID 掩蔽或改变 <br/> <input type="checkbox">基于位置的路由 <br/> <input type="checkbox">最低成本路由 <br/> <input type="checkbox">电梯间电话 | |

<a name="networking-and-access-to-office-365-services"></a>网络和访问 Office 365 提供服务
--------------------------------------------

使用下表来捕获您的组织的网络详细信息和您的用户是如何 （或会） 连接到 Office 365 提供服务。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 如何 （或会） 范围内的迁移用户 <br>当他们在办公室时，请访问团队？ <br/>请选择所有适用。 | <input type="checkbox">路由的 NAT 连接 <br/> <input type="checkbox">代理服务器 <br/> <input type="checkbox">公共 Wi-Fi <br/> <input type="checkbox">管理 （不公开） 的 Wi-Fi <br/> <input type="checkbox">ExpressRoute （Microsoft 对等） ||
> | 如果 Office 365 访问是通过代理服务器，有 <br>有办法绕过代理服务器？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 <br/> <input type="checkbox">没有，但在计划 | |
> | 您是否进行网络准备情况评估？ <br/>有关详细信息，请参阅[网络就绪性评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)。 | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 使用 VPN 连接时所需的用户 <br>公司资源远程吗？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 如果使用 VPN，可以团队通信从排除 <br>若要直接访问 Office 365 服务 VPN？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 你的网络是否支持 QoS？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 可以确定团队音频和视频通信的优先级 <br>能够提供高品质的体验吗？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 在区域内的所有位置都有互联网出口吗 <br>或者为整个区域集中式互联网出口？ | <input type="checkbox">地区访问互联网 <br/> <input type="checkbox">集中式的访问互联网 | |

> [!TIP]
> 要计算的带宽和其他网络要求的云语音量部署，具体取决于您所在组织的详细信息及估计的使用、 访问[网络规划人员](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)在[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)。

<a name="endpoints"></a>端点
---------

使用下表来捕获客户端和正在使用的终结点的详细信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 用户当前使用哪个桌面 OS？ | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac （指定的注释列中的版本）。 <br/> <input type="checkbox">其他 （请注意注释列中的详细信息）。 | |
> | 哪种版本的 Microsoft Office 部署 <br>向这些设备？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">2013 年办公室 <br/> <input type="checkbox">Office 2016 年 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox">其他 （请注意注释列中的详细信息）。 | |
> | 正在使用哪个 Office 部署技术 <br>在您的组织？ | <input type="checkbox">MSI <br/> <input type="checkbox">单击以运行 | |
> | 什么是允许并支持移动 <br>正在使用的平台？ <br/>请选择所有适用。 | <input type="checkbox">窗口 <br/> <input type="checkbox"> 手机 <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">其他 （请注意注释列中的详细信息）。 | |
> | 如何提供移动设备？ <br/>请选择所有适用。 | <input type="checkbox">企业设备 <br/> <input type="checkbox">将您自己的设备 | |
> | 哪些设备当前执行的用户用来访问 <br>语音和会议服务 <br>（话筒、 耳机、 电话、 视频）？ | | |

<a name="operations"></a>运营
----------

使用下表来捕获您的环境的操作方面的详细信息。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Lync 服务器，您操作的模型是什么 <br>Skype 业务服务器或 Office 365 部署 <br>今天吗？ | | |
> | 可以分级显示的当前支持排列 <br>Lync Server，Skype 业务服务器或 Office 365 的吗？ | | |
> | 如果要部署到多个国家或地区， <br>每个国家/地区有其自己的 IT / 电话 <br>人员处理，或将此管理集中？ | <input type="checkbox">区域的操作和支持 <br/> <input type="checkbox">集中式的操作和支持 | |
> | 是否遵循通话质量方法？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 | |
> | 已分配的个人或团队添加到 <br>质量冠军角色协作平台 <br>在使用？ | <input type="checkbox">是的 <br/> <input type="checkbox">不 ||
> | 您如何监视您 Lync Server，Skype 的 <br>企业服务器或 Office 365 部署？ | | |
> | 是否遇到了通话质量问题？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 如何以及何时您是否提供了培训对您 <br>对新的服务和功能的技术支持？ | | |

<a name="adoption-and-readiness"></a>采用和准备情况
----------------------

使用下表并提供组织的当前采用和就绪状态。

> | 问题 | 回答 | 备注 |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | 什么是您的当前活动的使用情况 <br>Skype 的业务？ | 与已启用的用户的 ___ %总活动用户 | |
> | 您的组织如何使用 <br>Skype 的业务？ | 一对一对话 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">调用 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">共享<br> 会议 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">会议<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">共享<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">调用| |
> | 贵组织在获得用户的认可 <br>并更改管理团队？ | <input type="checkbox">是的<br/> <input type="checkbox">不 | |
> | 当前如何测量技术的成功 <br>首次推出像 Skype 业务吗？ | | |
> | 百分之多少的用户群将您说了 <br>采用 Skype 业务吗？ | | |
> | 用户对 Skype for Business 的看法如何？ | <input type="checkbox">很好 <br/> <input type="checkbox">非特定语言 <br/> <input type="checkbox">错误 | |
> | 哪项最恰当地描述推广 <br>为您的业务 Skype 使用策略 <br>部署？ | <input type="checkbox">广泛的覆盖范围： 通过电子邮件发送与市场活动 <br>&nbsp;&nbsp; &nbsp;培训的链接 <br/> <input type="checkbox">扩展： 广泛的覆盖面以及各类 <br>&nbsp;&nbsp; &nbsp;的认识活动 （海报， <br>&nbsp;&nbsp; &nbsp;事件、 冠军) 和培训 <br>&nbsp;&nbsp; &nbsp;（视频、 用户指南、 当面） <br/> <input type="checkbox">定制： 展开，加上目标 <br>&nbsp;&nbsp; &nbsp;消息和培训角色 <br/> <input type="checkbox">其他 <br>&nbsp;&nbsp; &nbsp;（请注意注释列中的详细信息）。 | |