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
description: 了解如何在 Microsoft Teams 中设置呼叫队列。 呼叫队列提供问候消息、保持音乐、呼叫重定向和其他功能。
ms.openlocfilehash: 6fe298a3054165a95f496f8c1178a7fa8457542d
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614225"
---
# <a name="create-a-call-queue"></a>创建呼叫队列

呼叫队列将呼叫者路由到组织中可以帮助处理特定问题或问题的人员。 呼叫一次分发给队列中称为 *代理* 的人员。

呼叫队列提供：

- 问候语。
- 当人们在队列中等待等待时的音乐。
- 调用路由 - *在第一个 In，First Out* (FIFO) 顺序 - 代理。
- 处理队列溢出和超时的选项。

按照本文中的过程操作之前，请确保已阅读 [了 Teams 自动助理计划和呼叫队列](plan-auto-attendant-call-queue.md) ，并遵循 [了入门步骤](plan-auto-attendant-call-queue.md#getting-started)。

## <a name="whats-new-for-call-queues-in-the-past-6-months"></a>过去 6 个月呼叫队列的新增功能

- 八月
  - 现在，呼叫队列主问候语支持将 **问候消息** (文本添加到语音 (TTS) ) 。
  - **跳转语音邮件系统消息** 控件现在在路由到共享语音邮件时公开，这也适用于 **添加问候消息** 提示。

## <a name="steps-to-create-a-call-queue"></a>创建呼叫队列的步骤

设置呼叫队列的步骤包括：

1. 设置常规信息
1. 设置问候语和音乐
1. 设置呼叫应答
1. 选择并分配代理
1. 设置呼叫溢出处理
1. 设置呼叫超时处理

本文中概述的步骤使用 Teams 管理中心创建呼叫队列。 有关使用 PowerShell 创建呼叫队列的说明，请参阅 [使用 PowerShell cmdlet 创建呼叫队列](create-a-phone-system-call-queue-via-cmdlets.md)。

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>按照以下步骤设置呼叫队列

# <a name="step-1-general-info"></a>[步骤 1：常规信息](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>步骤 1：设置常规信息

若要设置呼叫队列，请在 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)展开 **语音**，选择 **呼叫队列**，然后选择 **“添加**”。

在顶部框中键入呼叫队列的名称。

### <a name="add-a-resource-account"></a>添加资源帐户

若要添加现有资源帐户，请执行以下操作：

1. 在 **“资源帐户**”下，单击 **“添加** ”按钮添加此呼叫队列的资源帐户。
1. 在 **“添加帐户** ”窗格中，搜索要添加的资源帐户。
1. 选择要分配给此呼叫队列的资源帐户旁边的 **“添加** ”按钮。
1. 在窗格底部，选择 **“添加** ”按钮。

如果需要创建资源帐户：

1. 在 **“资源帐户**”下，单击 **“添加** ”按钮添加此呼叫队列的资源帐户。
1. 在 **“添加帐户** ”窗格中，搜索任意一组字母以拉取结果下拉列表。
1. 选择结果底部的 **“+ 添加资源帐户** ”按钮。
1. 在 **“添加资源帐户** ”窗格上：
    1. 键入描述性 **显示名称**，该名称对代理可见。
    1. 键入资源帐户的描述性 **用户名** 。
    1. 选择 **“资源帐户”类型** 下拉列表，然后选择 **“呼叫队列**”。
1. 在窗格底部，选择“ **保存** ”按钮。
1. 在 **“资源帐户** ”窗格上，选择 **“添加** ”按钮。

代理在收到传入呼叫时将看到资源帐户名称。

有关详细信息，请参阅 [“管理 Teams 资源帐户](manage-resource-accounts.md)”。

### <a name="assign-a-calling-id-optional"></a> (可选) 分配呼叫 ID

**适用于 Teams 频道/协作呼叫桌面用户和具有标准呼叫队列的 Teams 移动客户端用户。**

可以通过指定一个或多个具有电话号码的资源帐户为代理分配出站呼叫者 ID 号码。 代理可以选择要用于每个出站呼叫的出站调用者 ID 号。 在呼叫应用中，代理可以使用其呼叫队列 (CQ) /自动助理 (AA) 号码或其自己的个人直接向内拨号 (DID) 。

> [!NOTE]
> 用于调用 ID 目的的资源帐户必须具有 **Microsoft Teams 电话资源帐户** 许可证，并分配了下列选项之一：
>
> - 呼叫计划许可证和分配的电话号码
> - 分配的运算符连接电话号码
> - 使用直接路由) 时，在线语音路由策略 (电话号码分配是可选的

1. 在 **“分配呼叫 ID**”下，选择 **“添加** ”按钮。
1. 在 **“添加帐户** ”窗格中，搜索要允许代理用于出站调用方 ID 的资源帐户 () 。
1. 选择分配有电话号码的资源帐户旁边的 **“添加** ”按钮。
1. 选择窗格底部的 **“添加** ”按钮。

如果没有分配有电话号码的资源帐户：

1. 在 **“资源帐户**”下，单击 **“添加** ”按钮添加资源帐户。
1. 在 **“添加帐户** ”窗格中，搜索任意一组字母以拉取结果下拉列表。
1. 选择结果底部的 **“+ 添加资源帐户** ”按钮。
1. 在 **“添加资源帐户** ”窗格上：
    1. 键入描述性 **显示名称**，该名称对呼叫收件人可见。
    1. 键入资源帐户的描述性 **用户名** 。
    1. 选择 **“资源帐户”类型** 下拉列表，然后选择 **“呼叫队列**”。
1. 在窗格底部，选择“ **保存** ”按钮。
1. 在 **“资源帐户** ”窗格上，选择 **“添加** ”按钮。

创建此用于调用 ID 的新资源帐户后，仍需要：

- 分配 [Teams 电话资源帐户许可证](manage-resource-accounts.md#assign-a-license)
- 分配 Microsoft 呼叫计划许可证、分配操作员连接电话号码或为直接路由分配联机语音路由策略
- 如果使用的是 Microsoft 呼叫计划[，请将服务电话号码分配到资源帐户](manage-resource-accounts.md#assign-a-service-number)

### <a name="set-the-call-queue-language"></a>设置呼叫队列语言

选择 [支持的语言](create-a-phone-system-call-queue-languages.md)。

如果启用，此语言将用于系统生成的语音提示和语音邮件听录。

选择语言后，选择 **“添加呼叫队列**”页底部的 **“下** 一步”按钮。

# <a name="step-2-greeting-and-music"></a>[步骤 2：问候语和音乐](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>步骤 2：添加问候语和保持音乐

*新建 - 现在支持将 **问候消息** (文本添加到语音 (TTS) ) ，以供呼叫队列主问候。*

指定在呼叫者到达队列时是否要向他们打 *招呼* 。

- 如果选择 **“播放音频文件**”，则必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。 上传的录制不得大于 5 MB。

- 如果选择 **“键入问候消息**”，系统会在呼叫队列接听呼叫时读取 (最多 1000 个字符) 键入的文本。

当呼叫者在 *队列中处于暂停* 状态时，Teams 会为调用方提供默认音乐。

- Teams 呼叫队列中提供的默认音乐不收取组织支付的任何版税。
- 如果要播放特定的音频文件，请选择 **“播放音频文件** ”并上传 MP3、WAV 或 WMA 文件。

> [!NOTE]
> 你负责独立清除和保护将任何音乐或音频文件与 Microsoft Teams 服务结合使用的所有必要权利和权限，这些权利和权限可能包括任何音乐、声音效果、音频、品牌、名称以及音频文件中所有相关权利持有者（包括艺术家）中的知识产权和其他权利， 演员、表演者、音乐家、词曲作者、作曲家、唱片公司、音乐出版商、工会、公会、权利协会、集体管理组织以及拥有、控制或许可音乐版权、音效、音频和其他知识产权的任何其他各方。

选择问候语和保持音乐后，选择 **“添加呼叫队列**”页面底部的 **“下一步**”按钮。

# <a name="step-3-call-answering"></a>[步骤 3：呼叫应答](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>步骤 3：设置谁将接听传入呼叫

查看 [将代理添加到呼叫队列的先决条件](plan-auto-attendant-call-queue.md#prerequisites)。

### <a name="teams-channel"></a>Teams 频道

最多可通过 Teams 频道添加 200 个代理。 必须是团队成员或频道的创建者或所有者才能向队列添加通道。

如果要 [使用 Teams 通道来管理队列](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)：

1. 选择 **“选择团队** 单选”按钮，然后选择 **“添加频道**”。
1. 搜索要使用的团队，选择该团队，然后选择 **“添加**”。
1. 选择要使用的通道 (仅支持标准通道) 并选择 **“应用**”。

使用 Teams 通道进行呼叫队列时，支持以下客户端：

- Microsoft Teams Windows 客户端
- Microsoft Teams Mac 客户端

> [!NOTE]
> 如果使用此选项，调用队列可能需要长达 24 小时才能完全正常运行。
>
> 如果团队中有 200 多个成员，则只有前 200 个成员将按字母顺序添加为呼叫队列中的代理。

### <a name="users-and-groups"></a>用户和组

可以通过组单独添加最多 20 个代理，最多可添加 200 个代理。

如果要将单个用户或组添加到队列：

1. 选择 **“选择用户和组** ”单选按钮。

若要将 **用户添加** 到队列，请执行以下操作：

1. 选择 **“添加用户**”，搜索用户，单击 **“添加**”，然后单击 **“添加**”。

若要将 **组添加** 到队列，请执行以下操作：

1. 选择 **“添加组**”，搜索组，单击 **“添加**”，然后单击 **“添加**”。 
    1. 可以使用通讯组列表、安全组和 Microsoft 365 组或 Microsoft Teams 团队。

> [!NOTE]
> 添加到组的新用户可能需要长达 8 小时才能到达其第一个呼叫。
>
> 如果组中有 200 多个成员，则只有前 200 个成员将按字母顺序添加为调用队列中的代理。

### <a name="conference-mode"></a>会议模式

**会议模式** 减少了调用方在代理接受呼叫后连接到代理所需的时间。 若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：

- 最新版本的 Microsoft Teams 桌面客户端、Android 应用或 iOS 应用
- Microsoft Teams 电话版本 1449/1.0.94.2020051601 或更高版本
  
代理的 Teams 帐户必须设置为 TeamsOnly 模式。 不符合要求的代理不包括在呼叫路由列表中。 如果代理使用兼容的客户端，建议为呼叫队列启用会议模式。

> [!TIP]
> 建议设置“将 **会议模式** 设置为 **打开** ”。

> [!NOTE]
> 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
>
> 如果电话呼叫从Skype for Business Server路由到队列，则不支持会议模式。
> 
> 如果 Teams 用户需要使用呼叫队列来咨询/转移呼叫，则需要会议模式。
>
> 首次加入呼叫时，代理可能会在队列中听到已配置的音乐暂停长达 2 秒。


选择呼叫应答选项后，选择 **“添加呼叫队列**”页底部的 **“下一步**”按钮。

# <a name="step-4-agent-selection"></a>[步骤 4：代理选择](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>步骤 4：选择代理路由选项

**路由方法** 确定代理从队列接收呼叫的顺序。

从以下选项中进行选择：

- **助理路由** 同时将队列中的所有代理都响铃。 第一个接听呼叫的呼叫代理获取呼叫。

- **串行路由** 按照呼叫代理列表中指定的顺序逐个调 **用代理** 。 如果代理关闭或未接听呼叫，则调用将拨打下一个代理。 这会重复，直到接听呼叫或超时。

- **轮循机制** 平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。 在入站销售环境中，可能需要使用此路由方法来保证所有调用代理之间的机会均等。

- **最长的空闲** 路由每次调用已空闲时间最长的代理。 如果代理的状态可用，则代理被视为空闲状态。 在将状态更改为“可用”之前，其状态不可用的代理将无法接收呼叫。

> [!TIP]
> 建议设置“ **将路由方法** 设置为 **轮循机制** ”或 **“最长空闲** ”。

> [!NOTE]
> 如果代理上启用了 [合规性录制](teams-recording-policy.md) ，则不支持 **会议模式** 和 **助理路由** 的组合。 如果需要使用 **会议模式**，请选择 **串行路由**、 **轮循机制** 或 **“最长空闲”** 作为 **路由方法**。 如果需要使用 **助理路由**，请将 **会议模式** 设置为 **“关闭**”。
>
> 使用 **最长空闲** 状态时，当队列中的呼叫少于可用代理时，只有前两个最长的空闲代理会显示来自队列的调用。
>
> 使用 **最长空闲** 时，有时代理在不可用后不久收到队列的呼叫，或在可用后从队列接收呼叫时出现短暂延迟。
>
> 对代理的呼叫队列调用演示可能与基于位置的路由限制冲突。 在这种情况下，代理将收到调用 toast，但无法接听呼叫。 此条件将继续，直到另一个代理可用于接听呼叫、调用方挂起或呼叫队列超时条件发生。  

### <a name="presence-based-call-routing"></a>基于状态的呼叫路由

**基于状态的呼叫路由** 使用调用代理的可用性状态来确定是否应将代理包含在所选路由方法的呼叫路由列表中。

可用性状态设置为 **“可用”** 的呼叫代理包含在呼叫路由列表中，可以接收呼叫。 其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在可用性状态更改回 **“可用**”之前不会接收呼叫。

可以使用任何路由方法启用 **基于状态的调用路由** 。

如果代理选择不接听呼叫，则无论其可用性状态设置为何种，它们都不会包含在呼叫路由列表中。

> [!TIP]
> 建议设置 **基于状态的路由**。

> [!NOTE]
> 选择 **“最长空闲时间** ”作为路由方法时，需要并自动启用基于状态的路由，即使基于状态的路由切换将 **关闭** 并灰显。
>
> 如果未启用基于状态的路由，并且队列中有多个调用，系统会同时向代理提供这些调用，而不管代理的状态如何。 此操作将导致向代理发出多个呼叫通知，特别是当某些代理未响应向其发出的初始调用时。
>
> 使用 **基于状态的路由** 时，有时代理在不可用后不久收到来自队列的呼叫，或在可用后接收来自队列的呼叫的短暂延迟。
>
> 启用基于状态的路由时，使用Skype for Business客户端的代理不会包含在呼叫路由列表中。 如果代理使用Skype for Business，请勿启用基于状态的呼叫路由。

### <a name="call-agents-can-opt-out-of-taking-calls"></a>呼叫代理可以选择不接听呼叫

可以指定呼叫代理是否能够选择不接听呼叫。

建议启用 **呼叫代理可以选择不接听呼叫**。

### <a name="agent-alert-time"></a>代理警报时间

**代理警报时间** 指定在队列将呼叫重定向到下一个代理之前代理的电话将响多长时间。

> [!TIP]
> 建议将 **代理警报时间** 设置为至少 **20 秒** 。

选择代理呼叫路由选项后，选择 **“添加呼叫队列**”页底部的 **“下一步**”按钮。

# <a name="step-5-call-overflow"></a>[步骤 5：呼叫溢出](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>步骤 5：设置如何处理呼叫溢出

**队列中的最大调用** 指定可在任何给定时间在队列中等待的最大调用数。

默认值为 50，但范围为 0 到 200。

达到此限制后，将按照 **达到最大呼叫数** 的设置指定处理调用。

可以选择 **断开呼叫连接** 或将其 **重定** 向到任何呼叫路由目标。

例如，你可能让调用方为队列中的代理保留语音邮件。

*新建 - **跳转语音邮件系统消息** 控件现在在路由到共享语音邮件时公开，这也适用于 **添加问候消息** 提示。*

有关外部传输，请参阅 [先决条件](./plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码传输 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 。

> [!NOTE]
> 如果最大呼叫数设置为 0，则问候消息将不播放。

选择呼叫溢出处理选项后，选择 **“添加呼叫队列**”页底部的 **“下一步**”按钮。

# <a name="step-6-call-timeout"></a>[步骤 6：调用超时](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>步骤 6：设置如何处理呼叫超时

**呼叫超时：最大等待时间** 指定调用在重定向或断开连接之前在队列中可以保持的最大时间。

可以指定从 0 秒到 45 分钟的值。

可以选择 **断开呼叫连接** 或将其 **重定** 向到某个呼叫路由目标。

例如，你可能让调用方为队列中的代理保留语音邮件。

*新建 - **跳转语音邮件系统消息** 控件现在在路由到共享语音邮件时公开，这也适用于 **添加问候消息** 提示。*

有关外部传输，请参阅 [先决条件](./plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码传输 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 。

选择呼叫超时处理选项后，选择 **“添加呼叫队列**”页底部的“**提交**”按钮。

---

## <a name="resources-for-complex-scenarios"></a>复杂方案的资源

### <a name="summary-of-recommended-call-queue-settings"></a>建议的呼叫队列设置摘要

建议使用以下设置：

- **会议模式** 为 **“打开”**
- **路由方法** 到 **轮循机制** 或 **最长空闲**
- **基于状态的路由** 到 **On**
- **代理警报时间：** 最少 **20 秒**

### <a name="call-queue-feature-compatibility"></a>呼叫队列功能兼容性

|功能                          |Teams 桌面<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype for Business |IP 电话 | 标准呼叫队列 |基于通道的呼叫队列 | 注释 |
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
|**协作呼叫**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |Y                       |N         |否               |否    |否         |n/a                   |Y<sup>8</sup>             |   |
|**动态调用方 ID**            |                          |          |                |     |          |                      |                          |   |
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
2. Microsoft Teams iPhone 应用，Microsoft Teams Android 应用。
3. 为代理路由方法选择“最长空闲时间”将自动启用基于状态的路由。
4. 只能在将单个用户添加为标准呼叫队列的一部分时设置顺序。 使用通讯组列表或 Teams 频道时，顺序将按字母顺序排列。
5. 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
6. 仅Microsoft Teams 电话。
7. 通过“用户设置门户”页。[https://aka.ms/vmsettings](https://aka.ms/vmsettings)
8. 仅支持公共频道。
9. 自动助理和呼叫队列无法在 PSTN 连接方法之间传输调用。
10. 对于 GCCH/DOD，只能通过用户设置门户在以下处使用：
- GCCH： [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)
- 国防部： [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)

### <a name="supported-clients"></a>支持的客户端

呼叫队列中的呼叫代理支持以下客户端：

- Skype for Business桌面客户端 2016 (32 位和 64 位版本) 
- Lync 桌面客户端 2013 (32 位和 64 位版本) 
- Microsoft Teams 支持的所有 IP 手机型号。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
- Mac Skype for Business 客户端（版本 16.8.196 及更高版本）
- Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）
- iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）
- iPad Skype for Business 客户端（版本 6.16.0 及更高版本）
- Microsoft Teams Windows 客户端 (32 位和 64 位版本) 
- Microsoft Teams Mac 客户端
- [虚拟化桌面基础](teams-for-vdi.md)结构上的 Microsoft Teams (Windows 虚拟桌面、Citrix 和 VMware) 
- Microsoft Teams iPhone 应用
- Microsoft Teams Android 应用

  > [!NOTE]
  > 分配有直接路由号码的呼叫队列不支持Skype for Business客户端、Lync 客户端或Skype for Business IP Phone 作为代理。 Teams 客户端仅支持 [Teams 的共存模式](setting-your-coexistence-and-upgrade-settings.md)。

### <a name="call-queue-diagnostic-tool"></a>呼叫队列诊断工具

如果你是管理员，则可以使用以下诊断工具来验证呼叫队列是否能够接收呼叫：

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。

   > [!div class="nextstepaction"]
   > [运行测试：Teams 呼叫队列](https://aka.ms/TeamsCallQueueDiag)

2. 在“运行诊断”窗格中，在 **“用户名”或“Email**”字段中输入资源帐户，然后选择 **“运行测试**”。

3. 测试将返回处理任何租户、策略和资源帐户配置的最佳后续步骤，以验证呼叫队列是否能够接收呼叫。

### <a name="related-topics"></a>相关主题

[下面是Microsoft Teams 电话](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
