---
title: 做出电话系统直接路由服务决策 - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解直接路由、许可和需要制定的决策。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57b3c8950f7e1618f578862290e8fb1696b6bc0
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018775"
---
# <a name="make-my-service-decisions"></a>作出我的服务决策

若要规划手机系统直接路由（"直接路由"）的技术实施，您必须提前制定一系列服务决策，以便更好地准备您的组织来实施满足您定义的业务要求的解决方案。

## <a name="calling-in-teams"></a>在团队中通话

通过 Microsoft 团队，您的用户可以拨打或接听公共交换电话网络（PSTN）的电话。 您的用户可以使用他们自己专用的电话号码从团队客户应用程序中拨打和接收国内和国际电话（包括语音邮件）。

## <a name="direct-routing"></a>直接路由

为了使团队用户能够放置和接收 PSTN 呼叫，需要为电话系统（Office 365 中的一项功能）启用它们。

若要启用与 PSTN 的连接，你可以使用直接路由让你的组织中的人员能够通过 PSTN 拨打和接听组织外部的电话。

通过直接路由，PSTN 连接由第三方提供商加速，让你能够继续使用 PSTN 服务提供商提供的现有 PSTN 中继。 这允许在带有呼叫计划（"通话计划"）的电话系统不可用的国家或地区内进行部署，或在需要维护现有 PSTN 服务提供商合同或与某些内部部署系统进行互操作的部署中使用必填。

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>直接路由的可用性

直接路由适用于任何可用 Office 365 的国家/地区。 有关这些国家/地区的列表，请参阅[国际供应](https://products.office.com/business/international-availability)。

确认您的组织可以获取电话系统功能后，请根据可用的国家和地区列表，将您将在其中实施电话系统的用户位置或办事处的列表进行编译。 同时确定要为每个位置启用呼叫计划或直接路由的用户。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定要在其中实施电话系统的用户位置或办公室。<li>确定要为每个位置启用呼叫计划或直接路由的用户。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要为电话系统启用的用户位置或办公室。<li>记录要为每个您拥有的位置启用呼叫计划或直接路由的用户列表</ul>|

> [!TIP]
> 下面是直接路由网站支持列表的示例。
> 
> | **Office**                     | **位置**   | **电话系统服务** |
> |--------------------------------|----------------|--------------------------|
> | 一个 Epping 道路                | 澳大利亚      | 旧版 PSTN 服务 |
> | 100 Cyberport 路             | 中国香港特别行政区  | 电话系统直接路由 |
> | 一个 Marina Boulevard royal           | 新加坡      | 电话系统直接路由 |
> | 32伦敦 Bridge 大街        | 英国 | 带有呼叫计划的电话系统 |
> | 39 quai du Président Roosevelt | 法国         | 带有呼叫计划的电话系统 |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

电话系统要求组织中的每个用户都有一个唯一的直接向内拨号（已拨）电话号码。 通过直接路由，电话号码和紧急服务由 PSTN 服务提供商提供。

> [!NOTE]
> 通过直接路由，你的用户可以继续使用由 PSTN 服务提供商提供的电话号码。
> 
> [!TIP]
> 可以使用以下模板记录电话号码的详细信息。
> 
> |用户 |电话号码 |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Lahr 港 | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

云语音邮件（由 Azure 语音邮件服务提供支持）仅支持 Exchange 邮箱的语音邮件存款，不支持第三方电子邮件系统。

云语音邮件包括语音邮件脚本，默认情况下为组织中的所有用户启用。 您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。 如果您的组织决定保持启用语音邮件脚本，还需要考虑是否需要启用语音邮件。 有关详细信息，请参阅[设置组织中的语音邮件策略](set-up-phone-system-voicemail.md)。

有关手机系统实现中的语音邮件的详细信息，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定是否要在直接路由实现中启用云语音邮件。<li>确定是在整个组织中还是针对特定用户启用或禁用语音邮件脚本和语音邮件。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>如果适用，请记录支持云语音邮件的决策点。<li>如果你将启用或禁用语音邮件、语音邮件脚本和语音邮件仅针对特定用户的猥亵屏蔽，请记录该用户列表。</ul>|

> [!TIP]
> 可在下表中记录有关呼叫计划实施的云语音邮件的详细信息。
> 
> | **User**         | **Exchange 邮箱** | **启用语音邮件？** | **语音邮件脚本** | **语音邮件功能猥亵猥亵屏蔽** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | 是                   | 已启用                     | 已启用                                       |
> | Lidia Holloway   | Online               | 是                   | 已启用                     | 已禁用                                      |
> | Lahr 港       | 本地部署          | 是                   | 已启用                     | 已启用                                       |
> | Marcel Beauchamp | 本地部署          | 是                   | 已禁用                    | 不适用                                           |
> | Rachelle Cormier | Online               | 是                   | 已禁用                    | 不适用                                           |
> | Isabell Potvin   | 本地部署          | 是                   | 已禁用                    | 不适用                                           |
> 
> [!NOTE]
> 若要使用团队和语音邮件，您的用户必须具有 Exchange 邮箱。 有关详细信息，请参阅[Exchange 和 Microsoft 团队的交互方式](exchange-teams-interact.md)。

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>直接路由的许可

如果你的组织打算使用直接路由，则需要获取所需的许可证。 直接路由用户必须在 Office 365 中分配以下许可证：

-   Microsoft Phone 系统

-   Microsoft Teams

-   音频会议

将外部参与者添加到计划会议需要使用音频会议许可证，方法是通过拨出或提供拨入号码。 向外拨出外部参与者时，音频会议服务通过使用在线呼叫功能来呼叫呼叫。 音频会议许可证是可选的，并且仅对将组织加入音频会议的团队会议所必需的用户。


> [!NOTE]
> 要提供免费的会议桥接电话号码，并支持向国际电话号码拨出的会议，您应该为您的组织设置[通讯信用点数](what-are-communications-credits.md)。

对于拥有 Office 365 E3 或 E1 订阅计划的现有客户的附加服务，音频会议和电话系统可以单独获得许可;它们已包含在 Office 365 E5 订阅计划中。

> [!TIP]
> 您还可以在将呼叫计划传送给第三方 Pbx 时，对启用了呼叫计划的用户使用直接路由。 有关更多详细信息，请参阅[直接路由的许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果你的组织没有所需的电话系统许可证，请确定你是否将通过执行现有 Office 365 订阅或获取手机系统加载项服务来获取电话系统许可证。<li>确定你是否需要直接路由实现的通信信用点数。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录分配电话系统许可证的部门、部门、办公室或用户组。<li>如果具有免费电话号码的音频会议在范围内，请记录您将启用通信信用点数的 "部门"、"部门"、"office" 或 "用户组"。</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Office 365 注意事项

任何将启用直接路由的用户都必须托管在 Office 365 中。 对于具有本地 Skype for Business 服务器或 Lync Server 的混合部署，在将用户配置为使用与团队的直接路由之前，需要将用户移动到 Skype for business Online。

必须为团队启用直接路由实现范围内的所有用户。

必须为你的 Office 365 租户启用一个或多个域，因为\*onmicrosoft.com 域不能与直接路由一起使用。 有关域和 Office 365 租户的详细信息，请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定是否需要将任何用户迁移到 Skype for business Online 以支持直接路由。<li>标识需要为团队启用的用户。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录需要移动到 Skype for Business Online 并为团队启用的用户列表。</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC 注意事项

需要使用经认证且支持的会话边界控制器（SBCs），需要将其配对到直接路由服务才能为你的用户提供 PSTN 连接。 有关已验证的 SBCs 的列表，请参阅[支持的会话边界控制器](direct-routing-plan.md#supported-session-border-controllers-sbcs)。

根据你的环境、位置数和语音路由需求，你可能需要部署多个 SBCs 以支持你的用户群。

### <a name="sbc-domain-names"></a>SBC 域名称

与直接路由配对的每个 SBC 必须具有唯一的 DNS 名称。 SBC DNS 名称必须来自 Office 365 租户中注册的其中一个域名。 如果你的租户已分配有多个域名，则你可以在规划 SBCs "DNS 名称时使用这些域名中的任何一个名称。

> [!IMPORTANT]
> 不允许对 SBC DNS 名称使用 *. onmicrosoft.com。

### <a name="certificates"></a>证书

使用直接路由部署的每个 SBC 都需要从受支持的证书颁发机构列表获得证书。 证书必须在 "主题"、"主题备用名称" 或 "公用名称" 字段中包含 SBC DNS 名称。

> [!NOTE]
> 也支持使用 SBCs 的通配符证书。

有关详细信息和受支持的证书颁发机构的列表，请参阅[SBC 的公共受信任证书](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)。


### <a name="sbc-ip-addresses-and-ports"></a>SBC IP 地址和端口

每个 SBC 都必须使用从 Office 365 数据中心访问的公共 IP 地址进行配置。 你还可以配置网络地址转换（NAT）以将你的 SBCs 发布到 Office 365 数据中心。

SBCs 需要双向连接才能与用于信号和媒体的云服务进行通信。 信号由名为*SIP 代理*的组件处理，媒体由*媒体处理器*处理。

你需要在每个 SBC 上为 SIP 信号和媒体定义特定的端口号，并将防火墙配置为允许指向这些端口的双向通信以及与其关联的 IP 地址。

有关更多详细信息，请参阅[SIP 信号： fqdn](direct-routing-plan.md#sip-signaling-fqdns)和[媒体流量：端口范围](direct-routing-plan.md#media-traffic-port-ranges)。


> [!NOTE]
> 强烈建议基于 SBC 模型为每个 SBC 设置最大并发会话限制。 然后，该限制将在 SBC 运行在其容量或接近其容量时触发通知。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定要部署 SBCs 的位置。<li>为你计划部署的每个 SBC 确定一个 DNS 名称。<li>根据 SBC 域名决策，确定你是否要使用通配符证书支持部署中的所有 SBCs 或每个 SBC 专用的证书。<li>确定从哪个公共证书颁发机构获取用于您的 SBCs 的证书。<li>为你要部署的每个 SBC 定义一个公共 IP 地址/端口对，并确定你是将公共 IP 地址分配给 SBCs 还是使用 NAT。<li>标识每个 SBC 支持或可以处理的最大并发会话数。<li>确定使用 "媒体绕过" 配置哪一个 SBCs。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>通过使用以下示例表来记录针对 SBCs 进行的每个决策。</ul>|


> [!TIP]
> 使用以下模板记录直接路由部署的 SBC 详细信息。
> 
> | **SBC DNS 名称（FQDN）** | **SBC 和型号** | **证书** | **位置**  | **IP 地址** | **SIP 信号端口** | **NAT?** | **最大并发会话数** | **已启用媒体旁路？** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*。 contoso.com | 阿姆斯特丹 | TBD | TBD | 是 | TBD | 否 |
> | SBC-Asia.contoso.com | TBD | \*。 contoso.com | 中国香港特别行政区 | TBD | TBD | 否 | TBD | 是 |
> | SBC-Africa.contoso.com | TBD | \*。 contoso.com | 约翰内斯堡 | TBD | TBD | 是 | TBD | 是 |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>语音路由

您需要将 Microsoft Phone 系统配置为将呼叫路由到特定 SBCs 以进行直接路由。 您可以根据以下内容配置语音路由：

-   名为 "数字模式"。

-   称为 "号码模式" + 进行呼叫的用户。


呼叫路由由以下元素组成：

-   语音路由策略-PSTN 使用的容器;可以分配给用户或多个用户

-   PSTN 用法–用于语音路由和 PSTN 使用的容器;可以在不同的语音路由策略中共享

-   语音路由-用于呼叫与模式匹配的呼叫的数字模式和联机 PSTN 网关集

-   Online PSTN 网关-位于 SBC 的指针还存储通过 SBC 发出调用时应用的配置，例如，前 P 声明的身份（PAI）或首选编解码器;可以添加到语音路由

您可以通过直接路由来配置您的语音路线，以便与通话计划共存。 该配置允许调用计划使用直接路由将某些调用路由到特定的 SBCs。

> [!TIP]
> SBCs 可以指定为 "*活动*" 和 "*备份*"。 这意味着当为此号码模式（或数字模式 + 特定用户）配置为活动的 SBC 不可用时，呼叫将路由到 backup SBC。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定你将创建的用于支持直接路由实现范围内的用户位置或分支的语音路由策略、PSTN 用法和语音路由。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>为你的组织记录语音路由策略、PSTN 使用情况和语音路由。<li>将为您定义的每个语音路由策略分配的用户记录到文档中。</ul>|

> [!TIP]
> 使用以下模板为直接路由部署记录语音策略。
> 
> | **PSTN 用法** | **语音路由** | **号码模式** | **优先级** | **SBC** | **说明** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | 仅限美国 | "雷德蒙 1" | \^\\+ 1 （425\|206）（\\d{7}）\$ | 1 | sbc1.contoso.com sbc2.contoso.com | 拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx |
> | 仅限美国 | "雷德蒙 2" | \^\\+ 1 （425\|206）（\\d{7}）\$ | 2 | sbc3.contoso.com sbc4.contoso.com | 已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx |
> | 仅限美国 | "其他 + 1" | \^\\+ 1 （\\d{10}）\$ | 3 | sbc5.contoso.com sbc6.contoso.com | 呼叫号码 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间）的路由 |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | 任何数字模式的路由 |
> 
> [!IMPORTANT]
> 语音路由策略中的 PSTN 用法按顺序应用，如果在第一次使用中发现了匹配项，则永远不会评估其他用法。

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>通话和互操作策略

直接路由仅受 Microsoft 团队支持。 要通过直接路由放置或接收 PSTN 呼叫，您需要配置必要的策略以确保在团队中接收传入呼叫。

> [!NOTE]
> 启用直接路由的用户不能通过使用 Skype for Business 来放置或接收直接路由呼叫，因此必须部署团队客户。

你可以通过以下两种方法中的一种将你的用户配置为将团队设置为其首选客户端调用：

-   为仅限团队模式配置用户

-   通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 将团队配置为首选调用客户端。

有关更多详细信息，请参阅向[用户分配 "仅团队" 模式以确保在 Microsoft 团队中拨打土地](direct-routing-configure.md#assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定你将使用哪种方法将团队设置为首选客户端进行呼叫。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要通过互操作和呼叫策略配置的用户。</ul>|

> [!IMPORTANT]
> 当用户配置为仅限工作组模式时，此用户无法再登录 Skype for Business。

若要让你的用户在团队客户端中看到 "呼叫" 选项卡，你需要在租户的组织级别启用专用呼叫。 有关如何启用私人通话的详细信息，请参阅[启用 Microsoft 团队呼叫](direct-routing-configure.md)。


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策

使用本文前面部分中的信息记录您的服务决策。 通常，本文档将包含以下主要部分：

-   带有呼叫计划网站支持列表的电话系统

-   语音邮件配置详细信息

-   电话系统直接路由用户的许可证分配

-   SBC 配置详细信息

-   语音路由策略和路由详细信息

-   互操作性和通话策略详细信息

<!--ENDOFSECTION-->
