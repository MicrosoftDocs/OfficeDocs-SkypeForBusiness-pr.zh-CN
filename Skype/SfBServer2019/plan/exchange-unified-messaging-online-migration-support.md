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
description: Microsoft 正在停用2020年2月28日的 Exchange 统一消息联机（ExchUMO）服务。 本文总结了受影响的客户应了解的内容，并将为其规划业务连续性而执行此操作。
ms.openlocfilehash: 3d6c30c1f6323030280fba29c6d53b89ed33c2c9
ms.sourcegitcommit: 44e47c3b2eb44c38cb8d761befdc6c0cef7c61bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2020
ms.locfileid: "44842023"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 统一消息在线迁移支持

> [!IMPORTANT]
> **Exchange Online 中的统一消息服务因太平洋时间2月28日（即2020、下午5日）而不提供支持。Microsoft 已将所有语音邮件帐户迁移到云语音邮件服务。任何剩余的自动助理流量都不会受到监控，并且可能会在任何时候中断。**

有关2019年2月8日[发布的通知](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)，Microsoft 正在注销 Exchange 统一消息联机（ExchUMO）服务（2020年2月28日）。 本文简要介绍了受影响的客户应了解的内容，并将为其规划业务连续性而执行此操作。

ExchUMO 由客户为语音邮件、自动助理、呼叫队列和传真集成服务进行部署。 Microsoft 计划帮助客户迁移到已在 Skype for Business Online 和 Microsoft 团队中支持数以千计客户的电话系统服务。

语音邮件主要是 Microsoft 驱动的迁移;对于客户的子集，可能需要管理员参与和/或投资。 自动助理是管理员驱动的迁移;你将需要在云自动助理云服务中重新创建现有 ExchUMO 自动助理树。 使用任何 ExchUMO 功能和第三方 PBX 的客户将不会迁移到 Skype 云服务，因为它们不支持第三方 PBX 系统。 在[此博客](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)中宣布了第三方支持的退休计划，此部署模型中的客户可以将他们的用户迁移到 Microsoft 的统一通信平台/服务之一，也可以为这些用户获取第三方语音邮件和/或自动助理解决方案。 在基于云的服务中不支持传真集成;客户将需要迁移到第三方解决方案。

## <a name="who-is-affected"></a>受影响的是谁？

使用 Exchange 统一消息在线服务中的以下任何功能的客户将受到影响：

- 语音邮件服务
- 自动助理服务
- 呼叫队列服务
- 传真集成

> [!Note]
> 在本地使用任意 Exchange Server 和统一消息的客户不受影响。

详细了解用户和管理员体验对[用户体验](#user-experience-impact)的影响。

## <a name="migration-plan-overview"></a>迁移计划概述

Microsoft 已识别出使用 ExchUMO 中的功能的各种客户部署，并将根据以下计划帮助客户进行迁移。

|Customer 组 |日程表  |详细信息  |
|---------|---------|---------|
|准备好迁移的客户<br><br>要迁移的功能：<br><ul><li>语音邮件</ul>   |   3月—5月2019  |示例：<ul><li>    具有简单语音邮件部署和使用情况的客户<li>已为 Microsoft 建立了所有要求以执行迁移的客户<ul>|
|具有先决条件的客户<br><br>要迁移的功能：<br><ul><li>语音邮件<li>自动助理<li>呼叫队列</ul> |  可能-12 月2019 |示例： <br><ul><li>混合配置未完成<li>未设置混合 PSTN 号码</ul>|
|需要管理员参与 & 客户投资的客户<br><br>要迁移的功能：<ul><li>语音邮件<li>自动助理<li>呼叫队列<li>传真集成</ul>| 年2月2020  | 示例： <br><ul><li>ExchUMO 服务由第三方 PBX 使用<li>具有 PSTN 订阅者访问要求的客户<li>SFB 2010 上的客户（不支持）<li>传真集成</ul> |

## <a name="voicemail-migration-guidelines"></a>语音邮件迁移指南

### <a name="get-informed"></a>获得通知

熟悉[博客通知](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)和本文，为您的用户规划平稳迁移。 有关电话系统语音邮件功能的详细信息，请参阅[检查 Skype For business 语音邮件和选项](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>建立 Skype for Business 混合拓扑

如果未建立 Skype for Business 混合拓扑，则需要执行此操作以启用语音邮件用户的平稳迁移。 有关更多详细信息，请参阅[配置 Skype For business 混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)。

> [!Note]
> 您无需联机迁移语音邮件服务迁移的用户。 但是，对于本地用户，要利用电话系统语音邮件服务，必须建立混合拓扑。

### <a name="plan-your-auto-attendant-migration"></a>规划自动助理迁移

管理员可以随时开始将其自动助理从 ExchUMO 迁移到云自动助理。 有关详细信息，请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。

Microsoft 继续提供其他自动助理功能，客户可能会考虑他们的迁移需要考虑的功能。 管理员应评估功能集并相应地迁移其自动助理实例。 有关功能列表比较，请参阅[ExchUMO 和基于 Azure 云的服务功能矩阵](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>规划语音邮件迁移后验证和测试

语音邮件迁移是 Microsoft 驱动的。 如果已建立先决条件混合拓扑，则管理员不需要执行任何操作。 Microsoft 执行所需的验证和测试以确保用户的语音邮件迁移不会中断。 鼓励管理员在自己的一侧执行测试和验证。 请参阅[针对管理员的建议测试计划和迁移后验证](#suggested-test-plan-and-post-migration-validation-for-admins)，以获取建议的测试计划。

> [!Note]
> 不支持 Lync Server 2010。 如果使用的是2010服务器部署，则应规划服务器升级或考虑将用户迁移到 Microsoft 团队或 Skype for Business Online。  

### <a name="monitor-the-admin-notification-center"></a>监视管理员通知中心

在管理员通知中心中观看有关用户迁移的详细信息和日程表的通知。 通知在迁移期前至少在30天内发送。

> [!Note]
> 如果您收到一条通知，告知用户的迁移时间线，并且希望由于业务关键型原因推迟迁移，您可以通过联系 Microsoft 支持来执行此操作。 您无法将迁移推迟到2020年2月28日的退休日期之后。 对于可能包含更多问题的客户，请联系你的帐户团队或 Microsoft 支持部门。 已使用 Microsoft 365 或 Office 365 的客户可以通过 Microsoft 365 管理中心提交支持案例。

### <a name="consider-opting-in-for-a-planned-migration"></a>考虑在计划迁移中选择加入

您可以选择加入规划的语音邮件服务迁移到 CVM。 在选择之前，请查看本文的详细信息，尤其是以下部分：

- 迁移步骤（本节）
- ExchUMO 和基于 Azure 云的服务功能矩阵
- 用户体验影响

选择托管迁移时，将不会在 Microsoft 365 管理门户消息中心收到预迁移30天通知。

若要选择加入计划迁移，请将电子邮件请求从管理员的电子邮件地址发送到[cvm@microsoft.com](mailto:cvm@microsoft.com) ，并提供以下信息：

- 首选日期（星期二）：每星期二执行一次迁移波形。 请选择星期二不超过12/3/2019 的日期。
 
- 租户 ID：32个字符，格式为 0046728c-688a-4472-a38f-098fec60ac6x。 您可以在 Microsoft 365 管理门户中的 Azure AD 下找到租户 ID，或使用以下 PowerShell cmdlet：`Get-CsTenant | Select ObjectId`

一旦成功迁移租户，你将收到电子邮件确认。

## <a name="auto-attendant-migration-guidelines"></a>自动助理迁移指南

Microsoft 365 和 Office 365 组织管理员需要在 Microsoft 云自动助理服务中重新创建 Exchange UM Online 自动助理，并在 Exchange UMO 服务退休日期2月 28 2020 日之前将其内部部署电话号码切换到这些号码。 这是成功迁移和测试新云自动助理的建议准则。 如果您有大量自动助理，则可以使用[EXCHANGE UM 自动助理到云自动助理迁移脚本](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)，以简化自动助理的批量迁移。

### <a name="auto-attendant-setup"></a>自动助理设置

强烈建议您尽早开始安装新的自动助理，以避免出现最后一分钟的问题，并熟悉云自动助理服务的功能和体验。 对于需要一个或多个间隙功能的自动助理，当间隙功能可用于准备部署时，您可以创建并测试自动助理。 有关间隙功能的详细信息，请参阅[附录](#appendix)。

1. 使用 Exchange UMO cmdlet 可以导出现有自动助理的配置，方法是使用[get-umautoattendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)。  
2. 在 Exchange Online PowerShell 中使用[import-umprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet 导出问候语媒体文件（如果使用），并将其转换为. mp3 格式。
3. 按照[规划云自动助理](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)中的说明进行操作，并[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)，以使用 Microsoft 团队管理员中心或 Powershell 创建自动助理。
4. 如果菜单选项发生更改，请查看你的问候语。
5. 使用本文的 "[已知问题](#known-issues)" 部分中的 "自动助理呼叫转移到 PSTN" 解决方法配置到响应组的传输。  
6. 通过在内部调用新的自动助理或分配测试电话号码来测试新的自动助理。  

### <a name="cutover"></a>直接转换

1. 将电话号码从 Exchange UMO 自动助理切换到新的自动助理。
2. 将 SIP URI 从 contact 对象移动到资源帐户。
3. 使用新分配的电话号码测试和验证自动助理。

## <a name="appendix"></a>附录

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和基于 Azure 云的服务功能矩阵

| 服务 | 功能级别 | 功能 | 注释  | 云 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VMNETWORK  | 服务功能| 支持第三方 PBX    | 使用来自 Exchange UM Online 的 SIP 通知邮件的第三方 PBX （邮件等待指示器）提供的所有功能（包括 MWI （邮件等待指示器）） | N   | Y    |
| VMNETWORK | 服务功能  | 支持 Skype for Business Server   |  | Y | Y    |
| VMNETWORK | 服务功能 | 支持 Microsoft 团队|  | Y | N    |
| VMNETWORK | 服务功能 | 电子数据展示和保留  | 出于安全和合规性  | Y | Y    |
| VMNETWORK | 服务功能 | Exchange 规则支持 | 出于安全和合规性  | Y | Y    |
| VMNETWORK | 用户功能 | PSTN 电话拨入访问  | 订阅者访问  | N | Y    |
| VMNETWORK | 用户功能 | 委派用户  | 未接来电电子邮件  | N | Y    |
| VMNETWORK | 用户功能 | PSTN Outlook Voice Access   | 订阅者访问  | N | Y    |
| VMNETWORK | 用户功能 | 使用经过身份验证的终结点拨入 | 调用语音邮件服务收听语音邮件和更改语音邮件设置| Y | Y    |
| VMNETWORK | 用户功能 | 禁用语音邮件的用户设置   |  | Y | Y    |
| VMNETWORK | 用户功能 | 用于更改个人问候语的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 用于创建 OOF 问候语的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 更改默认语言的用户设置  |  | Y | Y    |
| VMNETWORK | 用户功能 | 使用 TTS 覆盖默认问候语的用户设置  |  | Y | N    |
| VMNETWORK | 用户功能 | 录制个人问候语（经过身份验证的设备） |  | Y | Y    |
| VMNETWORK | 用户功能 | 录制个人问候语（PSTN）—在电话上播放 |  | N | Y    |
| VMNETWORK | 用户功能 | 禁用用户的用户设置 |  | N | Y    |
| VMNETWORK | 用户功能 | 转录  |  | Y | Y    |
| VMNETWORK | 用户功能 | 所有终结点上的视觉语音邮件   | 在所有受支持的终结点上播放、删除、邮件等待指示器和状态切换的用户控件  | Y | Y    |
| VMNETWORK | 用户功能 | Outlook 中的 MP3 音频文件格式    |  | Y | Y    |
| VMNETWORK | 用户功能 | 变速播放控制 |  | Y | Y    |
| VMNETWORK | 用户功能 | 转发语音邮件  | 将接收到的语音邮件转发给其他用户 | Y | Y    |
| VMNETWORK | 用户功能 | 向一组用户发送语音邮件  |语音邮件广播   | N | Y   |
| VMNETWORK | 用户功能 | 使用短信的语音邮件通知    | 用户在收到新的语音邮件时可以收到短信    | N | Y    |
| VMNETWORK | 用户功能 | 支持的问候语语言 | 详细信息如下：https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VMNETWORK | 用户功能 | 电话应答规则 |  | Y | Y    |
| VMNETWORK | 用户功能 | 在电话上播放（PSTN）-播放邮件 | 在我的单元格上呼叫我以收听语音邮件  | N | Y    |
| VMNETWORK | 用户功能 | 在电话上播放（身份验证）-播放邮件 | 呼叫我已通过身份验证的设备  | Y | Y    |
| VMNETWORK | 用户功能 | 多个用户之间的共享邮箱 |  | Y | Y    |
| VMNETWORK | 呼叫者功能  | 呼叫者体验-受保护的语音邮件 | 呼叫者可以选择将记录的邮件标记为受保护的选项| N | Y    |
| VMNETWORK | 呼叫者功能  | 呼叫者体验—专用语音邮件 | 呼叫者可以选择将录制的邮件标记为私人邮件的选项  | N | Y    |
| VMNETWORK | 呼叫者功能  | 静音检测   |  | N | Y    |
| VMNETWORK | 租户-管理员功能 | 服务器级别的受保护语音邮件    | 租户-管理员可以配置服务级别规则以将传入语音邮件标记为受保护 | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 更改录制持续时间限制  |     | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 更改静音检测超时    |  | 不适用    | Y    |
| VMNETWORK | 租户-管理员功能 | 更改输入失败的次数 | CVM：硬编码为3 | N | Y    |
| VMNETWORK | 租户-管理员功能 | 更改默认语言 |  | Y | Y    |
| VMNETWORK | 租户-管理员功能 | Disable/enable |  | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 禁用/启用未接来电通知 |  | N | Y    |
| VMNETWORK | 租户-管理员功能 | 帮助 Microsoft 改进语音邮件预览    |  | Y | Y    |
| VMNETWORK | 租户-管理员功能 | 为已启用的用户自定义短信|  | 不适用    | Y    |
| VMNETWORK | 租户-管理员功能 | 应对猥亵屏蔽|  | Y | N    |
| VMNETWORK | 租户-管理员功能 | 语音邮件策略    |   | Y | Y    |
| VMNETWORK | 租户-管理员功能 | Web 门户管理   |  | CY19   | Y    |
| VMNETWORK | 租户-管理员功能 | PowerShell   |  | Y | Y    |
| AA | 服务功能 | AA 支持第三方 PBX    |  | N | Y    |
| AA | 服务功能 | 支持 Skype for Business Server   |  | Y | Y    |
| AA | 服务功能 | 支持 Microsoft 团队|  | Y | N    |
| AA | 服务功能 | 按名称拨号，DTMF 输入    |  | Y | Y    |
| AA | 服务功能 | 按名称拨号，语音输入  |  | Y | Y    |
| AA | 服务功能 | 多语言支持 | 此处为语言详细信息：https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | 服务功能 | 转移到操作员、CQ.ADD 或用户 |  | Y | Y    |
| AA | 服务功能 | 内部转到 PSTN 号码（已 RNL）  |  | Y | Y    |
| AA | 服务功能 | 外部转接到 PSTN 号码  |  | 查看下面的 "已知问题" 部分 | Y    |
| AA | 服务功能 | 营业时间 |  | Y | Y    |
| AA | 服务功能 | 菜单选项 | IVR 菜单选项  | Y | Y    |
| AA | 服务功能 | 向 AA 分配云 PSTN 号码 |  | Y | N    |
| AA | 服务功能 | 为 AA 分配本地 PSTN 号码  |  | Y | Y    |
| AA | 服务功能 | 自定义用户选择  | 使呼叫者能够访问组织用户的自定义列表| Y | Y    |
| AA | 服务功能 | 工作时间和假日处理  |  | Y | Y    |
| AA | 服务功能 | 使用文本到语音的自定义问候语  |  | Y | Y    |
| AA | 服务功能 | 分机拨号   | 通过拨打用户的分机来联系用户  | Y   | Y    |
| AA | 服务功能 | 供 AA 呼叫者用来留下邮件的邮箱    |  | Y   | Y    |
| AA | 服务功能 | 向 AA 分配多个 PSTN 号码|  | Y | Y    |
| AA | 租户-管理员功能 | Web 门户管理   |  | Y | N    |
| AA | 租户-管理员功能 | PowerShell cmdlet  |  | Y | Y    |
| 传真| 服务功能 | 传真集成|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>针对管理员的建议测试计划和迁移后验证

若要验证您的用户是否已迁移到云语音邮件，请将语音邮件保留给用户，并在 Outlook 中检查邮件正文。 云语音邮件有一个页脚，其中包含以下内容：

"感谢你使用" 运行 "。 如果看不到上述脚本，这是因为音频质量不够清楚，无法 transcribe。

在迁移用户后测试语音邮件功能时，请务必考虑以下方案：

- 验证组织中所有终结点类型（如应用程序和 IP 电话）上的语音邮件访问。
- 使用示例用户验证向呼叫者播放已配置的个性化问候语。
- 如果您的组织有法律或合规性要求对用户禁用用户，请确保已在迁移后禁用该功能。 有关更多详细信息，请参阅[设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)。
- 如果您以前配置了 Exchange VM 策略和规则，请确保它们有效。
- 熟悉云语音邮件服务 PowerShell cmdlet，以更改用户设置。  

### <a name="user-experience-impact"></a>用户体验影响

以下是最终用户的语音邮件迁移体验的概述。


|体验  |用户体验方面的更改|
|---------|---------|
|电子邮件通知 | 无变化<br>不向用户发送电子邮件，通知他们有关语音邮件帐户激活/迁移的信息。 |
|对以前的邮件的访问 | 无变化<br>用户可以在所有受支持的终结点中访问其以前的语音邮件。 |
|在 outlook 中接收 VM，SFB 应用程序| 无变化<br>用户继续在所有受支持的终结点中接收语音邮件。 |
|转录 | 有所<br>CVM 与 ExchUMO 相比，精确度率高得多，且支持的语言更高。 |
|用户设置 | 新体验<br>用户可以从用户设置门户（USP）更改其首选项。 用户可以从其语音邮件中的超链接或其 SFB 客户端上的用户设置按钮访问其 USP;https://aka.ms/vmsettings.
 |功能| 有关详细信息，请参阅功能集比较。 |
|适用于 VM 邮件的 Outlook 规则 | 无变化<br>在迁移后，以前创建的规则将应用于 CVM 邮件。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的用户管理和预配

新的 Skype for Business 用户将在创建时自动为云语音邮件设置。 预配新的语音邮件用户不需要其他管理员工作或许可证。 请参阅[设置云语音邮件](/microsoftteams/set-up-phone-system-voicemail)，了解现有用户和新用户的策略管理。

### <a name="admin-auto-attendant-management-experience"></a>管理员自动助理管理体验

若要了解有关自动助理的详细信息，请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>已知问题

#### <a name="greeting-inconsistencies"></a>问候语不一致

订阅者访问可能仍适用于你的租户，直到服务完全停用，即使你的所有用户都已迁移到云语音邮件也是如此。 若要避免用户混淆和不一致的体验，请禁用订阅者访问，因为在迁移之后问候语发生更改。 为此，请使用删除每个订阅者访问线路的 EXUM 联系人 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自动助理呼叫转移到 PSTN

鼓励客户配置一种临时解决方法，以满足将自动助理呼叫转移到外部 PSTN 号码或 RGS 实例的要求。

在质量保证期间，使用 "转接到 PSTN 号码" 功能发现了一个问题，该问题将不会及时固定，以供客户在2月28日的计划退休日期2020之前开始迁移 Exchange UMO 服务。 作为一种解决方法，管理员可以将自动助理呼叫者转接到具有活动呼叫转接设置的本地虚拟用户，以使用所需的 PSTN 电话号码或 RGS 电话号码。 预期的体验是：

- 管理员无需向虚拟用户授予许可证，因为这是一个替代解决方案。
- 管理员可以通过将所需的号码分配给虚拟用户或使用 SBC 数字操作功能来操作 PSTN 接收器看到的呼叫者 ID。
- PSTN 呼叫者在呼叫转接过程中不会遇到任何延迟，并将在传输成功后继续看到自动助理的呼叫者 ID。

#### <a name="shared-mailbox-is-still-accessible"></a>共享邮箱仍可访问

使用 Exchange UM Online 配置的共享邮箱将在迁移到 CVM 后继续接收邮件，并可通过 Outlook 供用户访问。 但是，在迁移到 CVM 后，更改这些邮箱的问候语消息的访问权限将不可用。 使用共享邮箱（用于捕获自动助理呼叫者）的客户应使用自动助理和呼叫队列共享邮箱功能已发布（ETA 10 月2019）。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"用户名不使用 Skype for Business" 标题显示

CVM 服务基于 Microsoft 团队基础结构，并且来自 Skype for Business 客户端的调用可能会导致在客户端上显示信息横幅，以读取： "Username 未使用 Skype for Business。 若要获得更丰富的体验，请切换到团队或启动 Skype 会议。
确保将用户的 Skype for Business 客户端更新到最新的 C2R 客户端更新，以防止出现此标语。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"设置语音邮件" 将转到 OWA

在迁移到 CVM 后，单击 "从客户端**设置语音邮件**" 将继续让 Skype For business Server 2015/2013 客户进入 Office Web ACCESS （OWA）门户页面。 所有设置均已从 OWA 中的 "语音邮件" 选项卡中删除，标题将显示一个 "重定向" 链接，以使用户进入 CVM 用户设置门户。

#### <a name="changing-greeting-remotely"></a>远程更改问候语

PSTN 订阅者访问在 CVM 中不受支持。 对于需要远程更改其问候语的用户，已将 "更改问候语" 菜单选项添加到了移动客户端的语音邮件 IVR 服务中。 用户可以通过在移动客户端的拨号板上按住 "1" 键来呼叫此服务。
