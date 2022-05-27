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
description: Microsoft 将在 2020 年 2 月 28 日之前停用Exchange统一消息联机 (ExchUMO) 服务。 本文汇总了受影响的客户应该了解和执行哪些操作来规划其业务连续性。
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676364"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持

> [!IMPORTANT]
> **截至太平洋时间 2020 年 2 月 28 日下午 5 点，Exchange Online中的统一消息传送服务已失去支持。Microsoft 已将所有语音邮件帐户迁移到云语音邮件服务。不会监视剩余自动助理流量，并且随时可能会中断。**

有关 2019 年 2 月 8 日的[公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)，Microsoft 将在 2020 年 2 月 28 日之前停用Exchange统一消息在线 (ExchUMO) 服务。 本文概述了受影响的客户应该了解和执行哪些操作来规划其业务连续性。

ExchUMO 由客户部署，用于语音邮件、自动助理、呼叫队列和传真集成服务。 Microsoft 计划帮助客户迁移到已在 Skype for Business Online 和 Microsoft Teams 上支持数千名客户的电话系统服务。

语音邮件主要是 Microsoft 驱动的迁移;对于一部分客户，可能需要管理员参与和/或投资。 自动助理是管理员驱动的迁移;需要在云自动助理云服务中重新创建现有的 ExchUMO 自动助理树。 使用第三方 PBX 的任何 ExchUMO 功能的客户将不会迁移到Skype云服务，因为他们不支持第三方 PBX 系统。 [此博客](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)中宣布了第三方支持的停用计划，此部署模型中的客户可以将其用户迁移到 Microsoft 的统一通信平台/服务之一，或者为这些用户获取第三方语音邮件和/或自动助理解决方案。 基于云的服务不支持传真集成;客户需要迁移到第三方解决方案。

## <a name="who-is-affected"></a>Who受到影响？

使用Exchange统一消息联机服务中的以下任何功能的客户将受到影响：

- 语音邮件服务
- 自动助理服务
- 呼叫队列服务
- 传真集成

> [!Note]
> 使用任何本地Exchange Server统一消息的客户不会受到影响。

详细了解用户和管理员体验对 [用户体验影响的影响](#user-experience-impact)。

## <a name="migration-plan-overview"></a>迁移计划概述

Microsoft 已确定使用 ExchUMO 功能的各种客户部署，并将帮助客户根据以下计划进行迁移。

|客户组 |日程表  |详细信息  |
|---------|---------|---------|
|准备迁移的客户<br><br>要迁移的功能：<br><ul><li>语音邮件</ul>   |   2019 年 3 月 - 5 月  |示例:<ul><li>    具有简单语音邮件部署和使用情况的客户<li>为 Microsoft 制定执行迁移的所有要求的客户<ul>|
|具有先决条件的客户<br><br>要迁移的功能：<br><ul><li>语音邮件<li>自动助理<li>呼叫队列</ul> |  2019 年 5 月 - 12 月 |示例: <br><ul><li>混合配置未完成<li>未设置混合 PSTN 数字</ul>|
|需要管理员参与的客户&客户投资<br><br>要迁移的功能：<ul><li>语音邮件<li>自动助理<li>呼叫队列<li>传真集成</ul>| 到 2020 年 2 月  | 示例: <br><ul><li>ExchUMO 服务由第三方 PBX 使用<li>具有 PSTN 订阅服务器访问要求的客户<li>SFB 2010 上的客户 (不受支持的) <li>传真集成</ul> |

## <a name="voicemail-migration-guidelines"></a>语音邮件迁移指南

### <a name="get-informed"></a>获取信息

熟悉 [博客公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 和本文，为用户计划顺利迁移。 有关语音邮件电话系统功能的详细信息，请参阅[Skype for Business语音邮件和选项](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>建立Skype for Business混合拓扑

如果尚未建立Skype for Business混合拓扑，则需要执行此操作，以便顺利迁移语音邮件用户。 有关更多详细信息，请参阅“[配置Skype for Business混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)”。

> [!Note]
> 无需联机迁移用户即可进行语音邮件服务迁移。 但是，本地用户要利用语音邮件服务电话系统，必须建立混合拓扑。

### <a name="plan-your-auto-attendant-migration"></a>规划自动助理迁移

管理员可以随时开始将其自动助理从 ExchUMO 迁移到云自动助理。 有关更多详细信息，请参阅[“设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)”。

Microsoft 继续提供客户可能认为迁移所需的其他自动助理功能。 管理员应评估功能集，并相应地迁移其自动助理实例。 有关功能列表比较，请参阅 [ExchUMO 和 Azure 基于云的服务功能矩阵](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>规划语音邮件帖子迁移验证和测试

语音邮件迁移是 Microsoft 驱动的。 鉴于已建立必要的混合拓扑，管理员无需执行任何操作。 Microsoft 执行所需的验证和测试，以确保用户的语音邮件迁移不会中断。 建议管理员在其一侧执行测试和验证。 请参阅[建议的测试计划和帖子迁移验证，以便管理员](#suggested-test-plan-and-post-migration-validation-for-admins)了解建议的测试计划。

> [!Note]
> 不支持 Lync Server 2010。 如果使用的是 2010 服务器部署，则应计划服务器升级，或考虑将用户迁移到Microsoft Teams。  

### <a name="monitor-the-admin-notification-center"></a>监视管理员通知中心

请在管理员通知中心查看有关用户迁移的更多详细信息和日程表。 通知会在迁移期前至少 30 天发送。

> [!Note]
> 如果收到用户迁移时间线的通知，并且出于业务关键原因而想要推迟迁移，则可以通过联系Microsoft 支持部门来执行此操作。 不能将迁移推迟到 2020 年 2 月 28 日的停用日期之后。 对于可能遇到更多问题的客户，请联系你的帐户团队或Microsoft 支持部门。 已使用Microsoft 365或Office 365的客户可以通过Microsoft 365 管理中心提交支持案例。

### <a name="consider-opting-in-for-a-planned-migration"></a>考虑选择加入计划迁移

可以选择计划内语音邮件服务迁移到 CVM。 在选择加入之前，请查看本文的详细信息，尤其是以下部分：

- 本部分 (迁移步骤) 
- ExchUMO 和 Azure 基于云的服务功能矩阵
- 用户体验影响

选择托管迁移时，不会在Microsoft 365管理门户消息中心收到迁移前 30 天通知。

若要选择进行计划迁移，请从管理员的电子邮件地址发送电子邮件请求，以 [cvm@microsoft.com](mailto:cvm@microsoft.com) 以下信息：

- 首选日期 (星期二) ：迁移波每周二执行。 请在星期二选择不超出 2019/12/3 的日期。
 
- 租户 ID：此格式为 0046728c-688a-4472-a38f-098fec60ac6x 的 32 个字符号。 可以在 Azure AD 下的Microsoft 365管理门户中找到租户 ID，或者使用以下 PowerShell cmdlet：`Get-CsTenant | Select ObjectId`

成功迁移租户后，你将收到电子邮件确认。

## <a name="auto-attendant-migration-guidelines"></a>自动助理迁移指南

Microsoft 365和Office 365组织管理员必须在 Microsoft 云自动助理服务中重新创建其Exchange UM Online 自动助理，并在 2020 年 2 月 28 日Exchange UMO 服务停用日期之前将其本地电话号码切换到他们。 建议使用此指南成功迁移和测试新的云自动助理。 如果有大量自动助理，可以使用 [Exchange UM 自动助理到云自动助理迁移脚本](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)来简化自动助理的批量迁移。

### <a name="auto-attendant-setup"></a>自动助理设置

我们强烈建议你尽早开始设置新的自动助理，以避免最后一刻的问题，并熟悉云自动助理服务的功能和体验。 对于需要一个或多个间隙功能的自动助理，可以在可用间隙功能准备部署时创建和测试自动助理。 有关差距功能的详细信息，请参阅 [附录](#appendix)。

1. 使用 Exchange UMO cmdlet 通过 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant) 导出现有自动助理的配置。  

2. 使用 Exchange Online PowerShell 中的 [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet 导出问候媒体文件 (（如果) 使用，并将其转换为.mp3格式）。

3. 按照 [Plan Cloud 自动助理](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)中的说明操作，并使用 Microsoft Teams 管理中心或 PowerShell [设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)以创建自动助理。

4. 如果菜单选项已更改，请查看您的问候语。

5. 使用本文的 [“已知问题](#known-issues) ”部分中的“自动助理呼叫传输到 PSTN”解决方法配置到响应组的传输。  

6. 通过在内部呼叫新的自动助理或分配测试电话号码来测试这些自动助理。  

### <a name="cutover"></a>直接转换

1. 将电话号码从Exchange UMO 自动助理切换到新的自动助理。
2. 将 SIP URI 从联系人对象移动到资源帐户。
3. 使用新分配的电话号码测试和验证自动助理。

## <a name="appendix"></a>附录

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 基于云的服务功能矩阵

| 服务 | 功能级别 | 功能 | 注释  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 服务功能| 支持第三方 PBX    | 包括向第三方 PBX 提供的所有功能，例如 MWI (消息等待指示器) 使用 SIP 通知来自 Exchange UM Online 的消息 | N   | Y    |
| VM | 服务功能  | 支持Skype for Business Server   |  | Y | Y    |
| VM | 服务功能 | 支持Microsoft Teams|  | Y | N    |
| VM | 服务功能 | 电子数据展示和保留  | 为了实现安全性和符合性  | Y | Y    |
| VM | 服务功能 | Exchange规则支持 | 为了实现安全性和符合性  | Y | Y    |
| VM | 用户功能 | PSTN 拨入访问  | 订阅服务器访问权限  | N | Y    |
| VM | 用户功能 | 委派用户  | 错过呼叫电子邮件  | N | Y    |
| VM | 用户功能 | PSTN Outlook Voice Access   | 订阅服务器访问权限  | N | Y    |
| VM | 用户功能 | 使用经过身份验证的终结点进行拨入 | 调用语音邮件服务以侦听语音消息并更改语音邮件设置| Y | Y    |
| VM | 用户功能 | 用于禁用语音邮件的用户设置   |  | Y | Y    |
| VM | 用户功能 | 用于更改个人问候语的用户设置  |  | Y | Y    |
| VM | 用户功能 | 用于创建 OOF 问候语的用户设置  |  | Y | Y    |
| VM | 用户功能 | 用于更改默认语言的用户设置  |  | Y | Y    |
| VM | 用户功能 | 使用 TTS 覆盖默认问候语的用户设置  |  | Y | N    |
| VM | 用户功能 | 记录个人问候 (经过身份验证的设备)  |  | Y | Y    |
| VM | 用户功能 | 录制个人问候 (PSTN) - 在电话上播放 |  | N | Y    |
| VM | 用户功能 | 用于禁用听录的用户设置 |  | N | Y    |
| VM | 用户功能 | 听录  |  | Y | Y    |
| VM | 用户功能 | MWI (消息等待指示器) 使用 SIP 通知消息 |  | N | Y    |
| VM | 用户功能 | Outlook中的 MP3 音频文件格式    |  | Y | Y    |
| VM | 用户功能 | 变量速度播放控件 |  | Y | Y    |
| VM | 用户功能 | 转发语音邮件  | 将收到的语音邮件转发给其他用户 | Y | Y    |
| VM | 用户功能 | 向一组用户发送语音消息  |语音邮件广播   | N | Y   |
| VM | 用户功能 | 使用短信的语音邮件通知    | 当用户有新的语音邮件时，他们可以收到短信    | N | Y    |
| VM | 用户功能 | 支持的问候语 | 详细信息： [什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | 用户功能 | 电话应答规则 |  | Y | Y    |
| VM | 用户功能 | 在电话上播放 (PSTN) - 播放消息 | 在单元格上打电话给我，收听语音消息  | N | Y    |
| VM | 用户功能 | 在电话 (身份验证) 播放消息 | 在经过身份验证的设备上给我打电话  | N | Y    |
| VM | 用户功能 | 多个用户之间的共享邮箱 |  | Y | Y    |
| VM | 调用方功能  | 呼叫者体验 - 受保护的语音邮件 | 调用方可以选择将记录的消息标记为受保护的选项| N | Y    |
| VM | 调用方功能  | 呼叫者体验 - 专用语音邮件 | 调用方可以选择将记录的消息标记为专用邮件的选项  | N | Y    |
| VM | 调用方功能  | 静音检测   |  | N | Y    |
| VM | Tenant-Admin功能 | 服务器级受保护的语音邮件    | Tenant-admin 可以配置服务级别规则，将传入的语音邮件标记为受保护 | Y | Y    |
| VM | Tenant-Admin功能 | 更改录制持续时间限制  |     | Y | Y    |
| VM | Tenant-Admin功能 | 更改静音检测超时    |  | 不适用    | Y    |
| VM | Tenant-Admin功能 | 更改输入失败次数 | CVM：硬编码为 3 | N | Y    |
| VM | Tenant-Admin功能 | 更改默认语言 |  | Y | Y    |
| VM | Tenant-Admin功能 | 禁用/启用听录 |  | Y | Y    |
| VM | Tenant-Admin功能 | 禁用/启用未接听呼叫通知 |  | N | Y    |
| VM | Tenant-Admin功能 | 帮助 Microsoft 改进语音邮件预览    |  | Y | Y    |
| VM | Tenant-Admin功能 | 为已启用的用户自定义文本消息|  | 不适用    | Y    |
| VM | Tenant-Admin功能 | 听录亵渎屏蔽|  | Y | N    |
| VM | Tenant-Admin功能 | 语音邮件策略    |   | Y | Y    |
| VM | Tenant-Admin功能 | Web 门户管理   |  | CY19   | Y    |
| VM | Tenant-Admin功能 | PowerShell   |  | Y | Y    |
| UM | 用户功能 | Skype for Business认证手机上的消息等待指示器 (MWI)    |可由电话合作伙伴提供  | 否 | 是    |
| 机 管 局 | 服务功能 | AA 支持第三方 PBX    |  | N | Y    |
| 机 管 局 | 服务功能 | 支持Skype for Business Server   |  | Y | Y    |
| 机 管 局 | 服务功能 | 支持Microsoft Teams|  | Y | N    |
| 机 管 局 | 服务功能 | 按名称拨号，DTMF 输入    |  | Y | Y    |
| 机 管 局 | 服务功能 | 按名称拨号，语音输入  |  | Y | Y    |
| 机 管 局 | 服务功能 | 多语言支持 | 此处的语言详细信息： [什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| 机 管 局 | 服务功能 | 传输到操作员、CQ 或用户 |  | Y | Y    |
| 机 管 局 | 服务功能 | 在内部传输到 PSTN 号码 (DID RNL)   |  | Y | Y    |
| 机 管 局 | 服务功能 | 在外部传输到 PSTN 号码  |  | 查看下面的“已知问题”部分 | Y    |
| 机 管 局 | 服务功能 | 营业时间 |  | Y | Y    |
| 机 管 局 | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| 机 管 局 | 服务功能 | 将云 PSTN 号码分配到 AA |  | Y | N    |
| 机 管 局 | 服务功能 | 将本地 PSTN 号码分配到 AA  |  | Y | Y    |
| 机 管 局 | 服务功能 | 自定义用户选择  | 使调用方能够访问自定义的组织用户列表| Y | Y    |
| 机 管 局 | 服务功能 | 下班后和假期治疗  |  | Y | Y    |
| 机 管 局 | 服务功能 | 使用文本到语音的自定义问候语  |  | Y | Y    |
| 机 管 局 | 服务功能 | 分机拨号   | 通过拨号其扩展来联系用户  | Y   | Y    |
| 机 管 局 | 服务功能 | AA 调用方保留邮件的邮箱    |  | Y   | Y    |
| 机 管 局 | 服务功能 | 向 AA 分配多个 PSTN 号码|  | Y | Y    |
| 机 管 局 | Tenant-Admin功能 | Web 门户管理   |  | Y | N    |
| 机 管 局 | Tenant-Admin功能 | PowerShell cmdlet  |  | Y | Y    |
| Fax| 服务功能 | 传真集成|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>建议的管理员测试计划和帖子迁移验证

若要验证用户是否已迁移到云语音邮件，请将语音邮件保留给用户，并在Outlook中检查消息正文。 云语音邮件消息的页脚如下所示：

“感谢你使用听录！ 如果你没有看到上面的脚本，那是因为音频质量不够清晰，无法转录。

在用户迁移后测试语音邮件功能时，请务必考虑以下方案：

- 验证组织中所有终结点类型的语音邮件访问，例如应用和 IP 电话。
- 向示例用户验证配置的个性化问候语是否已播放给调用方。
- 如果你的组织有禁用用户听录的法律或合规性要求，请确保帖子迁移禁用听录。 有关详细信息，请参阅[“设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)。
- 如果之前已配置Exchange VM 策略和规则，请确保它们有效。
- 熟悉用于更改用户设置的 云语音邮件 服务 PowerShell cmdlet。  

### <a name="user-experience-impact"></a>用户体验影响

以下是最终用户语音邮件迁移体验的概述。


|体验  |用户体验的更改|
|---------|---------|
|电子邮件通知 | 无变化<br>不会向用户发送任何电子邮件，通知他们有关语音邮件帐户激活/迁移的信息。 |
|对以前的消息的访问权限 | 无变化<br>用户有权访问所有受支持的终结点中以前的语音邮件消息。 |
|在 outlook、SFB 应用中接收 VM| 无变化<br>用户继续在所有受支持的终结点中接收其语音邮件。 |
|听录 | 增强<br>CVM 听录的准确率和支持的语言比 ExchUMO 高得多。 |
|用户设置 | 新体验<br>用户可以从用户设置门户 (USP) 更改首选项。 用户可以从语音邮件电子邮件中的超链接或 SFB 客户端上的User-Settings按钮访问其 USP; https://aka.ms/vmsettings.
 |功能| 有关详细信息，请参阅功能集比较。 |
|VM 消息的Outlook规则 | 无变化<br>以前创建的规则将在迁移后应用于 CVM 消息。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的用户管理和预配

新Skype for Business用户将在创建时自动为云语音邮件预配。 预配新的语音邮件用户不需要其他管理员工作或许可证。 请参阅[“设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)了解现有用户和新用户的策略管理。

### <a name="admin-auto-attendant-management-experience"></a>管理员自动助理管理体验

若要了解有关自动助理的详细信息，请参阅[设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>已知问题

#### <a name="greeting-inconsistencies"></a>问候不一致

订阅服务器访问权限可能继续适用于租户，直到服务完全停用，即使所有用户已迁移到云语音邮件。 若要避免用户混淆和不一致的体验，请在迁移后禁用订阅者访问权限，因为问候语会更改。 为此，请删除每个 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`订阅者访问行的 EXUM 联系人。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自动助理呼叫传输到 PSTN

若要在Skype for Business Server上通过Skype for Business Server或响应组服务 (RGS) 将自动助理呼叫传输到外部 PSTN 电话号码，请创建新的本地用户，并将呼叫转接设置为 PSTN 电话号码或 RGS 电话号码。 必须为用户启用并正确配置企业语音并分配语音策略。

#### <a name="shared-mailbox-is-still-accessible"></a>共享邮箱仍可访问

使用 Exchange UM Online 配置的共享邮箱在迁移到 CVM 后继续接收邮件，用户可通过Outlook访问。 但是，迁移到 CVM 后，将无法访问更改这些邮箱的问候消息。 使用共享邮箱捕获自动助理调用方的客户在 2019 年 10 月)  (发布后，应利用自动助理和呼叫队列共享邮箱功能。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>“用户名未使用Skype for Business”横幅显示

CVM 服务基于Microsoft Teams基础结构，来自Skype for Business客户端的调用可能会导致客户端上显示信息横幅，上面写着：“用户名未使用Skype for Business。 若要获得更丰富的体验，请切换到Teams或开始Skype会议。
请确保将用户Skype for Business客户端更新到最新的 C2R 客户端更新，以防止显示此横幅。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>“设置语音邮件”将转到 OWA

在迁移到 CVM 后，单击“从客户端 **设置语音邮件**”将继续将 2015/2013 Skype for Business Server客户带到 Office Web 访问 (OWA) 门户页。 所有设置已从 OWA 中的“语音邮件”选项卡中删除，横幅将显示一个重定向链接，以将用户带到 CVM 用户设置门户。

#### <a name="changing-greeting-remotely"></a>远程更改问候语

CVM 不支持 PSTN 订阅者访问权限。 对于需要远程更改问候语的用户，已将“更改问候语”菜单选项添加到移动客户端的语音邮件 IVR 服务中。 用户可以通过在移动客户端拨号板上按住“1”密钥来调用此服务。