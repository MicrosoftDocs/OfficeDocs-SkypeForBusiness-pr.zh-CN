---
title: 使电话系统的调用计划服务决策-Microsoft 团队
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 从中调用计划和许可、 配置紧急位置和功能，如语音邮件和呼叫者 ID，获取或转接电话号码。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0794af6763dd91005bbe8dcd8b19e5a97db55d20
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014440"
---
# <a name="make-my-service-decisions"></a>决定我服务

规划电话系统的技术实现与调用计划，则必须进行准备您的组织，以实现解决方案满足您定义的业务要求的更好地提前服务决策一系列。

## <a name="calling-in-teams"></a>在 Teams 中进行通话

与 Microsoft 团队，用户可以发起和接收电话呼叫或从公用电话交换网 (PSTN)。 您的用户可以使用自己的专用的电话号码发出和接收来自团队客户端应用程序，其中包括语音邮件的高级功能的国内和国际电话呼叫。

> [!NOTE]
> 用于标识团队电话系统与调用规划范围内的功能，可在找到您的部署的最新的工作组路线图<https://aka.ms/skype2teamsroadmap>。

## <a name="phone-system-in-teams"></a>团队中的电话系统

对于能够发起和接收 PSTN 呼叫的团队用户，他们需要为启用电话系统，Office 365 中的功能。

若要启用与 PSTN 连接，您的组织可以使用其电信服务提供商作为 Microsoft。 最终，您还将具有"使用您自己"电信服务提供商的选项以启用电话系统的连接到 PSTN。

> [!IMPORTANT]
> 电话系统与团队部署使用您自己的电信服务提供商的功能也是提供电话系统直接路由。 若要了解有关直接路由的详细信息，请查看[直接路由的指南](2-envision-make-my-service-decisions-direct-routing.md)。

## <a name="phone-system-with-calling-plans"></a>具有通话套餐的电话系统

若要使用 Microsoft，根据您的电信服务提供程序，您需要获得调用规划许可证并将其分配给您电话系统的用户。

有两种主要类型的呼叫计划：

-   国内调用计划

-   国内和国际呼叫计划

每种类型的呼叫计划将分配给每个用户都已分配许可证的某些每月的呼叫分钟数。 在用尽呼叫分钟分配时，用户将无法发起出站呼叫 — 除外紧急呼叫，直到下个月的帐单周期。 如果您希望用户能够继续发起出站呼叫，即使它们已耗尽呼叫分钟数，其分配或要让具有国内调用计划进行国际呼叫的用户，您可以设置 Communications 字幕式为您的组织。

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通话套餐的可用情况

规划团队中调用计划的实现之前，请确认，调用计划服务都在您所在的区域中通过查看[国家和地区音频会议和调用计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

> [!IMPORTANT]
> 由于法律约束，调用计划可供跨国组织的 Office 365 订阅合同必须采用国家 / 地区内调用计划服务不可用，或可调用计划服务购买。

> [!NOTE]
> 如果在您所在的区域中不可用调用计划，可以使用[电话系统直接路由](2-envision-make-my-service-decisions-direct-routing.md)，使用户团队使用 PSTN 功能。

确认您的组织可以获取调用计划服务后, 编译用户位置或办公室，您将可以实施调用计划服务中，根据可用国家和地区的列表的列表。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定哪些用户位置或将实现调用计划的办公室服务中。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户的位置或办公室调用计划服务启用。</li></ul>|

> [!TIP]
> 下面是调用计划网站启用列表与电话系统的示例。
> | **办公室**                     | **位置**   | **电话系统服务** |
> |--------------------------------|----------------|--------------------------|
> | Epping 路一号                | 澳大利亚      | 旧的 PSTN 服务 |
> | 数码港道 100 号             | 香港 SAR  | 电话系统直接路由 |
> | 滨海林荫道一号           | 新加坡      | 电话系统直接路由 |
> | 伦敦桥大街 32 号        | 英国 | 具有通话套餐的电话系统 |
> | 39 quai du Président Roosevelt | 法国         | 具有通话套餐的电话系统 |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

与调用计划在 Office 365 中，您的组织中的每个用户需要有分机 (DID) 电话号码和相应的验证紧急地址唯一直接向。 查看[管理云语音电话号码](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers)，以规划调用计划实现电话号码获取。

当您正在配置的调用计划的电话号码时，必须将紧急地址分配给每个电话号码之前您分配给用户的数量。 为了支持紧急呼叫，必须这样做。 必须验证的紧急地址，以确保它按正确格式用于紧急响应服务。

> [!IMPORTANT]
> 紧急服务呼叫调用计划在服务中与传统电话服务中的工作方式不同。 很重要，您了解这些差异，以及向所有用户的通信它们。 有关详细信息，请参阅[紧急呼叫条款和条件](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/emergency-calling-terms-and-conditions)。

除了提供验证紧急地址，您可以定义紧急位置，并将它们与验证的紧急地址以提供更精确位置中的地址。 紧急位置通常是用户所在的建筑物编号、楼层、建筑物侧楼或办公室号码。

若要了解有关相对于调用计划的紧急位置的详细信息，请查看以下文章：

-   [什么是紧急位置、地址和呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [紧急呼叫条款和条件](https://docs.microsoft.com/SkypeForBusiness/legal-and-regulatory/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定要收集用户位置或调用计划实现的范围内的办公室的紧急位置信息的粒度。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>详细的紧急地址和紧急位置为每个用户的位置或调用计划实现范围中的 office 文档。</li></ul>|

> [!TIP]
> 您可以使用以下模板文档的详细信息的电话号码和紧急位置详细信息。
>|用户 |紧急位置和地址 |电话号码 |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, London, SE1, United Kingdom |+ 44 23 4567 8901 |
>|Lidia Holloway |1065/32 伦敦桥街道，伦敦，SE1，United Kingdom |+ 44 23 4567 89112 |
>|港 Lahr |1023/32 London Bridge Street, London, SE1, United Kingdom |+ 44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Rachelle Cormier |07N15D/39 quai 是 Président Roosevelt、 92130 Issy-les-Moulineaux，法国 | TBA |
>|Isabell Potvin |07F05E/39 quai 是 Président Roosevelt、 92130 Issy-les-Moulineaux，法国 | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

电话系统的语音邮件，由 Azure 语音邮件服务，支持语音邮件存款仅 Exchange 邮箱和不支持第三方电子邮件系统。

默认情况下，电话系统的语音邮件与 Exchange Online; 一起工作但是，它具有的最小支持的 Exchange 内部部署版本和部署模型以允许对内部部署 Exchange 部署中的用户邮箱发送的语音邮件消息。

电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 您的业务需求可能需要您禁用语音邮件转录的特定用户或整个组织中的每个人。 如果您的组织决定保留启用语音邮件转录，您需要还考虑是否需要启用语音邮件转录亵渎屏蔽。 有关详细信息，请参阅[设置您的组织中的语音邮件策略](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail)。

>[!NOTE]
> 实施了回退机制，以便电话系统语音邮件可以通过使用 SMTP 重新发送邮件，这意味着，在第三方电子邮件系统中有邮箱的用户将会收到其语音邮件。 此机制不包括保证的服务正常运行时间或其他语音邮件功能，如更改语音邮件问候语。

有关在电话系统的实施中的语音邮件的详细信息，请参阅[Exchange server 支持的 Azure PBX 语音邮件](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否将调用计划实现中启用电话系统的语音邮件。</li><li>如果使用 Exchange 内部部署和现有部署不满足要求以支持电话系统的语音邮件，从可用选项中选择 (升级和安装电话系统的语音邮件支持、 身份验证迁移到 Exchange Online，或利用回退机制前面所述）。</li><li>决定是否将启用或禁用语音邮件转录和语音邮件转录亵渎屏蔽在整个组织或特定用户。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>如果适用，文档 Exchange 决策点，以支持电话系统的语音邮件。</li><li>如果您将启用/禁用语音邮件、 语音邮件转录和仅为特定用户的语音邮件转录亵渎遮蔽，文档的用户的列表。</li></ul>|

> [!TIP]
> 可为以下记录调用计划实现与电话系统的电话系统的语音邮件详细信息。
>|用户 |Exchange 邮箱 |启用语音邮件？ |语音邮件转录 |语音邮件转录亵渎屏蔽 |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |Online      |是 |启用 |启用 |
>|Lidia Holloway   |Online      |是 |启用 |已禁用 |
>|港 Lahr       |本地 |是 |启用 |启用 |
>|Marcel Beauchamp |本地 |是 |禁用 |不适用 |
>|Rachelle Cormier |Online      |是 |禁用 |不适用 |
>|Isabell Potvin   |本地 |是 |禁用 |不适用 |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>呼叫标识

默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫方 ID）。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 在某些情况下，有合法的业务要求屏蔽要使用的 office 主行号保护呼叫者的标识的呼叫者 ID — 这通常是由自动助理配置一个服务号 — 为呼叫者 ID，或阻止呼叫者 ID演示文稿完全忽略。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否需要调用计划实现对呼叫者 ID 操作。</li><li>如果适用，确定呼叫者 ID 操作的类型 （屏蔽与服务号码或匿名） 实现。</li><li>如果适用，决定哪些用户需要呼叫者 ID 操作和要分配给每个用户的呼叫者 ID 操作的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户分配被呼叫者 ID 操作和呼叫者 ID 操作以分配的类型。</li></ul>|

> [!TIP]
> 下面是呼叫者 ID 屏蔽详细信息的文档的示例。
>|用户  |启用出站呼叫方 ID 屏蔽  |呼叫方 ID 屏蔽类型  |允许用户覆盖  | 启用入站呼叫方 ID 屏蔽  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|否|不适用|是|否|
>|Lidia Holloway|是|服务号码（OrgAA，+44 20 7946 0000）|否|是|
>|港 Lahr|否|不适用|是|否|
>|Marcel Beauchamp|是|服务号码（OrgAA，待定）|否|是|
>|Rachelle Cormier|是|匿名|是|否|
>|Isabell Potvin|是|服务号码（OrgAA，待定）|否|是|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>许可使用云语音功能

音频会议和电话系统是 Office 365 中的功能。 可以作为附加服务的现有用户拥有 Office 365 E3 或 E1 订阅计划; 单独授权他们它们已作为 Office 365 E5 订阅计划的一部分包含。

调用计划 Office 365，因此您必须具有许可电话系统中的电话系统功能的一个加载项启用用于调用计划。

若要支持的其他音频会议和调用计划使用情况 （国际会议拨出、 外部调用后调用规划 minute 分配用完，等等），可以设置您的组织 Communications 字幕式。

## <a name="licensing-for-calling-plans"></a>通话套餐许可

如果您的组织打算使用 Microsoft，如电信服务提供程序，您需要获取调用规划加载项适用于用户的业务需求。 一般情况下，不以为组织中的所有人需要进行国际呼叫，以便您可以设置大多数用户使用国内调用规划许可证。

有两种类型的通话套餐许可证：

-   国内通话套餐

-   国际和国内通话套餐

> [!NOTE]
> 对特定用户而言，“国内”由用户的已分配 Office 365 使用位置确定。

每种通话套餐类型均分配用户每月可以用于拨打国内电话或国际电话的通话分钟数。 国际和国内调用规划小于相比国内调用计划成本。

订阅和分配单个用户的业务要求的最适当调用规划类型的灵活性帮助组织控制其调用计划实现成本。

对于每个 Office 365 租户，按国家或地区以及按每种通话套餐类型共用组合的通话分钟数。 达到租户的每月通话分钟数上限时，将会在当月其余时间内暂停通话套餐服务（紧急呼叫除外）。 调用计划服务将自动继续执行下一个日历月的第一天。

您可以设置 Communications 字幕式的组织，允许用户为后调用分钟的分配耗尽而无需等待，直到下个月帐单周期发起出站呼叫。 此外，Communications 字幕式授予用户分配国内调用规划进行国际呼叫，然后使用"付薪每分钟"模型收取的能力。

若要了解有关电话系统和调用计划详细信息，请查看以下文章：

-   [电话系统](https://products.office.com/skype-for-business/phone-system)

-   [通话套餐](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果您的组织没有所需的电话系统许可证，决定是否按您现有的 Office 365 订阅逐步升级，或获取电话系统加载项服务，您将能够获得的电话系统许可证。</li><li>决定哪些用户需要国内调用规划许可证而需要国内和国际呼叫规划许可证。</li><li>决定是否需要 Communications 字幕式适合调用计划实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档部门、 部门、 office 或用户组的电话系统许可证与国内调用规划或国内和国际呼叫规划将分配。</li></ul>|

> [!TIP]
> 您可以使用下面的示例文档的电话系统与调用计划用户许可证分配。
>|用户 |办公地点 |Office 365 许可证 |调用计划 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |Office 365 E5 |国际和国内通话套餐 |
>|Lidia Holloway |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|港 Lahr |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3，电话系统加载项 |国内通话套餐 |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |国际和国内通话套餐 |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3，电话系统加载项 |国内通话套餐 |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>通信点数

使用 Communications 字幕式，用户可以从电话拨出音频会议 （外部会议组织者发起国家/地区） 世界任意位置添加从其他人。 您可以设置 Communications 字幕式为您的组织，以使用户为他们已耗尽而无需等待，直到下个月的帐单周期呼叫分钟，其分配后发起出站呼叫。 此外，Communications 字幕式授予用户分配与国内调用规划进行国际呼叫，然后使用"付薪每分钟"模型收取的能力。

实施通信点数时首先要考虑的是确定要购买的初始资金数额。 如果您的组织选择使用自动充电，您将通过测量实际使用率决定最佳量。 随时间推移，监视 Communications 字幕式使用率，并调整您所需的充电额。

对于调用计划实现中，您可以控制使用 Communications 字幕式基于每个用户，它可以帮助您确保您已与您的业务需求分配这些字幕式中对齐方式。

若要了解有关 Communications 字幕式的详细信息，请查看[Communications 字幕式是什么？](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否需要 Communications 字幕式音频会议或调用计划实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将启用 Communications 字幕式的部门、 部门、 office 或用户组。</li><li>记录您的音频会议或调用计划实现的通信字幕式计划。</li></ul>|

> [!TIP]
> 使用下面的示例文档调用计划的用户的通信字幕式工作分配列表。
>|用户 |办公地点 |调用计划 |通信点数 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |国际和国内通话套餐 |启用 |
>|Lidia Holloway |伦敦桥大街 32 号 |国内通话套餐 |已禁用 |
>|港 Lahr |伦敦桥大街 32 号 |国内通话套餐 |启用 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |国内通话套餐 |禁用 |
>|Rachelle Cormier |39 quai du Président Roosevelt |国际和国内通话套餐 |启用 |
>|Isabell Potvin |39 quai du Président Roosevelt |国内通话套餐 |已禁用 |

<br>
> [!TIP]
> 规划数字您 Communications 字幕式可以如以下示例所示进行归档。
>|         |         |
>|---------|---------|
>|初始数额|$ 1,000|
>|触发数额|$400|
>|自动充值数额|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

通过将您自己的电信服务提供程序，从而实现电话系统，如果电话号码管理仍为-是。

对于音频会议和调用计划实现，您可以选择获取新电话号码或转接 （端口） 现有的电话号码。

将使用户能够拨电话号码它们习惯的方法 — 例如，忽略的本地呼叫区域代码、 省略国内呼叫的国家/地区代码或甚至使用短位数时执行拨出式会议的拨号或组织中调用其他用户 —您可以配置自定义的拨号计划，并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新电话号码

Microsoft 云语音解决方案中的电话号码的两种类型包括：

-   订阅者 （用户） 号码，可以分配给您的组织中的用户。

-   服务号码，可用作收费和免费电话服务号码，具有更高的并发呼叫容量比订户号且可分配给服务，如要进行音频会议、 自动助理或呼叫的队列。

有关电话号码的类型的详细信息，请参阅[不同种类的用于调用计划的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

您可以获取的电话号码的总计取决于类型电话号码和您已购买和分配给您的用户的许可证数量。

有关您可以获取的电话号码的总计的详细信息，请参阅[您可以获取多少个电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置或办公室，其中将从 Microsoft 获取新电话号码。</li><li>决定从 Microsoft 获得的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的用户的位置或办公室，其中将从 Microsoft 获取新电话号码。</li><li>文档从 Microsoft 获得的电话号码的类型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>传输现有的电话号码

如果您的组织到传输 （或端口） 现有的电话号码向 Microsoft，则可以通过做到提交给 Microsoft 端口顺序请求。

您可以传输所有您现有的电话号码同时 （完整端口），和 — 中某些市场 — 可以传输您现有的电话号码 （部分端口） 的子集。 部分端口可在其中您只想逐步将用户移动到与调用计划的电话系统的情况下。

单个端口顺序只可以将电话号码转移到一个电话号码类型。 如果您需要将一些您为订阅者号码的电话号码和一些为服务号码，我们建议您先完成将传送给 Microsoft，然后执行转换为数字将 Microsoft 的控制。

或者 （如果支持部分端口），您可以一次提交多个端口请求、 一个端口请求。 但是，此替代方法将延长您现有的电信服务提供商的合同。

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

Office 365 的电话系统功能中的拨号计划是翻译的规范化规则的一组呼叫授权和呼叫路由到的备用格式 （通常为 E.164 格式） 拨打的电话号码。 音频会议服务将利用相同的功能电话系统用于翻译中会议拨出方案 （例如，通过 PSTN 和回到拨号"呼叫我"功能的邀请参与者） 将所拨打的电话号码。

在 Office 365 的电话系统功能，有两种类型的拨号计划：

-   **服务拨号计划：** 这是默认应用到用户的拨号计划基于其 Office 365 使用位置，并不能修改。

-   **租户拨号计划：** 这是可自定义的拨号计划中的租户，以进一步分为两种类型：

    -   **租户全局拨号计划：** 适用于为租户中的所有用户的拨号计划。

    -   **租户用户拨号计划：** 适用于仅特定用户的拨号计划。

分配给用户的有效拨号计划是服务拨号计划 （基于用户的 Office 365 使用位置） 的组合和租户拨号计划 （其可以是租户全局拨号计划或租户用户拨号计划）。

![表显示了三个服务和租户组合拨号计划。](media/audio_conferencing_image8.png "表显示了三个服务和租户组合拨号计划。")

> [!IMPORTANT]
> 每个租户拨号计划; 中可以有 25 规范化规则的最大因此，很重要，以避免重复已有的规范化规则作为服务的一部分拨号计划。

有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 （业务要求、 采用要求等）。</li><li>如果适用，决定租户拨号计划的范围 (租户全局或租户用户) 以支持自定义的拨号计划的要求。</li><li>如果适用，决定支持云语音实现的范围内的用户的位置或办公室，您将创建租户拨号计划。</li><li>如果适用，决定哪些用户需要自定义的拨号计划和每个用户分配的租户拨号计划。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档自定义的拨号计划和相关联的规范化规则要配置为云语音实现的一部分。</li><li>文档自定义的拨号计划和每个用户分配的租户拨号计划分配的用户。</li></ul>|

> [!TIP]
> 适用于您的项目时，您可以使用以下模板文档的租户拨号计划配置。
>|租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_新南威尔士北莱德 Epping 路一号，AU 拨号计划_|**AU-NSW-NorthRyde-OER-Internal**<br>_澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_澳大利亚新南威尔士的本地号码规范化_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
>||**AU-TollFree**<br>_澳大利亚的免费电话号码规范化_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
>||**AU-Service**<br>_澳大利亚的服务号码规范化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_新加坡 OMB，SG 拨号计划_|**SG-OMB-Internal**<br>_内部号码 （"x 8999 x8000 â €） OMB office，新加坡_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_新加坡的免费电话号码规范化_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
>||**SG-Service**<br>_新加坡的服务号码规范化_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划_|**FR-39qdPR-Internal**<br>_内部号码 （"x 7999 x7000 â €） 39 quai 是 Président Roosevelt office，Issy-les-Moulineaux，法国_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_法国的免费电话号码规范化_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
>||**FR-Service**<br>_法国的服务号码规范化_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

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
>|港 Lahr|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策 

使用从本文前面几节的信息来记录您服务的决策。 一般情况下，本文档将包含以下主要章节：

-   具有通话套餐的电话系统地点启用列表

-   具有通话套餐的电话系统用户的许可证分配

-   通信点数计划数量

-   电话号码获取、电话号码和紧急位置详细信息

-   语音邮件配置详细信息

-   呼叫方 ID 屏蔽配置详细信息

-   租户拨号计划

-   拨号计划分配

<!--ENDOFSECTION-->