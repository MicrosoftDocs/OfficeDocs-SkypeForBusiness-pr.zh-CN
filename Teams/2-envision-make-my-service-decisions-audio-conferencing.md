---
title: 做出音频会议服务决策 - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解会议、许可和可用性、配置会议桥设置、获取或传输电话号码, 以及选择租户拨号计划。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0155788ef4ba99a350be0043847edd5e705b75b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240572"
---
# <a name="make-my-service-decisions"></a>作出我的服务决策

若要规划音频会议的技术实现, 您必须提前制定一系列服务决策, 以便更好地准备您的组织来实施满足您定义的业务要求的解决方案。

## <a name="audio-conferencing-in-teams"></a>团队中的音频会议

在 Microsoft 团队中定义所需的音频会议功能的一部分, 首先要评估最新的公共路线图以确定:

-   将为范围内的用户部署的团队中的哪些音频会议功能。

-   团队中的音频会议的预期用户功能要求。

-   确认最新公共路线图中介绍的团队的音频会议功能在部署的时间线内满足你的用户、功能和范围要求。

> [!NOTE]
> 有关在部署范围内识别团队音频会议功能的最新团队路线图可在<https://aka.ms/O365Roadmap>中找到。

## <a name="meetings-in-teams"></a>Teams 中的会议

团队使用户能够使用高清视频、IP 语音 (VoIP) 和 PSTN 电话拨入式会议选项安排和加入联机会议。

会议可以安排为私人会议 (仅受邀请的参与方可以加入) 或频道会议 (为有权访问频道的所有用户打开), 并且你的用户也可以在频道中开始即席会议。

> [!NOTE]
> 若要了解有关团队中的会议功能的详细信息, 请参阅[Microsoft 365 路线图](https://aka.ms/O365Roadmap)。

会议参与者可以通过座机或移动电话拨入收费电话或免费电话拨入式会议桥接电话号码, 从而加入你的团队会议。 此外, 用户可以使用 "呼叫我" 功能启动 "呼叫我" 功能, 以便他们可以通过会议桥呼叫他们的电话来参与会议 (在数据连接不可靠时很有用), 或者让会议组织者邀请会议参与者通过拨出到他们的手机。

> [!IMPORTANT]
> 团队中的音频会议不支持第三方音频会议提供商 (ACPs)。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>音频会议的可用性

在为团队中的音频会议实施计划之前, 需要查看音频会议服务的可用性, 详细信息请参阅[音频会议和通话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

> [!IMPORTANT]
> 由于法律约束, 适用于多国组织的音频会议, Office 365 订阅的合约必须来自于商用的 "音频会议" 服务所在的国家和地区。

在确认您的组织有资格获得音频会议服务之后, 请根据可用的国家和地区的列表, 编译要在其中实施音频会议服务的用户位置或分支机构的列表。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定哪些用户位置或办事处将实现音频会议服务。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要为音频会议服务启用的用户位置或办公室。</li></ul>|

> [!TIP]
> 下面是音频会议网站支持列表模板的示例:
> 
> |Office   |位置 |PSTN 会议服务  |
> |---------|---------|---------|
> |一个 Epping 道路|澳大利亚|音频会议|
> |100 Cyberport 路|中国香港特别行政区|旧式 PSTN 会议|
> |一个 Marina Boulevard royal|新加坡|音频会议|
> |32伦敦 Bridge 大街|英国|音频会议|
> |39 quai du Président Roosevelt|法国|音频会议|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>音频会议的许可

[音频会议许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)作为 Office 365 E5 订阅计划的一部分, 或者作为 Office 365 E1 或 Office 365 E3 订阅计划的加载项服务提供。

> [!NOTE]
> 团队中的 PSTN 或电话拨入式会议不支持第三方音频会议提供商 (ACPs)。
> <br>如果您今天已使用 Skype for Business Online PSTN 会议, 则可以立即在团队中利用音频会议。

若要提供免费的会议桥接电话号码并支持电话会议到国际电话号码, 您必须为您的组织设置[通讯信用点数](what-are-communications-credits.md)。

> [!IMPORTANT]
> 某些国家/地区仅由免费的会议桥电话号码服务。 为了支持这些国家/地区的电话, 您必须使用通讯信用点数。

实施通讯信用点数的第一项考虑因素是确定要购买的初始资金量。 如果你的组织选择使用自动重新充电, 你需要确定 "触发器数量" (最少资金金额) 和自动重新充电金额。 你的实际使用将确定自动重新充电金额。 您应监控您的通信点数使用情况, 并根据需要调整充电金额。

您可以在[此处](what-are-communications-credits.md)了解有关通讯信用点数的详细信息。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果你的组织尚未购买所需的音频会议许可, 请确定你是否将通过启动现有 Office 365 订阅或通过获取音频会议加载项许可证来获取音频会议许可证。</li><li>确定你的音频会议实施是否需要通信信用点数。 如果是, 请决定要购买的初始资金量。 如果适用, 请确定 "触发器数量" 和 "自动重新充电金额"。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录将分配音频会议许可证的用户。</li><li>记录通信信用点数计划 (初始金额、触发器金额、自动重新充电金额)</li></ul>|

> [!TIP]
> 你可以使用以下示例为音频会议用户记录许可证分配列表。
> 
> |用户  |Office  |Office 365 许可证  |
> |---------|---------|---------|
> |Adele Vance|一个 Epping 道路|Office 365 E5|
> |Alex Wilber|一个 Epping 道路|Office 365 E3、音频会议加载项|
> |Ben Walters|一个 Epping 道路|Office 365 E3、音频会议加载项|
> |Christie Cline|一个 Marina Boulevard royal|Office 365 E3、音频会议加载项|
> |Debra Berger|一个 Marina Boulevard royal|Office 365 E5|
> |先生|一个 Marina Boulevard royal|Office 365 E5|
> |Emily Braun|32伦敦 Bridge 大街|Office 365 E5|
> |Lidia Holloway|32伦敦 Bridge 大街|Office 365 E5|
> |Lahr 港|32伦敦 Bridge 大街|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3、音频会议加载项|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3、音频会议加载项|

<br>

> [!TIP]
> 您的通讯信用点数计划号码可以记录如下:
>
> |         |         |
> |---------|---------|
> |初始金额|$1000|
> |触发金额|$400|
> |自动重新充电金额|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>会议桥接电话号码

Office 365 中的音频会议服务包括:

-   多类型的会议桥电话号码 (收费和免费电话)

-   多个类别的会议桥电话号码 (专用和共享)

-   支持多语言的会议桥 (主要和辅助)

-   租户的默认电话号码

> [!NOTE]
> 专用的会议桥电话号码根据适用许可证的数量, 向每个租户获取的电话号码限制。 免费电话会议桥电话号码需要通信信用点数。

如果必须将现有会议桥电话号码转移到音频会议服务 (假设他们满足特定于国家的要求), 则可以将这些现有的会议桥电话号码转移到 Microsoft。

> [!NOTE]
> 根据国家或地区、运营商、所涉及的电路数量以及其他许多相关因素, 将电话号码转移到 Microsoft 的复杂度会有很大的差异。 与您的当前提供商协作以调查这种情况, 以帮助确保您尽早开始该流程以满足您的日程表。

若要了解有关 "会议桥" 电话号码的详细信息, 请参阅以下文章:

-   [设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

-   [音频会议电话号码](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [获取服务电话号码](getting-service-phone-numbers.md)

-   [将电话号码转接到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要专用的会议桥电话号码。</li><li>确定如何为用户位置或办事处获取专用会议桥接电话号码, 以获取音频会议实施的范围 (即从 Microsoft 获取或转移现有电话号码)。</li><li>如果你选择从 Microsoft 获取它们, 请确定要对音频会议实现使用的用户位置或办事处使用的方法 (表单提交或自动)。</li><li>确定为每个专用会议桥接电话号码设置的语言首选项。</li><li>确定租户默认会议桥接电话号码。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录电话号码获取的主计划, 详细介绍在音频会议实现范围内如何为每个用户位置或 office 获取电话号码。</li><li>如果适用, 请完成 "新电话号码请求" 窗体, 每个位置或 office 一个窗体。</li><li>记录详细的会议桥接电话号码配置 (共享和专用会议桥接电话号码, 每个专用会议桥接电话号码的语言首选项, 租户默认会议桥接电话号码)。</li></ul>|

下面是可用于捕获会议桥详细信息的模板示例。

> [!TIP]
> 下面是一个用于捕获会议桥详细信息的模板示例:
> 
> |Office   |桥号码购置和网桥类型 |桥号码  |网桥语言|
> |---------|---------|---------|---------|
> |一个 Epping 道路|获取新的专用|TBA|英语 (澳大利亚)|
> |一个 Marina Boulevard royal|获取新的共享|TBA|英语 (美国)、中文 (简体、中国)|
> |32伦敦 Bridge 大街|端口现有、专用|+ 44 20 7946 0001|英语 (英国)|
> |39 quai du Président Roosevelt|获取新的专用|TBA|法语 (法国), 英语 (英国)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>"会议桥" 设置

若要进一步调整用户体验, 可以配置组织范围内的选项, 以便加入音频会议会议 (会议进入和退出通知和呼叫者姓名录制)、会议组织者的 PIN 长度和电子邮件通知:

-   会议进入和退出通知以记录的名称、电话号码和音调的形式提供。

-   PIN 长度可配置为4至12位数字, 使用5位 PIN 作为默认值。

-   默认情况下, 启用音频会议许可证或任何其他管理员驱动的更改时发送的通知电子邮件。 你可以禁用此功能并控制你的组织的用户通信。

对于分配有音频会议许可证的用户, 可将默认收费电话号码 (显示在音频会议坐标中) 配置为使用:

-   租户级默认值。

-   自动分配的会议桥接电话号码。

-   为每个用户手动配置的 "会议桥" 电话号码。

特定于用户的会议桥电话号码在用户进行分发的全球或全国组织中通常很有用, 并且必须在会议邀请中提供本地号码作为默认会议桥接电话号码。

从不同城市或海外加入的参与者可以查找在租户级别配置的其他号码, 但这些号码不会直接出现在会议邀请中。 会议邀请提供一个链接, 该链接将参与者转到 "**团队会议拨入号码**" 页面, 以便他们可以查找距离其位置最接近的会议桥接电话号码。

你还可以配置每个会议组织者如何处理未经身份验证的呼叫者-是否需要会议组织者在未经身份验证的呼叫者获准之前启动会议, 或允许未经身份验证的呼叫者启动会议.

您还可以为每个用户应用其他配置, 以控制使用免费的会议桥接电话号码和从会议拨出。

> [!NOTE]
> 这些与成本相关的控件目前仅可供预览客户使用。 您可以在预览版计划中注册您的组织https://www.skypepreview.com。

使用这些控件, 你可以确定会议组织者是否可以为组织的会议提供免费的会议桥电话号码, 以及参与者是否可以从组织的会议拨出。 拨出控制的级别从完全阻止拨出的范围开始, 只允许拨出到国内号码, 从而允许拨出到国内和国际号码。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定你的组织是否需要 "进入" 和 "退出" 通知, 如果需要, 则为要实现的通知类型 (音调、电话号码或录制的名称)。</li><li>确定满足组织安全要求的音频会议 PIN 长度。</li><li>确定你的组织是否需要控制与音频会议服务相关的用户通信。</li><li>确定要分配给每个会议组织者的会议桥接电话号码。</li><li>确定某些会议组织者是否需要对其会议使用免费的会议桥接电话号码。</li><li>确定某些会议组织者是否需要允许未经身份验证的呼叫者启动会议。</li><li>确定某些会议组织者是否需要进行会议拨出。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录详细的会议桥设置 (进入和退出通知、PIN 长度、配置更改电子邮件通知)</li><li>记录要分配给每个会议组织者的会议桥接电话号码, 以及用于控制未经身份验证的呼叫者和免费拨出控件的策略的相应设置。</li></ul>|

> [!TIP]
> 您的会议桥设置可以记录如下示例中所述。
> 
> |         |         |
> |---------|---------|
> |启用会议进入和退出通知|已启用|
> |进入/退出通知类型|肤色|
> |邀请呼叫者在加入会议之前录制其姓名|已禁用|
> |PIN 长度|5|
> |如果其拨入设置发生更改, 则自动向用户发送电子邮件|已禁用|

<br>

> [!TIP]
> 你可以使用以下示例为音频会议用户记录 "会议桥设置" 作业列表。
>
> |用户  |Office  |默认收费电话号码  |默认免费电话号码  |允许免费通话  |未经身份验证的呼叫者绕过大厅  |会议拨出  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|一个 Epping 道路|TBA|TBA|是|已启用|国际和国内|
> |Alex Wilber|一个 Epping 道路|TBA|TBA|否|已禁用|不允许|
> |Ben Walters|一个 Epping 道路|TBA|TBA|否|已禁用|不允许|
> |Christie Cline|一个 Marina Boulevard royal|TBA|TBA|是|已禁用|版|
> |Debra Berger|一个 Marina Boulevard royal|TBA|TBA|是|已启用|版|
> |先生|一个 Marina Boulevard royal|TBA|TBA|是|已启用|版|
> |Emily Braun|32伦敦 Bridge 大街|+ 44 20 7946 0001|TBA|是|已启用|不允许|
> |Lidia Holloway|32伦敦 Bridge 大街|+ 44 20 7946 0001|TBA|是|已禁用|不允许|
> |Lahr 港|32伦敦 Bridge 大街|+ 44 20 7946 0001|TBA|是|已禁用|不允许|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|否|已禁用|版|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|是|已启用|国际和国内|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|否|已禁用|版|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

对于音频会议实施, 您可以选择购买新电话号码或转移/端口现有电话号码。

若要允许用户以他们习惯的方式拨打电话号码 (例如, 忽略本地呼叫的区域代码、忽略国内电话的国家/地区代码, 或者甚至在执行电话会议时使用短数字拨号), 则可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新的电话号码

Microsoft cloud voice 解决方案中的两种电话号码类型如下:

-   订阅者 (用户) 号码, 可分配给您的组织中的用户。

-   服务号码, 作为收费电话和免费服务号码, 其具有比订户号码更高的并行通话容量, 并且可以分配给诸如音频会议、自动助理或呼叫队列等服务。

有关这些电话号码类型的详细信息, 请参阅[用于通话计划的不同类型的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

你可以获取的电话号码的总数取决于电话号码类型以及已购买并分配给你的用户的许可证数量。

说到服务号码, 您需要仔细规划您的音频会议实施。 评估您的企业是否需要专用的会议桥电话号码;如果不是, 您的组织可以选择使用共享的会议桥电话号码。

有关您可以获取的电话号码总数的详细信息, 请参阅[您可以获取多少个电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定将从 Microsoft 获取新电话号码的用户位置或办事处。</li><li>确定要从 Microsoft 获取的电话号码的类型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录将从 Microsoft 获取新电话号码的用户位置或办事处。</li><li>记录要从 Microsoft 获取的电话号码的类型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>转移现有电话号码

如果你的组织想要将现有电话号码转移 (或端口) 到 Microsoft, 你可以通过向 Microsoft 提交端口订单请求来执行此操作。

您可以同时转移您的所有现有电话号码 (完整端口), 并且在某些市场中, 您可以转移现有电话号码的子集 (部分端口)。 如果您只想将电话拨入式会议网桥移动到音频会议服务, 部分端口会很有用。

单个端口订单只能将电话号码转移到单个电话号码类型。 如果你需要将某些电话号码作为订户号和某些服务号码进行传输, 我们建议你首先完成到 Microsoft 的传输, 然后在数字位于 Microsoft 控制范围内时立即执行转换。

或者, 如果支持部分端口, 则可以提交多个端口请求, 一次一个端口请求。 但是, 此备用方法将使您的现有电信服务提供商延长您的合同。

电话号码移植是一个复杂的主题, 需要全面规划、协调和充分管理利益干系人的预期。 若要了解详细信息, 请参阅以下文章:

-   [将电话号码转移到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [转接电话号码常见问题](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

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

> [!Important]
> 每个租户拨号计划中最多可以有25个规范化规则;因此, 请务必避免将已提供的规范化规则作为服务拨号计划的一部分。

若要了解有关拨号计划的详细信息, 请参阅[什么是拨号计划？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定您的组织是否需要自定义的拨号计划 (业务要求、采纳要求等)。</li><li>如果适用, 请确定租户拨号计划 (租户-全局或租户-用户) 的范围, 以支持自定义的拨号计划的要求。</li><li>如果适用, 请确定你将创建的租户拨号计划, 以支持云语音实现的作用域内的用户位置或分支机构。</li><li>如果适用, 请确定需要为每个用户分配自定义拨号计划和租户拨号计划的用户。</li></ul>|
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

-   音频会议服务网站支持列表

-   音频会议组织者的许可证分配列表

-   通讯信用点数计划号码

-   会议网桥详细信息

-   "会议桥" 设置

-   会议桥设置分配

-   电话号码购买计划

-   租户拨号计划

-   拨号计划作业

<!--ENDOFSECTION-->