---
title: 为 Microsoft Teams 设置自动助理
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: 了解如何在 Microsoft Teams 中设置和管理自动助理。
ms.openlocfilehash: 041d58ff62304a704b86f6bb25a0ba934b58219f
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763693"
---
# <a name="set-up-an-auto-attendant"></a>设置自动助理

自动助理允许用户呼叫你的组织并导航菜单系统，以便与正确的部门、呼叫队列、人员或操作员交谈。 可以使用 Microsoft Teams 管理中心或 PowerShell 为组织创建自动助理。

在遵循本文中的过程之前，请确保已阅读 [规划 Teams 自动助理和呼叫队列](plan-auto-attendant-call-queue.md) 并遵循 [入门步骤](plan-auto-attendant-call-queue.md#getting-started) 。

自动助理可以根据呼叫者的输入将呼叫重定向到以下目标之一：

- **Operator** - 为自动助理定义的运算符。 定义运算符是可选的。 运算符可以定义为此列表中的任何其他目标。
- **组织中的人员** - 组织中可以接听语音呼叫的人员。 此人可以是联机用户，也可以是使用 Skype for Business Server 在本地托管的用户。
- **语音应用** - 另一个自动助理或呼叫队列。  (选择此 destination 时，选择与自动助理或呼叫队列关联的资源帐户。) 
- **Voicemail** - 与指定的 Microsoft 365 组关联的语音邮箱。 可以选择是否需要语音邮件听录和“请在音调后留言”。 系统提示。
  - 在 Microsoft 365 管理 中心，为指定的 Microsoft 365 组启用“让组织外部的人员向此团队发送电子邮件”
- **外部电话号码** - 任何电话号码。 请参阅 [外部传输技术详细信息](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details)。
- **公告 (音频文件)** - 播放音频文件。 上传的录制公告消息，在 中保存为音频。WAV、.MP3 或 。WMA 格式。 录制不能大于 5 MB。 系统播放公告，然后返回到自动助理菜单。
- **通知 (键入)** - 键入消息。 希望系统读取的文本。 最多可以输入 1000 个字符。 系统播放公告，然后返回到自动助理菜单。

> [!NOTE]
> 将呼叫重定向到 **组织中的人员** 时，该人员必须启用语音。 有关启用语音的详细信息，请参阅 [向用户分配 Teams 加载项许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
>
> 虽然定义 **运算符** 是可选的，但建议这样做。 如果自动助理配置中由于删除用户或共享语音邮件帐户而出现错误，则自动助理会将呼叫重定向到操作员。 如果未定义操作员，则自动助理将放弃呼叫。

## <a name="whats-new-for-auto-attendants-in-the-past-six-months"></a>过去六个月自动助理的新增功能

- 9 月 - **强制侦听** 选项现在可用于通话流、下班后的呼叫流和假日期间的呼叫流播放 **菜单选项** 。
- 8 月 - 通话流中的 **“播放”菜单选项** 、下班后的呼叫流和假日期间的呼叫流现在支持 \* (星号) 和 \# (磅) 键。

## <a name="steps-to-create-an-auto-attendant"></a>创建自动助理的步骤
添加自动助理的步骤包括：

1. 设置常规信息。
1. 设置基本调用流。
1. 设置下班后呼叫流。
1. 设置假日呼叫流。
1. 设置拨号范围。
1. 设置资源帐户。

使用 Teams 管理中心创建自动助理一文中所述的步骤。 有关 **使用 PowerShell 创建自动助理** 的说明，请参阅 [使用 PowerShell cmdlet 创建自动助理](create-a-phone-system-auto-attendant-via-cmdlets.md)。

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>按照以下步骤设置自动助理

# <a name="step-1-general-info"></a>[步骤 1：常规信息](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>步骤 1：设置自动助理的常规信息

若要设置自动助理，请在 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)中展开“ **语音**”，选择“ **自动助理**”，然后选择“ **添加**”。

1. 在顶部的框中键入自动助理的名称。

2. 若要指定操作员，请指定对运算符的调用的目标。 此指定是可选的，但建议使用。 设置 **“操作员”** 选项以允许呼叫者突破菜单，与指定人员交谈。

3. 指定此自动助理的时区。 如果 [为下班后创建单独的呼叫流](?tabs=after-hours)，则时区用于计算营业时间。

4. 为此自动助理指定 [支持的语言](create-a-phone-system-auto-attendant-languages.md) 。 此语言将用于系统生成的语音提示。

5. 选择是否要启用语音输入。 启用后，每个菜单选项的名称将成为语音识别关键字。 例如，调用方可以说出“One”来选择映射到键 1 的菜单选项，也可以说出“Sales”来选择名为“Sales”的菜单选项。

   > [!NOTE]
   > 如果在步骤 4 中选择不支持语音输入的语言，则会禁用此选项。

设置自动助理的常规信息后，选择“ **下一步**”。

# <a name="step-2-basic-call-flow"></a>[步骤 2：基本呼叫流](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>步骤 2：设置基本调用流

### <a name="set-a-greeting"></a>设置问候语

- 如果选择“ **播放音频文件** ”，则可以使用 **“上传文件** ”按钮上传在 中保存为音频的录制问候消息。WAV、.MP3 或 。WMA 格式。 录制不能大于 5 MB。

- 如果选择“ **键入问候消息** ”，则系统将在自动助理接听呼叫时) 读取键入的文本， (最多 1000 个字符。

### <a name="route-the-call"></a>路由呼叫

- 如果选择“ **断开连接**”，则自动助理将挂起呼叫。
- 如果选择“ **重定向呼叫**”，则可以选择呼叫路由目标之一。
- 如果选择“**播放”菜单选项**，可以选择“**播放音频文件****”或“键入问候消息**”，然后在菜单选项和目录搜索之间进行选择。

#### <a name="play-menu-options"></a>播放菜单选项

*新建 - 可以启用强制侦听选项，该选项要求调用方在进行选择之前侦听所有菜单选项。*
*新增 - \* (星号) 和 \# (磅) 键现在可以在菜单选项中使用*。

对于拨号选项，请将电话键盘上的 0-9 键分配给呼叫路由目标之一。  (星号) 和\# (磅) 的密钥\*由系统保留，无法重新分配。 按任一键将重复当前菜单。

> [!NOTE]
> # 键仅备份到最新的自动助理。 将边界越过到新的自动助理后，#键将无法将你带到上一个。

键映射不必是连续的。 可以创建一个菜单，其中键 0、1 和 3 映射到选项，而不使用数字 2 键。

如果已配置零键，建议将零键映射到运算符。 如果运算符未设置为任何键，则语音命令“Operator”也会被禁用。

对于每个菜单选项，请指定以下设置：

- **拨号键** - 用于访问此选项的电话键盘上的键。 如果语音输入可用，呼叫者也可以说出此号码来访问选项。

- **语音命令** - 定义呼叫者在启用语音输入时可以访问此选项的语音命令。 它可以包含多个字词，例如“客户服务”或“运营和场地”。 例如，调用方可以按 2、说“两个”或说“销售”来选择映射到这两个键的选项。 对于服务确认提示，此文本还会通过文本转语音呈现，这可能类似于“将呼叫转接到销售人员”。

- **重定向到** - 呼叫者选择此选项时使用的呼叫路由目标。 如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。

##### <a name="directory-search"></a>目录搜索

如果将拨号键分配给目标，建议选择 **“无****”进行目录搜索**。 在执行目录搜索之前，将匹配拨号键。 如果调用方开始使用分配给特定目标的拨号键输入名称或分机，则会在完成输入名称或分机之前将其路由到该目标。 建议为目录搜索创建单独的自动助理，并使用拨号键将主自动助理链接指向它。

如果未分配拨号键，请选择 **目录搜索** 选项。

**按名称拨号** - 如果启用此选项，呼叫者可以说出用户名或在电话键盘上键入。 任何联机用户或使用 Skype for Business Server 托管在本地的任何用户都是符合条件的用户，可以使用“按名称拨号”找到。

**按分机拨号** - 如果启用此选项，呼叫者可以通过拨打电话分机来与组织中的用户进行连接。 任何联机用户或使用 Skype for Business Server 托管在本地的任何用户都是符合条件的用户，并且可以通过 **按分机拨号** 找到。  (可以在 [“拨号范围](?tabs=dial-scope) ”页上设置目录中包括和未包含的人员。) 

> [!NOTE]
> 如果想要同时使用 **“按名称拨号”** 和“ **按分机拨号”** 功能，可以在主自动助理上分配一个拨号键，以便访问启用了“ **按名称拨号**”的自动助理。 在该自动助理中，可以分配 1 个键 (，其中没有与之关联的字母) 来访问 **按分机拨号** 自动助理。

有关详细信息，请参阅 [拨号和语音参考](dial-voice-reference.md)。

设置基本呼叫流选项后，选择“ **下一步**”。

# <a name="step-3-after-hours-call-flow"></a>[步骤 3：下班后呼叫流](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>步骤 3：为下班后的呼叫流设置 (可选) 

可以为每个自动助理设置营业时间。

- 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。
- 营业时间可以设置为白天的休息时间，所有未设置为营业时间的营业时间都被视为下班后。
- 可以为下班后设置不同的来电处理选项和问候语。

根据配置自动助理和呼叫队列的方式，可能只需为具有直接电话号码的自动助理指定下班后呼叫路由。

如果希望为下班后呼叫者单独路由呼叫，请指定每天的营业时间。

1. 在表中的工作日旁边，调整“ **开始时间** ”和“ **结束** 时间”。
1. 如果需要，请选择“ **添加新时间** ”，为给定的一天指定多个小时集，例如，指定午休时间。
1. 选择下班后的呼叫路由选项。 下班后也提供相同的常规呼叫流选项。

添加下班后呼叫流后，选择“ **下一步**”。

# <a name="step-4-holiday-call-flow"></a>[步骤 4：假日呼叫流](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>步骤 4：为假日设置呼叫流 (可选) 

自动助理可以为 [你设置的每个假日](set-up-holidays-in-teams.md)提供呼叫流。 最多可以向每个自动助理添加 20 个假日集。 每个假日集最多可以包含 10 个唯一日期范围。 在添加到自动助理的所有假日集中，假日日期必须是唯一的。

*新建 - 可以启用强制侦听选项，该选项要求调用方在进行选择之前侦听所有菜单选项。*
*新 - \* (星号) 和 \# (磅) 键现在可以在菜单选项中使用。*
*新增 - **“播放”菜单选项** 现已在假日呼叫流中提供。*

1. 在“假日呼叫设置”页上，选择“ **添加**”。

1. 为此假日设置键入名称。

1. 从“ **假日** ”下拉列表中，选择要使用的假日。

1. 选择要使用的问候语类型。

1. 选择是要 **断开连接** 还是 **重定向** 呼叫。

    1. 如果选择重定向，请选择呼叫的呼叫路由目标。
    1. 如果选择播放菜单选项，请配置 **“播放”菜单选项**。

1. 选择“**保存**”。

根据需要对每个额外的假日重复此过程。

添加所有假期时间后，选择“ **下一步**”。

# <a name="step-5-dial-scope"></a>[步骤 5：拨号范围](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>步骤 5：设置拨号范围 (可选) 

当调用方使用按名称拨号或按分机拨号时， *拨号范围* 定义目录中可用的用户。 默认的 **“所有联机用户**”包括组织中所有使用 Skype for Business Server 的联机用户或托管在本地的用户。

可以通过选择“**包括**”或“排除”下的 **“自定义用户组**”并选择一个或多个 Microsoft 365 组、通讯组列表或安全组来包括或 **排除** 特定用户。 例如，你可能希望从拨号目录中排除组织中的高管。

如果用户同时位于这两个列表中，则会将其从目录中排除。

> [!NOTE]
> 新用户可能需要长达 36 小时才能在目录中列出其名称。

选择 **“拨号范围** ”选项后，选择“ **下一步**”。

# <a name="step-6-resource-accounts"></a>[步骤 6：资源帐户](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>步骤 6： (可选) 设置资源帐户

所有自动助理都必须具有关联的资源帐户。  第一级自动助理至少需要一个具有关联服务编号的资源帐户。 如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。

若要添加资源帐户，请选择“ **添加帐户** ”并搜索要添加的帐户。 选择 **“添加**”，然后选择“ **添加**”。

添加资源帐户后，选择“ **下一步**”。

有关详细信息，请参阅 [管理 Teams 资源帐户](manage-resource-accounts.md)。

---

## <a name="resources-for-complex-scenarios"></a>复杂方案的资源

### <a name="external-phone-number-transfers---technical-details"></a>外部电话号码转移 - 技术详细信息

请参阅 [先决条件](plan-auto-attendant-call-queue.md#prerequisites) ，以便允许自动助理在外部转移呼叫。  另外

- 对于具有 [通话套餐许可证](calling-plans-for-office-365.md) 或 [运营商连接](operator-connect-plan.md) 号码的资源帐户，外部转接电话号码必须以 E.164 格式输入， (+[国家/地区代码][区号][电话号码]) 。

- 对于具有Microsoft Teams 电话许可证和直接路由联机语音路由策略的资源帐户，外部传输电话号码格式取决于[会话边界控制器 (SBC) ](direct-routing-connect-the-sbc.md)设置。

显示的出站电话号码按如下所示确定：

- 对于通话套餐和运营商连接号码，将显示原始呼叫者的电话号码。
- 对于直接路由号码，发送的数字基于 SBC 上的 P-Asserted-Identity (PAI) 设置，如下所示：
  - 如果设置为“禁用”，则显示原始呼叫者的电话号码。 “禁用”是默认设置和建议的设置。
  - 如果设置为“已启用”，则显示资源帐户电话号码。

在Skype for Business混合环境中，若要将自动助理呼叫转移到 PSTN，请创建一个新的本地用户，并将呼叫转接设置为 PSTN 号码。 必须为用户启用企业语音并分配有语音策略。 若要了解详细信息，请参阅 [自动助理呼叫转接到 PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

### <a name="auto-attendant-diagnostic-tool"></a>自动助理诊断工具

如果你是管理员，则可以使用以下诊断工具来验证自动助理是否能够接听呼叫：

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。

   > [!div class="nextstepaction"]
   > [运行测试：Teams 自动助理](https://aka.ms/TeamsAADiag)

2. 在“运行诊断”窗格中，在 **“用户名”或“Email**”字段中输入“资源帐户”，然后选择“**运行测试**”。

3. 这些测试将识别阻止自动助理接听呼叫的租户、策略或资源帐户配置，并提供解决所发现问题的步骤。

### <a name="related-articles"></a>相关文章

[以下是使用 Teams Phone 获得的功能](./here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](./getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
