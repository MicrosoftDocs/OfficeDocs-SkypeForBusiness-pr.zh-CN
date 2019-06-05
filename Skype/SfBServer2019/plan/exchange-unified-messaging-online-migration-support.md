---
title: Exchange 统一消息在线迁移支持
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft 将在2020年2月停用 Exchange 统一消息服务联机 (ExchUMO) 服务。 本文概述了哪些受影响的客户应了解哪些内容, 并针对其业务连续性进行规划。
ms.openlocfilehash: 785c80b435bfff5b8a9cda3fca17d57756d06091
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702678"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持

有关2019年2月8日的公告参考, Microsoft 将于 2 2020 月日停用 Exchange 统一消息服务联机 (ExchUMO) 服务。 本文简要介绍了受影响的客户应了解哪些内容, 并对其进行规划以实现其业务连续性。 
 
ExchUMO 由客户针对语音邮件、自动助理和/或传真集成服务进行部署。 Microsoft 计划可帮助这些客户迁移到其基于云的服务, 这些服务支持已在 Skype for Business Online 和 Microsoft 团队中的上千个客户。 

语音邮件主要是 Microsoft 驱动的迁移;对于客户的子集, 可能需要管理员参与和/或投资。 自动助理是管理员驱动的迁移;你将需要在云自动助理云服务中重新创建现有的 ExchUMO 自动助理树。 使用第三方 PBX 的任何 ExchUMO 功能的客户将不会迁移到 Skype 云服务, 因为它们不支持第三方 PBX 系统。 第三方支持的退休计划是在[本博客](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)的最后一年宣布的, 此部署模型中的客户可将其用户迁移到 Microsoft 的统一通信平台/服务之一, 或者获取第三方语音邮件和/或适用于这些用户的自动助理解决方案。 基于云的服务不支持传真集成;客户将需要迁移到第三方解决方案。 

### <a name="who-is-affected"></a>哪些人受到影响？

使用 Exchange 统一消息在线服务的以下任何功能的客户将受到影响:

- 语音邮件服务
- 自动助理服务
- 传真集成

> [!Note]
> 使用统一消息的任何 Exchange Server 内部部署的客户不受影响。 

了解有关用户和管理员体验对[用户体验](#user-experience-impact)的影响的详细信息。

## <a name="migration-plan-overview"></a>迁移计划概述

Microsoft 已确定从 ExchUMO 消耗各种功能的各种客户部署, 并将根据以下计划帮助客户迁移。 


|客户组 |上  |详细信息  |
|---------|---------|---------|
|准备迁移的客户<br><br>要迁移的功能:<br><ul><li>语音邮件</ul>   |   3月-5 月2019  |说明<ul><li>    具有简单语音邮件部署和使用情况的客户<li>已针对 Microsoft 执行迁移的所有要求均已建立的客户<ul>|
|具有先决条件的客户<br><br>要迁移的功能:<br><ul><li>语音邮件<li>自动助理</ul> |  五月-2019 年12月 |说明 <br><ul><li>未建立/完成混合配置<li>未设置混合 PSTN 号码</ul>|
|需要管理员参与 & 客户投资的客户<br><br>要迁移的功能:<ul><li>语音邮件<li>自动助理<li>传真集成</ul>| 2020年2月  | 说明 <br><ul><li>ExchUMO 服务已由第三方 PBX 使用<li>具有 PSTN 订阅者访问要求的客户<li>SFB 2010 上的客户 (不支持)<li>传真集成</ul> |

## <a name="migration-steps"></a>迁移步骤

1.  **了解**
 
    熟悉[博客公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)和本文, 以便为你的用户计划平稳迁移。 有关云语音邮件功能的详细信息, 请参阅[查看 Skype for business 语音邮件和选项](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)。  
 
2.  **建立 Skype for business 混合拓扑**

    如果您没有建立 Skype for Business 混合拓扑, 则需要执行此操作以启用语音邮件用户的平滑迁移。 有关详细信息, 请参阅[配置 Skype For business 混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)。 

    > [!Note]
    > 无需将用户迁移到语音邮件服务迁移。 但是, 为了使本地用户能够利用基于云的语音邮件服务, 必须建立混合拓扑。

3. **规划自动助理迁移**
    
    管理员可以随时开始将其自动助理从 ExchUMO 迁移到云自动助理。 有关详细信息, 请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。 Microsoft 计划提供附加的自动助理功能, 客户在3月2019的情况中认为他们的迁移非常重要。 管理员应评估该功能集并相应地迁移其自动助理实例。 有关功能列表比较, 请参阅[基于 ExchUMO 和 Azure 云的服务功能表](#exchumo-and-azure-cloud-based-services-feature-matrix)。

4. **规划语音邮件迁移后验证和测试**

    语音邮件迁移是指 Microsoft 驱动的;管理员无需执行任何操作, 前提是已建立必备的混合拓扑。 Microsoft 将执行所需的验证和测试以确保用户的语音邮件迁移不会中断;但是, 我们鼓励管理员在其一侧执行测试和验证。  有关建议的测试计划, 请参阅[管理员的建议测试计划和迁移后验证](#suggested-test-plan-and-post-migration-validation-for-admins)。 

    > [!Note]
    > 不支持 Lync Server 2010。 如果您使用的是2010服务器部署, 则应规划服务器升级, 或者考虑将用户迁移到 Microsoft 团队或 Skype for business Online。  

5. **监控管理员通知中心**

    通过有关用户的语音邮件迁移的详细信息和日程表, 在管理员通知中心查看通知。 将在迁移期前至少30天内发送通知。 

    > [!Note]
    > 如果你收到一条通知, 告知用户的迁移时间线, 并且希望推迟你的迁移以满足业务关键型原因, 你可以通过联系 Microsoft 支持人员来执行此操作。 请注意, 您不能将迁移推迟到2020年2月的退休日期。 对于可能有更多问题的客户, 请与您的帐户团队或 Microsoft 支持部门联系。 已使用 Office 365 的客户可以通过 Office 365 管理门户提交支持案例。 

6. **考虑为计划迁移选择**

    您可以选择加入计划的语音邮件服务迁移到 CVM。 在 "选择" 之前, 请查看本文的详细信息, 尤其是以下部分:

    - 迁移步骤 (本部分)
    - ExchUMO 和基于 Azure 云的服务功能表
    - 用户体验影响

    请注意, 通过选择加入托管迁移, 你将不会在 Microsoft 365 管理门户消息中心收到预迁移30天的通知。
 
    若要为计划迁移选择加入, 请使用管理员的电子邮件地址向[cvm@microsoft.com](mailto:cvm@microsoft.com)发送电子邮件请求, 其中包含以下信息:

    - 首选日期 (星期二): 每星期二执行迁移波形。 请选择星期二之外的日期, 不超过12/3/2019。
 
    - 租户 ID:32 0046728c-688a-4472-a38f-098fec60ac6x 格式的字符数。 你可以在 Microsoft 365 管理门户中的 Azure Active Directory 下或通过执行以下 PowerShell cmdlet 找到租户 ID:`Get-CsTenant | Select ObjectId`
 
    一旦租户成功迁移, 你将收到一封电子邮件确认。 

## <a name="appendix"></a>参见

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和基于 Azure 云的服务功能表

| 业务 | 功能级别 | 功能 | 注释  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VMNETWORK  | 服务功能| 支持第三方 PBX    | 包括 MWI (消息等待指示器) 提供给第三方 PBX 的所有功能, 使用 SIP 通知来自 Exchange UM 的联机消息 | 否   | 是    |
| VMNETWORK | 服务功能  | 支持 Skype for business 服务器   |  | Y | Y    |
| VMNETWORK | 服务功能 | 支持 Microsoft 团队|  | 是 | 否    |
| VMNETWORK | 服务功能 | 电子数据展示和保留  | 出于安全和合规性  | Y | Y    |
| VMNETWORK | 服务功能 | Exchange 规则支持 | 出于安全和合规性  | Y | Y    |
| VMNETWORK | 用户功能 | PSTN 拨入访问  | 订阅者访问  | 否 | 是    |
| VMNETWORK | 用户功能 | PSTN Outlook Voice Access   | 订阅者访问  | 否 | 是    |
| VMNETWORK | 用户功能 | 使用已验证终结点拨入 | 呼叫语音邮件服务收听语音消息和更改语音邮件设置| Y | Y    |
| VMNETWORK | 用户功能 | 禁用语音邮件的用户设置   |  | Y | Y    |
| VMNETWORK | 用户功能 | 用于更改个人问候语的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 用于创建 OOF 问候的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 用于更改默认语言的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 使用 TTS 覆盖默认问候语的用户设置  |  | 是 | 否    |
| VMNETWORK | 用户功能 | 录制个人问候语 (经过身份验证的设备) |  | Y | Y    |
| VMNETWORK | 用户功能 | 录制个人问候语 (PSTN)-在手机上播放 |  | 否 | 是    |
| VMNETWORK | 用户功能 | 用于禁用脚本的用户设置 |  | 否 | 是    |
| VMNETWORK | 用户功能 | 转录  |  | Y | Y    |
| VMNETWORK | 用户功能 | 所有终结点上的视觉语音邮件   | 在所有受支持的终结点上, 使用用户控件播放、删除、消息等待指示器和状态切换  | Y | Y    |
| VMNETWORK | 用户功能 | Outlook 中的 MP3 音频文件格式    |  | 是 | Y    |
| VMNETWORK | 用户功能 | 变速播放控制 |  | 是 | Y    |
| VMNETWORK | 用户功能 | 转发语音邮件  | 将接收到的语音邮件转发给其他用户 | 是 | Y    |
| VMNETWORK | 用户功能 | 向一组用户发送语音消息  |语音邮件直播   | 否 | 是   |
| VMNETWORK | 用户功能 | 语音邮件通知, 使用短信    | 当用户收到新语音邮件时, 可收到一条短信    | 否 | 是    |
| VMNETWORK | 用户功能 | 支持的问候语言 | 此处的详细信息:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | 是 | Y    |
| VMNETWORK | 用户功能 | 呼叫应答规则 |  | 是 | Y    |
| VMNETWORK | 用户功能 | 在手机 (PSTN) 上播放-播放消息 | 呼叫我的单元格以收听语音消息  | 否 | 是    |
| VMNETWORK | 用户功能 | 在电话上播放 (Auth)-播放消息 | 在已验证身份的设备上呼叫我  | 是 | Y    |
| VMNETWORK | 用户功能 | 在多个用户之间共享邮箱 |  | 是 | Y    |
| VMNETWORK | 来电显示功能  | 呼叫者体验受保护的语音邮件 | 呼叫者可以选择将录制的邮件标记为受保护的选项| 否 | 是    |
| VMNETWORK | 来电显示功能  | 呼叫者体验-私人语音邮件 | 呼叫者可以选择将录制的邮件标记为私密的选项  | 否 | 是    |
| VMNETWORK | 来电显示功能  | 静音检测   |  | 否 | 是    |
| VMNETWORK | 租户-管理员功能 | 服务器级别的受保护语音邮件    | 租户-管理员可以配置服务级别规则以将传入语音邮件标记为受保护 | 是 | Y    |
| VMNETWORK | 租户-管理员功能 | 更改录制持续时间限制  | CVM 硬性编码为5分钟    | 否 | 是    |
| VMNETWORK | 租户-管理员功能 | 更改静音检测超时    |  | 不适用    | Y    |
| VMNETWORK | 租户-管理员功能 | 更改输入失败次数 | CVM: 硬编码为3 | 否 | 是    |
| VMNETWORK | 租户-管理员功能 | 更改默认语言 |  | 是 | Y    |
| VMNETWORK | 租户-管理员功能 | 禁用/启用脚本关于 |  | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 禁用/启用未接来电通知 |  | 否 | 是    |
| VMNETWORK | 租户-管理员功能 | 帮助 Microsoft 改进语音邮件预览    |  | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 自定义已启用用户的文本消息|  | 不适用    | Y    |
| VMNETWORK | 租户-管理员功能 | 脚本语言屏蔽|  | 是 | 否    |
| VMNETWORK | 租户-管理员功能 | 语音邮件策略    |   | Y | Y    |
| VMNETWORK | 租户-管理员功能 | Web 门户管理   |  | CY19   | Y    |
| VMNETWORK | 租户-管理员功能 | PowerShell   |  | Y | Y    |
| AA | 服务功能 | AA 支持第三方 PBX    |  | 否 | 是    |
| AA | 服务功能 | 支持 Skype for business 服务器   |  | Y | Y    |
| AA | 服务功能 | 支持 Microsoft 团队|  | 是 | 否    |
| AA | 服务功能 | 按名称拨号, DTMF 输入    |  | Y | Y    |
| AA | 服务功能 | 按名称、语音输入拨号  |  | Y | Y    |
| AA | 服务功能 | 多语言支持 | 此处为语言详细信息:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | 服务功能 | 转移到操作员、CQ 或用户 |  | Y | Y    |
| AA | 服务功能 | 内部转到 PSTN 号码 (已 RNL)  |  | Y | Y    |
| AA | 服务功能 | 从外部转移到 PSTN 号码  |  | Q2CY19 | Y    |
| AA | 服务功能 | 工作时间 |  | Y | Y    |
| AA | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| AA | 服务功能 | 将云 PSTN 编号分配给 AA |  | 是 | 否    |
| AA | 服务功能 | 将本地 PSTN 号码分配给 AA  |  | Y | Y    |
| AA | 服务功能 | 自定义用户选择  | 使呼叫者能够访问组织用户的自定义列表| Y | Y    |
| AA | 服务功能 | 工作时间和假日处理后  |  | Y | Y    |
| AA | 服务功能 | 使用文本到语音的自定义问候语  |  | Y | Y    |
| AA | 服务功能 | 分机号码   | 通过拨入分机来联系用户  | CY19   | Y    |
| AA | 服务功能 | 用于 AA 呼叫者的邮箱离开消息    |  | CY19   | Y    |
| AA | 服务功能 | 将多个 PSTN 号码分配给 AA|  | Y | Y    |
| AA | 租户-管理员功能 | Web 门户管理   |  | 是 | 否    |
| AA | 租户-管理员功能 | PowerShell cmdlet  |  | Y | Y    |
| 传入| 服务功能 | 传真集成|  | 否 | 是    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>适用于管理员的建议测试计划和迁移后验证

若要验证用户是否已迁移到云语音邮件, 只需将语音邮件保留给用户并在 Outlook 中查看邮件正文, 则云语音邮件的其他页脚将显示:

**感谢您使用 "脚本"!如果在上述情况下看不到上述记录, 这是因为音频质量不够清晰, 无法稍后将。**

在用户迁移后测试语音邮件功能时, 请确保考虑以下方案:

- 验证你的组织中的所有终结点类型的语音邮件访问: 应用和 IP 电话。 
- 通过向呼叫者播放配置的个性化问候语的示例用户进行验证。   
- 如果你的组织具有对用户禁用脚本的法律或合规性要求, 请确保它已禁用迁移后。 有关更多详细信息, 请参阅[设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)。
- 如果你以前配置了 Exchange VM 策略和规则, 请确保它们有效。
- 熟悉云语音邮件服务 PowerShell cmdlet 以更改用户设置。  

### <a name="user-experience-impact"></a>用户体验影响

以下是最终用户语音邮件迁移体验概述。


|方面  |用户体验方面的更改|
|---------|---------|
|电子邮件通知 | 无更改<br>不会向用户发送电子邮件, 通知他们有关语音邮件帐户激活/迁移的信息。 |
|访问以前的消息 | 无更改<br>用户将有权访问其在所有支持的终结点中的以前的语音邮件。 |
|在 outlook 中接收 VM, SFB 应用| 无更改<br>用户将继续在所有支持的终结点接收语音邮件消息。 |
|转录 | 更<br>CVM 脚本的精确度比率和支持语言比 ExchUMO 高得多。 |
|用户设置 | 新体验<br>用户将能够从用户设置门户 (USP) 更改其首选项。 用户可以通过其语音邮件中的超链接或其 SFB 客户端上的用户设置按钮访问其 USP;https://aka.ms/vmsettings.   
 |功能| 有关详细信息, 请参阅功能集比较。 |
|适用于 VM 邮件的 Outlook 规则 | 无更改<br>迁移后, 以前创建的规则将应用于 CVM 消息。
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的用户管理和预配 

Skype for business 新用户将在创建时自动为 CVM 服务中的语音邮件设置。 为语音邮件预配新用户不需要额外的管理员工作或许可证。 请参阅[设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail), 了解如何管理现有用户和新用户的策略。

#### <a name="admin-auto-attendant-management-experience"></a>管理员自动助理管理体验 

请参阅[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant.md)以了解有关配置和管理自动助理的详细信息。 
