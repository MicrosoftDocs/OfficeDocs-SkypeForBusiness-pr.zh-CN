---
title: "Microsoft Teams 和 Skype for Business 互操作性"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "了解 Teams 和 Skype for Business 之间的互操作性，以及它对聊天和通话体验有何影响。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a6593d6e2bc7302817a87c418da4bacb70f03b42
ms.sourcegitcommit: 334fee0485e16a6485055eff586203cc30e6fdc9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Microsoft Teams 和 Skype for Business 互操作性
=======================================================

如果贵组织目前使用 Skype for Business 并打算开始使用 Teams，那么务必要了解如何配置这两个应用程序以便进行互操作。

> [!IMPORTANT]
> 本文档用于对 Teams 的通话套餐支持情况进行早期评估。 将来会更改 Teams 互操作性策略的详细信息。

互操作性功能用于支持 Skype for Business 和 Teams 用户相互之间进行聊天和通话，从而确保贵组织中通信保持顺畅。 为了帮助 IT 专业人士管理 Teams 的采用，我们添加了新的 Teams 互操作性策略，该策略通过 Skype for Business 远程 Windows PowerShell 会话，使用 [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlet 进行管理。 此策略用于将 Teams 配置为贵组织中所需的工作方式。


> [!TIP]
> 要查找你所需的互操作性相关 PowerShell cmdlet，请在 [Skype for Business PowerShell cmdlet 文档](https://docs.microsoft.com/powershell/module/skype)中的**“筛选”**框中键入 "CsTeamsInteropPolicy"。

IT 专业人士可以通过 Teams 互操作性策略指定用于接收聊天和呼叫的用户首选应用程序。 可以将其配置为使 Teams 和 Skype for Business 中的通信保持独立，也可以配置为支持用户跨应用程序界限进行通信。

Teams 互操作性策略可以按租户或按每个用户级别定义，甚至可以配置为支持用户选择希望用于接收聊天和呼叫的应用程序。

此内置的灵活性是为了帮助贵组织试用、评估以及按照最适合自己的进度和方式迁移到 Teams。

> [!NOTE]
> 支持在处于完全在线状态（使用 Skype for Business Online 和 Teams）的用户和混合 (Hybrid) 部署拓扑中的本地 Skype for Business 部署中承载的用户之间实现 Teams 和 Skype for Business 之间的互操作性。

## <a name="what-interoperability-means"></a>互操作性含义
互操作性是用于实现 Teams 和 Skype for Business 用户跨 Teams 和 Skype for Business 相互聊天（即时消息）和通话的功能。

组织开始从 Skype for Business 到 Teams 的旅程时，组织中会有使用不同客户端的各种用户。

为了确保工作的连续性，Teams 为用户提供了无论其他人使用的应用程序是什么（Teams 或 Skype for Business），都可以与之通信的功能。

支持的互操作性体验包括以下项：
- 不使用 Teams 的 Skype for Business 用户可以与 Teams 用户聊天，反之亦然<p>
![Teams 中的互操作性聊天体验](media/Interop_chat_experience_from_Teams.png)<br>
- Skype for Business 用户可以通过语音和视频呼叫 Teams 用户，反之亦然。 甚至对互操作性呼叫，仍提供高级呼叫选项，例如，呼叫转移和呼叫转接。<p>
![Teams 中的互操作性呼叫体验](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> 从 Skype for Business 用户角度而言，在 Teams 中进行的聊天和呼叫将与基本的 Skype for Business 聊天和呼叫一样。 有关详细信息，请参阅[互操作性体验限制](#interop-experiences-limitations)部分。

> [!IMPORTANT]
> 当前不支持在 Teams 和 Skype for Business 之间实现统一联机状态，即，Teams 和 Skype for Business 将显示其自己的独立联机状态。 要了解何时将支持统一联机状态，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。

## <a name="interop-requirements"></a>互操作性要求
为了启用互操作性功能，用户必须满足以下条件：
- 必须为 Teams 启用（和/或许可）用户
- 必须为 Skype for Business Online 启用（和/或许可）用户
    - 这适用于计划仅使用 Teams 或将 Teams 用作其主聊天和通话应用程序的用户。
- 在混合 Skype for Business 部署中：
    - 本地 Skype for Business（或 Skype for Business Hybrid 部署当前支持的任何 Lync Server 版本）承载的用户可以使用 Teams 与云用户进行互操作
    - 对于计划将 Teams 用作其主聊天和通话应用程序的云用户，必须为 Skype for Business Online 启用（和/或许可）这些用户。

## <a name="supported-topologies-for-interop"></a>用于实现互操作性的支持拓扑
主要是以下 Skype for Business 部署拓扑支持 Teams 和 Skype for Business 之间的互操作性：
- 仅 Skype for Business Online
- Skype for Business Hybrid（Skype for Business Online 和本地 Skype for Business 的混合部署）

### <a name="skype-for-business-online-only-topology"></a>仅有 Skype for Business Online 的拓扑
仅采用 Skype for Business Online 部署的组织可以享有 Skype for Business Online 用户和 Teams 用户之间的互操作性聊天和通话支持。

在此拓扑中，还必须为 Skype for Business Online 启用将 Teams 配置为主聊天和通话应用程序的用户，才能使互操作性发挥作用。

![仅有 Skype for Business Online 的部署拓扑中的互操作性](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Skype for Business Hybrid 部署拓扑
如果组织采用的部署是由 Skype for Business Online 和混合部署拓扑中的 Skype for Business Server（本地）的混合部署组成，则可以享有 Skype for Business 用户（在 Online 和本地承载）和 Teams 用户之间的互操作性聊天和通话支持。

与仅有 Skype for Business Online 的部署拓扑一样，还必须为 Skype for Business Online 启用将 Teams 配置为主聊天和通话应用程序的用户且在 Skype for Business Online 上承载这些用户，才能使互操作性发挥作用。

![Skype for Business Hybrid 部署拓扑中的互操作性](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> Skype for Business Hybrid 的互操作性支持不包括通过 CCE (Cloud Connector Edition) 或使用现有部署的本地 PSTN 连接（通常称为 OPCH (On Prem Config Hybrid)）提供的混合语音功能。 不能为使用 CCE 或 OPCH 的 PSTN 呼叫功能启用 Teams 用户。

### <a name="interop-experiences-limitations"></a>互操作性体验限制
当前，除了 Teams 和 Skype for Business 之间缺少统一联机状态（导致 Teams 和 Skype for Business 显示自己的独立联机状态）外，Teams 和 Skype for Business 之间的互操作性聊天和互操作性通话体验中还有一些功能不能使用。

对于聊天互操作性，当前的限制列表如下：
- Teams 中的多方（群组）对话（聊天）只能包括使用 Teams 的参与者
- Skype for Business 中的多方即时消息对话（聊天）只能包括使用 Skype for Business 的参与者
- 不支持在跨 Teams 和 Skype for Business 的两方聊天对话中传输文件或在多方对话中附加文件，反之亦然
- 在 Teams 中，互操作性聊天不是持久性的
- 在 Teams 中，互操作性聊天不支持标记、多信息文本、完整表情符集等

对于通话互操作性，当前的限制列表如下：
- 不支持在 Teams 和 Skype for Business 之间进行屏幕共享（桌面或应用共享）
- 不支持将正在进行的点对点 (P2P) 语音和视频通话提升至涉及 Teams 和 Skype for Business 用户的多方通话

## <a name="managing-interoperability"></a>管理互操作性
要管理 Teams 和 Skype for Business 之间的互操作性，可以利用名为 Teams 互操作性策略的新策略来控制用于发送聊天和路由呼叫的应用（Teams 或 Skype for Business），可以为组织中的所有用户配置此策略（全局策略），也可以按用户应用此策略，可以通过 Skype for Business 远程 Windows PowerShell 会话使用 [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) cmdlet 管理此策略。

默认情况下，配置此策略以确保可以并行使用 Teams 和 Skype for Business，并且尽量减少它们之间的互操作性。 此方法是为了确保贵组织中的当前业务流程和通信不会因为采用 Teams 而中断。

### <a name="interop-policy-overview"></a>互操作性策略概述
Teams 互操作性策略包括以下参数：

|参数                    |可能的值      |说明  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | 默认、SfB、Teams | 此参数指定默认聊天应用        |
|`CallingDefaultClient`       | 默认、SfB、Teams | 此参数指定默认通话应用        |
|`AllowEndUserClientOverride` | True、False         | 此参数指定用户是否可以覆盖默认聊天和通话应用         |

> [!WARNING]
> 虽然当前可以创建 `ChatDefaultClient` 和 `CallingDefaultClient` 参数有独立值的 Teams 互操作性策略，但我们预计将来会有更改。 目前，这两个参数务必使用相同的值。

#### <a name="chat-default-client"></a>聊天默认客户端
`ChatDefaultClient` 参数定义如何在 Teams 和 Skype for Business 之间路由聊天，此参数的默认全局值设置为**“默认”**。

> [!IMPORTANT]
> 目前，Teams 不支持 `ChatDefaultClient` 参数。 Teams 支持该参数时，我们将更新本文档来介绍预期行为。 在租户级别控制的 Teams 和 Skype for Business 之间的现有聊天互操作性功能将继续按现状发挥作用。

#### <a name="calling-default-client"></a>通话默认客户端
`CallingDefaultClient` 参数定义如何在 Teams 和 Skype for Business 之间路由呼叫，此参数的默认全局值设置为**“默认”**。

下面详细介绍了此参数的每个设置如何影响 Teams 和 Skype for Business 客户端行为。

|呼叫方呼叫时使用的应用  |设置：默认；接听呼叫时使用的应用  |设置：Teams；接听呼叫时使用的应用  |设置：SfB；接听呼叫时使用的应用  |
|---------|---------|---------|---------|
|**Skype for Business**     |Skype for Business         |Teams        |Skype for Business         |
|**Teams**     |Teams         |Teams         |Skype for Business         |
|**PSTN**   |Skype for Business        |Teams        |Skype for Business         |
|**Federated Skype for Business**     |Skype for Business         |Skype for Business         |Skype for Business         |

> [!IMPORTANT]
> 当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。 传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。 有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。

#### <a name="allowing-user-choice"></a>允许用户选择
`AllowEndUserClientOverride` 参数接受布尔值（**TRUE** 或 **FALSE**），该参数设置为 **TRUE** 时，Teams 将允许用户选择希望用于接听呼叫的应用（Teams 或 Skype for Business），用户将能够随时更改其主应用程序。

![首选通话应用程序选项](media/Preferred_calling_application_option.png)

此参数的全局默认值为 **FALSE**，因此，不允许用户在没有管理员干预的情况下选择自己的主应用程序。

## <a name="teams-interop-policy-special-cases"></a>Teams 互操作性特殊情况
分配 Teams 互操作性策略时，仍在（混合 (Hybrid) 部署拓扑中的）本地 Skype for Business 承载的用户、使用（通过 CCE 或 OPCH 提供）混合语音的用户以及采用专用 Skype for Business 工作流的用户均视为特殊情况，在为他们分配策略时，需要特别注意。

### <a name="policy-for-skype-for-business-on-premises-users"></a>适用于本地 Skype for Business 用户的策略
在混合 (Hybrid) 部署拓扑中，对于本地 Skype for Business 承载的用户，不应将其策略中的 `ChatDefaultClient` 和 `CallingDefaultClient` 参数设置为 Teams。 否则，他们将无法接收聊天和呼叫。 对于本地用户，应使用以下策略定义：

|参数  |值  |
|---------|---------|
|`ChatDefaultClient`    |默认或 SfB         |
|`CallingDefaultClient`     |默认或 SfB         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> 将用户从 Skype for Business Online 迁移到本地 Skype for Business 或反之时，需要确保为用户分配的 Teams 互操作性策略与需要强制实施的行为一致。 请注意，本地用户不能配置为将 Teams 用作主聊天和通话应用程序。

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>适用于混合语音用户（CCE 或 OPCH）的策略
为具有（通过 CCE 或 OPCH 提供）混合语音的电话系统启用的 Skype for Business Online 用户无法在 Teams 中接听 PSTN 呼叫。 为混合语音用户分配 Teams 互操作性策略时，请使用以下策略定义

|参数  |值  |
|---------|---------|
|`ChatDefaultClient`    |默认、SfB 或 Teams         |
|`CallingDefaultClient`     |默认或 SfB         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>适用于采用专用 Skype for Business 工作流的用户的策略
在有些情况下，一组用户可能使用依赖于 Skype for Business 的第三方应用程序（例如：呼叫中心、前台接待等）。 在这些情况下，你希望确保他们一直使用 Skype for Business，直到 Teams 中有相应的功能。 对于这些用户，请使用以下策略定义：

|参数  |值  |
|---------|---------|
|`ChatDefaultClient`    |默认或 SfB         |
|`CallingDefaultClient`     |默认或 SfB         |
|`AllowEndUserClientOverride`     |False         |