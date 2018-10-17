---
title: 决定要进行音频会议服务的 Microsoft 团队
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解有关会议、 授权和可用性、 配置会议网桥的设置，获取或转接电话号码、 选择租户拨号计划。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: b50baa8ddb7e29c4484adea7d9d0f0c6cab957dd
ms.sourcegitcommit: 0aa8b07480a68cd589bbb70a5a51c4e177758a80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25593716"
---
# <a name="make-my-service-decisions"></a>决定我服务

若要规划的音频会议的技术实现，则必须进行服务决策提前更好地准备您的组织，以实现解决方案满足您定义的业务要求的一系列。

## <a name="audio-conferencing-in-teams"></a>团队中的音频会议

作为 Microsoft 团队中定义所需的音频会议功能的一部分，第一步是评估的最新的公用路线图，以确定：

-   在将范围内的用户部署的团队中的音频会议功能。

-   预期团队中的音频会议的用户功能要求。

-   在最新公共路线图中所述的团队中的音频会议功能满足您的用户、 功能和部署的时间线中的作用域要求确认。

> [!NOTE]
> 用于标识范围中的团队音频会议功能，可在找到您的部署的最新的工作组路线图<https://aka.ms/skype2teamsroadmap>。

## <a name="meetings-in-teams"></a>Teams 中的会议

团队使用户能够安排和加入联机会议使用 HD 视频、 语音 IP 电话 (VoIP) 和 PSTN 电话拨入式会议选项。

作为 （仅限受邀的方可以加入） 的专用会议安排会议或通道会议 （有权访问该频道的所有用户的开放） 和您的用户还可以启动临时会议中通道。

> [!NOTE]
> 若要了解有关会议在工作组中的功能的详细信息，请参阅 [Skype 的 Microsoft 团队功能路线图业务] https://aka.ms/skype2teamsroadmap)。

会议参与者可以加入您的团队会议拨入的收费电话或免费电话拨入式会议桥通过 landlines 或移动电话的电话号码。 此外，用户可以让音频会议服务启动"呼叫我"功能，使他们可以参与会议由具有会议桥呼叫其电话 （有用的数据连接不可靠时），或允许的会议组织者邀请会议通过向其电话拨出的参与者。

> [!IMPORTANT]
> 团队中的音频会议不支持第三方音频会议提供商 (Acp)。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>音频会议可用情况

规划团队中的音频会议的实现之前，您需要查看按[国家和地区可用性音频会议和计划的调用](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)中所述的音频会议服务的可用性。

> [!IMPORTANT]
> 由于法律限制，可供跨国组织的音频会议的 Office 365 订阅合同必须源于国家/地区和商用音频会议服务所在的区域。

确认您的组织有资格后要获取音频会议服务、 编译的列表用户位置或办公室，其中将实现音频会议服务，基于可用国家和地区的列表。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定哪些用户位置或办公地点将实施音频会议服务。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要支持音频会议服务的用户位置或办公地点。</li></ul>|

> [!TIP]
> 下面是音频会议网站启用列表模板的示例：
> 
> |办公地点   |位置 |PSTN 会议服务  |
> |---------|---------|---------|
> |Epping 路一号|澳大利亚|音频会议|
> |数码港道 100 号|香港 SAR|旧的 PSTN 会议|
> |滨海林荫道一号|新加坡|音频会议|
> |伦敦桥大街 32 号|英国|音频会议|
> |39 quai du Président Roosevelt|法国|音频会议|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>许可音频会议

[音频会议许可证](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)是作为 Office 365 E5 订阅计划的一部分或作为 Office 365 E1 或 Office 365 E3 订阅计划的加载项服务。

> [!NOTE]
> 团队中的 PSTN 或电话拨入式会议不支持第三方音频会议提供商 (Acp)。
> <br>如果你现在已使用 Skype for Business Online PSTN 会议，则可以立即利用 Teams 中的音频会议。

提供免费的会议桥接电话号码和以支持会议拨出式国际电话号码，您必须为组织设置[Communications 字幕式](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

> [!IMPORTANT]
> 某些国家/地区免费的会议桥接电话号码只能由提供服务。 若要支持电话拨入式中的这些国家/地区，必须使用 Communications 字幕式。

首先要考虑实现 Communications 字幕式是确定的初始资金量时您想要购买。 如果您的组织选择使用自动充电，您需要决定自动充电量和触发器量 （最低量资金）。 实际使用将确定自动充电量。 您应随着时间的推移监视 Communications 字幕式使用率，并根据需要调整充电。

您可以了解有关 Communications 字幕式[此处](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果贵组织尚未已购买所需的音频会议许可，决定是否通过逐步升级现有 Office 365 订阅或获取音频会议加载项许可证，您将能够获得音频会议许可证。</li><li>决定是否 Communications 字幕式音频会议实现所必需的。 如果是，确定要购买的初始资金数额。 在适用的情况下，确定触发数额和自动充值数额。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将分配给音频会议许可证的用户。</li><li>文档 Communications 字幕式计划 （初始量、 触发器量自动充电量）</li></ul>|

> [!TIP]
> 可以使用下面的示例来记录要进行音频会议用户的许可证分配列表。
> 
> |用户  |办公地点  |Office 365 许可证  |
> |---------|---------|---------|
> |Adele Vance|Epping 路一号|Office 365 E5|
> |Alex Wilber|Epping 路一号|Office 365 E3、音频会议外接程序|
> |Ben Walters|Epping 路一号|Office 365 E3、音频会议外接程序|
> |Christie Cline|滨海林荫道一号|Office 365 E3、音频会议外接程序|
> |Debra Berger|滨海林荫道一号|Office 365 E5|
> |Lee Gu|滨海林荫道一号|Office 365 E5|
> |Emily Braun|伦敦桥大街 32 号|Office 365 E5|
> |Lidia Holloway|伦敦桥大街 32 号|Office 365 E5|
> |港 Lahr|伦敦桥大街 32 号|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3、音频会议外接程序|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3、音频会议外接程序|

<br>

> [!TIP]
> 可以按如下所示记录通信点数计划数量：
> |         |         |
> |---------|---------|
> |初始数额|$ 1,000|
> |触发数额|$400|
> |自动充值数额|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>会议桥接电话号码

Office 365 中的音频会议服务包括：

-   多种类型的会议桥接电话号码 (收费和免费电话)

-   多个类别的会议桥电话号码 （专用和共享）

-   对会议桥接支持多种语言（主要和辅助）

-   默认的电话号码为租户的

> [!NOTE]
> 专用的会议桥接电话号码算的每个租户，根据适用的许可证数量，可以获取电话号码的限制。 免费电话会议桥接电话号码需要通信点数。

如果您必须将现有的会议桥接电话号码传输到音频会议服务 — 假定它们满足特定国家/地区的要求，您可以向 Microsoft 传输这些现有的会议桥接电话号码。

> [!NOTE]
> 将电话号码传输到 Microsoft 的复杂性而异极大地国家 / 地区、 运营商、 电路所涉及的数量和其他许多因素。 使用您当前的提供程序来进行调查长，这是要花费以帮助确保早期启动过程足以满足您的时间线。

若要详细了解会议桥接电话号码，请查看以下文章：

-   [设置音频会议 for Skype Business 和 Microsoft 团队](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [音频会议的电话号码](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [获取服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [将电话号码转移到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要专用的会议桥接电话号码。</li><li>决定如何将用户位置或办公室获得的专用的会议桥接电话号码范围为音频会议实施 （即，获取从 Microsoft 或传输的现有电话号码）。</li><li>如果您选择从 Microsoft 获取它们，决定要使用的方法 （表单提交或自动） 用户位置或办公室中的作用域为音频会议实施。</li><li>确定要为每个专用的会议桥接电话号码设置的语言首选项。</li><li>确定租户默认会议桥接电话号码。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档主计划的电话号码获取，详细说明如何将为每个用户的位置或为要进行音频会议实施的范围中的 office 获取电话号码。</li><li>如果适用，完成新电话号码请求表单 — 一个窗体的每个位置或 office。</li><li>详细的会议桥电话号码的配置 （共享和专用的会议桥接电话号码，每个专用的会议桥接电话号码，租户的默认会议桥接电话号码的语言首选项） 的文档。</li></ul>|

下面是可用于捕获会议桥详细信息模板的示例。

> [!TIP]
> 下面是获取会议网桥详细信息的模板示例：
> 
> |办公地点   |桥接号码获取和桥接类型 |桥接号码  |桥接语言|
> |---------|---------|---------|---------|
> |Epping 路一号|获取新的专用|TBA|英语（澳大利亚）|
> |滨海林荫道一号|获取新的共享|TBA|英语（美国）、中文（简体，中国）|
> |伦敦桥大街 32 号|转网现有的专用|+44 20 7946 0001|英语（英国）|
> |39 quai du Président Roosevelt|获取新的专用|TBA|法语（法国）、英语（美国）|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>会议桥接设置

若要进一步定制的用户体验，可以配置组织范围内用于加入音频会议 （会议进入和退出通知和呼叫者的名称录制）、 会议组织者的 PIN 长度和电子邮件通知的选项：

-   会议进入和退出通知以记录的名称、电话号码和声音形式提供。

-   PIN 长度可配置为 4 到 12 位，默认为 5 位 PIN。

-   默认情况下启用电子邮件上的音频会议许可证或任何其他管理员驱动型更改启用发送的通知。 您可以禁用此功能，并控制您的组织的用户通信。

对于已分配的音频会议许可证的用户，默认收费电话/toll 自由中, 显示的数字的音频会议坐标，可以配置为使用：

-   租户级默认值。

-   自动分配的会议桥接电话号码。

-   手动配置每个用户的会议桥接电话号码。

特定于用户的会议桥接的电话号码是在全局或全国组织用户在分发和必须提供作为其会议邀请中的默认会议桥接电话号码的本地号码通常很有用。

参与者加入从不同城市或海外可以查找配置租户级别的其他号码，但这些号码不直接显示在会议邀请。 会议邀请提供将参与者带到以便查找其位置最接近的会议桥接电话号码**团队会议拨入号码**页上的链接。

您还可以配置如何未经身份验证的呼叫者的每个单个会议组织者会处理 — 是否需要会议组织者开始会议之前未经身份验证的呼叫者可以在获准加入会议，或允许未经身份验证的呼叫者在开始会议.

您还可以应用其他配置为每个用户可以控制使用免费的会议桥接电话号码，并从会议拨出。

> [!NOTE]
> 这些与成本相关的控制当前仅预览版用户可用。 您可以注册您的组织中的预览程序在https://www.skypepreview.com。

使用这些控件，您可以决定是否会议组织者可以通过其组织的会议提供免费的会议桥接电话号码和是否参与者可以从电话拨出其组织的会议。 从完全避免拨出，只允许拨出国内号码，对允许拨出国内和国际号码范围的电话拨出式控制级别。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要参加和退出通知和 — 如果是这样 — 实现的通知的类型 （音、 电话号码或录制的名称）。</li><li>确定满足组织的安全要求的音频会议 PIN 长度。</li><li>确定您的组织是否要控制与音频会议服务相关的用户通信。</li><li>确定要分配给每个会议组织者的会议桥接电话号码。</li><li>确定某些会议组织者是否需要为他们的会议使用免费的会议桥接电话号码。</li><li>决定是否需要某些会议组织者允许未经身份验证的呼叫者开始会议。</li><li>确定某些会议组织者是否需要拨出式会议进行控制。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录详细的会议网桥设置（进入和退出通知、PIN 长度、配置更改电子邮件通知）</li><li>文档是分配给每个会议组织者和相应的设置来控制未经身份验证的呼叫者的策略和免费的会议桥接电话号码和拨出控件。</li></ul>|

> [!TIP]
> 如以下示例所示，可以记录您的会议桥设置。
> 
> |         |         |
> |---------|---------|
> |启用会议进入和退出通知|启用|
> |进入/退出通知类型|声音|
> |要求呼叫方在加入会议之前记录其名称|禁用|
> |PIN 长度|5|
> |如果用户的拨入设置发生变化，自动向其发送电子邮件|禁用|

<br>
> [!TIP]
> 可以使用下面的示例来记录要进行音频会议用户的会议桥设置工作分配列表。
>
> |用户  |办公地点  |默认收费电话号码  |默认免费电话号码  |允许免费电话  |未经身份验证的呼叫方绕过休息室  |会议拨出  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|Epping 路一号|TBA|TBA|是|启用|国际和国内|
> |Alex Wilber|Epping 路一号|TBA|TBA|否|禁用|不允许|
> |Ben Walters|Epping 路一号|TBA|TBA|否|禁用|不允许|
> |Christie Cline|滨海林荫道一号|TBA|TBA|是|禁用|国内|
> |Debra Berger|滨海林荫道一号|TBA|TBA|是|启用|国内|
> |Lee Gu|滨海林荫道一号|TBA|TBA|是|启用|国内|
> |Emily Braun|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|启用|不允许|
> |Lidia Holloway|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|禁用|不允许|
> |港 Lahr|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|禁用|不允许|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|是|启用|国际和国内|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

对于要进行音频会议实现，您可以选择获取新电话号码或传输/端口现有的电话号码。

若要允许用户拨打习惯于的方式的电话号码 — 例如省略区域代码进行本地呼叫、 省略国内呼叫的国家/地区代码或甚至使用短数字拨号时执行会议拨出 — 您可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新电话号码

Microsoft 云语音解决方案中的电话号码的两种类型包括：

-   订阅者 （用户） 号码，可以分配给您的组织中的用户。

-   服务号码，可用作收费和免费电话服务号码，具有更高的并发呼叫容量比订户号且可分配给服务，如要进行音频会议、 自动助理或呼叫的队列。

有关这些类型的电话号码的详细信息，请参阅[不同种类的用于调用计划的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

电话号码，您可以获取取决于的电话号码类型和许可证数量的总计您购买并分配给用户。

当谈到服务号码时，您需要仔细规划要进行音频会议实现。 评估您的业务需要专用的会议桥接电话号码; 是否如果没有，可以选择您的组织使用共享的会议桥接电话号码。

有关您可以获取的电话号码的总计的详细信息，请参阅[您可以获取多少个电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置或办公室，其中将从 Microsoft 获取新电话号码。</li><li>决定从 Microsoft 获得的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户的位置或办公室，其中将从 Microsoft 获取新电话号码。</li><li>文档从 Microsoft 获得的电话号码的类型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>传输现有的电话号码

如果您的组织到传输 （或端口） 现有的电话号码向 Microsoft，则可以通过做到提交给 Microsoft 端口顺序请求。

您可以传输所有您现有的电话号码同时 （完整端口），和 — 中某些市场 — 可以传输您现有的电话号码 （部分端口） 的子集。 部分端口可在其中您只想将您的电话拨入式会议桥移动到音频会议服务的情况下。

单个端口顺序只可以将电话号码转移到一个电话号码类型。 如果您需要将一些您为订阅者号码的电话号码和一些为服务号码，我们建议您先完成将传送给 Microsoft，然后执行转换为数字是 Microsoft 的控件内。

或者，如果部分端口受支持，您可以提交多个端口请求、 一个端口请求一次。 但是，此替代方法将延长您现有的电信服务提供商的合同。

电话号码移植是一个复杂的主题，并要求进行规划时应、 协调和充分管理股东的期望。 若要了解详细信息，请参阅以下文章：

-   [转接到 Office 365 的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [关于转移电话号码的常见问题](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置或现有的电话号码将位置传输到 Microsoft 办事处。</li><li>决定要转移到 Microsoft 的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户的位置或办公室其中现有的电话号码将传输到 Microsoft。</li><li>文档类型的电话号码要转移到 Microsoft。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>拨号计划

Office 365 的电话系统功能中的拨号计划是转换规范化规则的一组呼叫授权和呼叫路由到备用格式 （通常为 E.164 格式） 拨打的电话号码。 音频会议服务将利用相同的功能电话系统用于翻译中会议拨出方案 （例如，通过 PSTN 和回到拨号"呼叫我"功能的邀请参与者） 将所拨打的电话号码。

在 Office 365 的电话系统功能，有两种类型的拨号计划：

-   **服务拨号计划：** 这是默认应用到用户的拨号计划基于其 Office 365 使用位置，并不能修改。

-   **租户拨号计划：** 这是可自定义的拨号计划中的租户，以进一步分为两种类型：

    -   **租户全局拨号计划：** 适用于为租户中的所有用户的拨号计划。

    -   **租户用户拨号计划：** 适用于仅特定用户的拨号计划。

分配给用户的有效拨号计划是服务拨号计划 （基于用户的 Office 365 使用位置） 的组合和租户拨号计划 （可以是租户全局拨号计划或租户用户拨号计划）。

![表显示了三个服务和租户组合拨号计划。](media/audio_conferencing_image8.png "表显示了三个服务和租户组合拨号计划。")

> [!Important]
> 每个租户拨号计划; 中可以有 25 规范化规则的最大因此，很重要，以避免重复已有的规范化规则作为服务的一部分拨号计划。

若要了解有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 （业务要求、 采用要求等）。</li><li>如果适用，确定租户拨号计划（租户-全局或租户-用户）的范围以支持自定义拨号计划的要求。</li><li>如果适用，决定租户拨号计划，您将创建为支持用户位置或办公室云语音实现范围内。</li><li>如果适用，决定哪些用户需要自定义的拨号计划和每个用户分配的租户拨号计划。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档自定义的拨号计划和相关联的规范化规则要配置为云语音实现的一部分。</li><li>文档自定义的拨号计划和每个用户分配的租户拨号计划分配的用户。</li></ul>|

> [!TIP]
> 适用于您的项目时，您可以使用以下模板文档的租户拨号计划配置。
> 
> |租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_新南威尔士北莱德 Epping 路一号，AU 拨号计划_|**AU-NSW-NorthRyde-OER-Internal**<br>_澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_澳大利亚新南威尔士的本地号码规范化_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_澳大利亚的免费电话号码规范化_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_澳大利亚的服务号码规范化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_新加坡 OMB，SG 拨号计划_|**SG-OMB-Internal**<br>_内部号码 （"x 8999 x8000 â €） OMB office，新加坡_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_新加坡的免费电话号码规范化_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_新加坡的服务号码规范化_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划_|**FR-39qdPR-Internal**<br>_内部号码 （"x 7999 x7000 â €） 39 quai 是 Président Roosevelt office，Issy-les-Moulineaux，法国_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_法国的免费电话号码规范化_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_法国的服务号码规范化_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>
> [!TIP]
> 可以利用下面的示例模板来记录拨号计划分配以支持你的项目：
>
> |用户  |办公地点  |拨号计划类型  |拨号计划名称  |
> |---------|---------|---------|---------|
> |Adele Vance|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Alex Wilber|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Ben Walters|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Christie Cline|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
> |Debra Berger|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
> |Lee Gu|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
> |Emily Braun|伦敦桥大街 32 号|服务拨号计划|不适用|
> |Lidia Holloway|伦敦桥大街 32 号|服务拨号计划|不适用|
> |港 Lahr|伦敦桥大街 32 号|服务拨号计划|不适用|
> |Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策 

使用从本文前面几节的信息来记录您服务的决策。 一般情况下，本文档将包含以下主要章节：

-   音频会议服务地点支持列表

-   音频会议组织者的许可证分配列表

-   通信点数计划数量

-   会议桥接详细信息

-   会议桥接设置

-   会议桥接设置分配

-   电话号码获取计划

-   租户拨号计划

-   拨号计划分配

<!--ENDOFSECTION-->