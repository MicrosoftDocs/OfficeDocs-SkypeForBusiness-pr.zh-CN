---
title: 决定电话系统直接路由服务的 Microsoft 团队
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 07/09/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解直接路由，许可，并需要进行决策。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02a9bc4f6f29107f4bda6f8353d63064de2fd7b9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884575"
---
# <a name="make-my-service-decisions"></a>决定我服务

若要规划的电话系统直接路由 （"直接路由"） 的技术实现，则必须进行一系列服务决策提前更好地准备您的组织，以实现解决方案满足业务要求您已定义。

## <a name="calling-in-teams"></a>在 Teams 中进行通话

与 Microsoft 团队，用户可以发起和接收电话呼叫或从公用电话交换网 (PSTN)。 您的用户可以使用自己的专用的电话号码发起和接收国内和国际电话呼叫 （包括语音邮件） 的团队客户端应用程序。

## <a name="direct-routing"></a>直接路由

对于能够发起和接收 PSTN 呼叫的团队用户，他们需要为启用电话系统，Office 365 中的功能。

若要启用与 PSTN 连接，您可以使用直接路由授予您的组织能够发起和接收组织外部的电话呼叫通过 PSTN 中的人员。

使用直接路由时，通过第三方提供程序，使您能够继续使用您现有的 PSTN 中继 PSTN 服务提供商提供方便了 PSTN 连接。 这将允许部署在国家/地区与调用计划 （"调用计划"） 的电话系统不会可用，或在部署中，需要进行维护现有 PSTN 服务提供程序合同或与特定的本地系统的互操作性必填。

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>直接路由的可用性

直接路由位于 Office 365 有任何国家/地区。 有关这些国家/地区的列表，请参阅[国际可用性](https://products.office.com/business/international-availability)。

确认您的组织可以获取电话系统功能之后, 编译用户位置或办公室，您将可以实施基于在可用的国家 / 地区列表的电话系统的列表。 同时也会指出您打算对您有每个位置启用调用计划或直接路由的用户。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>标识用户位置或在其中将实现电话系统的办公室。<li>确定要对您有每个位置启用调用计划或直接路由的用户。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户的位置或办公室电话系统要启用。<li>文档的用户要为每个位置必须启用调用计划或直接路由的列表</ul>|

> [!TIP]
> 下面是直接路由网站启用列表的示例。
> | **办公室**                     | **位置**   | **电话系统服务** |
> |--------------------------------|----------------|--------------------------|
> | Epping 路一号                | 澳大利亚      | 旧的 PSTN 服务 |
> | 数码港道 100 号             | 香港 SAR  | 电话系统直接路由 |
> | 滨海林荫道一号           | 新加坡      | 电话系统直接路由 |
> | 伦敦桥大街 32 号        | 英国 | 具有通话套餐的电话系统 |
> | 39 quai du Président Roosevelt | 法国         | 具有通话套餐的电话系统 |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

电话系统要求在组织中的每个用户具有唯一直接向内分机 (DID) 电话号码。 使用直接路由时，由 PSTN 服务提供商提供的电话号码和紧急服务。

> [!NOTE]
> 直接路由中，使用您的用户可以继续使用自己的电话号码，PSTN 服务提供商。

> [!TIP]
> 您可以使用以下模板文档的电话号码的详细信息。
>|用户 |电话号码 |
>|-----|-------------|
>|Emily Braun | + 44 23 4567 8901 |
>|Lidia Holloway | + 44 23 4567 89112 |
>|港 Lahr | + 44 23 4567 8921 |
>|Marcel Beauchamp | TBA |
>|Rachelle Cormier | TBA |
>|Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

电话系统的语音邮件，由 Azure 语音邮件服务，支持语音邮件存款仅 Exchange 邮箱和不支持第三方电子邮件系统。

电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 您的业务需求可能需要您禁用语音邮件转录的特定用户或整个组织中的每个人。 如果您的组织决定保留启用语音邮件转录，您需要还考虑是否需要启用语音邮件转录亵渎屏蔽。 有关详细信息，请参阅[设置您的组织中的语音邮件策略](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail)。

有关在电话系统的实施中的语音邮件的详细信息，请参阅[设置电话系统的语音邮件](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否将直接路由中实现中启用电话系统的语音邮件。<li>决定是否将启用或禁用语音邮件转录和语音邮件转录亵渎屏蔽在整个组织或特定用户。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>如果适用，记录以支持电话系统的语音邮件的决策点。<li>如果您将启用或禁用语音邮件、 语音邮件转录和仅为特定用户的语音邮件转录亵渎遮蔽，文档的用户的列表。</ul>|

> [!TIP]
> 按下表可以记录调用计划实现的电话系统的语音邮件详细信息。
> | **用户**         | **Exchange 邮箱** | **启用语音邮件？** | **语音邮件转录** | **语音邮件转录亵渎屏蔽** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | 是                   | 启用                     | 启用                                       |
> | Lidia Holloway   | Online               | 是                   | 启用                     | 已禁用                                      |
> | 港 Lahr       | 本地          | 是                   | 启用                     | 启用                                       |
> | Marcel Beauchamp | 本地          | 是                   | 禁用                    | 不适用                                           |
> | Rachelle Cormier | Online               | 是                   | 禁用                    | 不适用                                           |
> | Isabell Potvin   | 本地          | 是                   | 禁用                    | 不适用                                           |

> [!NOTE]
> 若要使用团队和语音邮件，您的用户必须具有 Exchange 邮箱。 有关详细信息，请参阅[如何 Exchange 和 Microsoft 团队进行交互](https://docs.microsoft.com/microsoftteams/exchange-teams-interact)。

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>许可直接路由

如果组织打算使用直接路由，则需要获得所需的许可证。 直接路由中的用户必须具有以下许可证分配 Office 365 中：



-   Microsoft 电话系统

-   Microsoft Teams

-   音频会议

需要向计划的会议，外部参与者通过向他们拨出或通过提供的电话拨入式号码音频会议许可证。 时为情况下，外部参与者拨出，音频会议服务呼叫使用放置 online 呼叫功能。 音频会议许可证是可选的和所需的用户仅将组织者团队包括音频会议的会议。


> [!NOTE]
> 要提供免费的会议桥接电话号码，并以支持会议拨出式国际电话号码，您应为组织设置[Communications 字幕式](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

音频会议和电话系统可以授权单独作为附加服务的现有用户拥有 Office 365 E3 或 E1 订阅计划;它们已作为 Office 365 E5 订阅计划的一部分包含。

> [!TIP]
> 您还可以使用直接路由中的第三方 Pbx 其呼叫路由时启用了调用计划的用户。 有关详细信息，请参阅[授权和其他要求的直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果您的组织没有所需的电话系统许可证，决定是否按您现有的 Office 365 订阅逐步升级，或获取电话系统加载项服务，您将能够获得的电话系统许可证。<li>决定是否需要 Communications 字幕式直接路由中实现的。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将分配电话系统许可证的部门、 部门、 office 或用户组。<li>范围与免费电话号码的音频会议时，文档将启用 Communications 字幕式部门、 部门、 office 或用户组。</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Office 365 注意事项

将为直接路由启用的任何用户必须驻留在 Office 365 中。 对于使用本地 Skype 业务服务器或 Lync Server 混合部署，需要将用户迁移到 Skype 业务 online 之前将其配置为使用直接路由团队。

直接路由中实现的范围中的所有用户必须都启用团队。

Office 365 租户必须启用与一个或多个域，因为默认\*。 onmicrosoft.com 域不能用于直接路由。 有关域和 Office 365 租户的详细信息，请参阅[域常见问题](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否需要迁移到 Skype 业务 Online 支持直接路由中的任何用户。<li>确定需要团队启用的用户。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户移动到 Skype 的业务联机和团队启用所需的列表。</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC 注意事项

您需要使用认证和受支持的会话边界控制器 (Sbc) 所需的直接路由服务为用户提供 PSTN 连接到配对。 认证的 Sbc 的列表，请参阅[支持的会话边界控制器](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)。

根据您的环境，位置数，以及语音路由要求，您可能需要部署多个 SBCs 以支持用户群。

### <a name="sbc-domain-names"></a>SBC 域名

每个直接路由与配对的 SBC 必须具有唯一的 DNS 名称。 SBC DNS 名称必须介于 1 中的 Office 365 租户注册的域名。 如果您的租户已分配多个域名，您可以使用这些域名的任何规划 SBCs 的 DNS 名称时。

> [!IMPORTANT]
> 使用 *。 不允许 onmicrosoft.com 的 SBC DNS 名称。

### <a name="certificates"></a>证书

每个直接路由与部署的 SBC 要求从列表中受支持的证书颁发机构获取证书。 证书必须主题、 使用者替代名称或公共名称字段中包括的 SBC DNS 名称。

> [!NOTE]
> 此外支持与 Sbc 的通配符证书的使用。

有关受支持的证书颁发机构的列表和详细信息，请参阅[SBC 的受信任的公共证书](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)。


### <a name="sbc-ip-addresses-and-ports"></a>SBC IP 地址和端口

必须使用可从 Office 365 数据中心访问公共 IP 地址配置每个 SBC。 您还可以配置网络地址转换 (NAT) 将您的 Sbc 发布到 Office 365 数据中心。

Sbc 需要双向连接与信号和媒体的云服务进行通信。 信号是通过名为*SIP 代理服务器*的组件和处理媒体处理*媒体处理器*。

您需要在每个 SIP 信号和媒体的 SBC 上定义特定端口号，配置防火墙以允许对这些端口和其关联的 IP 地址的双向通信。

有关详细信息，请参阅[SIP 信号： Fqdn 和防火墙端口](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)和[媒体流量： 端口范围](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)。


> [!NOTE]
> 我们强烈建议基于 SBC 模型的每个 SBC 设置最大并发会话限制。 SBC 或将达到其容量运行时，该限制将然后触发通知。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定哪些位置将部署 SBCs。<li>确定每个 SBC 您打算部署的 DNS 名称。<li>根据 SBC 域名称决策，决定是否要使用通配符证书支持您的部署中的所有 SBCs 或专用每 SBC 证书。<li>决定哪些公共证书颁发机构您将为您 SBCs 从获取证书。<li>定义公共 IP 地址/端口对每个 SBC 您将部署，并决定是否将在分配 SBCs 公共 IP 地址，或使用 nat。<li>识别每个 SBC 支持的并发会话的最大数目或可以处理。<li>决定将使用媒体绕过配置的 Sbc。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录每个的 Sbc 中使用如下表所做的决策。</ul>|


> [!TIP]
> 使用以下模板文档直接路由中部署的 SBC 详细信息。
> | **SBC DNS 域名 (FQDN)** | **SBC 品牌和型号** | **证书** | **位置**  | **IP 地址** | **SIP 信号端口** | **NAT？** | **最大并发会话** | **启用媒体绕过？** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC Europe.contoso.com | TBD | \*。 contoso.com | 阿姆斯特丹 | TBD | TBD | 是 | TBD | 否 |
> | SBC Asia.contoso.com | TBD | \*。 contoso.com | 香港特别行政区 | TBD | TBD | 否 | TBD | 是 |
> | SBC Africa.contoso.com | TBD | \*。 contoso.com | 约翰内斯堡 | TBD | TBD | 是 | TBD | 是 |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>语音路由

您需要配置 Microsoft 电话系统，以将呼叫路由至特定的 Sbc 直接路由的。 您可以配置基于语音路由：

-   呼叫的号码模式。

-   呼叫的号码模式 + 调用的用户。


呼叫路由组成的以下元素：

-   语音路由策略 – 容器的 PSTN 用法;可分配给用户或多个用户

-   PSTN 用法 – 语音路由和 PSTN 用法; 容器可以共享在不同的语音路由策略

-   语音路由 – 号码模式和联机 PSTN 网关要用于呼叫呼叫号码与模式匹配的其中一组

-   联机 PSTN 网关-指针位于 SBC，还会存储通过 SBC，如转发 P 已断言标识 (PAI) 或首选的编解码器; 发出呼叫时应用的配置可以添加到语音路由

您可以直接路由与调用计划的共存配置语音路由。 配置允许调用计划路由到特定的 Sbc 呼叫的一些使用直接路由。

> [!TIP]
> Sbc 可以被指定为*活动状态*且*备份*。 这意味着，在 SBC 配置为活动，此数字模式 — 号码模式 + 特定用户或 — 不可用，呼叫将被路由至备份 SBC。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定语音路由策略、 PSTN 用法和语音路由，您将创建为支持用户位置或直接路由实现的范围内的办公室。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档语音路由策略、 PSTN 用法和您的组织的语音路由。<li>文档用户对于您定义的每个语音路由策略分配。</ul>|

> [!TIP]
> 使用以下模板文档直接路由中部署的语音策略。
> | **PSTN 用法** | **语音路由** | **号码模式** | **优先级** | **SBC** | **说明** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | 仅限美国 | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | 活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码 |
> | 仅限美国 | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | 备份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码 |
> | 仅限美国 | "其他 + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | 呼叫的号码的路由 （除 +1 425 XXX XX XX 或 +1 206 XXX XX XX） + 1 XXX XXX XX XX |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | 任何号码模式的路由 |

> [!IMPORTANT]
> 在语音路由策略中的 PSTN 用法的顺序，应用，如果第一个用法中找到匹配项，则永远不会计算其他用法。

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>呼叫和互操作策略

与 Microsoft 团队才支持直接路由。 若要发起或接收直接路由通过 PSTN 呼叫，您需要配置所需的策略，以确保团队中收到传入呼叫。

> [!NOTE]
> 启用直接路由不能发起或接收的用户路由呼叫定向使用 Skype 业务，并因此必须部署团队客户端。

您可以配置用户设置为其首选的客户端的呼叫的团队，通过以下两种方法之一：

-   配置为仅团队模式的用户

-   配置为首选调用客户端通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 团队。

有关详细信息，请参阅[设置为首选的 Microsoft 团队呼叫的用户的客户端](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定哪种方法，您将使用设置为首选客户端的呼叫的团队。</ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档用互操作和呼叫策略来配置的用户。</ul>|

> [!IMPORTANT]
> 当用户配置为仅团队模式时，此用户可以不再登录到 for Business 的 Skype。

要让您用户可以查看团队客户端中的呼叫选项卡，您需要启用专用的租户组织级别呼叫。 有关如何启用接听私人电话的详细信息，请参阅[启用 Microsoft 团队呼叫](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)。


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策

使用从本文前面几节的信息来记录您服务的决策。 一般情况下，本文档将包含以下主要章节：

-   具有通话套餐的电话系统地点启用列表

-   语音邮件配置详细信息

-   电话系统直接路由的用户的的许可证分配

-   SBC 配置详细信息

-   语音路由策略和路由详细信息

-   互操作性和调用策略的详细信息

<!--ENDOFSECTION-->
