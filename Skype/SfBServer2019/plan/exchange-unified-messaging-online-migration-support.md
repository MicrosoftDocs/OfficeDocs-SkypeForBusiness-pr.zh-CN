---
title: Exchange 统一消息在线迁移支持
ms.author: heidip
author: heidip
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft 按年 2 月 2020 retiring Exchange 统一消息在线 (ExchUMO) 服务。 本文概述了什么影响客户应知道并执行的操作及其业务连续性规划。
ms.openlocfilehash: 1f755f8974ba18eba296051c547ee12b79b114d1
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "29779882"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持  

[通知](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-support-for-unified-messaging-in-exchange-online/)年 2 月 8 2019年上没有 Microsoft 按年 2 月 2020 retiring Exchange 统一消息在线 (ExchUMO) 服务。 本文提供了哪些受影响的客户的摘要应知道以及操作将其业务连续性规划。 
 
ExchUMO 客户的语音邮件、 自动助理和/或集成的传真服务部署。 Microsoft 帮助这些客户迁移到其支持成千上万客户已 Skype 业务 Online 和 Microsoft 团队的基于云的服务计划。 

语音邮件是主要 Microsoft 驱动型迁移;管理员参与和/或投资可能需要客户的子集。 自动助理是管理员驱动型迁移;您将需要重新创建云自动助理云服务中的现有 ExchUMO 自动助理树。 因为它们不支持第三方 PBX 系统，所使用的任何与第三方 PBX ExchUMO 功能的客户将不迁移到 Skype 云服务。 第三方支持退休计划已宣布[此博客](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)中的最后一年和此部署模型中的客户可以将用户迁移到 Microsoft 的统一通信平台/服务之一或获取第三方语音邮件和/或自动助理解决方案，这些用户。 在基于云的服务; 不支持传真的集成客户需要迁移到第三方解决方案。 

### <a name="who-is-affected"></a>受影响用户？

影响客户占用的任何 Exchange 统一消息在线服务中的以下功能：

1. 语音邮件服务 
2. 自动助理服务 
3. 传真的集成 

> [!Note]
> 使用任何内部部署 Exchange Server 统一消息与客户不会影响。 

了解更多的用户和管理体验中[用户体验影响](#user-experience-impact)的影响。

## <a name="migration-plan-overview"></a>迁移规划概述

Microsoft 已发现的占用 ExchUMO 功能并将帮助客户迁移基于以下计划的各种客户部署。 


|客户组 |时间线  |详细信息  |
|---------|---------|---------|
|准备要迁移的客户<br><br>若要迁移的功能：<br><ul><li>语音邮件</ul>   |   年 3 月 – 2019 年 5  |示例：<ul><li>    提供简单的语音邮件部署和使用的客户<li>具有所有要求建立 microsoft 执行迁移的客户<ul>|
|客户与必备组件<br><br>若要迁移的功能：<br><ul><li>语音邮件<li>自动助理</ul> |  可能 – 年 12 月 2019 |示例： <br><ul><li>混合配置未建立/完成<li>混合 PSTN 号码不设置</ul>|
|需要管理员参与 & 客户投资客户<br><br>若要迁移的功能：<ul><li>语音邮件<li>自动助理<li>传真的集成</ul>| 通过年 2 月 2020  | 示例： <br><ul><li>ExchUMO 服务使用第三方 PBX<li>客户与 PSTN 订阅者访问要求<li>客户 SFB 2010 （不支持）<li>传真的集成</ul> |

## <a name="migration-steps"></a>迁移步骤

1.  **获取通知**
 
    熟悉[博客通知](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-support-for-unified-messaging-in-exchange-online/)和此文，规划您的用户的顺利迁移。 有关云语音邮件功能的详细信息，请参阅[检查的 Skype 业务语音邮件和选项](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)。  
 

2.  **建立业务混合拓扑的 Skype**

    如果您没有为业务建立的混合拓扑 Skype，您需要执行的启用语音邮件用户的顺利迁移。 有关详细信息，请参阅[业务混合配置 Skype](../hybrid/configure-federation-with-skype-for-business-online.md) 。 

    > [!Note]
    > 不需要将用户迁移到语音邮件服务迁移联机。 但是，对于内部部署用户利用基于云的语音邮件服务，混合拓扑是必须建立。

3. **规划自动助理的迁移**
    
    管理员可以开始在任何时候其自动助理 ExchUMO 从迁移到云自动助理。 有关详细信息，请参阅[设置电话系统自动助理](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md)。 Microsoft 计划以提供其他客户考虑关键的按年 3 月 2019年其迁移的自动助理功能。 管理员应评估的功能集，并相应地迁移其自动助理实例。 功能列表比较，请参阅[ExchUMO 和 Azure 基于云的服务功能组合](#exchumo-and-azure-cloud-based-services-feature-matrix)。

4. **规划您的语音邮件迁移后验证和测试**

    语音邮件迁移是 Microsoft 驱动;管理员不需要执行任何操作，假定将建立必备混合拓扑。 Microsoft 将执行所需的验证和测试以确保用户的语音邮件迁移不会中断。但是，鼓励管理员对其侧执行测试和验证。  建议的测试计划，请参阅[测试计划和管理员的迁移后验证的建议](#suggested-test-plan-and-post-migration-validation-for-admins)。 

    > [!Note]
    > 不支持 Lync Server 2010。 如果您是 2010年服务器部署中，您应规划服务器升级或者考虑业务 online 迁移到 Microsoft 团队或 Skype 的用户。  

5. **监视管理中心通知**

    查找提供更多详细信息和有关用户的语音邮件迁移日程表通知管理中心中的通知。 至少 30 天之前迁移期间，都将会发送通知。 

    > [!Note]
    > 如果您收到包含用户的迁移日程表的通知，并且想要迁移延迟关键业务原因，您可以通过做到联系 Microsoft 支持。 请注意，不能推迟超出退休日期，年 2 月 2020年迁移。 对于拥有更多问题的客户，请联系您的帐户团队或 Microsoft 支持。 已在使用 Office 365 的客户可以提交到 Office 365 管理门户支持案例。 

6. **请考虑选择中启动从 2019 年 5**

    您可以选择使用通过 2019 年 5 早期语音邮件服务迁移 （如果您未收到迁移通知）、 对齐与许可年金或管理人员假期、 迁移或以避免业务关键型时间段。 本文中的前 2019 年 5 将更新自愿加入过程的详细信息。  

## <a name="appendix"></a>附录

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 基于云的服务功能组合 




|  服务 | 功能级别 | 功能 | 备注  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| 虚拟机  | 服务功能| 支持第三方 PBX    |  | 否   | 是    |
| 虚拟机 | 服务功能  | 支持的业务服务器 Skype   |  | Q1CY19 | Y    |
| 虚拟机 | 服务功能 | 支持的 Microsoft 团队|  | 是 | 否    |
| 虚拟机 | 服务功能 | 电子数据展示和保留  | 安全性和相容性  | Y | Y    |
| 虚拟机 | 服务功能 | Exchange 规则支持 | 安全性和相容性  | Y | Y    |
| 虚拟机 | 用户功能 | PSTN 电话拨入式访问  | 订阅者访问  | 否 | 是    |
| 虚拟机 | 用户功能 | PSTN Outlook Voice Access   | 订阅者访问  | 否 | 是    |
| 虚拟机 | 用户功能 | 电话拨入式使用经过身份验证终结点 | 呼叫语音邮件服务，以收听语音邮件，并更改语音邮件设置| Y | Y    |
| 虚拟机 | 用户功能 | 若要禁用语音邮件的用户设置   |  | Y | Y    |
| 虚拟机 | 用户功能 | 用户设置更改个人问候语  |  | Y | Y    |
| 虚拟机 | 用户功能 | 用户设置创建 OOF 问候语  |  | Y | Y    |
| 虚拟机 | 用户功能 | 若要更改默认语言的用户设置  |  | Y | Y    |
| 虚拟机 | 用户功能 | 设置与 TTS 覆盖默认问候语的用户  |  | 是 | 否    |
| 虚拟机 | 用户功能 | 记录的个人问候语 （经过身份验证设备） |  | Y | Y    |
| 虚拟机 | 用户功能 | 记录个人问候语 (PSTN)-在电话上播放 |  | 否 | 是    |
| 虚拟机 | 用户功能 | 若要禁用转录的用户设置 |  | 否 | 是    |
| 虚拟机 | 用户功能 | 转录  |  | Y | Y    |
| 虚拟机 | 用户功能 | 所有终结点上的可视语音邮件   | 与播放、 删除、 消息等待指示器和状态切换到用户控件，在所有支持的终结点  | Y | Y    |
| 虚拟机 | 用户功能 | 在 Outlook 中的 MP3 音频文件格式    |  | Y | Y    |
| 虚拟机 | 用户功能 | 变量速度播放控件 |  | Y | Y    |
| 虚拟机 | 用户功能 | 转发的语音邮件  | 将收到的语音邮件转发给其他用户 | 是 | Y    |
| 虚拟机 | 用户功能 | 发送到一组用户的语音邮件  |语音邮件广播   | 否 | 是   |
| 虚拟机 | 用户功能 | 使用 SMS 的语音邮件通知    | 当有新的语音邮件时，用户可接收 SMS    | 否 | 是    |
| 虚拟机 | 用户功能 | 支持的问候语语言 | 此处详细信息：https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | 是 | Y    |
| 虚拟机 | 用户功能 | 呼叫应答规则 |  | Q1CY19 | Y    |
| 虚拟机 | 用户功能 | 在 (PSTN) 电话上播放-播放消息 | 呼叫我我单元格以收听语音邮件  | 否 | 是    |
| 虚拟机 | 用户功能 | 在电话 （身份验证） 上播放-播放消息 | 呼叫我我经过身份验证的设备上  | 是 | Y    |
| 虚拟机 | 用户功能 | 多个用户之间共享的邮箱 |  | 是 | Y    |
| 虚拟机 | 呼叫者功能  | 呼叫者体验的受保护的语音邮件 | 呼叫者可以选择将录制的消息标记为受保护的选项| 否 | 是    |
| 虚拟机 | 呼叫者功能  | 呼叫者体验-专用的语音邮件 | 呼叫者可以选择一个选项，将标记为私有录制的消息  | 否 | 是    |
| 虚拟机 | 呼叫者功能  | 静音检测   |  | 否 | 是    |
| 虚拟机 | 租户管理员功能 | 服务器级受保护的语音邮件    | 租户管理员可以配置将传入语音邮件标记为受保护的服务级别规则 | 是 | Y    |
| 虚拟机 | 租户管理员功能 | 更改录制持续时间时间限制  | CVM 硬编码为 5 分钟    | 否 | 是    |
| 虚拟机 | 租户管理员功能 | 更改无声检测超时    |  | 不适用    | Y    |
| 虚拟机 | 租户管理员功能 | 更改输入故障数 | CVM： 硬编码为 3 | 否 | 是    |
| 虚拟机 | 租户管理员功能 | 更改默认语言 |  | 是 | Y    |
| 虚拟机 | 租户管理员功能 | 禁用/启用转录 |  | 是 | Y    |
| 虚拟机 | 租户管理员功能 | 禁用未接的来电通知 |  | 否 | 是    |
| 虚拟机 | 租户管理员功能 | 帮助改善语音邮件预览 Microsoft    |  | Y | Y    |
| 虚拟机 | 租户管理员功能 | 自定义启用的用户的短信|  | 不适用    | Y    |
| 虚拟机 | 租户管理员功能 | 转录亵渎屏蔽|  | 是 | 否    |
| 虚拟机 | 租户管理员功能 | 语音邮件策略    |   | Y | Y    |
| 虚拟机 | 租户管理员功能 | Web 门户管理   |  | CY19   | Y    |
| 虚拟机 | 租户管理员功能 | PowerShell   |  | Y | Y    |
| AA | 服务功能 | AA 支持第三方 PBX    |  | 否 | 是    |
| AA | 服务功能 | 支持的业务服务器 Skype   |  | Y | Y    |
| AA | 服务功能 | 支持的 Microsoft 团队|  | 是 | 否    |
| AA | 服务功能 | 按名字，DTMF 输入拨叫    |  | Y | Y    |
| AA | 服务功能 | 按名字，语音输入拨叫  |  | Y | Y    |
| AA | 服务功能 | 多语言支持 | 语言的详细信息此处：https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | 服务功能 | 转接到运算符、 CQ 或用户 |  | Y | Y    |
| AA | 服务功能 | 内部转接到 PSTN 号码 (未 RNL)  |  | Y | Y    |
| AA | 服务功能 | 转接到 PSTN 号码外部  |  | Q2CY19 | Y    |
| AA | 服务功能 | 工作时间 |  | Y | Y    |
| AA | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| AA | 服务功能 | 将云 PSTN 号码分配给 AA |  | 是 | 否    |
| AA | 服务功能 | 将上 prem PSTN 号码分配给 AA  |  | Y | Y    |
| AA | 服务功能 | 自定义用户所选内容  | 启用呼叫者在到达的组织用户的自定义的列表| Y | Y    |
| AA | 服务功能 | 下班后和假日诊  |  | Y | Y    |
| AA | 服务功能 | 使用文本到语音转换的自定义问候语  |  | Y | Y    |
| AA | 服务功能 | 扩展拨号   | 通过拨打其扩展到达用户  | CY19   | Y    |
| AA | 服务功能 | AA 呼叫者留下一条消息的邮箱    |  | CY19   | Y    |
| AA | 服务功能 | 多个 PSTN 号码分配给 AA|  | Y | Y    |
| AA | 租户管理员功能 | Web 门户管理   |  | 是 | 否    |
| AA | 租户管理员功能 | PowerShell cmdlet  |  | Y | Y    |
| 传真| 服务功能 | 传真的集成|  | 否 | 是    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>建议的测试计划和管理员的迁移后验证

测试时语音邮件功能已迁移用户之后，请确保要考虑以下方案：

- 验证跨组织中的所有终结点类型的语音邮件的访问： 应用程序和 IP 电话。 
- 验证与配置个性化的问候语向呼叫者播放的示例用户。   
- 如果您的组织已禁用的用户的转录法律或合规性要求，请确保已禁用的 post 迁移。 有关详细信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。
- 如果您已配置 Exchange VM 策略和规则，请确保它们是有效。
- 熟悉更改用户设置的云语音邮件服务 PowerShell cmdlet。  


### <a name="user-experience-impact"></a>用户体验的影响

以下是最终用户的语音邮件迁移体验概述。


|体验  |更改用户体验|
|---------|---------|
|电子邮件通知 | 无更改<br>没有电子邮件发送给用户，通知他们有关语音邮件帐户激活/迁移。 |
|访问前面的消息 | 无更改<br>用户将有权访问其以前的语音邮件消息，在所有支持的终结点。 |
|在 outlook 中，SFB 应用程序接收 VM| 无更改<br>用户将继续支持的所有终结点接收其语音邮件消息。 |
|转录 | 增强<br>CVM 转录具有更高的准确性速度和比 ExchUMO 支持的语言。 |
|用户设置 | 新的体验<br>用户将能够更改其首选项的用户设置门户 (USP)。 用户可以从其语音邮件的电子邮件或其 SFB 客户端; 上的用户设置按钮中的超链接来访问其 USPhttps://aka.ms/vmsettings.   
 |功能| 请功能集比较的详细信息，参阅。 |
|Outlook 的 VM 邮件的规则 | 无更改<br>以前创建的规则将应用于 CVM 邮件迁移后。
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>用户管理和设置中 CVM 

适用于业务新用户的 Skype 将自动设置为 CVM 时创建的服务中的语音邮件。 没有其他管理员工作或许可证需要设置新的语音邮件的用户。 请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)以了解如何管理的现有和新用户策略。

#### <a name="admin-auto-attendant-management-experience"></a>管理自动助理管理体验 

请参阅[设置电话系统自动助理](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md)以详细了解如何配置和管理自动助理。 