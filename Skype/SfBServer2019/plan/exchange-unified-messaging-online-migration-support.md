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
ms.localizationpriority: medium
description: Microsoft 将于 2020 年 2 Exchange 28 (ExchUMO) 停用统一消息 Online 服务。 本文总结了受影响的客户应了解并执行哪些工作来规划其业务连续性。
ms.openlocfilehash: 1e6d24b05b8f1c6b8d2b47533edbd9ad79c5022e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013286"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持

> [!IMPORTANT]
> **截至太平洋时间Exchange Online 2020 年 2 月 28 日下午 5 点，Exchange Online统一消息服务已不支持。所有语音邮件帐户已由 Microsoft 云语音邮件服务。任何剩余的自动助理流量将不会受到监视，并且可能随时中断。**

为了引用 2019 年 2 月 8 日发布的通知，Microsoft 将于 2020 年 2 月 28 日停用 Exchange 统一消息 Online (ExchUMO) 服务。 [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 本文汇总了受影响的客户应了解和应做哪些工作来规划其业务连续性。

客户为语音邮件、自动助理、呼叫队列和传真集成服务部署 ExchUMO。 Microsoft 计划帮助客户迁移到已经支持 电话系统 Online 和 Microsoft Teams 上成千上万客户的 Skype for Business 服务。

语音邮件主要是 Microsoft 推动的迁移;部分客户可能需要管理员参与和/或投资。 自动助理是管理员驱动的迁移;你需要在云和云服务中重新创建现有 ExchUMO 自动助理树。 使用具有第三方 PBX 的任何 ExchUMO 功能的客户不会迁移到 Skype 云服务，因为他们不支持第三方 PBX 系统。 此博客中宣布停用第三方支持计划，此[](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)部署模型的客户可以将他们的用户迁移到 Microsoft 的统一通信平台/服务之一，或为这些用户获取第三方语音邮件和/或自动助理解决方案。 基于云的服务不支持传真集成;客户需要迁移到第三方解决方案。

## <a name="who-is-affected"></a>Who受到影响？

使用统一消息 Online 服务中的Exchange功能的客户会受到影响：

- 语音邮件服务
- 自动助理服务
- 呼叫队列服务
- 传真集成

> [!Note]
> 使用统一消息Exchange Server本地部署部署的客户不受影响。

详细了解用户体验影响 中的用户和 [管理员体验影响](#user-experience-impact)。

## <a name="migration-plan-overview"></a>迁移计划概述

Microsoft 已识别各种客户部署，这些部署使用 ExchUMO 中的功能，并且将帮助客户基于以下计划进行迁移。

|客户组 |日程表  |详细信息  |
|---------|---------|---------|
|准备迁移的客户<br><br>要迁移的功能：<br><ul><li>Voicemail</ul>   |   2019 年 3 月 - 5 月  |示例:<ul><li>    具有简单语音邮件部署和使用的客户<li>满足 Microsoft 执行迁移的所有要求的客户<ul>|
|具有必备组件的客户<br><br>要迁移的功能：<br><ul><li>Voicemail<li>自动助理<li>呼叫队列</ul> |  2019 年 5 月 - 12 月 |示例: <br><ul><li>混合配置不完整<li>未设置混合 PSTN 号码</ul>|
|需要管理员参与客户&客户投资的客户<br><br>要迁移的功能：<ul><li>语音邮件<li>自动助理<li>呼叫队列<li>传真集成</ul>| 到 2020 年 2 月  | 示例: <br><ul><li>ExchUMO 服务由第三方 PBX 使用<li>具有 PSTN 订阅者访问要求的客户<li>使用 SFB 2010 的客户 (不支持) <li>传真集成</ul> |

## <a name="voicemail-migration-guidelines"></a>语音邮件迁移指南

### <a name="get-informed"></a>获取通知

熟悉博客 [公告和](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 本文，为用户规划顺利迁移。 有关[电话系统](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)语音邮件功能的详细信息，请参阅检查Skype for Business语音邮件和选项。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>建立Skype for Business拓扑

如果没有建立混合Skype for Business，则需要这样做，以便顺利迁移语音邮件用户。 有关详细信息[，Skype for Business](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)配置混合环境。

> [!Note]
> 无需联机迁移用户进行语音邮件服务迁移。 但是，对于利用语音邮件服务电话系统本地用户，必须建立混合拓扑。

### <a name="plan-your-auto-attendant-migration"></a>规划自动助理迁移

管理员可以随时开始将其自动助理从 ExchUMO 迁移到云自动助理。 有关详细信息 [，请参阅设置云](/microsoftteams/create-a-phone-system-auto-attendant) 自动助理。

Microsoft 继续提供客户可能认为迁移所需的其他自动助理功能。 管理员应评估功能集并相应地迁移其自动助理实例。 有关功能列表比较，请参阅 [ExchUMO 和 Azure 基于云的服务功能矩阵](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>规划语音邮件迁移后验证和测试

语音邮件迁移由 Microsoft 驱动。 如果已建立先决条件混合拓扑，则管理员无需执行任何操作。 Microsoft 执行所需的验证和测试，以确保用户的语音邮件迁移不会中断。 建议管理员在自己一侧执行测试和验证。 有关 [建议的测试计划](#suggested-test-plan-and-post-migration-validation-for-admins) ，请参阅建议的测试计划和迁移后对管理员的验证。

> [!Note]
> 不支持 Lync Server 2010。 如果部署的是 2010 服务器，则应该规划服务器升级或考虑将用户迁移到 Microsoft Teams。  

### <a name="monitor-the-admin-notification-center"></a>监视管理员通知中心

观看管理员通知中心中的通知，提供有关用户迁移的更多详细信息和日程表。 通知在迁移期前至少 30 天发送。

> [!Note]
> 如果收到用户的迁移时间线通知，并且出于业务关键原因希望推迟迁移，可以联系 Microsoft 支持部门。 您不能将迁移延迟到 2020 年 2 月 28 日停用日期之后。 对于可能有任何疑问的客户，请联系你的帐户团队或 Microsoft 支持部门。 已使用 Microsoft 365 或 Office 365的客户可以通过客户请求提交Microsoft 365 管理中心。

### <a name="consider-opting-in-for-a-planned-migration"></a>考虑选择加入计划迁移

你可以选择加入计划到 CVM 的语音邮件服务迁移。 在选择加入之前，请查看本文的详细信息，尤其是以下各节：

- 本节 (迁移步骤) 
- ExchUMO 和 Azure 基于云的服务功能矩阵
- 用户体验影响

选择托管迁移时，将不会在管理门户消息中心收到迁移前 30 Microsoft 365通知。

若要选择加入计划的迁移，请从管理员的电子邮件地址发送电子邮件请求，cvm@microsoft.com 以下信息进行迁移： [](mailto:cvm@microsoft.com)

- 首选日期 (周二) ：每个星期二执行一次迁移波。 Please select a date on a Tuesday that is not beyond 12/3/2019.
 
- 租户 ID：32 个字符，格式为 0046728c-688a-4472-a38f-098fec60ac6x。 可以在 Azure AD 下的 Microsoft 365 管理门户中查找租户 ID，或者使用下面的 PowerShell cmdlet：`Get-CsTenant | Select ObjectId`

租户成功迁移后，你将收到一封电子邮件确认。

## <a name="auto-attendant-migration-guidelines"></a>自动助理迁移指南

Microsoft 365和 Office 365 组织管理员需要在 Microsoft Cloud 自动助理 服务中重新创建其 Exchange UM Online 自动助理，在 Exchange UMO 服务停用日期（2020 年 2 月 28 日）之前将其本地电话号码切换为他们。 这是成功迁移和测试新的云自动助理的建议准则。 如果您具有大量自动助理，可以使用 Exchange UM 自动助理[到云 自动助理 迁移](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)脚本来简化自动助理的批量迁移。

### <a name="auto-attendant-setup"></a>自动助理设置

强烈建议您尽早开始设置新的自动助理，以避免最后一分钟的问题，并熟悉云 自动助理 服务的功能和体验。 对于需要一个或多个间隙功能的自动助理，可以在间隙功能可用于准备部署时创建和测试自动助理。 有关间隙功能详细信息，请参阅 [附录](#appendix)。

1. 使用 Exchange UMO cmdlet，使用[Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant)导出现有自动助理的配置。  

2. 使用 Exchange Online PowerShell 中的[Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet 导出问候语媒体文件 (如果已) ，请将其转换为 .mp3 格式。

3. 按照规划云自动[助理](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)和设置云自动助理[](/microsoftteams/create-a-phone-system-auto-attendant)中的说明，使用管理中心或 PowerShell Microsoft Teams自动助理。

4. 如果菜单选项发生更改，请查看问候语。

5. 使用本文已知问题部分中的"自动助理呼叫转接到 PSTN"解决方法配置到 [响应组的](#known-issues) 转移。  

6. 通过内部呼叫或分配测试电话号码来测试新的自动助理。  

### <a name="cutover"></a>直接转换

1. 将电话号码从 UMO Exchange切换到新的自动助理。
2. 将联系人对象的 SIP URI 移动到资源帐户。
3. 使用新分配的电话号码测试和验证自动助理。

## <a name="appendix"></a>附录

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 基于云的服务功能矩阵

| 服务 | 功能级别 | 功能 | 备注  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 服务功能| 支持第三方 PBX    | 包括向第三方 PBX 提供的所有功能，例如 MWI (消息等待指示器) UM Online 发送的 SIP Exchange消息 | 网络   | Y    |
| VM | 服务功能  | 支持Skype for Business Server   |  | Y | Y    |
| VM | 服务功能 | 支持Microsoft Teams|  | Y | N    |
| VM | 服务功能 | 电子数据展示和保留  | 出于安全性和合规性要求  | Y | Y    |
| VM | 服务功能 | Exchange规则支持 | 出于安全性和合规性要求  | Y | Y    |
| VM | 用户功能 | PSTN 拨入访问  | 订阅者访问  | 网络 | Y    |
| VM | 用户功能 | 委派用户  | 未接来电电子邮件  | 网络 | Y    |
| VM | 用户功能 | PSTN Outlook Voice Access   | 订阅者访问  | 网络 | Y    |
| VM | 用户功能 | 使用经过身份验证的终结点拨入 | 呼叫语音邮件服务以收听语音邮件并更改语音邮件设置| Y | Y    |
| VM | 用户功能 | 禁用语音邮件的用户设置   |  | Y | Y    |
| VM | 用户功能 | 用于更改个人问候语的用户设置  |  | Y | Y    |
| VM | 用户功能 | 用于创建 OOF 问候语的用户设置  |  | Y | Y    |
| VM | 用户功能 | 用于更改默认语言的用户设置  |  | Y | Y    |
| VM | 用户功能 | 使用 TTS 覆盖默认问候语的用户设置  |  | Y | N    |
| VM | 用户功能 | 在经过身份验证的设备 (个人问候语)  |  | Y | Y    |
| VM | 用户功能 | 在 PSTN (录制个人) — 在电话上播放 |  | 网络 | Y    |
| VM | 用户功能 | 禁用转录的用户设置 |  | 网络 | Y    |
| VM | 用户功能 | 听录  |  | Y | Y    |
| VM | 用户功能 | MWI (消息等待指示器) SIP 通知消息 |  | 网络 | Y    |
| VM | 用户功能 | MP3 音频文件格式Outlook    |  | Y | Y    |
| VM | 用户功能 | 可变速度播放控件 |  | Y | Y    |
| VM | 用户功能 | 转发语音邮件  | 将收到的语音邮件转发给其他用户 | Y | Y    |
| VM | 用户功能 | 向一组用户发送语音邮件  |语音邮件广播   | 网络 | Y   |
| VM | 用户功能 | 使用 SMS 的语音邮件通知    | 当用户有新的语音邮件时，可以收到短信    | 网络 | Y    |
| VM | 用户功能 | 支持的问候语语言 | 详细信息： [什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | 用户功能 | 电话应答规则 |  | Y | Y    |
| VM | 用户功能 | 在电话上 (PSTN) - 播放消息 | 在我的单元格上呼叫我以收听语音邮件  | 网络 | Y    |
| VM | 用户功能 | 在电话上 (身份验证) - 播放消息 | 在经过身份验证的设备上呼叫我  | 网络 | Y    |
| VM | 用户功能 | 多个用户之间的共享邮箱 |  | Y | Y    |
| VM | 呼叫者功能  | 呼叫者体验 - 受保护的语音邮件 | 呼叫者可以选择一个选项，将录制的邮件标记为受保护| 网络 | Y    |
| VM | 呼叫者功能  | 呼叫者体验 — 私人语音邮件 | 呼叫者可以选择将录制的邮件标记为私人的选项  | 网络 | Y    |
| VM | 呼叫者功能  | 静默检测   |  | 网络 | Y    |
| VM | Tenant-Admin功能 | 服务器级受保护的语音邮件    | 租户管理员可配置服务级别规则以将传入语音邮件标记为受保护 | Y | Y    |
| VM | Tenant-Admin功能 | 更改录制持续时间限制  |     | Y | Y    |
| VM | Tenant-Admin功能 | 更改静默检测超时    |  | 不适用    | Y    |
| VM | Tenant-Admin功能 | 更改输入失败次数 | CVM：硬编码为 3 | 网络 | Y    |
| VM | Tenant-Admin功能 | 更改默认语言 |  | Y | Y    |
| VM | Tenant-Admin功能 | 禁用/启用转录 |  | Y | Y    |
| VM | Tenant-Admin功能 | 禁用/启用未接来电通知 |  | 网络 | Y    |
| VM | Tenant-Admin功能 | 帮助 Microsoft 改进语音邮件预览    |  | Y | Y    |
| VM | Tenant-Admin功能 | 为启用的用户自定义短信|  | 不适用    | Y    |
| VM | Tenant-Admin功能 | 转录亵亵屏蔽|  | Y | N    |
| VM | Tenant-Admin功能 | 语音邮件策略    |   | Y | Y    |
| VM | Tenant-Admin功能 | Web 门户管理   |  | CY19   | Y    |
| VM | Tenant-Admin功能 | PowerShell   |  | Y | Y    |
| UM | 用户功能 | 邮件等待指示器 (认证的) MWI Skype for Business MWI 服务   |可能由电话合作伙伴提供  | 否 | 是    |
| AA | 服务功能 | AA 支持第三方 PBX    |  | 网络 | Y    |
| AA | 服务功能 | 支持Skype for Business Server   |  | Y | Y    |
| AA | 服务功能 | 支持Microsoft Teams|  | Y | N    |
| AA | 服务功能 | 按名称拨号，DTMF 输入    |  | Y | Y    |
| AA | 服务功能 | 按名称拨号，语音输入  |  | Y | Y    |
| AA | 服务功能 | 多语言支持 | 此处的语言详细信息 [：什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| AA | 服务功能 | 转接到话务员、CQ 或用户 |  | Y | Y    |
| AA | 服务功能 | 通过 DID RNL (内部转移到 PSTN)   |  | Y | Y    |
| AA | 服务功能 | 从外部转移到 PSTN 号码  |  | 请查看下面的已知问题部分 | Y    |
| AA | 服务功能 | 营业时间 |  | Y | Y    |
| AA | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| AA | 服务功能 | 将云 PSTN 号码分配给 AA |  | Y | N    |
| AA | 服务功能 | 向 AA 分配内部 PSTN 号码  |  | Y | Y    |
| AA | 服务功能 | 自定义用户选择  | 使呼叫者能够访问自定义的组织用户列表| Y | Y    |
| AA | 服务功能 | 非工作时间和假日处理  |  | Y | Y    |
| AA | 服务功能 | 使用文本到语音的自定义问候语  |  | Y | Y    |
| AA | 服务功能 | 分机拨号   | 通过拨打用户的分机来访问用户  | Y   | Y    |
| AA | 服务功能 | AA 呼叫者留言的邮箱    |  | Y   | Y    |
| AA | 服务功能 | AA 的多个 PSTN 号码分配|  | Y | Y    |
| AA | Tenant-Admin功能 | Web 门户管理   |  | Y | N    |
| AA | Tenant-Admin功能 | PowerShell cmdlet  |  | Y | Y    |
| Fax| 服务功能 | 传真集成|  | 网络 | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>为管理员建议的测试计划和迁移后验证

若要验证您的用户已迁移到 云语音邮件，请为用户保留语音邮件，并检查邮件正文Outlook。 云语音邮件邮件的页脚显示：

"感谢您使用转录！ 如果你未看到上述脚本，这是因为音频质量不够清晰，无法转录。"

在迁移用户后测试语音邮件功能时，请确保考虑以下方案：

- 验证组织中所有终结点类型（如应用和 IP 电话）的语音邮件访问。
- 向示例用户验证是否向呼叫者播放配置的个性化问候语。
- 如果您的组织具有禁用用户转录的法律或合规性要求，请确保它在迁移后被禁用。 有关详细信息，请参阅设置[云语音邮件。](/microsoftteams/set-up-phone-system-voicemail)
- 如果你之前已配置Exchange VM 策略和规则，请确保它们有效。
- 熟悉用于更改云语音邮件设置的服务 PowerShell cmdlet。  

### <a name="user-experience-impact"></a>用户体验影响

以下是最终用户语音邮件迁移体验的概述。


|体验  |用户体验变化|
|---------|---------|
|电子邮件通知 | 无变化<br>不会向用户发送电子邮件，通知他们有关语音邮件帐户激活/迁移的信息。 |
|访问以前的邮件 | 无变化<br>用户可以在所有受支持的终结点中访问其以前的语音邮件。 |
|在 outlook 中接收 VM，SFB 应用| 无变化<br>用户继续在所有受支持的终结点中接收语音邮件。 |
|听录 | 增强<br>CVM 转录的精确度和受支持的语言比 ExchUMO 高很多。 |
|用户设置 | 新体验<br>用户可以从 USP 用户设置门户或 USP (更改) 。 用户可以从语音邮件电子邮件中的超链接或 SFB 客户端上的 User-Settings 按钮访问 USP; https://aka.ms/vmsettings.
 |功能| 有关详细信息，请参阅功能集比较。 |
|Outlook VM 消息的规则 | 无变化<br>迁移后，之前创建的规则将应用于 CVM 消息。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的用户管理和预配

新建Skype for Business用户将在创建时自动预配云语音邮件。 无需额外的管理员工作或许可证来设置新的语音邮件用户。 请参阅[设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)了解现有用户和新用户的策略管理。

### <a name="admin-auto-attendant-management-experience"></a>管理员自动助理管理体验

若要了解有关自动助理的更多信息，请参阅 [设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>已知问题

#### <a name="greeting-inconsistencies"></a>问候语不一致

订阅者访问可能继续适用于你的租户，直到服务完全停用，即使在所有用户都迁移到 云语音邮件。 为了避免用户混淆和不一致体验，请禁用订阅者访问，因为问候语在迁移后会更改。 为此，使用 删除每个订阅者访问行的 EXUM 联系人 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自动助理呼叫转接到 PSTN

若要通过 Skype for Business Server 或 Skype for Business Server 上的响应组服务 (RGS) 将自动助理呼叫转移到外部 PSTN 电话号码，请创建一个新的本地用户，将呼叫转接设置为 PSTN 电话号码或 RGS 电话号码。 必须为用户启用并正确配置企业语音分配语音策略。

#### <a name="shared-mailbox-is-still-accessible"></a>仍可访问共享邮箱

使用 UM Online Exchange的共享邮箱在迁移到 CVM 后将继续接收邮件，并且用户可通过 Outlook。 但是，迁移到 CVM 后，将无法访问更改这些邮箱的问候语消息。 拥有用于捕获自动助理呼叫者的共享邮箱的客户应在 2019 年 10 月 (ETA 发布后利用自动助理和呼叫队列共享邮箱功能) 。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"Username is not using Skype for Business"banner displays

CVM 服务基于 Microsoft Teams 基础结构，来自 Skype for Business 客户端的调用可能会导致在客户端上显示一个信息横幅，提示："用户名没有使用 Skype for Business。 若要获得更丰富的体验，请Teams或开始Skype会议。"
请确保将用户的客户端Skype for Business最新的 C2R 客户端更新，以防止显示此横幅。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"设置语音邮件"将您带至 OWA

在 **迁移到** CVM 后，单击"从客户端设置语音邮件"将继续使 Skype for Business Server 2015/2013 客户访问 Office Web Access (OWA) 门户页。 所有设置已从 OWA 中的"语音邮件"选项卡中删除，将显示横幅，并会显示重定向链接，以将用户定向到 CVM 用户设置门户。

#### <a name="changing-greeting-remotely"></a>远程更改问候语

CVM 不支持 PSTN 订阅者访问。 对于需要远程更改问候语的用户，"更改问候语"菜单选项已添加到移动客户端的语音邮件 IVR 服务中。 用户可以通过在移动客户端拨号盘上长按"1"键来调用此服务。