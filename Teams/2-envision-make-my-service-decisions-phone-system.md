---
title: 做出具有通话套餐的电话系统服务决策 - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择 "呼叫计划和许可", 配置紧急位置和功能 (如语音邮件和来电显示)、获取或转移电话号码。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232354"
---
# <a name="make-my-service-decisions"></a>作出我的服务决策

若要使用通话计划规划电话系统的技术实现, 您必须提前制定一系列服务决策, 以便更好地准备组织以实现满足您定义的业务要求的解决方案。

## <a name="calling-in-teams"></a>在团队中通话

通过 Microsoft 团队, 您的用户可以拨打或接听公共交换电话网络 (PSTN) 的电话。 您的用户可以使用他们自己专用的电话号码, 通过来自团队客户端应用程序的国内和国际电话呼叫, 以及包含语音邮件的高级功能。

> [!NOTE]
> 有关在部署范围内通过呼叫计划功能确定团队电话系统的最新团队路线图可在<https://aka.ms/O365Roadmap>中找到。

## <a name="phone-system-in-teams"></a>团队中的电话系统

为了使团队用户能够放置和接收 PSTN 呼叫, 需要为电话系统 (Office 365 中的一项功能) 启用它们。

要启用与 PSTN 的连接, 您的组织可以使用 Microsoft 作为其电信服务提供商。 最终, 您还可以选择 "携带自己的" 电信服务提供商, 以便为手机系统启用 PSTN 连接。

> [!IMPORTANT]
> 通过 "电话系统直接路由", 您也可以将您自己的电话服务提供商与您的团队部署配合使用。 若要了解有关直接路由的详细信息, 请参阅[直接路由指南](2-envision-make-my-service-decisions-direct-routing.md)。

## <a name="phone-system-with-calling-plans"></a>带有呼叫计划的电话系统

若要将 Microsoft 用作您的电信服务提供商, 您需要获取呼叫计划许可证并将其分配给您的电话系统用户。

通话计划有两种主要类型:

-   国内呼叫计划

-   国内和国际通话计划

每种类型的通话计划都为分配了许可证的每个用户分配特定数量的每月通话分钟数。 当通话分钟分配已用完时, 用户将无法在下个月的帐单周期内拨打出站呼叫——紧急电话除外。 如果您希望用户即使在用尽呼叫分钟数后也可以继续呼叫出站呼叫, 或者让拥有国内呼叫计划的用户进行国际通话, 您可以为您的组织设置通讯信用点数。

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通话计划的可用性

在为团队中的呼叫计划实施计划之前, 请通过查看[音频会议和通话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), 验证呼叫计划服务在你的区域中是否可用。

> [!IMPORTANT]
> 由于法律约束, Office 365 订阅的合同必须基于 "呼叫计划服务" 可用的国家或地区, 或者 "呼叫计划" 服务所在的国家或地区另行.

> [!NOTE]
> 如果您所在区域没有通话计划, 则可以使用 "[电话系统直接路由](2-envision-make-my-service-decisions-direct-routing.md)", 让用户能够使用具有 PSTN 功能的团队。

确认你的组织可以获取呼叫计划服务后, 根据可用国家和地区的列表, 编译你将在其中实施呼叫计划服务的用户位置或分支机构的列表。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定要在其中实施呼叫计划服务的用户位置或办公室。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要为呼叫计划服务启用的用户位置或办公室。</li></ul>|

> [!TIP]
> 下面是带有呼叫计划网站支持列表的电话系统的示例。
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

使用 Office 365 中的呼叫计划, 组织中的每个用户都需要有一个唯一的直接向内拨号 (已拨) 电话号码和相应的验证紧急地址。 查看[管理云语音电话号码](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers), 以便为您的通话计划实施计划电话号码购置。

为通话计划配置电话号码时, 必须为每个电话号码分配一个紧急地址, 然后才能将该号码分配给用户。 这是支持紧急呼叫所必需的。 必须验证紧急地址, 以确保它采用紧急响应服务所使用的正确格式。

> [!IMPORTANT]
> 紧急服务通话在通话计划服务中的工作方式与传统电话服务中的运行方式不同。 了解这些差异并将它们传达给所有用户非常重要。 有关详细信息, 请参阅[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)。

除了提供已验证的紧急地址, 您还可以定义紧急位置并将其与已验证的紧急地址相关联, 以便在地址中提供更准确的位置。 紧急位置通常是用户所在的建筑物编号、楼层、建筑物侧楼或办公室号码。

若要了解有关与通话计划相关的紧急位置的详细信息, 请参阅以下文章:

-   [什么是紧急位置、地址和呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)

-   [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定要在通话计划实现范围内为用户位置或分支机构收集的紧急位置信息的粒度。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>在 "通话计划实施" 范围内记录每个用户位置或 office 的详细紧急地址和紧急位置。</li></ul>|

> [!TIP]
> 你可以使用以下模板记录电话号码和紧急位置详细信息的详细信息。
> 
> |用户 |紧急位置和地址 |电话号码 |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 伦敦 Bridge 大街, 伦敦, SE1, 英国 |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 伦敦 Bridge 大街, 伦敦, SE1, 英国 |+ 44 23 4567 89112 |
> |Lahr 港 |1023/32 伦敦 Bridge 大街, 伦敦, SE1, 英国 |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-果, 法国 | TBA |
> |Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-果, 法国 | TBA |
> |Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-果, 法国 | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

云语音邮件 (由 Azure 语音邮件服务提供支持) 仅支持 Exchange 邮箱的语音邮件存款, 不支持第三方电子邮件系统。

默认情况下, 云语音邮件适用于 Exchange Online;但是, 它具有最低支持的 Exchange 本地版本和部署模型, 以允许向本地 Exchange 部署中的用户邮箱发送语音邮件消息。

云语音邮件包括语音邮件脚本, 默认情况下为组织中的所有用户启用。 您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。 如果您的组织决定保持启用语音邮件脚本, 还需要考虑是否需要启用语音邮件。 有关详细信息, 请参阅[设置组织中的语音邮件策略](set-up-phone-system-voicemail.md)。

>[!NOTE]
> 已实现回退机制, 以便云语音邮件可以使用 SMTP 重新发送邮件, 这意味着在第三方电子邮件系统上拥有邮箱的用户将收到其语音邮件。 此机制不包括有保证的服务正常运行时间或其他语音邮件功能, 例如更改语音邮件问候语。

有关手机系统实现中的语音邮件的详细信息, 请参阅[带有通话计划的电话系统](calling-plan-landing-page.md)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定是否要在通话计划实现中启用云语音邮件。</li><li>如果使用 Exchange 本地版和现有部署不符合支持云语音邮件的要求, 请从可用选项 (升级和设置) 中选择 "云语音邮件支持"、"迁移到 Exchange Online" 或 "利用回退"之前所述的机制)。</li><li>确定是在整个组织中还是针对特定用户启用或禁用语音邮件脚本和语音邮件。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>如果适用, 请记录 Exchange 决策点以支持云语音邮件。</li><li>如果你将启用/禁用语音邮件、语音邮件脚本和语音邮件仅针对特定用户的猥亵屏蔽, 请记录该用户列表。</li></ul>|

> [!TIP]
> 带有通话计划实施的电话系统的云语音邮件详细信息可以记录如下。
> 
> |用户 |Exchange 邮箱 |启用语音邮件？ |语音邮件脚本 |语音邮件功能猥亵猥亵屏蔽 |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |是 |已启用 |已启用 |
> |Lidia Holloway   |Online      |是 |已启用 |已禁用 |
> |Lahr 港       |本地部署 |是 |已启用 |已启用 |
> |Marcel Beauchamp |本地部署 |是 |已禁用 |不适用 |
> |Rachelle Cormier |Online      |是 |已禁用 |不适用 |
> |Isabell Potvin   |本地部署 |是 |已禁用 |不适用 |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>通话标识

默认情况下, 所有出站呼叫均使用分配的电话号码作为呼叫标识 (呼叫者 ID)。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 在某些情况下, 有合法的业务要求通过使用 office 主行号屏蔽呼叫方 ID 来保护呼叫方的身份—这通常是由自动助理配置服务的服务号码, 作为呼叫方 ID, 或阻止呼叫方 ID演示文稿。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的通话计划实现是否需要呼叫方 ID 操作。</li><li>如果适用, 请确定要实现的调用方 ID 操作 (带服务号或 anonymize 的掩码) 的类型。</li><li>如果适用, 请确定需要呼叫者 ID 处理的用户以及要分配给每个用户的呼叫者 ID 操作类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要为其分配呼叫者 ID 处理的用户以及要分配的呼叫者 ID 操作的类型。</li></ul>|

> [!TIP]
> 下面是呼叫方 ID 屏蔽详细信息文档的示例。
> 
> |用户  |启用出站呼叫方 ID 掩码  |呼叫方 ID 掩码类型  |允许用户替代  | 启用入站呼叫方 ID 掩码  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|否|不适用|是|否|
> |Lidia Holloway|是|服务号码 (OrgAA + 44 20 7946 0000)|否|是|
> |Lahr 港|否|不适用|是|否|
> |Marcel Beauchamp|是|服务号码 (OrgAA、TBA)|否|是|
> |Rachelle Cormier|是|Anonymize|是|否|
> |Isabell Potvin|是|服务号码 (OrgAA、TBA)|否|是|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>云语音功能的许可

音频会议和电话系统是 Office 365 中的一项功能。 对于拥有 Office 365 E3 或 E1 订阅计划的现有客户, 他们可以以附加服务的形式单独获得许可;它们已包含在 Office 365 E5 订阅计划中。

通话计划是 Office 365 中的电话系统功能的加载项, 因此必须启用电话系统以使用呼叫计划。

若要支持其他音频会议和呼叫计划使用案例 (国际会议拨出、通话计划分钟分配已用尽的外部呼叫等), 您可以为您的组织设置通讯信用点数。

## <a name="licensing-for-calling-plans"></a>呼叫计划的许可

如果你的组织打算将 Microsoft 用作电信服务提供商, 你需要获取适合你的用户的业务需求的呼叫计划加载项。 通常, 不是组织中的每个人都需要进行国际通话, 因此您可以为大多数用户预配国内呼叫计划许可证。

有两种类型的通话计划许可证:

-   国内通话套餐

-   国际和国内通话套餐

> [!NOTE]
> 为特定用户视为 "国内" 的内容由用户分配的 Office 365 使用位置确定。

每个通话计划类型提供每月可供用户拨打国内电话或国际长途的通话分钟数。 与国际和国内通话计划相比, 国内通话计划成本更低。

为单个用户的业务需求订阅和分配最合适的通话计划类型可帮助组织控制其通话计划实施的成本。

对于每个 Office 365 租户, 通话分钟数的组合按国家或地区以及按呼叫计划类型进行缓冲。 当达到租户的每月通话分钟数上限时, 将暂停当月剩余的通话计划服务 (除紧急电话之外)。 通话计划服务将在下一个日历月的第一天自动恢复。

你可以为你的组织设置通讯信用点数, 以使用户能够在分配通话分钟数后进行拨出通话, 而无需等到下个月的帐单周期。 此外, 通讯信用点数向用户分配国内呼叫计划能够拨打国际长途, 然后使用 "每分钟支付" 模式进行收费。

若要了解有关电话系统和通话计划的详细信息, 请参阅以下文章:

-   [电话系统](https://products.office.com/en-us/skype-for-business/phone-system)

-   [通话套餐](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果你的组织没有所需的电话系统许可证, 请确定你是否将通过执行现有 Office 365 订阅或获取手机系统加载项服务来获取电话系统许可证。</li><li>确定哪些用户需要国内呼叫计划许可证, 哪些用户需要国内和国际呼叫计划许可证。</li><li>确定是否需要通话计划实施的通信信用点数。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录 "部门"、"部门"、"office" 或 "用户" 组你将使用国内呼叫计划或国内和国际通话计划分配电话系统许可证。</li></ul>|

> [!TIP]
> 你可以使用以下示例, 通过呼叫计划用户来记录电话系统的许可证分配。
> 
> |用户 |Office |Office 365 许可证 |通话计划 |
> |----|----|----|----|
> |Emily Braun |32伦敦 Bridge 大街 |Office 365 E5 |国际和国内通话套餐 |
> |Lidia Holloway |32伦敦 Bridge 大街 |Office 365 E5 |国内通话套餐 |
> |Lahr 港 |32伦敦 Bridge 大街 |Office 365 E5 |国内通话套餐 |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, 电话系统加载项 |国内通话套餐 |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |国际和国内通话套餐 |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, 电话系统加载项 |国内通话套餐 |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>通信点数

使用通讯信用点数, 用户可以从音频会议会议拨出, 以便从世界上的任何地方 (在会议组织者的始发国家外) 添加其他人。 您可以为您的组织设置通讯信用点数, 以便用户在用尽通话分钟数后进行出站呼叫, 而无需等到下个月的帐单周期。 此外, 通讯信用点数向分配了国内呼叫计划的用户提供进行国际通话的功能, 然后使用 "每分钟支付" 模式进行计费。

在实施通讯信用点数时, 首先要考虑的是决定购买的初始资金量。 如果您的组织选择使用自动重新充电, 您将通过测量实际使用来确定最佳金额。 按时间监控您的通讯信用点数, 并根据需要调整您的重新充电金额。

对于您的通话计划实施, 您可以基于每个用户控制通讯信用点数的使用, 这有助于确保您已分配这些信用点数以满足您的业务需求。

若要了解有关通讯信用点数的详细信息, 请参阅[什么是通讯信用点数？](what-are-communications-credits.md)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定你是否需要用于音频会议或通话计划实现的通信信用点数。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录您将为其启用通讯信用点数的部门、部门、办公室或用户组。</li><li>为您的音频会议或通话计划实施记录您的通讯信用点数计划。</li></ul>|

> [!TIP]
> 使用以下示例为通话计划用户记录通讯信用点数分配列表。
> 
> |用户 |Office |通话计划 |通信点数 |
> |----|----|----|----|
> |Emily Braun |32伦敦 Bridge 大街 |国际和国内通话套餐 |已启用 |
> |Lidia Holloway |32伦敦 Bridge 大街 |国内通话套餐 |已禁用 |
> |Lahr 港 |32伦敦 Bridge 大街 |国内通话套餐 |已启用 |
> |Marcel Beauchamp |39 quai du Président Roosevelt |国内通话套餐 |已禁用 |
> |Rachelle Cormier |39 quai du Président Roosevelt |国际和国内通话套餐 |已启用 |
> |Isabell Potvin |39 quai du Président Roosevelt |国内通话套餐 |已禁用 |

<br>

> [!TIP]
> 您的通讯信用点数计划号码可以记录在以下示例中。
>
> |         |         |
> |---------|---------|
> |初始金额|$1000|
> |触发金额|$400|
> |自动重新充电金额|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

如果您通过携带自己的电信服务提供商实施电话系统, 则电话号码管理将保持原样。

对于音频会议和通话计划实现, 您可以选择获取新的电话号码或转移 (端口) 现有电话号码。

让用户以他们习惯的方式拨打电话号码 (例如, 忽略本地电话的区号、忽略国内电话的国家代码, 或者甚至在执行电话会议或呼叫组织中的其他用户时使用短数字拨号)您可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新的电话号码

Microsoft cloud voice 解决方案中的两种电话号码类型为:

-   订阅者 (用户) 号码, 可分配给您的组织中的用户。

-   服务号码, 作为收费电话和免费服务号码, 其具有比订户号码更高的并行通话容量, 并且可以分配给诸如音频会议、自动助理或呼叫队列等服务。

有关电话号码类型的详细信息, 请参阅[用于通话计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)。

你可以获取的电话号码的总数取决于电话号码的类型以及已购买并分配给你的用户的许可证数量。

有关您可以获取的电话号码总数的详细信息, 请参阅[您可以获取多少个电话号码？](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定将从 Microsoft 获取新电话号码的用户位置或办事处。</li><li>确定要从 Microsoft 获取的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录将从 Microsoft 获取新电话号码的用户位置或办事处。</li><li>记录要从 Microsoft 获取的电话号码的类型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>转移现有电话号码

如果你的组织想要将现有电话号码转移 (或端口) 到 Microsoft, 你可以通过向 Microsoft 提交端口订单请求来执行此操作。

您可以同时转移您的所有现有电话号码 (完整端口), 并且在某些市场中, 您可以转移现有电话号码的子集 (部分端口)。 部分端口在你只想将用户通过通话计划逐渐移动到电话系统的情况下很有用。

单个端口订单只能将电话号码转移到单个电话号码类型。 如果你需要将某些电话号码作为订户号和某些服务号码进行传输, 我们建议你首先完成到 Microsoft 的传输, 然后在 Microsoft 的控制中立即执行转换。

作为替代方法 (如果支持部分端口), 你可以一次提交多个端口请求, 一个端口请求。 但是, 此备用方法将使您的现有电信服务提供商延长您的合同。

电话号码移植是一个复杂的主题, 需要全面规划、协调和充分管理利益干系人的预期。 若要了解详细信息, 请参阅以下文章:

-   [将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)

-   [转接电话号码常见问题](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定将现有电话号码转移到 Microsoft 的用户位置或办事处。</li><li>确定要转移到 Microsoft 的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录将现有电话号码转移到 Microsoft 的用户位置或办事处。</li><li>记录要转移到 Microsoft 的电话号码类型。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>拨号计划

Office 365 的电话系统功能中的拨号计划是一组规范化规则, 可将拨出的电话号码转换为 "呼叫授权" 和 "呼叫路由" 的备用格式 (通常为 E-164 格式)。 音频会议服务利用与电话系统相同的功能来在会议拨出方案中翻译拨出的电话号码 (例如, 通过 PSTN 邀请参与者, 然后再拨 "呼叫我" 功能)。

在 Office 365 的电话系统功能中, 有两种类型的拨号计划:

-   **服务拨号计划:** 这是基于用户的 Office 365 使用位置应用于用户的默认拨号计划, 不能修改。

-   **租户拨号计划:** 这是租户内可自定义的拨号计划, 它进一步分为两种类型:

    -   **租户-全局拨号计划:** 适用于租户中的所有用户的拨号计划。

    -   **租户-用户拨号计划:** 仅适用于特定用户的拨号计划。

分配给用户的有效拨号计划是服务拨号计划 (基于用户的 Office 365 使用位置) 和租户拨号计划 (可以是租户-全局拨号计划或租户-用户拨号计划) 的组合。

![表显示了服务和租户拨号计划的三个组合。](media/audio_conferencing_image8.png "表显示了服务和租户拨号计划的三个组合。")

> [!IMPORTANT]
> 每个租户拨号计划中最多可以有25个规范化规则;因此, 请务必避免将已提供的规范化规则作为服务拨号计划的一部分。

有关拨号计划的详细信息，请参阅[什么是拨号计划？](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 (业务要求、采纳要求等)。</li><li>如果适用, 请确定租户拨号计划 (租户-全局或租户-用户) 的范围, 以支持自定义的拨号计划的要求。</li><li>如果适用, 请确定你将创建的租户拨号计划, 以支持云语音实现范围内的用户位置或分支机构。</li><li>如果适用, 请确定需要为每个用户分配自定义拨号计划和租户拨号计划的用户。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录自定义的拨号计划和关联的规范化规则, 以便将其配置为云语音实现的一部分。</li><li>记录要分配给每个用户的自定义拨号计划和租户拨号计划的用户。</li></ul>|

> [!TIP]
> 如果它适用于你的项目, 你可以使用以下模板来记录租户拨号计划配置。
> 
> |租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_一 Epping 路北 Ryde、NSW、AU 拨号计划_|**AU-NSW-NorthRyde-OER-内部**<br>_一个 Epping 公路机构、北 Ryde、NSW、澳大利亚的内部号码 (x7000-x7999)_|^ (7 \ d{3}) $<br>+ 6125550 $ 1<br>True|
> ||**AU-本地 NSW**<br>_适用于 NSW、澳大利亚的本地号码规范化_|^ ([2-9] \d{7}) $<br>+ 612 $ 1<br>False|
> ||**AU-TollFree**<br>_澳大利亚免费电话号码规范化_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $ 1<br>False|
> ||**AU-服务**<br>_澳大利亚的服务号码规范化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-新加坡-OMB**<br>_OMB 新加坡的 SG 拨号计划_|**SG-OMB-内部**<br>_内部号码 (x8000 "x8999"), 适用于 OMB office, 新加坡_|^ (8 \ d{3}) $<br>+ 656888 $ 1<br>True|
> ||**SG-TollFree**<br>_适用于新加坡的免费电话号码规范化_|^ (1 – 800 \\ d{7}) \d * $<br>+ 65 $ 1<br>False|
> ||**SG 服务**<br>_适用于新加坡的服务号码规范化_|^ (1 d{3,4}\|9 d{2}) $<br>$1<br>False|
> |**FR-巴黎-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-果-Moulineaux, 法国拨号计划_|**FR-39qdPR-内部**<br>_内部号码 (x7000 "x7999) for 39 quai du Président Roosevelt office, Issy-果-Moulineaux, 法国_|^ (7 \ d{3}) $<br>+ 3319999 $ 1<br>True|
> ||**FR-TollFree**<br>_法国免费电话号码规范化_|^ 0？(80 \ d{7}) \d * $<br>+ 33 $ 1<br>False|
> ||**FR-服务**<br>_法国的服务号码规范化_|^{1,2}\|(1 d 11 [68]{3}\|\d 10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> 可利用下面的示例模板来记录拨号计划作业以支持您的项目:
>
> |用户  |Office  |拨号计划类型  |拨号计划名称  |
> |---------|---------|---------|---------|
> |Adele Vance|一个 Epping 道路|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Alex Wilber|一个 Epping 道路|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Ben Walters|一个 Epping 道路|租户拨号计划|AU-NSW-NorthRyde-OER|
> |Christie Cline|一个 Marina Boulevard royal|租户拨号计划|SG-新加坡-OMB|
> |Debra Berger|一个 Marina Boulevard royal|租户拨号计划|SG-新加坡-OMB|
> |先生|一个 Marina Boulevard royal|租户拨号计划|SG-新加坡-OMB|
> |Emily Braun|32伦敦 Bridge 大街|服务拨号计划|不适用|
> |Lidia Holloway|32伦敦 Bridge 大街|服务拨号计划|不适用|
> |Lahr 港|32伦敦 Bridge 大街|服务拨号计划|不适用|
> |Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-巴黎-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-巴黎-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-巴黎-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>文档服务决策 

使用本文前面部分中的信息记录您的服务决策。 通常, 本文档将包含以下主要部分:

-   带有呼叫计划网站支持列表的电话系统

-   带有呼叫计划用户的电话系统许可证分配

-   通讯信用点数计划号码

-   电话号码购置、电话号码和紧急地点详细信息

-   语音邮件配置详细信息

-   呼叫方 ID 掩码配置详细信息

-   租户拨号计划

-   拨号计划作业

<!--ENDOFSECTION-->