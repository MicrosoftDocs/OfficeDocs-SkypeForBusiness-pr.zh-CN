---
title: 电话系统进行调用计划服务决策-Microsoft 小组
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 从中调用计划，并授权、 配置紧急位置和功能，如语音邮件和呼叫者 ID、 获取或转移的电话号码。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b7b1aaff60d6aa35fa10334c8d55e6a057eccaf
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="make-my-service-decisions"></a>决定我的服务

与调用计划规划电话系统的技术实现，必须进行一系列的服务决策，以更好地提前准备您的组织能够实现的解决方案能够满足您定义的业务需求。

## <a name="calling-in-teams"></a>在 Teams 中进行通话

与 Microsoft 的团队，您的用户可以放置和接听电话或从公用交换的电话网 (PSTN)。 您的用户可以使用自己的专用的电话号码放置并从团队客户端应用程序，使用高级功能，包括语音邮件和紧急调用 (增强 911) 接收国内和国际电话。

> [!NOTE]
> 最新的团队路线图为可以在上找到您的部署使用调用计划范围内的功能识别团队电话系统<https://aka.ms/skype2teamsroadmap>。

## <a name="phone-system-in-teams"></a>在团队中的电话系统

团队能够发送和接收 PSTN 呼叫用户，他们需要能够使用电话系统，Office 365 中的功能。

若要启用连接到 PSTN，您的组织可以为其电信服务提供商使用 Microsoft。 最终，您还必须到"携带您自己"电信服务提供商可以启用连接到 PSTN 电话系统。

> [!IMPORTANT]
> 能够选择自己电信服务提供商的电话系统将可在未来。 若要了解有关计划的时间线的详细信息，请查看[Microsoft 小组功能规划业务的 Skype](https://aka.ms/skype2teamsroadmap)。

## <a name="phone-system-with-calling-plans"></a>具有通话套餐的电话系统

若要为您的电信服务提供商，请使用 Microsoft，您需要获取调用规划许可证，并将它们分配给您的电话系统用户。

有两种主要的通话方案：

-   国内的调用计划

-   国内和国际呼叫计划

每种类型的调用计划将某些每月的通话分钟数分配给每个用户的已分配的许可。 在用尽通话分钟分配时，用户将无法发出出站呼叫 — — 除了紧急电话 — — 直到下个月的结帐周期。 如果您希望用户能够继续进行出站呼叫，即使他们已经耗尽的通话分钟他们分配或为了让有国内调用计划国际呼叫的用户，您可以设置通信信用组织。

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通话套餐的可用情况

规划团队中调用计划的实现之前，请验证调用计划服务，则可在当地通过查看[音频会议和调用计划的国家和地区可用性](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。

> [!IMPORTANT]
> 由于法律的限制，对于调用计划供跨国组织，调用计划服务不可用，或者可以调用计划服务必须在国家或地区基于 Office 365 订阅的协定购买。

确认您的组织可以获得调用计划服务后, 编译用户位置或办公室： 您会将实现调用计划服务，根据可用的国家 / 地区列表的列表。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定哪些用户的位置或将实现调用计划的机构在提供服务。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录用户的位置或办事处启用调用计划服务。</li></ul>|

> [!TIP]
> 下面是电话系统调用计划网站支持列表的一个示例。
>|办公地点   |位置 |电话系统服务  |
>|---------|---------|---------|
>|Epping 路一号|澳大利亚|旧的 PSTN 服务|
>|数码港道 100 号|香港 SAR|旧的 PSTN 服务|
>|滨海林荫道一号|新加坡|旧的 PSTN 服务|
>|伦敦桥大街 32 号|英国|具有通话套餐的电话系统|
>|39 quai du Président Roosevelt|法国|具有通话套餐的电话系统|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

有调用中 Office 365 计划，您的组织中的每个用户需要拨号 (DID) 的电话号码和相应的已验证紧急地址唯一直接向。 查看[管理云语音电话号码](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers)，以调用计划实现的数字电话购置计划。

当您正在调用计划配置的电话号码时，您必须分配紧急通讯每个电话号码之前向用户分配数。 为了支持紧急呼叫，必须这样做。 必须验证的紧急的地址以确保它是正确的格式将由紧急响应服务。

> [!IMPORTANT]
> 紧急服务调用调用计划服务中比在传统电话服务的工作方式不同。 值得您了解这些差异，并对所有用户进行沟通。 有关更多详细信息，请参见[紧急调用的条款和条件](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)。

除了提供经验证的紧急通讯，您可以定义紧急位置并将其与经过验证的紧急地址使内地址的更精确位置关联。 紧急位置通常是用户所在的建筑物编号、楼层、建筑物侧楼或办公室号码。

若要了解有关紧急位置相对于调用计划的详细信息，请参阅以下文章：

-   [什么是紧急位置、地址和呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [紧急呼叫条款和条件](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置或调用计划实施范围内的办事处收集紧急位置信息的粒度。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录详细的紧急通讯和紧急为每个用户的位置或调用计划实施范围内的办公室位置。</li></ul>|

> [!TIP]
> 可以使用以下模板来记录的电话号码的详细信息和紧急的位置的详细信息。
>|用户 |紧急的位置和地址 |电话号码 |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, London, SE1, United Kingdom |+ 44 23 4567 8901 |
>|Lidia Holloway |1065/32 伦敦桥街道，伦敦 SE1，美国英国 |+ 44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, London, SE1, United Kingdom |+ 44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Rachelle Cormier |07N15D/39 quai du Président 罗斯福总统那个时代、 92130 Issy-les-Moulineaux，法国 | TBA |
>|Isabell Potvin |07F05E/39 quai du Président 罗斯福总统那个时代、 92130 Issy-les-Moulineaux，法国 | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

电话系统语音邮件，采用 Azure 语音邮件服务，支持语音邮件存款只有 Exchange 邮箱并不支持第三方电子邮件系统。

默认情况下，语音邮件电话系统适用于 Exchange 联机;但是它具有最小支持的 Exchange 内部部署版本和部署模型允许语音邮件传递到本地 Exchange 部署中的用户邮箱。

电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 您的业务需求可能要求您禁用语音邮件转换为特定用户或整个组织内的所有人。 如果您的组织决定保持启用语音邮件抄写，需要还考虑是否需要启用语音邮件抄写亵渎屏蔽。 更多详细信息，请参阅[您的组织中设置语音邮件策略](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail)。

>[!NOTE]
> 实施了回退机制，以便电话系统语音邮件可以通过使用 SMTP 重新发送邮件，这意味着，在第三方电子邮件系统中有邮箱的用户将会收到其语音邮件。 这种机制不包括有保证的服务的正常运行时间或其他语音邮件功能，例如更改语音邮件问候语。

有关电话系统实现中的语音邮件的详细信息，请参阅[支持 Exchange Server 的 Azure PBX 语音邮件](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>决定是否在调用计划实现，则将启用电话系统语音邮件。</li><li>如果使用 Exchange 部署和现有部署不能满足您的需求来支持电话系统语音邮件，从可用选项中选择 (升级和安装的语音邮件的电话系统支持，迁移到 Exchange 联机状态，或利用回退机制前面所述）。</li><li>决定将启用还是禁用语音转换和语音邮件抄写亵渎屏蔽整个组织或特定的用户。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>如果适用，文档交换的决策点，以支持电话系统语音邮件。</li><li>如果您将启用/禁用语音邮件、 语音邮件抄写和仅对特定用户的语音邮件抄写亵渎掩蔽，文档的用户的列表。</li></ul>|

> [!TIP]
> 可按以下记录调用计划实现电话系统的电话系统语音邮件详细信息。
>|用户 |Exchange 邮箱 |启用语音邮件吗？ |语音邮件抄写 |语音邮件抄写亵渎屏蔽 |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |Online      |是 |启用 |启用 |
>|Lidia Holloway   |Online      |是 |启用 |已禁用 |
>|Louis Lahr       |本地 |是 |启用 |启用 |
>|Marcel Beauchamp |本地 |是 |禁用 |不适用 |
>|Rachelle Cormier |Online      |是 |禁用 |不适用 |
>|Isabell Potvin   |本地 |是 |禁用 |不适用 |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>呼叫标识

默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫方 ID）。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 在某些情况下，有合法的业务需求来屏蔽呼叫方 ID 使用以防止调用方的标识的办公室主行号 — — 这通常是由自动助理配置一个服务号码 — — 作为呼叫方 ID 或阻止的呼叫方 ID演示文稿完全。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定呼叫者 ID 操作是否您调用计划实现所必需的。</li><li>如果适用，请确定类型的呼叫方 ID 操作 （与服务号码屏蔽或匿名） 来实现。</li><li>如果适用，请决定哪些用户需要呼叫方 ID 操作和要分配给每个用户的呼叫方 ID 操作的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录呼叫者 ID 操作和类型的呼叫方 ID 操作指定要分配的用户。</li></ul>|

> [!TIP]
> 以下是屏蔽详细信息文档的呼叫方 ID 的示例。
>|用户  |启用出站呼叫方 ID 屏蔽  |呼叫方 ID 屏蔽类型  |允许用户覆盖  | 启用入站呼叫方 ID 屏蔽  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|否|不适用|是|否|
>|Lidia Holloway|是|服务号码（OrgAA，+44 20 7946 0000）|否|是|
>|Louis Lahr|否|不适用|是|否|
>|Marcel Beauchamp|是|服务号码（OrgAA，待定）|否|是|
>|Rachelle Cormier|是|匿名|是|否|
>|Isabell Potvin|是|服务号码（OrgAA，待定）|否|是|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>授权的云语音功能

音频会议和电话系统是在 Office 365 的功能。 可以作为附加服务的 Office 365 E3 或 E1 订阅计划; 现有客户单独许可他们它们已经将 Office 365 E5 订阅计划的一部分。

调用计划不到 Office 365 提供，因此您必须授权电话系统的电话系统功能的加载项可以使用调用计划。

要支持其他音频会议并调用计划使用案例 （国际会议拨出、 外部调用之后调用计划分钟分配已用尽，等等），可以设置您的组织通信贷。

## <a name="licensing-for-calling-plans"></a>通话套餐许可

如果您的组织打算使用 Microsoft，如电信服务提供商，您需要获取加载项调用计划适用于用户的业务需求。 通常情况下，人在组织中都不需要进行国际呼叫，以便可以设置调用规划许可证，国内大多数用户。

有两种类型的调用规划许可证：

-   国内通话套餐

-   国际和国内通话套餐

> [!NOTE]
> 对特定用户而言，“国内”由用户的已分配 Office 365 使用位置确定。

每种通话套餐类型均分配用户每月可以用于拨打国内电话或国际电话的通话分钟数。 国际和国内调用计划少相比国内调用计划成本。

订阅和分配最适当的调用计划类型为单个用户的业务需求的灵活性可帮助组织控制其调用计划实施的成本。

对于每个 Office 365 租户，按国家或地区以及按每种通话套餐类型共用组合的通话分钟数。 达到租户的每月通话分钟数上限时，将会在当月其余时间内暂停通话套餐服务（紧急呼叫除外）。 调用计划服务将自动继续执行下一个月的第一天。

您可以设置为组织的通信贷方以使用户后分配调用分钟耗尽而无需等待，直到下个月计费周期进行出站呼叫。 此外，通信贷方授予用户分配给国内调用计划来打国际电话，然后收取通过"支付每分钟"模型的能力。

若要了解有关电话系统和调用计划的详细信息，请参阅以下文章：

-   [电话系统](https://products.office.com/skype-for-business/phone-system)

-   [通话方案](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果您的组织没有所需的电话系统许可证，决定是否通过逐步升级现有 Office 365 提供订阅或购买电话系统附加服务，您将可以获得电话系统许可证。</li><li>决定哪些用户需要国内调用规划许可证，这需要国内和国际调用规划许可证。</li><li>决定是否需要通信信用为您调用计划的实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档分部、 部门、 办公室或电话系统许可证与国内调用计划或国内和国际调用计划会将指派的用户组。</li></ul>|

> [!TIP]
> 下面的示例可用于文档调用计划用户与电话系统的许可分配。
>|用户 |办公地点 |Office 365 许可证 |调用计划 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |Office 365 E5 |国际和国内通话套餐 |
>|Lidia Holloway |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|Louis Lahr |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3，电话系统加载项 |国内通话套餐 |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |国际和国内通话套餐 |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3，电话系统加载项 |国内通话套餐 |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>通信点数

使用通信信用，您的用户可以拨出音频会议会议 （在外部会议组织者的原始国家/地区） 世界上任意位置添加从其他人中。 您可以设置为您的组织的通信贷方以使用户之后他们已经耗尽其分配调用分钟的时间，而无需等待，直到下个月的计费周期进行出站呼叫。 此外，通信贷给用户分配与国内调用计划来打国际电话，然后收取通过"支付每分钟"模型的能力。

实施通信点数时首先要考虑的是确定要购买的初始资金数额。 如果您的组织选择使用自动充电，你需要通过测量实际使用情况来确定最佳的量。 随着时间的推移监视通信富余的使用量和调整根据需要您重新充电量。

对于调用计划实现时，您可以控制将通信贷方在每用户的基础，它可以帮助您确保您已与您的业务需求分配这些信用部门的协调。

若要了解有关通信片尾，查看[通讯片尾是什么？](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定是否需要通信片尾音频会议或调用计划实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将启用通信贷方的部、 部门、 办公室电话或用户组。</li><li>记录音频会议或调用计划实施通信贷计划。</li></ul>|

> [!TIP]
> 下面的示例用于调用计划用户通信信用分配列表中的文档。
>|用户 |办公地点 |调用计划 |通信点数 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |国际和国内通话套餐 |启用 |
>|Lidia Holloway |伦敦桥大街 32 号 |国内通话套餐 |已禁用 |
>|Louis Lahr |伦敦桥大街 32 号 |国内通话套餐 |启用 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |国内通话套餐 |禁用 |
>|Rachelle Cormier |39 quai du Président Roosevelt |国际和国内通话套餐 |启用 |
>|Isabell Potvin |39 quai du Président Roosevelt |国内通话套餐 |已禁用 |

<br>
> [!TIP]
> 规划数字您通信贷方可记录如以下示例所示。
>|         |         |
>|---------|---------|
>|初始数额|$ 1,000|
>|触发数额|$400|
>|自动充值数额|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

如果通过将您自己的电信服务提供商，从而实现电话系统，电话号码管理仍为-是。

对于音频会议和调用计划的实现，可以选择将获得新的电话号码或传输 （端口） 现有的电话号码。

若要让用户拨号电话号码他们习惯的方式 — — 如忽略本地电话的区号、 省略拨打国内电话的国家/地区代码或甚至使用短数字拨号执行会议拨出时或调用其他用户组织中 — —您可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新的电话号码

两种类型的 Microsoft 云语音解决方案中的电话号码是：

-   订户 （用户） 号，可以分配给组织中的用户。

-   服务编号，可用作收费和免费电话服务号码，它具有更高的并发呼叫容量比订户号并可以分配给服务，如音频会议、 自动助理或调用队列。

有关类型的电话号码的详细信息，请参阅[用于调用计划的电话号码的不同种类](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

电话号码可获得的总数取决于类型的电话号码，并且已经购买和分配给您的用户许可证的数量。

总计数的电话号码，您可以获得有关的详细信息，请参阅[您可以得到多少的电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定用户位置的机构将从 Microsoft 中获取新的电话号码。</li><li>确定类型的电话号码，可以从 Microsoft 获得。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录用户的位置或办公室将从 Microsoft 中获取新的电话号码。</li><li>文档类型的电话号码，可以从 Microsoft 获得。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>现有的电话号码的转移

如果您的组织希望为传输 （或端口） 现有的电话号码给 Microsoft，您可以通过提交给 Microsoft 的端口订单请求将这样做。

您可以传输所有您现有电话号码一次 （全端口），和 — — 在某些市场中 — — 可以转移现有的电话号码 （部分端口） 的子集。 部分端口可在情况下，只是需要逐渐将用户移动到调用计划与电话系统。

单个端口订单只可以将电话号码转移到一个电话号码类型。 如果您需要转移一些订户号作为您的电话号码和服务号码，我们建议您首先完成将传送到 Microsoft，然后执行转换，只要微软控件中数字的。

或者 （如果支持部分的端口），可以将多个端口的请求，一个端口请求提交一次。 但是，此种方法将延续现有的电信服务提供商与您签订合同。

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

在 Office 365 的电话系统功能的拨号计划是一套翻译的规范化规则调用授权和呼叫路由到备用格式 （通常为 E.164 格式） 拨打的电话号码。 音频会议服务利用电话系统用于翻译会议拨出方案 （例如，邀请参与者通过 PSTN 和回拨"请呼叫我"功能） 中拨出的电话号码相同的功能。

在 Office 365 的电话系统功能，有两种类型的拨号计划：

-   **服务的拨号计划：**这是默认设置适用于用户的拨号计划按 Office 365 的使用地点，并不能对其进行修改。

-   **租户拨号计划：**这是可自定义的拨号计划内的租户，进一步划分为两类：

    -   **组织全局拨号计划：**适用于组织中的所有用户的拨号计划。

    -   **租户用户拨号计划：**应用只为特定用户的拨号计划。

分配给用户的有效拨号计划是服务拨号计划 （根据用户的 Office 365 使用位置） 的组合，租户拨号计划 （它可以是全局租户拨号计划或租户用户拨号计划）。

![表显示了三个组合服务和租户的拨号计划。](media/audio_conferencing_image8.png "表显示了三个组合服务和租户的拨号计划。")

> [!IMPORTANT]
> 在每个租户拨号计划; 可以有最多的 25 个规范化规则因此，十分重要，以避免重复已有的规范化规则作为服务的一部分，拨号计划。

有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 （业务需求、 应用要求，等）。</li><li>如果适用，请决定租户拨号计划的范围 (全局租户或租户用户) 来支持自定义的拨号计划的要求。</li><li>如果适用，请确定在云的声音实现的范围内支持用户的位置或办公室，您将创建这些租户拨号计划。</li><li>如果适用，请决定哪些用户需要自定义的拨号计划和为每个用户分配的租户拨号计划。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档自定义的拨号计划和相关联的规范化规则作为云语音实现的一部分进行配置。</li><li>文档自定义的拨号计划和租户拨号计划，要将其指定为每个用户分配用户。</li></ul>|

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

-   具有通话套餐的电话系统地点启用列表

-   具有通话套餐的电话系统用户的许可证分配

-   通信点数计划数量

-   电话号码获取、电话号码和紧急位置详细信息

-   语音邮件配置详细信息

-   会议桥接设置分配

-   呼叫方 ID 屏蔽配置详细信息

-   租户拨号计划

-   拨号计划分配

<!--ENDOFSECTION-->