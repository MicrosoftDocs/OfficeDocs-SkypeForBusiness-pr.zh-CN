---
title: Exchange 统一消息在线迁移支持
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft 正在通过 2020 年 2 月 28 日 (UmO) UmO) UmO Online 服务。 本文汇总了受影响的客户应了解并制定其业务连续性的计划。
ms.openlocfilehash: 587a6f0e17729181d7e0ba2389ed32faee07ff71
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824893"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持

> [!IMPORTANT]
> **自 2020 年 2 月 28 日下，5 月下，5 月 5 日时，Exchange Online 中的统一消息服务已停止支持。所有语音邮件帐户均已由 Microsoft 迁移到云语音邮件服务。任何其余的自动助理流量都不会被监控，并且任何时机都可能中断。**

及 2019 [年](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 2 月 8 日发布的通知，Microsoft 将于 2020 年 2 月 28 日停用 Exchange 统一消息 Online (ExchUMO) 服务。 本文汇总了受影响的客户在规划其业务连续性时应了解和执行哪些操作。

ExchUMO 由客户部署语音邮件、自动助理、呼叫队列和传真集成服务。 帮助客户迁移到电话系统服务，这些服务已支持 Skype for Business Online 和 Microsoft Teams 上数千个客户。

语音邮件主要是 Microsoft 驱动的迁移;一小部分客户可能需要有管理员参与和/或投资。 自动助理是管理员驱动的迁移;在云服务中重新创建现有 ExchUMO 自动助理树。 使用任一 ExchUMO 功能和第三方 PBX 的客户将不会迁移到 Skype 云服务，因为他们不支持第三方 PBX 系统。 此博客中即表示第三方支持的停用计划，此部署模型[this blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)中的客户可以将用户迁移到 Microsoft 的统一通信平台/服务之一，或者为这些用户获取第三方语音邮件和/或自动助理解决方案。 基于云的服务不支持传真集成;客户需要迁移到第三方解决方案。

## <a name="who-is-affected"></a>受影响的用户？

在 Exchange 统一消息联机服务中使用以下任何功能的客户会受到影响：

- 语音邮件服务
- 自动助理 服务
- 呼叫队列服务
- 传真集成

> [!Note]
> 与统一消息一起使用Exchange Server的客户不受影响。

了解有关用户体验影响影响[的详细信息。](#user-experience-impact)

## <a name="migration-plan-overview"></a>迁移计划概述

Microsoft 已识别出各种客户部署，这些部署正在使用 ExchUMO 的功能，并且有助于客户根据以下计划进行迁移。

|客户组 |日程表  |详细信息  |
|---------|---------|---------|
|准备迁移的客户<br><br>要迁移的功能：<br><ul><li>语音邮件</ul>   |   2019 年 5 月 - 5 月  |示例：<ul><li>    具有简单语音邮件部署和用法的客户<li>Microsoft 已满足所有要求以供 Microsoft 执行迁移的客户<ul>|
|具有先决条件的客户<br><br>要迁移的功能：<br><ul><li>语音邮件<li>自动助理<li>呼叫队列</ul> |  2019 年 5 月 - 12 月 |示例： <br><ul><li>混合配置未完成<li>未设置混合 PSTN 号码</ul>|
|在客户投资中需要&管理员参与的客户<br><br>要迁移的功能：<ul><li>语音邮件<li>自动助理<li>呼叫队列<li>传真集成</ul>| 2020 年 2 月  | 示例： <br><ul><li>ExchUMO 服务由第三方 PBX 使用<li>具有 PSTN 订户访问要求的客户<li>客户使用 SFB 2010 (不支持的) <li>传真集成</ul> |

## <a name="voicemail-migration-guidelines"></a>语音邮件迁移准则

### <a name="get-informed"></a>获取有关信息

熟悉博客公 [告和](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 本文为用户计划顺利迁移。 有关 ["电话系统语音邮件"功能的详细信息，](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 请参阅"Skype for Business 语音邮件和选项"。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>创建 Skype for Business 混合拓扑

如果未设置 Skype for Business 混合拓扑，则需要进行该操作以便于对您的语音邮件用户进行顺利迁移。 请参阅 [配置 Skype for Business 混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 以了解更多详细信息。

> [!Note]
> 无需为语音邮件服务迁移在线迁移用户。 但是，为使内部用户利用电话系统语音邮件服务，必须建立混合拓扑。

### <a name="plan-your-auto-attendant-migration"></a>规划自动助理迁移

管理员可以随时开始将其自动助理从 ExchUMO 迁移到云自动助理。 有关 [更多详细信息，请参阅"设置](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 云自动助理"。

Microsoft 继续提供客户在迁移时可能考虑的其他自动助理功能。 管理员应评估该功能集并相应地迁移其自动助理实例。 有关功能列表比较，请参阅 [ExchUMO 和基于云的服务功能矩阵](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>规划迁移后的语音邮件和测试

语音邮件迁移是由 Microsoft 驱动的。 如果建立了先决条件混合拓扑，则不需要管理员执行任何操作。 Microsoft 会执行进行验证和测试，以确保用户的语音邮件迁移不会中断。 建议管理员在其一边执行测试和验证。 请参阅 [针对建议测试计划的管理员推荐的测试计划](#suggested-test-plan-and-post-migration-validation-for-admins) 和迁移后验证。

> [!Note]
> 不支持 Lync Server 2010。 如果进行的是 2010 服务器部署，则应规划服务器升级或考虑将用户迁移到 Microsoft Teams 或 Skype for Business Online。  

### <a name="monitor-the-admin-notification-center"></a>监视管理员通知中心

通过进一步的详细信息和有关用户迁移的时间线，在管理通知中心中观看通知。 通知至少比迁移期前 30 天发送。

> [!Note]
> 如果在收到与用户的迁移日程表有关的通知，并且出于业务关键原因希望推迟迁移，则可以通过联系 Microsoft 支持人员来实现此目的。 迁移推迟到 2020 年 2 月 28 日的停用日期。 对于可能有更多问题的客户，请联系你的帐户团队或 Microsoft 支持部门。 已使用 Microsoft 365 或 Office 365 的客户可以通过 Microsoft 365 管理中心提交支持案例。

### <a name="consider-opting-in-for-a-planned-migration"></a>考虑选择加入计划的迁移

你可以选择将计划的语音邮件服务迁移到 CVM。 选择加入之前，请查看本文的详细信息，尤其是下面几节：

- 本节中的 (步骤) 
- ExchUMO 和基于云的服务功能矩阵
- 用户体验影响

选择托管迁移时，你不会在 Microsoft 365 管理门户消息中心收到 30 天前的通知。

若要选择加入计划的迁移，请从管理员的电子邮件地址发送一个电子邮件请求 [cvm@microsoft.com](mailto:cvm@microsoft.com) 有以下信息：

- 星期二 (日) ：每周二执行迁移波。 请选择 Tuesday 中不在 2019 年 12 月 3 日以外的日期。
 
- 租户 ID：格式为 0046728c-688a-4472-a38f-098fec60ac6x 的 32 个字符号码。 可在 Azure AD 下的 Microsoft 365 管理门户中查找租户 ID，或使用以下 PowerShell cmdlet 查找租户 ID： `Get-CsTenant | Select ObjectId`

成功迁移租户后，你将收到一封电子邮件确认。

## <a name="auto-attendant-migration-guidelines"></a>自动助理迁移准则

Microsoft 365 和 Office 365 组织管理员必须重新在 Microsoft 云 自动助理 服务中创建其 Exchange UM Online 自动助理，并在 Exchange UMO 服务停用日期 2020 年 2 月 28 日之前将本地电话号码切换为他们。 这是成功迁移和测试新云自动助理的推荐指导方。 如果有大量的自动助理，可以使用 [Exchange UM 自动助理 到"云 自动助理 迁移](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) "脚本，以简化自动助理的批量迁移。

### <a name="auto-attendant-setup"></a>自动助理设置

强烈建议您尽早安装新的自动助理以避免过去几分钟出现的问题并熟悉云 自动助理 服务的相关功能和体验。 对于需要一个或多个不下隙功能的自动助理，可以在可以使用用于准备部署的不用功能时创建和测试自动助理。 有关外加功能的详细信息，请参阅 [附录](#appendix)。

1. 使用 Exchange UMO cmdlet 通过 [Get-UMAutoAttendant 导出现有自动助理的配置](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)。  
2. 在 Exchange Online PowerShell [中使用 Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet 导出问非法媒体文件 (前提是使用) 并将其转换为 .mp3 格式。
3. 按照"规划云 ["自动助理中的说明](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) 进行操作 [并设置云自动助理，](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 以使用 Microsoft Teams 管理中心或 Powershell 创建自动助理。
4. 如果菜单选项更改，请查看问问。
5. 在本文的"已知问题"部分，使用"自动助理 呼叫转移至 PSTN"解决方法， [将转](#known-issues) 移到您的响应组。  
6. 通过在内部呼叫或分配测试电话号码来测试新的自动助理。  

### <a name="cutover"></a>直接转换

1. 将电话号码从 Exchange UMO 自动助理切换到新的自动助理。
2. 将 SIP URI 从联系人对象移动到资源帐户。
3. 通过使用新分配的电话号码，测试并验证自动助理。

## <a name="appendix"></a>附录

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和基于云的服务功能矩阵

| 服务 | 功能级别 | 功能 | 注释  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 服务功能| 支持第三方 PBX    | 包含提供给第三方 PBX（例如 MWI (消息等待指示器）所) SIP 从 Exchange UM Online 通知消息的所有功能 | N   | Y    |
| VM | 服务功能  | 支持 Skype for Business Server   |  | Y | Y    |
| VM | 服务功能 | 支持 Microsoft Teams|  | Y | N    |
| VM | 服务功能 | 电子数据展示和保留  | 出于安全和合规性  | Y | Y    |
| VM | 服务功能 | Exchange 规则支持 | 出于安全和合规性  | Y | Y    |
| VM | 用户功能 | PSTN 拨入访问  | 订阅者访问  | N | Y    |
| VM | 用户功能 | 委派用户  | 未呼叫电子邮件  | N | Y    |
| VM | 用户功能 | PSTN Outlook Voice Access   | 订阅者访问  | N | Y    |
| VM | 用户功能 | 使用经过身份验证的终结点拨入 | 调用语音邮件服务来收听语音邮件并更改语音邮件设置| Y | Y    |
| VM | 用户功能 | 禁用语音邮件的用户设置   |  | Y | Y    |
| VM | 用户功能 | 用于更改个人问问的用户设置  |  | Y | Y    |
| VM | 用户功能 | 创建 OOF 问问语的用户设置  |  | Y | Y    |
| VM | 用户功能 | 更改默认语言的用户设置  |  | Y | Y    |
| VM | 用户功能 | 使用 TTS 覆盖默认问答的用户设置  |  | Y | N    |
| VM | 用户功能 | 录制已通过 (问问)  |  | Y | Y    |
| VM | 用户功能 | 使用 PSTN 电话 (问) — 在电话上播放 |  | N | Y    |
| VM | 用户功能 | 禁用脚本的用户设置 |  | N | Y    |
| VM | 用户功能 | 听录  |  | Y | Y    |
| VM | 用户功能 | 所有终结点上的可视语音信用   | 用于在所有受支持的终结点上播放、删除、消息等待指示器和状态切换功能时  | Y | Y    |
| VM | 用户功能 | Outlook 中的 MP3 音频文件格式    |  | Y | Y    |
| VM | 用户功能 | 变量速度播放控件 |  | Y | Y    |
| VM | 用户功能 | 转发语音邮件  | 将收到的语音邮件转发到其他用户 | Y | Y    |
| VM | 用户功能 | 向一组用户发送语音邮件  |语音邮件广播   | N | Y   |
| VM | 用户功能 | 使用短信的语音邮件通知    | 用户具有新的语音邮件时可接收短信    | N | Y    |
| VM | 用户功能 | 支持的问语语言 | 此处的详细信息： https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | 用户功能 | 电话应答规则 |  | Y | Y    |
| VM | 用户功能 | 在电话上 (PSTN) 播放消息 | 通过呼叫我的单元格上的"我"来收听语音邮件  | N | Y    |
| VM | 用户功能 | 在电话上 (Auth) ） 以播放消息 | 在我的已验证设备上呼叫我  | Y | Y    |
| VM | 用户功能 | 多个用户间共享邮箱 |  | Y | Y    |
| VM | 呼叫者功能  | 呼叫者体验 - 受保护的语音邮件 | 呼叫者可以选择将记录的邮件标记为受保护的邮件的选项| N | Y    |
| VM | 呼叫者功能  | 呼叫者体验 私人语音邮件 | 呼叫者可以选择将录制的邮件标记为私人的选项  | N | Y    |
| VM | 呼叫者功能  | 无提示检测   |  | N | Y    |
| VM | 租户管理员功能 | 服务器级受保护的语音邮件    | 租户管理员可以将服务级别规则配置为将传入语音邮件标记为受保护 | Y | Y    |
| VM | 租户管理员功能 | 更改录制持续时间限制  |     | Y | Y    |
| VM | 租户管理员功能 | 更改无提示检测超时    |  | 无    | Y    |
| VM | 租户管理员功能 | 更改输入失败的次数 | CVM：硬编码为 3 | N | Y    |
| VM | 租户管理员功能 | 更改默认语言 |  | Y | Y    |
| VM | 租户管理员功能 | 禁用/启用跟踪 |  | Y | Y    |
| VM | 租户管理员功能 | 禁用/启用未启用的呼叫通知 |  | N | Y    |
| VM | 租户管理员功能 | 帮助 Microsoft 改进语音邮件预览    |  | Y | Y    |
| VM | 租户管理员功能 | 为启用的用户自定义短信|  | 无    | Y    |
| VM | 租户管理员功能 | 转网出发比例掩码|  | Y | N    |
| VM | 租户管理员功能 | 语音邮件策略    |   | Y | Y    |
| VM | 租户管理员功能 | Web 门户管理   |  | CY19   | Y    |
| VM | 租户管理员功能 | PowerShell   |  | Y | Y    |
| 统一消息 | 用户功能 | MWI 认证 (手机) 上显示 MWI 的邮件等待指示器   |可以由电话合作伙伴提供  | 否 | 是    |
| AA | 服务功能 | AA 支持第三方 PBX    |  | N | Y    |
| AA | 服务功能 | 支持 Skype for Business Server   |  | Y | Y    |
| AA | 服务功能 | 支持 Microsoft Teams|  | Y | N    |
| AA | 服务功能 | 按名称拨号，DTMF 输入    |  | Y | Y    |
| AA | 服务功能 | 按名称拨号、语音输入  |  | Y | Y    |
| AA | 服务功能 | 多语言支持 | 此处的语言详细信息： https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | 服务功能 | 转接到话务员、CQ 或用户 |  | Y | Y    |
| AA | 服务功能 | 转到内部或 DID RNL (PSTN)   |  | Y | Y    |
| AA | 服务功能 | 在外部转接到 PSTN 号码  |  | 查看以下"已知问题"部分 | Y    |
| AA | 服务功能 | 营业时间 |  | Y | Y    |
| AA | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| AA | 服务功能 | 将云 PSTN 号码分配给 AA |  | Y | N    |
| AA | 服务功能 | 将本地 PSTN 号码分配给 AA  |  | Y | Y    |
| AA | 服务功能 | 自定义用户选择  | 允许呼叫者访问组织用户的自定义列表| Y | Y    |
| AA | 服务功能 | 在按小时和假日协议  |  | Y | Y    |
| AA | 服务功能 | 使用文本到语音的自定义问答  |  | Y | Y    |
| AA | 服务功能 | 分机拨号   | 通过拨号联系用户  | Y   | Y    |
| AA | 服务功能 | AA 呼叫者留下消息的邮箱    |  | Y   | Y    |
| AA | 服务功能 | 向 AA 分配多项 PSTN 号码|  | Y | Y    |
| AA | 租户管理员功能 | Web 门户管理   |  | Y | N    |
| AA | 租户管理员功能 | PowerShell cmdlet  |  | Y | Y    |
| Fax| 服务功能 | 传真集成|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>针对管理员推出的建议测试计划和迁移后验证

若要验证用户是否已迁移到云语音邮件，请将语音邮件留给用户，然后选中 Outlook 中的邮件正文。 云语音邮件具有读出的页脚：

"感谢您使用脚本！ 如果没有看到上述脚本，是因为音质不够清晰，不够易转。

迁移用户后测试语音邮件功能时，请确保考虑下列情形：

- 验证组织中所有终结点类型的语音邮件访问（如应用和 IP 电话）。
- 与示例用户验证配置的个性化问答将向呼叫者播放。
- 如果你的组织对于禁用用户脚本具有法律或合规要求，请确保其在迁移后已禁用。 有关详细信息，请参阅"[设置云语音邮件"。](/microsoftteams/set-up-phone-system-voicemail)
- 如果您之前配置了 Exchange VM 策略和规则，请确保它们有效。
- 熟悉云语音邮件服务 PowerShell cmdlet 以更改用户设置。  

### <a name="user-experience-impact"></a>用户体验影响

下面概述了最终用户语音邮件迁移体验。


|体验  |用户体验变化|
|---------|---------|
|电子邮件通知 | 无变化<br>不会向用户发送任何有关语音邮件帐户激活/迁移的通知。 |
|访问以前的邮件 | 无变化<br>用户可以在所有受支持的终结点中访问其以前的语音邮件。 |
|在 Outlook 中接收 VM SFB 应用| 无变化<br>用户仍能够在所有受支持的终结点中接收语音邮件。 |
|听录 | 增强<br>与 ExchUMO 相比，CVM 跟踪具有更高的准确率和支持的语言。 |
|用户设置 | 新体验<br>用户可以从 USP 用户设置门户更改其 (首) 。 用户可以从语音邮件电子邮件中的超链接或其 SFB 客户端上的用户设置按钮访问其 USP; https://aka.ms/vmsettings.
 |功能| 请参阅功能集比较以了解详细信息。 |
|VM 邮件的 Outlook 规则 | 无变化<br>以前创建的规则在迁移后将应用于 CVM 邮件。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的用户管理和设置

创建云语音邮件时，将自动为新的 Skype for Business 用户提供云语音邮件。 无需其他管理员工作或许可证即可设置新的语音邮件用户。 请参阅 ["设置云语音邮件"，](/microsoftteams/set-up-phone-system-voicemail) 了解关于现有和新用户的策略管理。

### <a name="admin-auto-attendant-management-experience"></a>管理员自动助理管理体验

有关自动助理的详细信息，请参阅"[设置云自动助理"。](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>已知问题

#### <a name="greeting-inconsistencies"></a>问答不一致

在服务完全停用前，订阅者访问可能会继续对你的租户运行，即使所有用户都已迁移到云语音邮件之后。 为避免用户混淆和不一致的体验，请禁用订阅者访问，因为问问语在迁移后会更改。 为此，请删除每个订阅者访问行的 EXUM 联系 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自动助理 PSTN 的呼叫转移

若要通过 Skype for Business Server 将自动助理呼叫转移至外部 PSTN 电话号码或在 Skype for Business Server 上的响应组服务 (RGS) ，请创建新的内部部署用户，将呼叫转接设置为 PSTN 电话号码或 RGS 电话号码。 必须为用户启用和正确配置企业语音并已分配了语音策略。

#### <a name="shared-mailbox-is-still-accessible"></a>共享邮箱仍然可访问

使用 Exchange UM Online 配置的共享邮箱在迁移到 CVM 后仍然可以继续接收邮件，并且用户可通过 Outlook 访问这些邮件。 但是，迁移到 CVM 后，将无法访问这些邮箱的问答邮件。 如果具有用于捕获自动助理呼叫者的共享邮箱的客户，则在发布 2019 年 10 月的电子邮件后，应利用自动助理和呼叫 (队列共享邮箱) 。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>显示"用户名未使用 Skype for Business"横幅

CVM 服务基于 Microsoft Teams 基础结构，来自 Skype for Business 客户端的调用可能会导致信息横幅显示在客户端上，其消息名为"用户名正在未使用 Skype for Business。 有关更丰富体验，请切换到 Teams 或开始 Skype 会议。"
请务必将用户的 Skype for Business 客户端更新为最新的 C2R 客户端更新，以防止出现此横幅。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"设置语音邮件"，将使您进一个 OWA

从 **客户端单击"设置语音邮件** "，则在迁移到 CVM 后，继续将 Skype for Business Server 2015/2013 客户联系到 Office Web Access (OWA) 门户页。 所有设置均已从 OWA 的"语音邮件"选项卡中删除，并且横幅均会显示一个重定向链接，以使用户进入 CVM 用户设置门户。

#### <a name="changing-greeting-remotely"></a>远程更改问问

CVM 不支持 PSTN 订阅者访问。 对于需要远程更改问号的用户，"更改问任何问语"菜单选项已添加到适用于移动客户端的语音邮件 IVR 服务。 用户可以通过长按移动客户端拨号盘上的"1"键来呼叫此服务。
