---
title: 在 Microsoft Teams 中创建呼叫队列
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: 了解如何在 Microsoft Teams 中设置呼叫队列。 呼叫队列提供问候消息、保留音乐、呼叫重定向和其他功能。
ms.openlocfilehash: 84dd975e93340f6b5985e8239e7bf78f051debbc
ms.sourcegitcommit: e5f5a1a164576b317e89340e233c9b67f082d19c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2022
ms.locfileid: "68890071"
---
# <a name="create-a-call-queue"></a>创建呼叫队列

呼叫队列将呼叫者路由到组织中可以帮助解决特定问题的人员。 呼叫一次分发给队列中的人员，他们称为 *代理*。

呼叫队列提供：

- 问候消息。
- 当人们在队列中等待时播放音乐。
- 呼叫路由 - 先入 *先出* (FIFO) 顺序 - 到代理。
- 队列溢出和超时的处理选项。

在按照本文中的过程操作之前，请确保已阅读 [规划 Teams 自动助理和呼叫队列](plan-auto-attendant-call-queue.md) 并遵循 [入门步骤](plan-auto-attendant-call-queue.md#getting-started)。

## <a name="whats-new-for-call-queues-in-the-past-six-months"></a>过去六个月通话队列的新增功能

- 八月
  - **添加问候语消息** (文本转语音 (TTS) ) 现在支持呼叫队列主问候语。
  - 路由到共享语音邮件时，跳过 **语音邮件系统邮件** 控件现在公开，这也适用于 **添加问候消息** 提示。

## <a name="steps-to-create-a-call-queue"></a>创建呼叫队列的步骤

设置呼叫队列的步骤包括：

1. 设置常规信息
1. 设置问候语和音乐
1. 设置呼叫应答
1. 选择和分配代理
1. 设置调用溢出处理
1. 设置呼叫超时处理

使用 Teams 管理中心创建呼叫队列一文中所述的步骤。 有关使用 PowerShell 创建呼叫队列的说明，请参阅 [使用 PowerShell cmdlet 创建呼叫队列](create-a-phone-system-call-queue-via-cmdlets.md)。

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>按照以下步骤设置呼叫队列

# <a name="step-1-general-info"></a>[步骤 1：常规信息](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>步骤 1：设置常规信息

若要设置呼叫队列，请在 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)中展开“ **语音**”，选择“ **呼叫队列**”，然后选择“ **添加**”。

在顶部的框中键入呼叫队列的名称。

### <a name="add-a-resource-account"></a>添加资源帐户

添加现有资源帐户：

1. 在“ **资源帐户**”下，单击“ **添加** ”按钮，为此调用队列添加资源帐户。
1. 在“ **添加帐户** ”窗格中，搜索要添加的资源帐户。
1. 选择要分配给此调用队列的资源帐户旁边的“ **添加** ”按钮。
1. 在窗格底部，选择“ **添加** ”按钮。

如果需要创建资源帐户：

1. 在“ **资源帐户**”下，单击“ **添加** ”按钮，为此调用队列添加资源帐户。
1. 在“ **添加帐户** ”窗格中，搜索任意一组字母以拉取结果下拉列表。
1. 选择结果底部的“ **+ 添加资源帐户** ”按钮。
1. 在 **“添加资源帐户** ”窗格中：
    1. 键入对代理可见的描述性 **显示名称**。
    1. 键入资源帐户的描述性 **用户名** 。
    1. 选择“ **资源帐户类型** ”下拉列表，然后选择“ **呼叫队列**”。
1. 在窗格底部，选择“ **保存”** 按钮。
1. 在“ **资源帐户** ”窗格中，选择“ **添加** ”按钮。

代理在收到来电时将看到资源帐户名称。

有关详细信息，请参阅 [管理 Teams 资源帐户](manage-resource-accounts.md)。

### <a name="assign-a-calling-id-optional"></a>分配呼叫 ID (可选) 

**适用于 Teams 频道/协作通话桌面用户和具有标准呼叫队列的 Teams 移动客户端用户。**

可以通过使用电话号码指定一个或多个资源帐户，为代理分配出站呼叫方 ID 号码。 代理可以选择用于每个出站呼叫的出站呼叫方 ID 号。 在呼叫应用中，代理可以使用其呼叫队列 (CQ) /自动助理 (AA) 号码或他们自己的个人直接向内拨号 (DID) 。

> [!NOTE]
> 用于调用 ID 的资源帐户必须具有 **Microsoft Teams 电话资源帐户** 许可证，并且分配有以下其中一项：
>
> - 通话套餐许可证和分配的电话号码
> - 分配的操作员连接电话号码
> - 使用直接路由时，在线语音路由策略 (电话号码分配是可选的) 

1. 在 **“分配呼叫 ID**”下，选择“ **添加** ”按钮。
1. 在“ **添加帐户** ”窗格中，搜索要允许代理用于出站呼叫方 ID 目的的资源帐户 () 。
1. 选择分配有电话号码的资源帐户旁边的 **“添加** ”按钮。
1. 选择窗格底部的“ **添加** ”按钮。

如果没有分配了电话号码的资源帐户：

1. 在 **“资源帐户**”下，单击“ **添加** ”按钮添加资源帐户。
1. 在“ **添加帐户** ”窗格中，搜索任意一组字母以拉取结果下拉列表。
1. 选择结果底部的“ **+ 添加资源帐户** ”按钮。
1. 在 **“添加资源帐户** ”窗格中：
    1. 键入对呼叫收件人可见的描述性 **显示名称**。
    1. 键入资源帐户的描述性 **用户名** 。
    1. 选择“ **资源帐户类型** ”下拉列表，然后选择“ **呼叫队列**”。
1. 在窗格底部，选择“ **保存”** 按钮。
1. 在“ **资源帐户** ”窗格中，选择“ **添加** ”按钮。

创建用于呼叫 ID 的新资源帐户后，仍需要：

- 分配 [Teams 电话资源帐户许可证](manage-resource-accounts.md#assign-a-license)
- 分配 Microsoft 通话套餐许可证、分配 Operator Connect 电话号码或为直接路由分配在线语音路由策略
- 如果你使用的是 Microsoft 通话套餐，[请将服务电话号码分配给资源帐户](manage-resource-accounts.md#assign-a-service-number)

### <a name="set-the-call-queue-language"></a>设置呼叫队列语言

选择 [支持的语言](create-a-phone-system-call-queue-languages.md)。

此语言将用于系统生成的语音提示和语音邮件听录（如果启用）。

选择语言后，选择 **“添加呼叫队列**”页底部的“**下一步**”按钮。

# <a name="step-2-greeting-and-music"></a>[步骤 2：问候语和音乐](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>步骤 2：添加问候语和保留音乐

*新建 - 现在支持呼叫队列主 **问候语** (文本转语音 (TTS) ) 添加问候语消息。*

指定是否要在呼叫者到达队列时向他们发出 *问候* 语。

- 如果选择“ **播放音频文件**”，则必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。 上传的录制不能超过 5 MB。

- 如果选择“ **键入问候消息**”，系统将在呼叫队列接听呼叫时) 读取您键入的文本 (最多 1000 个字符。

Teams 在 *呼叫者处于保留状态* 时为呼叫者提供默认音乐。

- Teams 呼叫队列中提供的默认音乐无需支付组织支付的任何版税。
- 如果要播放特定的音频文件，请选择“ **播放音频文件** ”并上传 MP3、WAV 或 WMA 文件。

> [!NOTE]
> 你负责独立清除和保护与 Microsoft Teams 服务一起使用任何音乐或音频文件的一切必要权利和权限，其中可能包括来自所有相关权利持有者（可能包括艺术家）的任何音乐、音效、音频、品牌、名称和其他内容的知识产权和其他权利， 演员、表演者、音乐家、词曲作者、作曲家、唱片公司、音乐出版商、工会、公会、权利协会、集体管理组织以及拥有、控制或许可音乐版权、音效、音频和其他知识产权的任何其他方。

选择问候语和保持音乐后，选择 **“添加呼叫队列**”页面底部的“**下一步**”按钮。

# <a name="step-3-call-answering"></a>[步骤 3：呼叫应答](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>步骤 3：设置谁将接听来电

查看将 [代理添加到呼叫队列的先决条件](plan-auto-attendant-call-queue.md#prerequisites)。

### <a name="teams-channel"></a>Teams 频道

最多可以通过 Teams 频道添加 200 个代理。 你必须是团队成员或频道的创建者或所有者，才能将频道添加到队列。

如果要 [使用 Teams 通道来管理队列](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)：

1. 选择 **“选择团队** ”单选按钮，然后选择“ **添加频道**”。
1. 搜索要使用的团队，将其选中，然后选择“ **添加**”。
1. 选择要使用的通道， (仅支持标准通道) 并选择“ **应用**”。

将 Teams 通道用于呼叫队列时，支持以下客户端：

- Microsoft Teams Windows 客户端
- Microsoft Teams Mac 客户端

> [!NOTE]
> 如果使用此选项，则呼叫队列可能需要长达 24 小时才能完全正常运行。
>
> 如果团队中有 200 多个成员，则只有前 200 名成员（按字母顺序）将作为代理添加到呼叫队列。

### <a name="users-and-groups"></a>用户和组

最多可以单独添加 20 个代理，通过组最多可以添加 200 个代理。

如果要将单个用户或组添加到队列：

1. 选择“ **选择用户和组** ”单选按钮。

将 **用户添加到** 队列：

1. 选择“ **添加用户**”，搜索用户，单击“ **添加**”，然后单击“ **添加**”。

若要 **向队列添加组** ，请执行以下操作：

1. 选择“ **添加组**”，搜索该组，单击“ **添加**”，然后单击“ **添加**”。 
    1. 可以使用通讯组列表、安全组和 Microsoft 365 组或 Microsoft Teams 团队。

> [!NOTE]
> 添加到组的新用户可能需要长达 8 小时才能到达第一个呼叫。
>
> 如果组中有 200 多个成员，则只会将前 200 个成员（按字母顺序）作为代理添加到呼叫队列。

### <a name="conference-mode"></a>会议模式

**会议模式** 减少了在代理接受呼叫后呼叫方连接到代理所需的时间。 若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：

- 最新版本的 Microsoft Teams 桌面客户端、Android 应用或 iOS 应用
- Microsoft Teams 电话版本 1449/1.0.94.2020051601 或更高版本
  
代理的 Teams 帐户必须设置为 TeamsOnly 模式。 不符合要求的代理不包括在呼叫路由列表中。 如果代理使用兼容的客户端，我们建议为呼叫队列启用会议模式。

> [!TIP]
> 建议将 **“会议模式** ”设置为“ **打开** ”。

> [!NOTE]
> 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
>
> 如果电话呼叫从Skype for Business Server路由到队列，则不支持会议模式。
> 
> 如果 Teams 用户需要使用呼叫队列进行咨询/转接呼叫，则需要会议模式。
>
> 首次加入呼叫时，代理可能会在队列中听到配置的保持音乐长达 2 秒。
> 
> 如果在代理上启用了 [合规性录制](teams-recording-policy.md) ，则不支持会议模式和助理路由的组合。 如果需要使用会议模式，请选择“ **串行路由**”、“ **轮循机制**”或“ **最长空闲** 时间”作为 **路由方法**。 如果需要使用助理路由，请将“会议模式”设置为 **“关闭**”。

选择呼叫应答选项后，选择 **“添加呼叫队列**”页面底部的“**下一步**”按钮。

# <a name="step-4-agent-selection"></a>[步骤 4：代理选择](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>步骤 4：选择代理路由选项

**路由方法** 确定代理接收来自队列的调用的顺序。

从以下选项中进行选择：

- **助理路由** 同时对队列中的所有代理进行响铃。 接听呼叫的第一个呼叫代理将接收呼叫。

- **串行路由** 按呼叫代理列表中指定的顺序逐个地为所有 **呼叫代理拨打电话** 。 如果代理关闭或未接听呼叫，呼叫将拨打下一个代理。 此操作将重复，直到接听呼叫或超时。

- **轮循机制** 平衡传入呼叫的路由，以便每个呼叫代理从队列获取相同数量的呼叫。 在入站销售环境中，可能需要使用此路由方法，以确保所有呼叫代理之间的机会均等。

- **最长空闲** 时间路由对空闲时间最长的代理的每次调用。 如果代理的状态为“可用”，则将其视为空闲。 状态为“不可用”的代理在将状态更改为“可用”之前，没有资格接听呼叫。

> [!TIP]
> 建议将 **路由方法** 设置为 **轮循机制** 或 **最长空闲** 时间。

> [!NOTE]
> 如果在代理上启用了 [合规性录制](teams-recording-policy.md) ，则不支持 **会议模式** 和 **助理路由** 的组合。 如果需要使用 **会议模式**，请选择“ **串行路由**”、“ **轮循机制**”或“ **最长空闲** 时间”作为 **路由方法**。 如果需要使用 **助理路由**，请将 **“会议模式** ”设置为 **“关闭**”。
>
> 使用 **最长空闲** 时间且队列中的调用数少于可用代理时，只有前两个最长空闲代理会显示来自队列的调用。
>
> 使用 **最长空闲** 时间时，代理可能在变得不可用后不久收到来自队列的呼叫，或者在变得可用后接收来自队列的呼叫有短暂延迟。
>
> 向代理呈现的呼叫队列呼叫可能与基于位置的路由限制冲突。 在这种情况下，代理将接收呼叫 Toast，但无法应答呼叫。 这种情况将继续存在，直到另一个代理可以应答呼叫、调用方挂起或出现呼叫队列超时条件。  

### <a name="presence-based-call-routing"></a>基于状态的呼叫路由

**基于状态的呼叫路由** 使用呼叫代理的可用性状态来确定是否应将代理包含在所选路由方法的呼叫路由列表中。

可用性状态设置为“ **可用”** 的呼叫代理包含在呼叫路由列表中，可以接收呼叫。 其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在其可用性状态更改为“ **可用**”之前不会接听呼叫。

可以使用任何路由方法启用 **基于状态的呼叫** 路由。

如果代理选择不接听呼叫，则无论其可用性状态设置为什么，它们都不会包含在呼叫路由列表中。

> [!TIP]
> 建议将 **基于状态的路由** 设置为 **“打开** ”。

> [!NOTE]
> 选择 **“最长空闲** 时间”作为路由方法时，需要基于状态的路由并自动启用，即使“基于状态的路由”开关将为 **“关闭** ”并灰显。
>
> 如果未启用基于状态的路由，并且队列中有多个调用，则系统将同时向代理显示这些调用，而不管代理的状态如何。 此操作将导致向代理发出多个呼叫通知，尤其是当某些代理未接听提供给代理的初始呼叫时。
>
> 使用 **基于状态的路由** 时，代理可能会在变得不可用后不久收到来自队列的呼叫，或者在变得可用后接收来自队列的呼叫有短暂延迟。
>
> 启用基于状态的路由后，使用 Skype for Business 客户端的代理不会包含在呼叫路由列表中。 如果你有使用 Skype for Business 的代理，请不要启用基于状态的呼叫路由。

### <a name="call-agents-can-opt-out-of-taking-calls"></a>呼叫代理可以选择不接听电话

可以指定呼叫代理是否能够选择不接听呼叫。

建议启用 **呼叫代理可以选择不接听电话**。

### <a name="agent-alert-time"></a>代理警报时间

**代理警报时间** 指定在队列将呼叫重定向到下一个代理之前代理的电话将响铃的时间。

> [!TIP]
> 建议将 **代理警报时间** 设置为至少 **20 秒** 。

选择代理呼叫路由选项后，选择 **“添加呼叫队列**”页面底部的“**下一步**”按钮。

# <a name="step-5-call-overflow"></a>[步骤 5：调用溢出](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>步骤 5：设置如何处理调用溢出

**队列中的最大调用** 数指定在任何给定时间可以在队列中等待的最大调用数。

默认值为 50，但范围为 0 到 200。

达到此限制时，将按照“ **达到最大调用数** ”设置指定的处理调用。

可以选择 **断开呼叫连接** ，或 **将其重定向** 到任何呼叫路由目标。

例如，你可能让呼叫者为队列中的代理留下语音邮件。

*新建 - 路由到共享 **语音邮件时，跳过语音邮件系统邮件** 控件现在公开，这也适用于 **添加问候消息** 提示。*

有关外部转移，请参阅 [先决条件](./plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码转移 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 。

> [!NOTE]
> 如果最大呼叫数设置为 0，则不会播放问候消息。
>  
> 语音邮件 (个人) 将向用户发送呼叫，而不是按指示直接发送到其语音邮件。 支持部门正在对此进行调查。

选择呼叫溢出处理选项后，选择 **“添加呼叫队列**”页底部的“**下一步**”按钮。

# <a name="step-6-call-timeout"></a>[步骤 6：呼叫超时](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>步骤 6：设置如何处理呼叫超时

**呼叫超时：最长等待时间** 指定呼叫在重定向或断开连接之前可在队列中保持的最长时间。

可以指定一个介于 0 秒到 45 分钟之间的值。

可以选择 **断开呼叫连接** ，或 **将其重定向** 到呼叫路由目标之一。

例如，你可能让呼叫者为队列中的代理留下语音邮件。

*新建 - 路由到共享 **语音邮件时，跳过语音邮件系统邮件** 控件现在公开，这也适用于 **添加问候消息** 提示。*

有关外部转移，请参阅 [先决条件](./plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码转移 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 。

> [!NOTE]
> 语音邮件 (个人) 将向用户发送呼叫，而不是按指示直接发送到其语音邮件。 支持部门正在对此进行调查。

选择呼叫超时处理选项后，选择 **“添加呼叫队列**”页面底部的“**提交**”按钮。

---

## <a name="resources-for-complex-scenarios"></a>复杂方案的资源

### <a name="summary-of-recommended-call-queue-settings"></a>建议的呼叫队列设置摘要

建议使用以下设置：

- **会议模式** 为 **“开”**
- 轮 **循机制** 或 **最长空闲** 的 **路由方法**
- **基于状态的路由** 到 **“打开”**
- **代理警报时间：** 至少 **20 秒**

### <a name="call-queue-feature-compatibility"></a>呼叫队列功能兼容性

|功能                          |Teams 桌面<sup>版 1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype for Business |IP 电话 | 标准呼叫队列 |基于通道的呼叫队列 | 注释 |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**代理路由方法**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*Default*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y         |Y               |N    |Y         |Y                     |Y                         |*建议* |
|`Round Robin`                    |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*建议* |
|`Serial`                         |Y                         |Y         |Y               |Y    |Y         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**代理路由选项**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|Y                      |Y         |Y               |N    |Y         |Y                     |Y                         |*Default* |
|`Agents can Opt-out`<sup>10</sup> |Y                       |Y         |Y               |Y<sup>7</sup>|Y<sup>7</sup>|Y          |Y                         |*Default*     |
|**传输模式**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |Y                         |Y         |Y               |N    |Y<sup>6</sup>|Y                  |Y                         |*Default* |
|`Transfer Mode`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|**协作通话**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |Y                       |N         |否               |否    |否         |n/a                   |Y<sup>8</sup>             |   |
|**动态呼叫者 ID**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |Y                         |Y         |Y               |N    |否         |是                     |n/a                       |   |
|`Channel based call queue`       |Y                         |n/a       |n/a             |n/a  |n/a       |n/a                   |Y                         |   |
|**PSTN 连接方法**    |                          |          |                |     |          |                      |                          |请参阅注释 9   |
|`Calling Plans`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|`Direct Routing`                 |Y                         |Y         |Y               |N    |是         |Y<sup>6</sup>         |Y                         |   |
|`Operator Connect`               |Y                         |Y         |Y               |     |Y         |Y<sup>6</sup>         |Y                         |   |
|**杂项**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |Y                 |N         |Y               |Y    |          |Y                     |Y                         |              |

#### <a name="notes"></a>注释

1. Microsoft Teams Windows 客户端、Microsoft Teams Mac 客户端、虚拟化桌面基础结构上的 Microsoft Teams。
2. Microsoft Teams iPhone 应用、Microsoft Teams Android 应用。
3. 为代理路由方法选择“最长空闲时间”将自动启用基于状态的路由。
4. 无法设置调用代理的顺序。
5. 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
6. 仅限Microsoft Teams 电话。
7. 通过 位于 [https://aka.ms/vmsettings](https://aka.ms/vmsettings)的“用户设置门户”页。
8. 仅支持公共频道。
9. 自动助理和呼叫队列无法在 PSTN 连接方法之间转移呼叫。
10. 对于 GCCH/DOD，只能通过以下位置的用户设置门户使用：
- GCCH： [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)
- 国防部： [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)

### <a name="supported-clients"></a>支持的客户端

呼叫队列中的呼叫代理支持以下客户端：

- Skype for Business桌面客户端 2016 (32 位和 64 位版本) 
- Lync 桌面客户端 2013 (32 位和 64 位版本) 
- Microsoft Teams 支持的所有 IP 电话型号。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
- Mac Skype for Business 客户端（版本 16.8.196 及更高版本）
- Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）
- iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）
- iPad Skype for Business 客户端（版本 6.16.0 及更高版本）
- Microsoft Teams Windows 客户端 (32 位和 64 位版本) 
- Microsoft Teams Mac 客户端
- [虚拟化桌面基础结构](teams-for-vdi.md)上的 Microsoft Teams (Windows 虚拟桌面、Citrix 和 VMware) 
- Microsoft Teams iPhone 应用
- Microsoft Teams Android 应用

  > [!NOTE]
  > 分配有直接路由号码的呼叫队列不支持Skype for Business客户端、Lync 客户端或Skype for Business IP 电话作为代理。 Teams 客户端仅支持 [“仅 Teams 共存”模式](setting-your-coexistence-and-upgrade-settings.md)。

### <a name="call-queue-diagnostic-tool"></a>呼叫队列诊断工具

如果你是管理员，则可以使用以下诊断工具来验证呼叫队列是否能够接收呼叫：

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。

   > [!div class="nextstepaction"]
   > [运行测试：Teams 呼叫队列](https://aka.ms/TeamsCallQueueDiag)

2. 在“运行诊断”窗格中，在 **“用户名”或“Email**”字段中输入“资源帐户”，然后选择“**运行测试**”。

3. 测试将返回处理任何租户、策略和资源帐户配置的最佳后续步骤，以验证呼叫队列是否能够接收呼叫。

### <a name="related-topics"></a>相关主题

[以下是你使用Microsoft Teams 电话](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
