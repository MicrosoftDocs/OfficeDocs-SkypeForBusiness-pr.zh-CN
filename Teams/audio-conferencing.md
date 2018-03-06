---
title: "Microsoft Teams 中的音频会议实践指导"
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/22/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: "使用展望（规划）、上线（交付）、推动价值（运营）框架在 Microsoft Teams 中规划、部署和管理音频会议的实践指导。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f845be7ddf83605adad119f7efa53725033a7823
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a>Microsoft Teams 中的音频会议实践指导
============================================================

Office 365 中的音频会议允许参与者从任何电话加入 Teams 会议。

下面是使用 Office 365 中的[音频会议](https://go.microsoft.com/fwlink/?linkid=858992)完成的内容。

此实践指导介绍 Office 365 FastTrack 客户旅程框架及其三个阶段（展望、上线和推动价值），帮助你规划、交付和运营音频会议实施以获得成功的业务成果。

> [!TIP]
> 在此实践指导中，我们为每个活动和关键讨论提供了示例输出。 本文档中的示例包含在“提示”标注中，它们是可以重用的模板。 对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。

展望 <a name="Envision_AudioConferencing"> </a>
=========

展望阶段提供 Office 365 客户旅程的基础，适用于音频会议等所有工作负荷。

在此阶段，确定业务目标，并集合相关项目利益干系人，以最终交付：

-   高级成功计划，包含业务用例、关键利益干系人、目标和关键成果 (OKR)、关键成功指标 (KSI)、风险、环境评估、采用就绪和运营计划。

-  详细的音频会议技术实施计划，以达到所需的最终状态。

<a name="define-business-use-cases-for-audio-conferencing"></a>定义音频会议的业务用例
------------------------------------------------

音频会议允许会议参与者使用传统座机、PBX 或移动电话拨号通过 PSTN（公用电话交换网）加入会议，从而为组织提供了连接任何会议（临时和安排的会议）的附加入口点。

在以下情况下，这很有用：当组织者或参与者不在计算机前时，当数据连接不可用或不可靠而无法支持语音通信（例如，在移动数据覆盖范围不稳定的远程区域中）时，如果连接到带宽有限的免费公共 Wi-Fi 服务，或者会议参与者更愿意使用他们方便接触到的电话服务终结点拨号加入会议时。

在此步骤中，核心项目利益干系人将定义支持实施音频会议的业务用例。

业务用例的目的是定义和记录预期的可衡量业务成果，包括以下内容：

-   当前业务流程说明
-   定义现有业务流程上的挑战
-   技术如何帮助克服这些挑战
-   克服了这些挑战的情况下预期的可衡量业务成果

> [!TIP]
> 下面是完成的业务用例示例：
>|         |
>|---------|
>|**当前业务流程说明**<br>Contoso 当前依赖现任本地电话服务提供商提供的 PSTN 会议服务，按内部会议和涉及外部各方的会议的会议分钟数收费。|
>|**现有业务流程上的挑战**<br>Contoso 每年为当前 PSTN 会议服务支出大约一百万美元，产生的 75% 的成本用于内部会议。<br>使用传统电话服务终结点加入 PSTN 会议服务托管的会议与组织采用 Teams 作为新式通信与协作平台的计划不一致。|
>|**技术如何能够克服这些挑战**<br>通过采用 Microsoft Teams 作为新式通信与协作平台，要求内部用户主要使用其配备了优化耳机的 PC 和会议室设备加入会议。 音频会议服务将可用于支持外部参与者或支持内部参与者不便使用 PC 音频的情况。|
>|**预期的可衡量业务成果**<br>迁移至作为新式通信与协作平台的 Teams，并结合使用音频会议服务，将会大大降低交付 PSTN 会议服务的成本，预期 Contoso 要支出的成本大约只是现有 PSTN 会议服务的年度成本的 20%。|

除了定义你的业务用例外，在继续执行展望阶段的下一步之前，还应澄清以下事项：
- 组织范围和
- 项目时间线

<a name="identify-key-stakeholders"></a>确定关键利益干系人
-------------------------

在上一步中定义的业务用例将包括音频会议实施的组织范围，基于此，可以完成综合性的利益干系人矩阵以包含要在项目中涉及的合适人员。

> [!TIP]
> 下面是可以用于记录项目利益干系人的利益干系人列表模板示例：
>|角色  |说明  |姓名、联系人信息、位置  |
>|---------|---------|---------|
>|项目执行发起人|<ul><li>对项目和按项目目标交付具有最高权力和责任</li><li>协助解决项目主管上提的问题</li><li>提倡在公司内就项目目标进行沟通</li><li>负责制定关键的战略决策</li><li>负责提供所需的资源和预算</li><li>主导季度业务回顾 (QBR)</li><li>认可和支持认知推行活动工作</li><li>担当项目部署的项目发起人</li></ul>|TBA|
>|项目主管|<ul><li>管理和领导项目团队</li><li>协调参与项目的合作伙伴和工作团队</li><li>负责制定和管理项目计划以符合季度关键结果</li><li>解决跨智能的问题</li><li>向项目发起人提供定期更新</li><li>将采用的各方面合并到整体项目计划中</li><li>领导月度业务和运营回顾 (MBR)，为季度业务回顾做准备</li></ul>|TBA|
>|协作主管/架构师|<ul><li>负责执行公司高层制定的协作策略</li><li>为公司分析和选择符合业务目标的协作产品</li><li>负责设计协作产品的运营</li><li>定义运营和支持模式</li><li>为月度和季度业务回顾做准备</li><ul>|TBA|
>|顾问|<ul><li>负责配置服务</li><li>参与整体解决方案体系结构</li></ul>|TBA|
>|项目经理|<ul><li>开发和维护项目计划</li><li>按照项目计划和预算管理项目交付物</li><li>记录和管理项目问题，包括上提问题</li><li>每周鼓舞士气</li><li>与项目执行发起人保持联系并向其提供更新</li><li>与架构师合作定义变更管理方法和通信计划</li></ul>|TBA|
>|变更管理/采用专业人员|<ul><li>在发现阶段向采用和培训流程提供信息</li><li>参与采用策略研讨会</li><li>制定和负责采用策略</li><li>制定和执行通信计划</li><li>负责向最终用户提供培训</li><li>收集反馈和进行调查</li></ul>|TBA|
>|网络主管|<ul><li>在发现阶段向网络设计提供信息</li><li>在展望研讨会期间参与计划</li><li>在项目执行期间协调网络团队的工作</li></ul>|TBA|
>|安全主管|<ul><li>在发现阶段向安全设计和流程提供信息</li><li>在展望研讨会期间参与计划</li><li>在项目执行期间协调安全团队的工作</li></ul>|TBA|
>|电话服务主管|<ul><li>在发现阶段向电话服务设计提供信息</li><li>在展望研讨会期间参与计划</li><li>在项目执行期间协调电话服务团队的工作</li></ul>|TBA|
>|桌面主管|<ul><li>在发现阶段向客户端和更新流程提供信息</li><li>在展望研讨会期间参与计划</li><li>在项目执行期间协调桌面团队的工作</li></ul>|TBA|
>|支持主管|<ul><li>在发现阶段向运营和支持模式提供信息</li><li>在展望研讨会期间参与计划</li><li>参与支持模式计划</li><li>在项目执行期间协调支持团队/资源的工作</li></ul>|TBA|
>|业务单位代表|<ul><li>参与准备基于最终用户的采用指南和材料</li><li>参与并检查业务用例</li></ul>|TBA|
>|部署主管|<ul><li>确保满足部署先决条件</li><li>请客户资源参与准备和部署阶段活动</li><li>参与会议以检查准备和部署状态</li></ul>|TBA|
>|IT 管理员|<ul><li>负责为测试计划和执行提供协助的 IT 专业人士</li></ul>|TBA|
>|服务所有者|<ul><li>负责音频会议服务整体的运营</li><li>音频会议服务的所有者</li></ul>|TBA|
>|质量支持者|<ul><li>推动质量、可靠性和用户反馈</li><li>了解质量趋势，并与各个团队一起推动采取补救措施</li><li>通过指导委员会向领导汇报</li><li>通过“为我的通话评分”和“净推荐值”报告质量、可靠性和用户看法</li></ul>|TBA|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>定义目标和关键结果、关键成功指标及风险
--------------------------------------------------------------------

集合了项目利益干系人后，可以将业务用例、组织范围和项目时间线转换为目标和关键结果 (OKR)，以及将衡量项目成功的方式定义为一组关键成功指标 (KSI)。

定义 OKR 和 KSI 时项目利益干系人全面参与将确保归属感，并且它们将与组织的业务需求一致。

OKR 将包含在项目开始时设定的一组目标，并具有按季度定义的可衡量的关键结果。 按月检查关键结果以跟踪整个项目的状态，并且基于进度，可以根据需要对季度计划进行调整。

> [!TIP]
> 与音频会议实施相关的 OKR 示例参考如下：
><br>
>
>**愿景：通过最大限度地利用 Office 365 投资来提高工作效率**
>|目标  |关键结果  |待办事项  |
>|---------|---------|---------|
>|到 2018 财年结束时在 Teams 中部署音频会议|FY18Q1：在 Teams 中部署音频会议（全球）|展望<ul><li>制定成功计划</li><li>制定详细的技术实施计划</li></ul><p>上线<ul><li>执行成功计划</li><li>执行技术实施计划</li></ul>|
>|到 2018 财年中期全球停用旧的 PSTN 会议服务|FY18Q2：全球停用旧的 PSTN 会议服务|推动价值<ul><li>激励用户参与并推动采用</li><li>管理和准备变更</li><li>衡量、分享成功以及重复进行</li>|

KSI 通过详细记录好和/或坏的结果来衡量质量和是否成功得到关键结果，以及补充 IKR 的二元性质（实现或未实现）。 定义 KSI 时，我们建议利用“具体、可衡量、可分配、实际、时间相关”或 SMART 标准。

> [!TIP]
> 下面是与此项目相关的 KSI 示例：
>|类型  |KSI 问题和标准  |衡量方式  |成功标准  |衡量时间  |负责方  |
>|---------|---------|---------|---------|---------|---------|
>|使用/采用|通话质量与以前的解决方案一样或优于以前的解决方案|调查|80% 的用户同意或非常同意|启用和季度后|信息技术团队|
>|使用/采用|Microsoft Teams 简化了通信流程|调查|80% 的用户同意或非常同意|启用和季度后|变更管理团队|
>|使用/采用|用户主动使用解决方案|Office 365 报告、通话质量仪表板|80% 的用户每天主动使用|每天|变更管理团队|
>|使用/质量|质量较差的通话/会议的百分比应尽可能低|通话质量仪表板|每月质量较差的通话低于 5%|每天|信息技术团队|
>|使用/支持|我知道如何获取技术支持|调查|90% 的用户同意或非常同意|启用和季度后|变更管理团队|
>|使用/支持|我对技术支持的质量感到满意|调查|80% 的用户同意或非常同意|每次事故后|信息技术团队|
>|财务|旧会议分钟数减少|财务系统|符合定义的 ROI|基于 ROI|变更管理团队|

你需要在此行动中确定业务风险，以及为每个确定的风险制定迁移计划。 此信息可以收集到风险计划中。

> [!TIP]
> 风险计划可以按以下示例记录：
>|风险  |可能性  |影响  |综合  |迁移计划  |
>|---------|---------|---------|---------|---------|
>|即将进行的合并将最多添加 1,000 人|高|高|高|<ul><li>对于合并的公司，有自己的流程（展望、上线、推动价值）的单独 OKR</li><li>不在现有 OKR 中包含它们</li></ul>|
>|电话携号转网将延迟项目完成|高|高|高|<ul><li>提前准备所有所需的信息以支持电话携号转网（即：客户服务记录、帐单详细信息、授权书）</li><li>调整项目时间线以预留电话携号转网过程的周转时间</li><li>向外部参与者说明使用新的电话拨入式会议号码</li></ul>|
>|规划的网络重新设计|高|中|中|<ul><li>在将 Teams 作为新式通信与协作平台实施之前，对项目范围内的站点进行网络就绪评估</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>评估环境和采用就绪情况
--------------------------------------------------

为了实现预期 OKR，你可能必须定义解决方案的高级体系结构。 这将进行环境发现以评估与 IT 和电话服务基础结构、网络和操作有关的所有方面。

在环境发现中，将包括与最终用户计算有关的所有内容（从硬件要求到软件要求），例如，对个人计算机和移动设备进行就绪评估以支持音频会议业务用例。

环境发现还可以揭示要[将电话号码转移到 Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) 是否存在要求。 这将帮助贵组织相应地调整项目计划，并准备携号转网所需的必要信息。 你可以通过利用以下[调查表](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3)来进行环境发现。

环境发现必须包括网络就绪评估以确保网络可以支持实施音频会议服务。

可以在 [MyAdvisor 网络规划](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)工具中利用通过环境发现获取的信息（例如，Internet 连接和 WAN 拓扑的详细信息、站点链接和可用带宽）以及人员分析数据（可以转换为每个工作负荷的预期使用情况）来确定支持音频会议的网络就绪情况。 为了进一步确定网络就绪情况，可以使用 [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) 或[网络就绪评估工具合作伙伴](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners)提供的解决方案执行实时媒体流量模拟。

网络就绪评估的结果将更加清晰地提供有关成功实施音频会议所需的网络优化或补救的信息。

可以执行人员分析来评估采用就绪情况，以找出组织中可以作为实施音频会议服务的目标的一组人员。 人员分析包括确定实现预期业务结果所需的其他外设或设备。

要执行人员分析，你可以召集相关项目利益干系人、利用[人员联盟](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7)研讨会框架和[人员特征矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8)来召开研讨会。 可以使用[人员分析报告](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9)模板将人员分析研讨会的结果汇总成报告。

> [!NOTE]
> 虽然发现调查表和人员分析示例最初是为 Skype for Business Online 编写的，但大部分内容与 Teams 相关。 请随意修改和删除与你的项目目标无关的项。

你可以在环境评估和采用就绪评估中确定技术风险，并为每个确定的风险制定迁移计划。 此信息应包含在风险计划内。

<a name="map-operational-roles"></a>映射运营角色
---------------------

规划运营和确定将运营音频会议服务的团队是重要的一步，因为必须在已有首批试点用户的情况下开始运营。 每个确定的团队必须审阅并同意确定的任务和责任，然后开始为运营音频会议服务做准备。 准备工作可能包括培训和就绪、其他人员配备或确保安排外部提供商交付服务。

> [!TIP]
> 下面是用于记录你为了支持此项目而执行的运营角色映射行动的结果的模板示例：
>|运营角色  |说明  |团队  |联系详细信息  |
>|---------|---------|---------|---------|
>|服务所有者|服务所有者、与业务部门的接口、策略|TBA|TBA|
>|音频会议运营|日常运营、用户和设备帐户移动/添加/更改、监控|TBA|TBA|
>|租户管理员|更改租户范围的设置、启用新功能|TBA|TBA|
>|支持|供最终用户获取支持的接口|TBA|TBA|
>|网络运营|支持 LAN、WAN、Wi-Fi 和 Internet 访问|TBA|TBA|
>|客户端和终结点团队|管理桌面部署|TBA|TBA|
>|标识运营|管理标识基础结构（AD、ADFS、Azure AD）|TBA|TBA|
>|采用/变更管理|管理解决方案的认知、培训和采用|TBA|TBA|
>|Exchange 运营|管理 Exchange 环境|TBA|TBA|

为了便于完成更加详细的运营角色映射（包括与每个运营角色关联的任务），你可以使用[运营角色映射工作簿](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16)获取将明确角色和责任的详细信息以支持音频会议服务。

<a name="document-success-plan"></a>记录成功计划
---------------------

成功计划是在展望阶段创建的文档，包括业务案例、服务就绪、采用计划和运营计划。

成功计划将提供项目团队（可以包括 FastTrack 或部署合作伙伴），具有用于实现组织的音频会议服务目标的充分信息。

通常，成功计划包含以下主要部分：

-   业务案例
-   服务就绪
-   采用计划
-   运营计划

### <a name="business-case"></a>业务案例

业务用例、利益干系人、OKR 和 KSI、风险以及项目时间线通常组成业务案例所需的信息主体。 你需要在成功计划中记录它们。

### <a name="service-readiness"></a>服务就绪

环境评估提供确定组织实施音频会议的技术就绪情况所需的初步信息。

此处包括用于解决通过环境评估发现且需要补救的方面的计划。 你需要在成功计划中包括服务就绪评估和补救计划。

### <a name="adoption-plan"></a>采用计划

在采用就绪评估后，必须完成更加详细的计划，以便项目团队制定一套全面的通信计划、培训计划以及启动前、启动时和启动后采用活动。

在此步骤将确定用于支持采用活动的资源（例如，传单、欢迎电子邮件和培训材料）以及满足组织需求所需的任何自定义项。

[此处](https://www.microsoft.com/download/details.aspx?id=54244)提供了适用于采用活动的模板。

### <a name="operational-plan"></a>运营计划

运营角色映射行动将设立角色和责任以及为每个运营角色分配的团队以支持实施音频会议。

你需要完成此项，并在成功计划中包括运营计划以确保完成解决方案的运营就绪。

<br>
音频会议技术规划
-----------------------------------------

为了规划音频会议的技术实施，必须提前制定一系列决策，让贵组织做好更充分的准备以便实施满足业务需求的解决方案。 这些决策将记录到技术实施计划中。

## <a name="availability-of-audio-conferencing"></a>音频会议可用情况

在这些[国家和地区](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)提供音频会议。

> [!IMPORTANT]
> 由于受到法律约束的原因，为了向跨国组织提供音频会议，必须从音频会议服务覆盖的国家和地区或销售音频会议服务的地方提供 Office 365 订阅的合同。

确定贵组织符合获取音频会议服务的条件后，将根据可用国家和地区列表编写将实施音频会议服务的用户位置或办公地点列表。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定哪些用户位置或办公地点将实施音频会议服务</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录要支持音频会议服务的用户位置或办公地点</li></ul>|

> [!TIP]
> 下面是具有通话套餐的电话系统地点支持列表模板示例：
>|办公地点   |位置 |PSTN 会议服务  |
>|---------|---------|---------|
>|Epping 路一号|澳大利亚|音频会议|
>|数码港道 100 号|香港 SAR|旧的 PSTN 会议|
>|滨海林荫道一号|新加坡|音频会议|
>|伦敦桥大街 32 号|英国|音频会议|
>|39 quai du Président Roosevelt|法国|音频会议|

## <a name="licensing-for-audio-conferencing"></a>许可音频会议

[音频会议许可证](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)作为 Office 365 E5 订阅计划的一部分提供，或者作为 Office 365 E1 或 Office 365 E3 订阅计划的附加内容提供。

> [!NOTE]
> Teams 中的 PSTN 或电话拨入式会议不支持第三方<sup></sup>音频会议提供商 (ACP)。<br>如果你现在已使用 Skype for Business Online PSTN 会议，则可以立即利用 Teams 中的音频会议。

为了提供免费电话会议桥接电话号码以及支持向国际电话号码拨出的会议，你需要为贵组织设置[通信点数](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

> [!IMPORTANT]
> 在有些国家/地区，仅通过免费电话会议桥接电话号码提供服务，这种情况下，在此类国家/地区，必须使用通信点数以支持拨入。

实施通信点数时首先要考虑的是确定要购买的初始资金数额。 可以参考[通信点数](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)一文中的建议资金数额。

如果贵组织选择使用自动充值，[通信点数](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)文档中也提供了触发数额（最低资金数额）建议。 自动充值数额需要由实际使用情况确定。 应持续监控通信点数使用情况，并根据需要调整充值数额。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>如果贵组织尚未购买所需的音频会议许可，确定是通过提升现有 Office 365 订阅还是通过购买音频会议外接程序来获取音频会议许可证</li><li>确定实施音频会议是否需要通信点数。 如果是，确定要购买的初始资金数额。 在适用的情况下，确定触发数额和自动充值数额。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录将为其分配音频会议许可证的用户</li><li>记录通信点数计划（初始数额、触发数额、自动充值数额）</li></ul>|

> [!TIP]
> 可以使用以下示例记录音频会议用户的许可证分配列表：
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
>|Pradeep Gupta|伦敦桥大街 32 号|Office 365 E5|
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

## <a name="conference-bridge-phone-numbers"></a>会议桥接电话号码

Office 365 中的音频会议服务包括：

-   多种类型的会议桥接电话号码（收费电话和免费电话）
-   多种类别的电话号码（专用和共享）
-   对会议桥接支持多种语言（主要和辅助）
-   租户的默认电话号码

有关包含的功能的完整说明，请参阅[为 Skype for Business 和 Microsoft Teams 设置音频会议](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)以及[用于音频会议的电话号码](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)。

> [!NOTE]
> 根据[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)中所述的适用许可证数量，专用会议网桥电话号码的数量不超过每个租户可以获取的电话号码限制。 免费电话会议桥接电话号码需要通信点数。

如果存在必须转移到音频会议服务的现有会议桥接电话号码，假定它们满足国家/地区特定的要求，那么可以将现有会议桥接电话号码转移到 Microsoft。

> [!NOTE]
> 将电话号码转移到 Microsoft 的复杂性根据国家或地区、运营商、涉及的线路数量以及许多其他影响因素而有很大不同。 要计划电话携号转网，请查看[携号转网指南](https://go.microsoft.com/fwlink/?linkid=859011)。

有关将电话号码转移到音频会议服务的其他详细信息，请参阅[将电话号码转移到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定组织是否需要专用会议桥接电话号码</li><li>确定将如何为音频会议实施的范围内用户位置或办公地点获取专用会议桥接电话号码（从 Microsoft 获取，或转移现有电话号码）</li><li>如果你选择从 Microsoft 获取，请确定用于为音频会议实施的范围内用户位置或办公地点获取电话号码的方法（表单提交或自动）。</li><li>确定要为每个专用会议桥接电话号码设置的语言首选项</li><li>确定租户默认会议桥接电话号码</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录电话号码获取的主计划，详细说明为音频会议实施的范围内每个用户位置或办公地点获取电话号码的方式。</li><li>如果适用，完成<a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">新电话号码请求表单</a>，每个位置或办公地点一个表单。</li><li>如果你选择转移现有电话号码，请参阅<a href="https://go.microsoft.com/fwlink/?linkid=859011">携号转网指南</a>以对其进行计划并相应地调整音频会议实施时间线。</li><li>记录详细的会议桥接电话号码配置（共享和专用会议桥接电话号码、每个专用会议桥接电话号码的语言首选项、租户默认会议桥接电话号码）</li></ul>|

> [!TIP]
> 下面是获取会议网桥详细信息的模板示例：
>|办公地点   |桥接号码获取和桥接类型 |桥接号码  |桥接语言|
>|---------|---------|---------|---------|
>|Epping 路一号|获取新的专用|TBA|英语（澳大利亚）|
>|滨海林荫道一号|获取新的共享|TBA|英语（美国）、中文（简体，中国）|
>|伦敦桥大街 32 号|转网现有的专用|+44 20 7946 0001|英语（英国）|
>|39 quai du Président Roosevelt|获取新的专用|TBA|法语（法国）、英语（美国）|

## <a name="conference-bridge-settings"></a>会议桥接设置

提供了与音频会议加入体验（会议进入和退出通知以及呼叫方名称记录）、会议组织者的 PIN 长度及电子邮件通知的组织范围的配置选项，以进一步定制最终用户体验。

-   会议进入和退出通知以记录的名称、电话号码和声音形式提供。
-   PIN 长度可配置为 4 到 12 位，默认为 5 位 PIN。
-   默认情况下，在启用音频会议许可证或管理员完成的任何其他更改后，启用通知电子邮件。 你可以禁用此功能并控制贵组织的最终用户通信。

对于为其分配了音频会议许可证的用户，可配置默认的收费/免费电话号码（在音频会议协调中显示）以使用：

-   租户级别默认电话号码，或
-   自动分配的会议桥接电话号码，或
-   手动为每个用户定义的会议桥接电话号码。

对于用户分散在各地且必须在会议邀请中提供本地号码作为默认会议桥接电话号码的全球性或全国性组织，用户特定的会议桥接电话号码通常很有用。

从不同城市或国家/地区加入的参与者可以查找在租户级别配置的其他号码，但这些号码并不直接显示在会议邀请中。 会议邀请提供一个链接，参与者通过该链接可访问 Teams 会议拨入号码页面，在该页面中可查找距离其位置最近的可用会议桥接电话号码。

你还可以配置各个会议组织者如何处理未经身份验证的呼叫方，是要求会议组织者先开始会议才能允许未经身份验证的呼叫方加入，还是允许未经身份验证的呼叫方开始会议。

提供了可以针对每个用户应用的其他配置，用于控制使用免费电话会议桥接电话号码和从会议拨出。

> [!NOTE]
> 这些与成本相关的控制当前仅预览版用户可用。 你可以在 [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) 上注册贵组织参与预览版计划。

通过这些控制，你可以确定会议组织者是否可以为其组织的会议提供免费电话会议桥接电话号码，以及控制参与者是否可以从其组织的会议拨出。 拨出控制级别涵盖不允许拨出、仅允许拨出到国内号码、允许拨出到国内号码和国际号码。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定组织是否需要进入和退出通知，如果需要，确定要实施的通知类型（声音、电话号码或记录的名称）</li><li>确定满足组织安全要求的音频会议 PIN 长度</li><li>确定组织是否要控制与音频会议服务有关的最终用户通信</li><li>确定要分配给每个会议组织者的会议网桥电话号码</li><li>确定某些会议组织者是否需要能够在其会议中使用免费电话会议桥接电话号码。</li><li>确定某些会议组织者是否需要能够允许未经身份验证的呼叫方开始会议</li><li>确定某些会议组织者是否需要控制会议拨出</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录详细的会议网桥设置（进入和退出通知、PIN 长度、配置更改电子邮件通知）</li><li>记录要分配给每个会议组织者的会议网桥电话号码，以及用于控制未经身份验证的呼叫方策略、免费电话和拨出的相应设置</li></ul>|

> [!TIP]
> 可以按如下所示记录会议网桥设置：
>|         |         |
>|---------|---------|
>|启用会议进入和退出通知|启用|
>|进入/退出通知类型|声音|
>|要求呼叫方在加入会议之前记录其名称|禁用|
>|PIN 长度|5|
>|如果用户的拨入设置发生变化，自动向其发送电子邮件|禁用|

<br>
> [!TIP]
> 可以使用以下示例记录音频会议用户的会议网桥设置分配：
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
>|Pradeep Gupta|伦敦桥大街 32 号|+44 20 7946 0001|TBA|是|禁用|不允许|
>|Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|
>|Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|是|启用|国际和国内|
>|Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|否|禁用|国内|

## <a name="dial-plans"></a>拨号计划

Office 365 的电话系统功能中的[拨号计划](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)是一组规范化规则，用于将拨打的电话号码转换为替代格式（通常为 [E.164](https://go.microsoft.com/fwlink/?linkid=859014) 格式）以便进行呼叫授权和呼叫路由。 音频会议服务利用电话系统使用的相同功能在会议拨出应用场景中转换拨打的电话号码。

拨号计划允许用户按其习惯的方式（例如，对于本地呼叫省略区号，对于国内呼叫省略国家/地区代码，甚至在进行会议拨出时使用简短数字拨号）拨打电话号码。

在 Office 365 的电话系统功能中，有两种类型的拨号计划：

-   **服务拨号计划**。 这是默认的拨号计划，基于 Office 365 使用位置适用于用户，无法修改。
-   **租户拨号计划**。 这是租户中的自定义拨号计划，进一步分成两种类型：
    -   **租户-全局拨号计划** - 该拨号计划适用于租户中的所有用户。
    -   **租户-用户拨号计划** - 该拨号计划仅适用于特定用户。

> [!NOTE]
> 有关进一步详细信息和示例，请参阅[什么是拨号计划？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)文档。

分配给用户的有效拨号计划是服务拨号计划（基于用户的 Office 365 使用位置）和租户拨号计划（可以是租户-全局拨号计划或租户-用户拨号计划）的组合。

![此表显示服务和租户拨号计划的三种组合。](media/audio_conferencing_image8.png)

每个租户拨号计划中最多可以有 25 个规范化规则，因此，需要避免重复出现已作为服务拨号计划的一部分提供的规范化规则。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定贵组织是否需要自定义拨号计划（业务需求、采用需求等）</li><li>如果适用，确定租户拨号计划的范围（租户-全局或租户-用户）以支持自定义拨号计划的要求</li><li>如果适用，确定为支持音频会议实施的范围内用户位置或办公地点将创建的租户拨号计划</li><li>如果适用，确定哪个用户需要自定义拨号计划以及要为每个用户分配的租户拨号计划</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录自定义拨号计划和要配置为音频会议实施的一部分的关联规范化规则</li><li>记录要为其分配自定义拨号计划的用户以及要为每个用户分配的租户拨号计划</li></ul>|

> [!TIP]
> 如果适用于你的项目，你可以使用以下模板来记录租户拨号计划配置：
>|租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_新南威尔士北莱德 Epping 路一号，AU 拨号计划_|**AU-NSW-NorthRyde-OER-Internal**<br>_澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_澳大利亚新南威尔士的本地号码规范化_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_澳大利亚的免费电话号码规范化_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_澳大利亚的服务号码规范化_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_新加坡 OMB，SG 拨号计划_|**SG-OMB-Internal**<br>_新加坡 OMB 办公地点的内部号码 (x8000 - x8999)_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_新加坡的免费电话号码规范化_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_新加坡的服务号码规范化_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划_|**FR-39qdPR-Internal**<br>_法国 Issy-les-Moulineaux 39 quai du Président Roosevelt 办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+3319999$1<br>True|
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
>|Pradeep Gupta|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|

## <a name="microsoft-teams-configurations"></a>Microsoft Teams 配置

临时和安排的会议支持音频会议。 对于安排的会议，必须启用控制会议安排（私人会议和频道会议）的租户级别配置。

> [!NOTE]
> 当前，如果贵组织具有合规性要求以确保所有会议讨论均可发现，当组织者有本地 Exchange 邮箱时，你应禁用私人会议。<br>
> 在另外一个用例中，如果组织中的所有会议都必须仅**对受邀各方**可见，为了避免向未受邀各方透露会议信息，我们建议禁用在**频道**中安排会议的功能。

这些设置以租户级别配置方式提供，适用于组织中的所有用户，将影响 Teams 中的所有会议安排，并不限于**使用**音频会议的 Teams 会议。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定组织需要启用还是禁用安排私人会议</li><li>确定组织需要启用还是禁用安排频道会议</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>记录 Teams 的会议安排配置</li></ul>|

> [!TIP]
> 可以按如下所示记录 Teams 会议配置：
>|         |         |
>|---------|---------|
>|允许安排私人会议|启用|
>|允许安排频道会议|禁用|

## <a name="document-technical-implementation-plan"></a>记录技术实施计划

使用上面的决策点记录你的技术实施计划。
此技术实施计划将为项目团队（可以包括 FastTrack 或部署合作伙伴）提供为实施音频会议执行技术上线所需的信息。

通常，技术实施计划包含以下主要部分：

-   音频会议服务地点支持列表

-   音频会议组织者的许可证分配列表

-   通信点数计划数量

-   会议桥接详细信息

-   会议桥接设置

-   会议桥接设置分配

-   租户拨号计划

-   拨号计划分配

-   Microsoft Teams 会议配置

<br>
完成成功计划和技术实施计划后，你现在即可带领贵组织进入 Office 365 客户旅程的后续步骤。

<br>
上线 =======

*即将提供。*

<br>
推动价值 ===========

*即将提供。*

<br>
## <a name="see-also"></a>另请参阅

[设置 Skype for Business 和 Microsoft Teams 音频会议](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)