---
title: 使音频会议服务决策-Microsoft 小组
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 了解有关会议、 许可和可用性、 配置会议网桥的设置、 获取或转移的电话号码，选择租户拨号计划。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa51cda9a9ce57d7672b152b45eb9c8e3cf4ba46
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="make-my-service-decisions"></a>决定我的服务

规划的音频会议服务的技术实现，必须进行一系列的服务决策提前准备好您的组织能够实现的解决方案能够满足您定义的业务需求。

## <a name="audio-conferencing-in-teams"></a>在团队中的音频会议

作为 Microsoft 小组中定义所需的音频会议功能的一部分，第一步是评估最新的公共路线图，以确定：

-   在作用域中的用户将被部署的团队中的音频会议功能。

-   在团队中预期用户的音频会议的功能要求。

-   在最新的公共路线图中所述的小组中的音频会议功能满足您的用户、 功能和范围的要求，部署的时间轴中的确认。

> [!NOTE]
> 用于标识团队音频会议范围内的功能，可以在中找到您的部署的最新小组路线图<https://aka.ms/skype2teamsroadmap>。

## <a name="meetings-in-teams"></a>Teams 中的会议

团队为您的用户提供了安排并加入联机会议通过高清视频、 语音 (VoIP)，IP 和 PSTN 拨入会议选项的能力。

可以为专用 （只有被邀请的方可以加入） 的会议安排会议或通道会议 （所有用户有权访问通道的打开） 和您的用户还可以启动在通道内的举行会议。

> [!NOTE]
> 若要了解有关会议在团队中的功能的详细信息，请参阅 [Skype 为 Microsoft 小组功能规划的业务] https://aka.ms/skype2teamsroadmap)。

会议参与者加入您的团队会议，拨入的收费或免费电话拨入会议桥通过 landlines 或移动电话的电话号码。 此外，用户可以让音频会议服务启动"请呼叫我"功能，使他们可以参与会议通过会议桥调用其电话 （有用的数据连接不可靠时），或让的会议组织者邀请会议参与者通过拨打其电话。

> [!IMPORTANT]
> 在团队中的音频会议不支持第三方音频会议提供商 (ACPs)。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>音频会议可用情况

在团队中的音频会议的实施计划之前，您需要查看[音频会议和调用计划的国家和地区可用性](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)中详细介绍音频会议服务的可用性。

> [!IMPORTANT]
> 由于法律的限制，对于音频会议供跨国组织，必须从国家和商用音频会议服务的地区来源 Office 365 订阅的协定。

确认您的组织有资格后获取音频会议服务、 编译用户位置或办公室实现音频会议服务，其中的列表基于可用的国家 / 地区列表。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定哪些用户位置或办公地点将实施音频会议服务。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要支持音频会议服务的用户位置或办公地点。</li></ul>|

> [!TIP]
> 下面是音频会议站点支持列表模板的示例：
>|办公地点   |位置 |PSTN 会议服务  |
>|---------|---------|---------|
>|Epping 路一号|澳大利亚|音频会议|
>|数码港道 100 号|香港 SAR|旧的 PSTN 会议|
>|滨海林荫道一号|新加坡|音频会议|
>|伦敦桥大街 32 号|英国|音频会议|
>|39 quai du Président Roosevelt|法国|音频会议|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>许可音频会议

[音频会议许可](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)是可作为 Office 365 E5 订阅计划的一部分或作为附加服务到 Office 365 E1 或 Office 365 E3 订阅计划。

> [!NOTE]
> 在团队中的 PSTN 或拨入会议不支持第三方音频会议提供商 (ACPs)。
> <br>如果你现在已使用 Skype for Business Online PSTN 会议，则可以立即利用 Teams 中的音频会议。

若要提供免费会议电话号码桥并支持会议拨出的国际电话号码，必须设置[通信信用](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)组织。

> [!IMPORTANT]
> 某些国家/地区是通过免费的会议桥接电话号码仅提供服务。 要拨入支持在这些国家中，必须使用通信的贷方。

实施通信片尾是确定基金的初始金额时首先要考虑您想要购买。 如果您的组织选择使用自动充电，您需要决定自动充电量和触发器量 （最低金额的资金）。 实际的使用情况将决定自动充电量。 应该随着时间的推移监视通信富余的使用量并根据需要调整充电。

您可以了解有关通信片尾[此处](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果您的组织尚未购买授权所需的音频会议，决定是否通过逐步升级现有 Office 365 提供订阅或购买音频会议附加许可，您将能够获得音频会议许可证。</li><li>确定通信贷方是否音频会议实现所必需的。 如果是，确定要购买的初始资金数额。 在适用的情况下，确定触发数额和自动充值数额。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将音频会议许可证分配的用户。</li><li>文档 （初始量、 触发器量，自动充电量） 的通信积分计划</li></ul>|

> [!TIP]
> 可以通过使用下面的示例记录音频会议用户许可证分配列表。
>|用户  |办公地点  |Office 365 许可证  |
>|---------|---------|---------|
>|Adele Vance|Epping 路一号|Office 365 E5|
>|Alex Wilber|Epping 路一号|Office 365 E3、音频会议外接程序|
>|Ben Walters|Epping 路一号|Office 365 E3、音频会议外接程序|
>|Christie Cline|滨海林荫道一号|Office 365 E3、音频会议外接程序|
>|Debra Berger|滨海林荫道一号|Office 365 E5|
>|Lee Gu|滨海林荫道一号|Office 365 E5|
>|Emily Braun|伦敦桥大街 32 号|Office 365 E5|
>|Lidia Holloway|伦敦桥大街 32 号|Office 365 E5|
>|Louis Lahr|伦敦桥大街 32 号|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3、音频会议外接程序|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3、音频会议外接程序|

<br>
> [!TIP]
> 可以按如下所示记录通信点数计划数量：
>|         |         |
>|---------|---------|
>|初始数额|$ 1,000|
>|触发数额|$400|
>|自动充值数额|TBA|

<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>会议桥接电话号码

Office 365 中的音频会议服务包括：

-   多种类型的会议桥接电话号码 (收费和免费电话)

-   多个类别会议桥的电话号码 （专用和共享）

-   对会议桥接支持多种语言（主要和辅助）

-   默认的电话号码的租户

> [!NOTE]
> 专门的会议桥接电话数字算的电话号码可以获得每个租户，基于可用许可证数量的限制。 免费电话会议桥接电话号码需要通信点数。

如果必须转给音频会议服务的现有会议桥接电话号码 — — 假定它们符合特定国家的要求 — — 您可以将这些现有的会议桥接电话号码转移到 Microsoft。

> [!NOTE]
将电话号码转到 Microsoft 的复杂性取决于国家 / 地区、 载波、 数电路复杂和许多其他因素变化很大。 当前提供程序要多长时间，这是有可能有助于确保及早启动过程进行研究与合作不足以满足您的时间线。

若要了解更多有关会议桥的电话号码，请参阅以下文章：

-   [设置音频会议 for Skype Business 和 Microsoft 团队](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [音频会议的电话号码](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [获取服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [将电话号码转移到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要专用的会议桥的电话号码。</li><li>决定专门的会议桥接电话号码的用户位置或办公室获得的方式 （即，获得 Microsoft 或转移现有的电话号码） 的音频会议实现的范围内。</li><li>如果您选择从 Microsoft 获取它们，决定要使用的方法 （表单提交或自动） 用户的位置或办事处范围内的音频会议实现。</li><li>决定的语言首选项设置为每个专用的会议桥接电话号码。</li><li>决定租户默认会议桥的电话号码。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录电话号码收购，详细说明将如何为每个用户的位置或办公室中的音频会议实现的范围内获取电话号码的主计划。</li><li>如果适用，请填写新电话号码请求表 — — 为每个位置或办公室的一种形式。</li><li>详细的会议桥的电话号码 （共享和专用会议桥的电话号码，每个专用的会议桥接电话号码，租户默认会议桥接电话号码的语言首选项） 的配置文档。</li></ul>|

下面是您可以使用它来捕获会议桥详细信息模板的示例。

> [!TIP]
> 下面是获取会议网桥详细信息的模板示例：
>|办公地点   |桥接号码获取和桥接类型 |桥接号码  |桥接语言|
>|---------|---------|---------|---------|
>|Epping 路一号|获取新的专用|TBA|英语（澳大利亚）|
>|滨海林荫道一号|获取新的共享|TBA|英语（美国）、中文（简体，中国）|
>|伦敦桥大街 32 号|转网现有的专用|+44 20 7946 0001|英语（英国）|
>|39 quai du Président Roosevelt|获取新的专用|TBA|法语（法国）、英语（美国）|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>会议桥接设置

若要进一步自定义用户体验，您可以配置全组织加入音频会议的会议 （会议进入和退出通知和调用方名称录制）、 会议组织者的针长度和电子邮件通知的选项：

-   会议进入和退出通知以记录的名称、电话号码和声音形式提供。

-   PIN 长度可配置为 4 到 12 位，默认为 5 位 PIN。

-   默认情况下启用上实现了音频会议许可或其他任何管理驱动的更改发送电子邮件通知。 您可以禁用此功能并控制组织的用户通信。

对于音频会议许可证分配的用户，默认收费/toll 自由中, 显示的数字音频会议坐标中，可以配置为使用：

-   组织级的默认。

-   自动分配的会议桥的电话号码。

-   为每个用户手动配置会议桥接电话号码。

特定于用户的会议桥接的电话号码是在全球或全国组织的用户分布和必须提供作为默认其会议邀请中的会议桥电话号码的本地号码通常很有用。

加入从不同的城市或海外的参与者可以查找配置组织级别的其他号码，但这些数字没有直接在会议邀请中。 会议邀请提供将参与者带到他们查找它们的位置最接近会议桥接电话号码**拨入号码团队会议**页的链接。

您还可以配置如何未经身份验证的调用方将由每个单独的会议组织者 — — 是否要求会议组织者开始会议之前未经身份验证的调用方可以允许，或允许未经身份验证的调用方开始会议.

您还可以应用控制免费会议电话号码桥的使用和从会议拨出每个用户的附加配置。

> [!NOTE]
> 这些与成本相关的控制当前仅预览版用户可用。 您可以注册您的企业中的预览程序https://www.skypepreview.com。

使用这些控件，您可以决定是否会议组织者可以提供免费会议电话号码桥，通过这些组织的会议和是否参与者可以从拨出参加它们组织的会议。 拨出控制级别范围从完全避免拨出，只允许拨出为国内的数字，到允许拨出为国内和国际的数字。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定您的组织是否需要进入和退出的通知，和 — — 如果是这样 — — 要实现的通知类型 （色调、 电话号码或记录的名称）。</li><li>确定音频会议针长度符合您组织的安全要求。</li><li>确定您的组织是否要控制与音频会议服务相关的用户通信。</li><li>确定要分配给每个会议组织者的会议桥接电话号码。</li><li>决定是否需要为他们的会议使用免费会议电话号码桥一些会议的组织者。</li><li>决定是否需要某些会议组织者允许未经身份验证的调用启动会议。</li><li>确定一些会议组织者是否需要大会拨出被控制。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录详细的会议网桥设置（进入和退出通知、PIN 长度、配置更改电子邮件通知）</li><li>记录分配给每个会议组织者和相应的设置来控制策略的未经身份验证的调用方，且免费的会议桥电话号码并拨出控件。</li></ul>|

> [!TIP]
> 如以下示例所示，可以记录会议网桥的设置。
>|         |         |
>|---------|---------|
>|启用会议进入和退出通知|启用|
>|进入/退出通知类型|声音|
>|要求呼叫方在加入会议之前记录其名称|禁用|
>|PIN 长度|5|
>|如果用户的拨入设置发生变化，自动向其发送电子邮件|禁用|

<br>
> [!TIP]
> 可以通过使用下面的示例文档会议桥设置分配列表中的音频会议的用户。
>|用户  |办公地点  |默认收费电话号码  |默认免费电话号码  |允许免费电话  |未经身份验证的呼叫方绕过休息室  |会议拨出  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|Epping 路一号|TBA|TBA|是|启用|国际和国内|
>|Alex Wilber|Epping 路一号|TBA|TBA|否|禁用|不允许|
>|Ben Walters|Epping 路一号|TBA|TBA|否|禁用|不允许|
>|Christie Cline|滨海林荫道一号|TBA|TBA|是|禁用|国内|
>|Debra Berger|滨海林荫道一号|TBA|TBA|是|启用|国内|
>|Lee Gu|滨海林荫道一号|TBA|TBA|是|启用|国内|
>|Emily Braun|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|启用|不允许|
>|Lidia Holloway|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|禁用|不允许|
>|Louis Lahr|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|禁用|不允许|
>|Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|
>|Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|是|启用|国际和国内|
>|Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

对于音频会议实现，可以选择以获取新的电话号码或传输/端口现有的电话号码。

若要允许用户以他们习惯的方式拨电话号码 — — 如忽略本地电话的区号、 省略拨打国内电话的国家/地区代码或甚至使用短数字拨号时执行会议拨出 — — 您可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新的电话号码

两种类型的 Microsoft 云语音解决方案中的电话号码是：

-   订户 （用户） 号，可以分配给组织中的用户。

-   服务编号，可用作收费和免费电话服务号码，它具有更高的并发呼叫容量比订户号并可以分配给服务，如音频会议、 自动助理或调用队列。

有关这些类型的电话号码的详细信息，请参阅[用于调用计划的电话号码的不同种类](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

电话可以获得的数字取决于电话号码类型及数量的许可证总数已经购买和分配给您的用户。

于服务号码时，您需要仔细规划您的音频会议实现。 评估是否您的业务需要专门的会议桥的电话号码;否则，您的组织可以选择使用共享的会议桥的电话号码。

总计数的电话号码，您可以获得有关的详细信息，请参阅[您可以得到多少的电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置的机构将从 Microsoft 中获取新的电话号码。</li><li>确定类型的电话号码，可以从 Microsoft 获得。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录用户的位置或办公室将从 Microsoft 中获取新的电话号码。</li><li>文档类型的电话号码，可以从 Microsoft 获得。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>现有的电话号码的转移

如果您的组织希望为传输 （或端口） 现有的电话号码给 Microsoft，您可以通过提交给 Microsoft 的端口订单请求将这样做。

您可以传输所有您现有电话号码一次 （全端口），和 — — 在某些市场中 — — 可以转移现有的电话号码 （部分端口） 的子集。 部分的端口非常有用的情况下，您只需要拨入会议桥进入音频会议服务。

单个端口订单只可以将电话号码转移到一个电话号码类型。 如果您需要转移一些订户号作为您的电话号码和服务号码，我们建议您首先完成将传送到 Microsoft，然后执行转换，只要在 Microsoft 的控件内的数字是。

作为一种替代方法，如果支持部分的端口，则您可以提交多个端口的请求，一个端口请求一次。 但是，此种方法将延续现有的电信服务提供商与您签订合同。

电话号码移植是一个复杂的话题，需要全面规划、 协调和充分管理利益干系人的期望。 若要了解详细信息，请参阅下列文章：

-   [将电话号码转到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [关于转移电话号码的常见问题](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户的位置或办公室现有的电话号码，会被传输到 Microsoft。</li><li>确定类型的电话号码，以转移到 Microsoft。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录用户的位置或办公室现有的电话号码，会被传输到 Microsoft。</li><li>文档类型的电话号码，以转移到 Microsoft。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>拨号计划

在 Office 365 的电话系统功能的拨号计划是一套规范化规则将转换调用授权和呼叫路由到备用格式 （通常为 E.164 格式） 拨电话号码。 音频会议服务利用电话系统用于翻译会议拨出方案 （例如，邀请参与者通过 PSTN 和回拨"请呼叫我"功能） 中拨出的电话号码相同的功能。

在 Office 365 的电话系统功能，有两种类型的拨号计划：

-   **服务的拨号计划：**这是默认设置适用于用户的拨号计划按 Office 365 的使用地点，并不能对其进行修改。

-   **租户拨号计划：**这是可自定义的拨号计划内的租户，进一步划分为两类：

    -   **组织全局拨号计划：**适用于组织中的所有用户的拨号计划。

    -   **租户用户拨号计划：**应用只为特定用户的拨号计划。

分配给用户的有效拨号计划是 （基于用户的 Office 365 使用位置） 服务的拨号计划的组合和租户拨号计划 （可以是全局租户拨号计划或租户用户拨号计划）。

![表显示了三个组合服务和租户的拨号计划。](media/audio_conferencing_image8.png "表显示了三个组合服务和租户的拨号计划。")

> [!Important]
> 在每个租户拨号计划; 可以有最多的 25 个规范化规则因此，十分重要，以避免重复已有的规范化规则作为服务的一部分，拨号计划。

若要了解有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 （业务需求、 应用要求，等）。</li><li>如果适用，确定租户拨号计划（租户-全局或租户-用户）的范围以支持自定义拨号计划的要求。</li><li>如果适用，请决定您将创建用于支持用户的位置或办公室租户拨号计划云语音实施范围内。</li><li>如果适用，请决定哪些用户需要自定义的拨号计划和为每个用户分配的租户拨号计划。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档自定义的拨号计划和相关联的规范化规则配置成云语音实现的一部分。</li><li>文档自定义的拨号计划和租户拨号计划，要将其指定为每个用户分配用户。</li></ul>|

> [!TIP]
> 它是否适用于您的项目，可以使用以下模板来记录租户的拨号计划配置。
>|租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_新南威尔士北莱德 Epping 路一号，AU 拨号计划_|**AU-NSW-NorthRyde-OER-Internal**<br>_澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_澳大利亚新南威尔士的本地号码规范化_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_澳大利亚的免费电话号码规范化_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_澳大利亚的服务号码规范化_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_新加坡 OMB，SG 拨号计划_|**SG-OMB-Internal**<br>_OMB 办公室后，新加坡内部号 （"x 8999 x8000 要 €）_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_新加坡的免费电话号码规范化_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_新加坡的服务号码规范化_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划_|**FR-39qdPR-Internal**<br>_39 quai du Président 罗斯福总统那个时代办公室、 Issy 内部号 （"x 7999 化 — x7000） 的 les-Moulineaux，法国_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_法国的免费电话号码规范化_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_法国的服务号码规范化_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> 可以利用下面的示例模板来记录拨号计划分配以支持你的项目：
>|用户  |办公地点  |拨号计划类型  |拨号计划名称  |
>|---------|---------|---------|---------|
>|Adele Vance|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Alex Wilber|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Ben Walters|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Christie Cline|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Debra Berger|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Lee Gu|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Emily Braun|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Lidia Holloway|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Louis Lahr|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策 

这篇文章的前面部分中使用的信息记录您服务的决策。 一般情况下，此文档将包含下列各节：

-   音频会议服务地点支持列表

-   音频会议组织者的许可证分配列表

-   通信点数计划数量

-   会议桥接详细信息

-   会议桥接设置

-   会议桥接设置分配

-   电话号码收购计划

-   租户拨号计划

-   拨号计划分配

<!--ENDOFSECTION-->