---
title: 对于 Microsoft 小组中的音频会议企业测试计划
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 验证通过团队特征、 功能，以及可用性测试音频会议符合您所在组织的期望。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0630cb5bf054c693f1175101f9e1edbe7c408b2f
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="define-and-document-your-audio-conferencing-in-teams-test-plan-for-enterprises"></a>定义和记录的企业团队在测试计划中的音频会议 
===============================================================================

已定义并记录您团队的业务成功和技术实现计划中的音频会议构想阶段的一部分后下, 一步通过功能，满足公司的期望和要求验证功能和易用性。 试验或最终部署在生产环境中部署之前，您应该执行此验证步骤。

您可以利用业务成功计划构想阶段，作为确定活动、 期望、 特性/功能的测试用例和总体范围的测试阶段进行评估的基础定义。

<a name="identify-testing-support-stakeholders"></a>确定测试支持利益干系人
-------------------------------------

在您准备评估音频会议功能，创建测试的支持利益相关者列表，以确定支持测试阶段所需的角色。

> [!TIP]
> 随着填充测试支持利益相关者列表的团队，您可能会看到一些角色都在构想阶段，但是与倾斜向测试角色说明标识的相同。 您可能需要其他的角色，具体取决于您的测试方案的独特要求。

#### <a name="teams-testing-support-stakeholder-matrix"></a>团队测试支持利益相关者列表

> [!TIP]
> 下面是一个示例可用于文档支持测试阶段时所需的利益干系人的测试支持利益相关者模板。

| 角色                          | 角色描述                                                                                                                                                                          | 分配的资源、 联系人信息和位置 |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| 测试上级主管  | <ul><li>确保团队的功能能够满足业务需求;执行发起人都熟知关键业务成果，并优先的使用的情况。</li><li>作为最大的权限，并且假定负责团队功能测试目标。</li><li>帮助解决升级的测试导致的问题。</li><li>发起有关测试目标公司内部的沟通。</li><li>负责作出关键的战略决策。</li><li>是负责确保的可用性所需的资源和预算支持测试工作。</li><li>推动意识和在测试市场活动与其他主要的利益相关者的购买。</li><li>计算测试阶段作为测试的赞助商。</li></ul>                                                 | 待定                                                  |
| 指导委员会成员    | <ul><li>保持兴趣并提供音频会议服务部署的总体方向的指导。<li>Evangelizing 通过在组织推动购买战略性洞察力帮助。</li></ul>                                                                        | 待定                                                  |
| 项目主管                  |<ul><li> 管理和领导项目团队。</li><li>协调合作伙伴和从事项目工作团队。</li><li>负责创建和管理项目计划以满足关键的季度结果。</li><li>解决跨职能部门的问题。</li><li>项目主办方提供的定期更新。</li><li>包含在测试结果中标识到整体用户采用计划的关键用户体验经验教训。</li><li>领导每月业务和操作考核，每季度业务回顾。</li></ul>                                                                                                                                                         | 待定                                                  |
| 协作主管/架构师  | <ul><li>负责执行由公司执行官协作战略。</li><li>分析并选择协作产品为公司符合业务目标。</li><li>负责设计的协作产品的操作。</li><li>定义操作和支持模型。</li><li>参与每月和每季度业务回顾。</li></ul>                                                                                                 | 待定                                                  |
| 项目经理               | <ul><li>开发和维护项目计划。</li><li>管理嵌入项目计划和预算的项目可交付结果。</li><li>记录和管理项目问题，其中包括升级。</li><li>开展每周都站立通电话。</li><li>请联系，然后对项目执行发起人提供更新。</li><li>使用内部更改管理和通信小组，以更新更改管理的方法和通信计划，根据需要。</li></ul>                                                                                                                                                   | 待定                                                  |
| 网络主管                  | <ul><li>在发现阶段对网络设计中提供输入。</li><li>参与规划在构想阶段研讨会。</li><li>在项目执行过程中协调网络组的工作。</li></ul>                                                                                                                               | 待定                                                  |
| 安全主管                 | <ul><li>在发现阶段对安全设计和流程提供输入。</li><li>参与规划在构想阶段研讨会。</li><li>在项目执行过程中协调安全小组的工作。</li></ul>                                                                                                                | 待定                                                  |
| 电话服务主管                | <ul><li>在发现阶段对电话设计提供输入。</li><li>参与规划在构想阶段研讨会。</li><li>在项目执行过程中协调电话服务团队的工作。</li></ul>                                                                                                                           | 待定                                                  |
| 桌面主管                  | <ul><li>在发现阶段对客户端和更新过程提供输入。</li><li>参与规划在构想阶段研讨会。</li><li>在项目执行过程中协调桌面团队的工作。</li></ul>                                                                                                              | 待定                                                  |
| 业务单位代表 | <ul><li>为采用基于用户的指南和资料做出贡献。</li><li>参与其中并复查，业务用例。</li></ul>                                                                                                                                   | 待定                                                  |
| IT 管理员                     | <ul><li>协助测试规划和执行 （该角色仅适用于 IT 专业人员）。                                                                                                                       | 待定                                                  |
| 服务所有者                 | <ul><li>负责操作的音频会议服务，所有最多。</li><li>作为所有者的音频会议服务。</li></ul>                                                                                                               | 待定                                                  |
| 测试主管/经理             | <ul><li>定义测试计划，包括活动、 依赖关系、 环境、 目标、 战略、 资源 （环境和人力资源） 和支持测试阶段所需的时间线。</li><li>协调交货和准备测试计划依赖关系。</li><li>与缺陷分辨率的适当优先级相一致。</li><li>作为测试所出现的问题上报路径。</li><li>交流和报告与内部团队和指定的风险承担者的测试计划状态。</li><li>记录并显示最终的测试结果。</li></ul> | 待定                                                  |
| 音频会议测试人员     | <ul><li>查看以了解测试要求、 目标、 时间轴、 问题解决和测试用例执行的测试计划。</li><li>审查和制定支持音频会议验收和功能要求的测试用例。</li><li>执行测试用例，并记录测试结果。</li><li>记录缺陷，因为它们出现并上报给领导优先顺序和分辨率测试它们。</li><li>测试回归后已确认缺陷解决关闭出缺陷。</li></ul>                                                                | 待定                                                  |
| 网络测试人员                | <ul><li>查看以了解测试要求、 目标、 时间轴、 问题解决和测试用例执行的测试计划。</li><li>查看支持的网络准备验收和性能要求的测试用例。</li><li>执行测试相关的网络准备工作，包括网络连接性和性能验证、 QoS 验证和拆分隧道配置验证。</li><li>通过使用 MyAdvisor 通过网络规划人员完成带宽的站点范围内的验证。</li><li>记录测试结果的网络准备工作。</li><li>记录缺陷，因为它们出现并上报给领导优先顺序和分辨率测试它们。</li><li>测试回归后已确认缺陷解决关闭出缺陷。</li></ul>                                                                | 待定                                                  |
| 安全测试               | <ul><li>查看以了解测试要求、 目标、 时间轴、 问题解决和测试用例执行的测试计划。</li><li>审查和制定支持安全验收要求的测试用例。</li><li>执行测试与测试用例的安全验收。</li><li>文档安全验收测试的结果。</li><li>记录缺陷，因为它们出现并上报给领导优先顺序和分辨率测试它们。</li><li>测试回归后已确认缺陷解决关闭出缺陷。</li></ul>                                                                | 待定                                                  |
| 电话测试人员              | <ul><li>查看以了解测试要求、 目标、 时间轴、 问题解决和测试用例执行的测试计划。</li><li>检查支持服务编号移植验收和功能要求的测试用例。</li><li>执行测试相关数字移植，包括服务编号端口到 Office 365 提供服务。</li><li>执行测试用例和测试用例结果文档。</li><li>记录缺陷，因为它们出现并上报给领导优先顺序和分辨率测试它们。</li><li>测试回归后已确认缺陷解决关闭出缺陷。</li></ul>                                                                | 待定                                                  |
| 音频会议管理测试 | <ul><li>查看以了解测试要求、 目标、 时间轴、 问题解决和测试用例执行的测试计划。</li><li>审查和制定支持音频会议管理验收和功能要求的测试用例。</li> <li>执行测试用例和测试用例结果文档。</li><li>记录缺陷，因为它们出现并上报给领导优先顺序和分辨率测试它们。</li><li>测试回归后已确认缺陷解决关闭出缺陷。</li></ul>                                                                | 待定                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定您需要在您的环境中测试音频会议功能的测试支持和利益相关者角色。</li><li>决定将已确定的测试支持和利益相关者角色分配哪些资源。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档在您测试支持利益相关者列表中所需的测试支持和利益相关者角色。</li><li>记录联系人信息，以及测试支持利益相关者列表中列出的每个资源位置的详细信息。
</table>


<a name="define-audio-conferencing-feature-requirements"></a>定义音频会议功能要求 
-----------------------------------------------

作为在作用域中定义用户的音频会议功能要求的一部分，一个应该在构想阶段完成的第一步就是[角色分析](https://docs.microsoft.com/MicrosoftTeams/audio-conferencing#assess-environment-and-evaluate-adoption-readiness)，在其中定义您的音频会议角色和方案。 标识此基线下, 一步是评估新的团队公用路线图，以确定：

-   音频会议功能您将部署的作用域中的用户。

-   预计用户音频会议功能的需求，提供您当前的 Skype 业务、 交换和 SharePoint 部署环境。

-   是否可以确认最新的公共路线图所述音频会议功能满足用户、 功能和部署在时间轴中的范围要求

> [!TIP]
> 用于识别范围中的音频会议功能为您的部署可以在上找到最新的团队路线图<https://aka.ms/skype2teamsroadmap>。

既然已定义的音频会议的角色和功能，下一步评估标准将与团队的互操作性体验。 有关互操作性经验以及可用的配置选项的其他信息，请参阅[Microsoft 小组和 Skype 业务互操作性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)。

#### <a name="audio-conferencing-feature-definition"></a>音频会议功能定义

> [!TIP]

> 下面是可以使用音频会议定义模板的示例文档的音频会议管理和用户组功能进行评估。

| 企业级   | 协作会议    | 平台和设备   | IT 专业人员  | 特定于站点的其他业务组  | 由最新团队路线图满足需求 |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>计划通过音频会议会议：<ul><li>Outlook 日程安排接</li><li>Teams 客户端</li></ul></li><li>承载通道和专用会议</li><li>主持会议，与会者达 80</li><li>音频会议功能</li><li>匿名的联接</li><li>会议厅的支持</li><li>参与者的管理</li><li>将其他参与者设为静音</li><li>通过团队客户端的设备管理</li></ul> |<ul><li>生命周期管理前/中/后会议</li><li>桌面共享</li><li>对话</li><li>令人陶醉的会议体验</li><li>应用程序共享</li><li>授予/带内应用程序共享控件</li></ul> |<ul><li> Windows、 Mac 团队客户会议功能支持</li><li>浏览器团队客户会议功能支持：<ul><li>铬色</li><li>Microsoft Edge</li></ul></li><li>iOS 和 Android 团队客户会议功能支持</li></ul> | <ul><li>通话质量诊断门户</li><li>租户音频会议策略</li><li>启用呼叫质量分析 (CQD)</li></ul> | <ul><li>验证小组会议基于企业便携式计算机图像功能</li><li>特定的语言支持</li><li>对于给定的用户方案或特定站点应用的 GPO 设置</li></ul> | 是  |

#### <a name="audio-conferencing-user-functionality-definition"></a>音频会议用户功能定义

> [!TIP]
> 下面是用户功能模板，您可以使用文档所需的用户体验的示例基于音频会议功能进行评估。

| 交换经验                          | SharePoint 的经验                            | 团队的互操作性策略经验 |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>创建团队 （Office 组创建启用）</li><li>加入团队</li><li>创建频道</li><li>创建和查看会议</li><li>修改用户个人资料图片</li><li>添加和配置连接器</li><li>添加和配置选项卡</li><li>添加和配置聊天机器人</li></ul> | <ul><li>Store and share files within Teams conversations</li><li>Store and share and files within private chats (based on OneDrive)</li></ul> | <ul><li>ChatDefaultClient： 默认值</li><li>CallingDefaultClient： 默认值</li></ul>      |

 

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li> 决定将部署在您的环境中的音频会议类别功能。</li><li>确定用户音频会议功能要求您当前的 Skype 提供业务、 交换和 SharePoint 部署环境。</li><li>决定您将部署哪些团队互操作性体验。</li><li>检查最新的团队公用路线图并确定当前的工作负载能力是否满足您的部署时间线。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>音频会议类别功能支持音频会议部署所需的文档。</li><li>记录用户音频会议功能和互操作性要求提供您当前的 Skype 业务、 交换和 SharePoint 部署环境。</li><li>文档是否最新团队公用的路线图表示音频会议功能可以满足业务需要和部署的计时要求。</li></ul></td></tr>
</table>

<a name="define-and-document-your-audio-conferencing-test-plan"></a>定义和记录音频会议测试计划
-----------------------------------------------------

已经在范围内定义的音频会议功能后下, 一步是创建测试计划。 从较高层次的测试计划包括整体测试策略和方法体系，您将使用在测试过程中支持的功能验证。

从较高层次的测试计划应包括：

-   **测试范围：**作为测试阶段总结重点领域 （目标、 方案和目标） 进行评估

-   **测试用例：**一组测试用例可在作用域中的音频会议功能进行验证

-   **测试资源：**支持从环境、 技术和人员的角度来看测试工作所需的资源的一个矩阵

-   **测试计划 （时间轴）：**表示当测试将开始，多长时间很可能到最后，并且希望测试阶段结束时

-   **缺陷报告和修正：**准则应报告方式问题的测试，跟踪，和会审

-   **脱离会审和上报：**有关如何以及何时应该启动缺陷上报的大纲

-   **测试退出并挂起条件：**指导大纲的条件，可以实现注销退出测试阶段或暂停测试，直到确定了优先级的缺陷得到解决

-   **测试可交付结果：**其中开发和提供支持签收验收和退出测试过程的结果的摘要

> [!TIP]

>   测试方法可能已存在于您的组织，但下面的指南反映最佳做法可以包含也分别用于您的环境中测试团队功能。

在以下各节您会发现将帮助特定的决策和模板和主题供您选择为您完成您的测试计划中的其他规定的指导。

### <a name="define-and-document-testing-scope"></a>定义和记录测试范围

随着您着手制定测试计划，您必须定义最优先考虑，在测试范围内突出显示工作负荷，您是要评估的功能的列表。

正确评估通常音频会议功能的范围包括：

-   音频会议地点准备情况

-   音频会议的用户体验

-   音频会议管理

#### <a name="audio-conferencing-testing-scope"></a>音频会议测试范围

> [!TIP]
> 下面是可以使用的测试范围模板的示例文档的音频会议管理和用户组功能进行评估。

| 音频会议地点准备情况                                                                                                                                                                                                 | 音频会议的用户体验                                                   | 音频会议管理经验                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>网络 （通过 MyAdvisor) 计划的进度表带宽</li><li>（通过业务网络评估工具 Skype) 的网络连接性和性能验证</li><li> 质量服务 (QoS) 验证的</li><li>远程访问拆分隧道验证</li></ul> |<ul><li>拨入会议日程安排</li><li> 通过 PSTN 加入会议</li><li>添加与会者通过 PSTN 号码</li></ul> |<ul><li>授权的工作分配</li><li>服务编号管理</li><li>移植到 Office 365 的服务编号</li><li>音频会议报告</li><li>呼叫质量报告 (CQD)</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定音频会议通过识别功能测试范围进行评估的重点关注领域。</li><li>决定其他目的和目标进行评估。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档的音频会议功能的重点关注领域进行评估。</li><li>记录额外的目的和目标进行评估。</li></ul></td></tr>
</table>
 

### <a name="define-and-document-audio-conferencing-test-cases"></a>定义和记录音频会议的测试用例

音频会议功能、 客户端部署和并排比较方案与业务 （如果适用） 的 Skype 已定义之后下, 一步是制定评估范围中的音频会议功能所需的测试用例。 在高级别，测试用例通常按焦点区域分组，包括：

-   **测试用例的标题：**功能测试的焦点区域评估 （例如，音频会议）

-   **测试用例描述：**大纲显示测试的功能进行计算的目标汇总

-   **测试用例的说明：**按照正常执行测试用例所执行的步骤

-   **环境要求 （前提条件）：**正确执行测试所需的安装程序说明

-   **所需资源：**人事资源所需的正确的评估和测试执行

-   **预期结果：**您期望在测试成功完成后的结果

> [!NOTE]
> 由于组织内不同可能的方法和测试用例生成所需的详细程度，最好遵循一种允许足够级别的明细数据，但平衡与实用，而来支持整体测试的完整性可管理性。

> [!TIP]
> 为了帮助作为起始点的测试用例创建，请参阅音频会议用户指南可在[团队会议和调用](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)的列表。

#### <a name="audio-conferencing-test-case"></a>音频会议测试用例

> [!TIP]
> 下面是示例的测试用例模板，您可以使用文档的音频会议管理和用户组功能进行评估。

音频会议验证

| 测试用例 ID | 测试用例的标题                             | 测试用例说明                                                                       | 测试用例执行所需的环境                                               | 测试用例执行所需的步骤                                                                                                                                             | 测试所需资源 |
|--------------|---------------------------------------------|---------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
| 1            | 计划团队音频会议会议 | 安排联机会议和检查会议桥出现在邀请中。 |<ul><li>小组客户端安装</li><li>启用以下 Office 365 许可证分配的用户：<ul><li>Office Enterprise E5 with Audio Conferencing and Microsoft Teams</li><li>Office Enterprise E3 with Audio Conferencing and Microsoft Teams</li></ul></li></ul> |<ol><li>Sign in to the Teams client.</li><li>打开 Outlook，并安排新的工作组会议。</li><li>验证新的会议邀请显示 Microsoft 桥数显示在租户。</li></ol>      | 音频会议测试人员 |


> [!TIP]
> 为推动各个测试用例和评估您的组织中的音频会议功能的整体计划创建的其他指南，查看[音频会议测试计划](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)由[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)提供。


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Decision points</td><td><ul><li>Decide which Audio Conferencing administration and user features will be evaluated.</li><li>Decide what test environment is required to support test case execution.</li><li>Decide the steps required for test case evaluation.</li><li>决定正确执行的测试所需的资源。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档测试用例进行评估，根据提供的测试用例模板。</li><li>包括已完成的模板作为整体测试计划的一部分。</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>定义和记录测试资源

若要支持的测试阶段，值得您制定资源规划细节需要的人员、 支持和技术资源。 可能需要的总体测试计划的一个重要组成部分，资源计划可帮助您确定您的任何依赖项可能存在，并为您提供了高级别的意义上的资源支持。

在高级别上，这些资源通常包括：

-   **人物**： 利益相关者

-   **技术**： 租户，授权，设备

-   **支持**： 培训 （卡、 视频），管理支持定义的升级路径

#### <a name="testing-resource-requirements"></a>测试资源需求

> [!TIP]
> 下面是您可以使用文档的不同类型的资源支持您测试阶段所需的测试资源需求模板示例。

[//]: # (是否可以此示例讨论有关调用计划？)

| 资源类型 | 所需资源                                           | 资源描述 |
|---------------|--------------------------------------------------------------|----------------------|
| 人员        | 利益相关者测试潜在顾客的测试人员                               | 待定                  |
| 技术    | 访问 Office 365 与启用下列服务：<ul><li>Office 365 E5 授权分配</li><li>国内和国际电话计划分配</li></ul>    | 待定                  |
| 支持       | Test administrator Test support lead Test support technician | 待定                  |

   


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Decision points</td><td><ul><li>决定您需要支持的测试阶段的资源类型 （用户、 技术和支持）。</li><li>决定用于确定资源类型所需的特定资源。</li><li>决定是否应该提供进一步详细地描述了所需的资源的类型。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档可能需要支持测试阶段的资源类型 （用户、 技术和支持）。</li><li>文档所标识的资源类型所需的特定资源。</li><li>如果您决定很有必要，文档类型的所需的资源以支持测试阶段的任何进一步细节。</li></ul></td></tr>
</table>

### <a name="define-and-document-a-testing-timeline"></a>定义和记录测试的时间线

作为测试计划定义的一部分，创建时间线，其中列出了如果您希望完成测试活动，并取得高级里程碑的计划。

在高级别上，这通常包括：

-   **任务：**高级别活动来完成

-   **里程碑：**高级别目标或已完成的进度

-   **所需资源：**测试支持交付里程碑或标识任务所需的资源

-   **开始日期：**在开始活动、 里程碑或任务的日期

-   **完成日期：**希望活动、 里程碑或任务的完成日期

-   **负责人：**负责确保按时按照完成日期完成活动、 里程碑或任务分配的资源

-   **估计：**需要确保按时完成活动、 里程碑或任务所分配的资源预测它的小时数

#### <a name="testing-scheduling-and-timeline-requirements"></a>测试计划和日程表的要求

> [!TIP]
> 下面是您可以使用文档的预期的日期时将完成具体的测试活动或交付里程碑的测试时间线要求模板示例。

| 任务                                     | 里程碑       | 开始日期                                                             | 完成日期 | 所有者 | 分配的资源 | 估计 |
|------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| 测试报表                              | 待定             | 待定                                                                    | 待定             | 待定   | 待定                | TBD 小时  |
| Test Case Execution: Audio Conferencing  | TBD             | TBD                                                                    | 待定             | 待定   | TBD                | TBD hours  |
| Test Case Execution: Network Readiness   | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | TBD hours  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Decision points</td><td><ul><li>Decide timeline activity, milestone, and tasks that you need to track.</li><li>Decide which resources you’ll need to assign.</li><li>Decide the date you expect to be done.</li><li>Identify the delivery owner.</li><li>Decide how much time it will take to complete the activity, milestone, or task.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>Document your testing timeline by using the template provided, and include:<ul><li>Timeline activity, milestone, and tasks that need to be tracked.</li><li>Resources that need to be assigned.</li><li>Anticipated completion date.</li><li>Delivery owner.</li><li>Time required to complete the activity, milestone, or task.</li></ul></li><li>Include the completed template as part of your overall test plan.</li></ul></td></tr>
</table>



### <a name="define-and-document-test-defect-report-criteria"></a>Define and document test defect report criteria

As test cases within a given phase or stream are executed, issues might arise where the result from the test case being executed isn’t what you expected.

When these types of results occur, they should be captured in a defect report and remediation plan that’s escalated to the designated test lead for review, reporting, and defect resolution.

Typically, a defect report and remediation plan includes the following:

-   **Defect ID:** The number assigned to the issue

-   **Test case ID impacted**: The number assigned to the test case that was being evaluated at the time the defect was identified

-   **Defect description:** Summary of the issue

-   **Environment/steps to reproduce:** Summary of the testing environment setup, along with the exact steps required to reproduce the issue

-   **Defect severity**: The impact of the issue, ranging from preventing the test case from being approved to its being accepted with minimal risk. Some examples might include:

-   **Low:** The issue has little impact and won’t prevent the test case from achieving acceptance if the issue can be resolved later.

-   **Medium:** The issue has substantial impact, but won’t prevent the test case from achieving acceptance if the issue can be resolved before the testing phase is completed.

-   **High:** -The issue has critical impact on the test case. The issue must be resolved before the test case can be accepted.

-   **Status:** Has the issue been resolved, is it open, or still under investigation

-   **Submitted by:** The tester who reported the issue

-   **Assigned owner:** The resource assigned from the testing team who is responsible for resolving the issue

-   **Supporting details:** This can include—but isn’t limited to—client-side logs, screenshots, or video of the issue.

As testers execute the test cases outlined in your test plan, they should be sure to complete a defect report and remediation plan for any issues that arise.
This will highlight potential impact that could impede or even halt the testing evaluation process.

#### <a name="testing-defect-report-and-remediation-plan"></a>Testing defect report and remediation plan

> [!TIP]
> Below is an example of Defect Report and Remediation Plan template that you can use to document issues discovered during the testing phase.

| Defect ID                                | Test case ID impacted | Defect description                                                                                                                           | Environment /steps to reproduce                                                                                                                    | Severity | Status | Submitted by | Assigned owner | Supporting details (logs, screenshots, and so on) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | 拨入坐标通过团队 Outlook 外接程序安排地区组织寄宿会议 (RHM) 启用的用户，不填充 | 将一个测试帐户移动到另一个区域，RHM。<br/> 登录到 Outlook，然后尝试安排团队音频会议通过团队 Outlook 外接程序计划 | 中   | 关闭 | Louis Lahr   | Lisa 灰色      | Teams client-side log<br/> Teams client screenshot     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>决定将分配来支持测试工作的缺陷条件严重级别。</li><li>Decide what testing defect reporting criteria you’ll document if issues arise during testing.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档测试缺陷报告中提供的模板所需的条件。</li><li>包括已完成的模板作为整体测试计划的一部分。</li></ul></td></tr>
</table>

 
### <a name="define-and-document-exit-and-suspension-criteria"></a>定义和记录退出并挂起条件

作为总体测试计划执行进程的一部分，您需要定义条件以指示该点处应暂停测试工作和获得签收和退出测试阶段必须满足的要求。

#### <a name="test-plan-exit-and-suspension-criteria"></a>测试计划退出并挂起条件

> [!TIP]
> 下面是退出并挂起条件模板，您可以使用测试计划文档条件中的一个示例实现签收、 退出测试阶段，或需暂停测试活动。

| 测试退出条件                            | 挂起的测试条件                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>所有测试用例必须都获得待定 %通过率</li><li>所有测试用例必须完全都执行完</li><li>计算所有的测试用例，必须先关闭所有严重缺陷</li></ul> | <ul><li>所有测试用例必须都获得待定 %失败率</li><li>测试可以继续之前，必须先解决标识为高严重性的所有缺陷。</li></ul> |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>Decide on suspension criteria that must be met if issues with testing are identified.</li><li>Decide on exit criteria that must be met to obtain testing acceptance sign-off and support exiting the testing phase after all testing activities are complete.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档中提供的测试并退出模板所需的测试退出并挂起条件。</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>定义并记录缺陷问题上报过程

整个测试计划执行的过程中，可能发现问题或确定促进和确定所需的分辨率，以允许测试继续要求上报到相应的资源的缺陷。

与相应的严重性和优先级分配在发现缺陷后，创建一个上报矩阵和会审检查过程中的映射出触发上报后如何，何时，以及缺陷将分配给有关的进一步审查，分辨率。

通常情况下，缺陷报告和修正计划包括以下内容：

-   **脱离 ID:**您指派的问题数

-   **缺陷描述：**问题摘要

-   **缺陷优先级评估：**分配给解决缺陷的优先级基于对业务的影响和缺陷严重程度。 一些示例可能包括：

-   **低：**该问题有防止测试阶段实现签收，如果稍后解决问题上的影响很小。

-   **媒体：**该问题已对防止测试阶段获得签署，如果不能解决问题的巨大影响。

-   **高：**该问题已对防止测试阶段获得签署，如果不能解决问题的严重影响。

-   **分配缺陷所有者：**从测试团队负责解决该问题分配的资源

-   **分配缺陷上报点：**资源分配谁是点逐级上报问题组织中的 （如果需要） 对于推动解决方法;根据缺陷的严重性

-   **Defect status:** Has the issue been resolved, is it open, or still under investigation

-   **Required resolution by date:** The date which the issue must be resolved by

-   **Status date:** The date reflecting the last time status was updated as an outcome of a defect triage review

#### <a name="test-plan-defect-escalation"></a>Test plan defect escalation

> [!TIP]
> Below is an example of a defect escalation template that you can use in part of your test plan to document the escalation process required for prioritizing and resolving testing defects.

| Defect ID                                | Defect description                                                                                          | Defect priority assessment                                           | Assigned defect owner | Assigned defect escalation point | Defect escalation method                                          | Defect status | Required resolution by date | Status date |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1    | RHM 启用，用户拨入的坐标不填充通过团队 Outlook 外接程序安排。 | 中                                                               | Lisa 灰色             | Louis Lahr                       | 每周一次会审复查高优先级发送电子邮件至受影响的利益相关者 | 打开          | 尽快                        | 于 2018 1/12 年   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>决定并达成一致意见的缺陷优先级来支持您的测试计划。</li><li>决定每个缺陷区域的升级点。</li><li>决定的缺陷问题上报和会审打算按照，根据优先级。</li><li>确定缺陷报告和会审上报的沟通计划。</li><li>Decide the defect triage review meeting cadence.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>商定的缺陷优先级的文档。</li><li>记录每个潜在的焦点区域的升级点。</li><li>记录缺陷问题上报和会审计划根据商定的标准。</li><li>记录您报告规定的缺陷。</li><li>计划的一系列缺陷的碰头会。</li></ul></td></tr>
</table>

   

### <a name="define-and-document-testing-deliverables"></a>定义和记录测试的可交付结果

创建一个测试计划中的最后一次和最后组件是确定在特定的总体测试计划将提供的可交付结果方面的成果。

在高级别，这通常包括但不限于：

-   测试计划

-   测试用例

-   缺陷报告

-   测试结果摘要

-   测试验收和签收

#### <a name="test-plan-deliverables"></a>测试计划可交付结果

> [!TIP]
> Below is an example of a test plan deliverable matrix that you can use to document the deliverables to be created, along with resources required for review, approval, and sign-off.

| Test plan deliverable                    | Test plan deliverable format | Test plan deliverable owner                                                                                                      | Test plan deliverable reviewer | Test plan deliverable approver | Test plan deliverable sign-off date |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Test plan                                | Word                         | 待定                                                                                                                              | 待定                            | 待定                            | TBD                                 |
| Defect management reports                | Word                         | 待定                                                                                                                              | 待定                            | 待定                            | 待定                                 |
| 测试状态报告                   | Word                         | 待定                                                                                                                              | 待定                            | 待定                            | 待定                                 |
| 测试结果摘要                     | Word PPTX                    | 待定                                                                                                                              | TBD                            | TBD                            | 待定                                 |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>决定哪些可交付结果创建和捕获为每个测试阶段的输出。 每个可交付结果，决定其：<ul><li>格式</li><li>所有者</li><li>审阅者</li><li>审批者</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档测试计划可交付结果创建和传递矩阵。</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>评估网络就绪
--------------------------

为支持您的团队部署的一个关键元素，网络准备工作是测试，以确保正确地进行网络优化支持团队通信的一个重要组成部分。 若要确保网络就可以在作用域中的网站，包括整体测试策略中列出以下重点领域：

-   带宽估计和规划网络规划人员 （通过 MyAdvisor)

-   质量服务 (QoS) 配置验证的

-   网络连接性和性能检查通信模拟

-   拆分隧道验证

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>为站点和角色作用域中的执行 （通过 MyAdvisor) 网络规划器

之前引入实时通信服务，如团队环境中的，很重要，以确保网络具有已正确进行了优化和大小从 Azure ExpressRoute （如果适用）、 互联网和广域网带宽的角度来看。

为了帮助确定的带宽和支持您的部署的范围中的站点所需的网络优化程度，完成 （通过 MyAdvisor)[网络计划](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp)工具来验证您组织的网络准备工作需要。 有关如何确定网络规划人员通过团队的网络要求的其他指南，请参阅 MyAdvisor： 网络规划人员。

> [!TIP]
> **建议**选项卡上的示例说明了如何配置并解释结果，与有关的其他信息，请参阅网络规划人员[的建议概述](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)。


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>决定哪些网络站点是部署团队的作用域中的服务。</li><li>决定所需的团队形式在作用域中的角色。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>完成网络规划人员 （通过 MyAdvisor) 的作用域中的网站的列表。</li><li>提供测试计划结果模板文档网络规划人员验证结果。</li><li>验证 ExpressRoute （如果适用）、 互联网和广域网带宽的站点范围内计算对应当前分配的带宽值。</li><li>对于没有足够的带宽的站点，执行问题上报和补救措施的计划，以解决带宽问题。</li><li>建立一种网络监控解决方案范围以监测带宽使用情况中的站点和 QoS 为 ExpressRoute （如果适用）、 互联网和广域网网段。</li><li>计划指导委员会会议审查网络计划的结果。</li><li>提供带宽计划向指导委员会，以查明任何需要修正的结果。</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>评估范围内的站点的 QoS 配置
---------------------------------------------

作为验证准备支持团队实时通信的网络，是同样重要的是要确保网络已被正确配置并从 QoS 的角度进行了优化。

如何配置、 部署和验证团队 QoS 网络准备工作，通过使用组策略的其他指南，请参阅[启用团队的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>决定上的 QoS 配置来实现。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>配置 QoS。</li><li>通过"验证通过 GPO"中列出的步骤中所述执行 QoS 验证和上面的"消息分析器通过验证"部分。</li></ul></td></tr>
</table>

 

### <a name="document-qos-configuration-validation-test-results"></a>记录 QoS 配置验证测试结果

完成 QoS 验证测试通过使用组策略的作用域中的网站后，创建一个报告，总结了测试的结果在最终指导委员会审查期间呈现。

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>站点 a: QoS 配置验证测试摘要报告

> [!TIP]
> 以下示例测试摘要报告模板，可以通过检查在下一次指导委员会会议期间时到板载音频会议服务决定在试验阶段。

**通过 GPO 和消息分析器的 QoS 配置验证**

**结果摘要**：&nbsp;&nbsp;&nbsp;& #9744;通过&nbsp;&nbsp; &nbsp; & #9744;部分&nbsp;&nbsp; &nbsp; & #9744;失败

<table>
<tr><th colspan="2">测试亮点 </th></tr>
<tr><td>待定</td><td>待定</td></tr>
<tr><th colspan="2">测试的缺点  </th></tr>  
<tr><td>**问题**： 待定</td><td>**修正：**待定</td></tr>
<tr><th colspan="2">拦截器标识 </td></tr>
<tr><td>**窗口**： 待定</td><td>**修正**： 待定</td></tr>
</table>

> [!TIP]
> 为便于进一步讨论在最终指导委员会评审过程，可以使用[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)从更新后的[测试结果矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)记录并突出显示需要修正的其他区域。


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估 QoS 测试结果以确保的团队实时媒体通信正在正确标记并按优先级排列。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档的 QoS 提供测试计划结果模板中的测试结果。</li><li>执行升级和补救措施的计划，以解决 QoS 可能未正确配置或不作为的工作预期支持团队媒体通信的问题。</li></ul></td></tr><li>安排评审测试的摘要结果指导委员会会议。</li><li>存在的测试摘要结果向指导委员会，以查明任何需要修正。</li>
</table>



<a name="execute-split-tunnel-enablement-validation"></a>执行拆分隧道启用验证
------------------------------------------

很常见的企业目前都有一个或多个解决方案提供远程访问 [例如虚拟专用网络或 VPN。 这些解决方案使内部业务线的资产和应用程序的连接安全、 可靠。

远程访问解决方案可以为隧道团队实时媒体通信时有权访问一些应用程序，很好地工作，但是这些解决方案通常会导致较少比最佳的用户体验团队音频中的所有参与者会议或调用方案。

为了确保团队媒体通信 does*遍历远程访问解决方案在您的环境中*，将要求拆分隧道配置。

有关如何配置和验证配置拆分隧道网络准备工作小组的其他指南，请参阅[网络](https://docs.microsoft.com/MicrosoftTeams/prepare-network)准备工作。

> [!NOTE]
> 因为在市场上可用的远程访问解决方案的巨大工作量，本文档不提供特定于供应商的详细信息，应配置远程访问解决方案的内容不仅仅是一般原则。


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>确定要实现的拆分隧道配置。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>实现拆分隧道配置。</li><li>测试和验证的拆分隧道配置。</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>文档拆分隧道配置验证测试结果

已完成测试的拆分隧道配置范围中的站点后，创建一个报表，总结测试结果，然后将其提交下一步筹划指导委员会评审期间。

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>答： 站点拆分隧道配置验证测试摘要报告

> [!TIP]
> 以下示例测试摘要报告模板，可以通过检查在下一次指导委员会会议期间时到板载音频会议服务决定在试验阶段。

**拆分隧道配置验证**

**结果摘要**：&nbsp;&nbsp;&nbsp;& #9744;通过&nbsp;&nbsp; &nbsp; & #9744;部分&nbsp;&nbsp; &nbsp; & #9744;失败

<table>
<tr><th colspan="2">测试亮点 </th></tr>
<tr><td>待定</td><td>待定</td></tr>
<tr><th colspan="2">测试的缺点  </th></tr>  
<tr><td>**问题**： 待定</td><td>**修正：**待定</td></tr>
<tr><th colspan="2">拦截器标识 </td></tr>
<tr><td>**窗口**： 待定</td><td>**修正**： 待定</td></tr>
</table>

> [!TIP]
> 为便于进一步讨论在最终指导委员会评审过程，可以使用[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)从更新后的[测试结果矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)记录并突出显示需要修正的其他区域。



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估拆分隧道以确保团队中的实时通信正在被远程访问解决方案的测试结果。</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档中提供的测试计划结果模板拆分隧道连接测试结果。</li><li>执行升级和修正计划要解决的问题，正确的路由可能不存在支持团队媒体配置拆分隧道内。</li><li>安排评审测试的摘要结果指导委员会会议。</li><li>存在的测试摘要结果向指导委员会，以查明任何需要修正。</li></ul></td></tr>
</table>

   

<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>通过使用 microsoft 的网络评估工具执行网络连接性和性能验证
-----------------------------------------------------------------------------------------------------------

从 Microsoft 网络评估工具执行预定义的时间段和迭代次数，到最近的边缘站点提供连接到的团队服务流模拟的音频包，流量模拟和连接测试。 此测试的目标之一是评估网络数据包丢失、 抖动、 往返延迟和数据包重新排序百分比从每个模拟调用的性能指标。 另外，该测试可验证之间内部，允许有适当的连接和边缘网络元素与支持小组服务连接的所有边入口点。

有关如何确认并评估团队网络准备在作用域中指定网站的其他指南，请参阅[网络](https://docs.microsoft.com/MicrosoftTeams/prepare-network)准备工作。

> [!TIP]
> 若要完成网络准备情况分析和准备工作范围中的站点，指定每个网站可以帮助您的网络准备情况评估工作人员领导。

<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>确定网络评估以及连接的站点范围内的测试配置文件。</li><li>确定站点范围内的网络评估配置文件要求。</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>在作用域中配置站点的网络评估配置文件的要求。</li><li>在作用域中执行站点的网络性能和连接性的验证。</li></ul></td></tr>
</table>

 

### <a name="document-network-connectivity-and-performance-validation-test-results"></a>记录网络连接性和性能验证测试结果

所有网络连接和性能测试的站点范围内都完成之后，创建一个报表，总结测试结果，然后将其提交下一步筹划指导委员会评审期间。

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>站点 a： 网络连接性和性能摘要报告

> [!TIP]
> 下面是示例网络连接性和性能摘要模板时，可以使用在下一步筹划指导委员会评审过程决定整个网络站点范围内的准备工作。

**位置： 西雅图 [内部有线] 客户端到 Office 365 的结果**

**结果摘要**：&nbsp;&nbsp;&nbsp;& #9744;通过&nbsp;&nbsp; &nbsp; & #9744;部分&nbsp;&nbsp; &nbsp; & #9744;失败 



| 指标                                                        | 目标                                                                                                            | 工作日： 办公时间为上午 9:30 到 11:00                                                                                                                                                                                                                                                                                                 | 工作日： 办公时间到下午 2:30 到下午 4:30 | 下午 10:30 至 12:30 上午下班后工作日： | 上午 9:30 至 11:30 小时之后周末： | 下午 2:30 到下午 4:30 小时之后周末： |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| 滞后时间 （单向）                                             | \<50 毫秒                                                                                                           | 40 毫秒                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 毫秒                                     | 35 毫秒                                    | 36 ms                                   |
| 滞后时间 （往返时间或 RTT）                             | \<100 毫秒                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 毫秒                                     | 72 ms                                    | 70 毫秒                                   |
| 突发数据包丢失                                             | \<任何 200 毫秒间隔期间的 10%                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2%                                       | 2%                                        | 0.2%                                     | 0.1%                                    |
| 数据包丢失                                                   | \<1%，在所有 15 秒时间间隔                                                                                   | 0.4%                                                                                                                                                                                                                                                                                                                                      | 0.3%                                     | 0.3%                                      | 0.1%                                     | 0%                                      |
| 数据包间到达抖动                                   | \<任何 15 秒间隔期间 30 毫秒                                                                                | 12 毫秒                                                                                                                                                                                                                                                                                                                                     | 11 毫秒                                    | 13 毫秒                                     | 5 毫秒                                     | 5 毫秒                                    |
| 数据包重新排序                                                | \<0.05%无序的数据包                                                                                      | 0%                                                                                                                                                                                                                                                                                                                                        | 0%                                       | 0%                                        | 0%                                       | 0%                                      |


<table>
<tr><th colspan="2">测试亮点 </th></tr>
<tr><td>待定</td><td>待定</td></tr>
<tr><th colspan="2">测试的缺点  </th></tr>  
<tr><td>**问题**： 高滞后时间</td><td>**修正：**调查数据包路由并实现理想的工艺路线。</td></tr>
<tr><td>**问题**： 往返时间没有加倍的反应</td><td>**修正：**调查可能的防火墙或路由器配置问题。 调查通信量的路径。</td></tr>
<tr><td>**问题**： 较高的数据包丢失 </td><td>**修正：**通过网络规划人员验证已分配足够的带宽。 </td></tr>
<tr><td>**问题**： 高抖动 </td><td> **修正：**检查是否正在使用正确区分的服务代码点 (DSCP) 值。 </td></tr>
<tr><td>**问题**： 较高的数据包丢失 </td><td>**修正：**数据包的丢失进行调查。 </td></tr>
<tr><td>**问题**： 较高的数据包重新排序 </td><td>**修正：**研究路由器队列和带宽。 </td></tr>
<tr><th colspan="2">拦截器标识 </td></tr>
<tr><td>**窗口**： 待定</td><td>**修正**： 待定</td></tr>
</table>

 
<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估网络评估和连接测试结果以确保满足边段和客户端网段中[的媒体质量和网络连接的性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)描述的要求。</li><li>您已经评估了作用域中的所有站点支持实时媒体网络功能？</li><li> 如果您的网络没有正确评估，或知道它将不会支持实时媒体，将禁用视频和屏幕共享功能，以减少网络影响并改进用户的团队体验吗？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档的网络性能和连接性测试结果。</li><li>执行升级和补救措施的计划，以解决的站点位置没有足够的带宽，或者网络性能和连接性要求未得到满足的问题。</li><li>安排评审测试的摘要结果指导委员会会议。</li><li>存在的测试摘要结果向指导委员会，以查明任何需要修正。</li></ul></td></tr>
</table>



<a name="execute-service-number-port-validation"></a>执行服务编号端口验证
--------------------------------------

如果您需要转换为提供拨号音频会议服务支持的团队中的功能中的一部分数据，您应该执行部分端口服务号码。 这将帮助您验证完准备部署在生产环境中的音频会议服务的期望、 需求和合理的时间线。

要完成团队到您当前的 PSTN 服务提供商的服务数字的部分端口，演练如下所述的步骤。

#### <a name="step-1"></a>第 1 步

确定您希望到 Office 365 的端口为拨入号码 （服务号码） 音频会议的测试号

**重要**

计划编号移植测试时，请务必阅读数字移植请求[编号端口常见问题](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)中的最新指导原则。

#### <a name="step-2"></a>第 2 步

识别并记录当前运营商测试数将移植您的所有帐户信息 （包括用于特定帐户的名称）。
通常情况下，您可以找到您需要发票的最新清单中的信息来自您当前的服务提供程序。

> [!TIP]
> 可以移植或传输电话号码中所有当前支持的国家/地区。但是，提交端口订单请求的方式可能会根据国家 （地区） 的电话号码源于不同。 有关当前支持的国家/地区的最新列表，请参见[国家和区域可用性的音频会议并调用计划](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。 < /br/ ><br/>
>   如欲进一步了解将电话号码转到音频会议 — — 以及潜在的限制 — — 请参阅[传输到 Office 365 的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)以及[免费拨打 Office 365 中的限制](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.)。

#### <a name="step-3"></a>第 3 步

下载并创建字母的授权 (LOA) 的基于数字移植类型为"服务号码"您所在国家/地区。

> [!NOTE]
> 因为 LOA 格式可以与不同的国家、 地区或数字类型 (即地理与非地理或与服务的用户数或免费电话号码)，请确保为您的特定方案类型使用正确的保证书模板。 信息，请参阅[下载授权信函 (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa)更多关于选择提供保证书，或者直接转到[下载页面](https://www.microsoft.com/download/details.aspx?id=49167)。

> [!NOTE]
> **仅限美国**<br/>
> 因为我们只移植一个服务编号，此测试，请务必选择相应的字段中提供保证书，如下所示：

![如何许多电话号码将会转移？答案是： 我仅传输一些我的号码从我当前的运营商。](media/onboarding-test-plan-image1.png "如何许多电话号码将会转移？答案是： 我仅传输一些我的号码从我当前的运营商。") 


![什么类型的电话号码将您传送吗？答案是： 我正在转移语音服务电话号码，如自动助理或会议桥。](media/onboarding-test-plan-image2.png "什么类型的电话号码将您传送吗？答案是： 我正在转移语音服务电话号码，如自动助理或会议桥。")

> [!IMPORTANT]
> 如果服务数字音频会议桥、 自动助理或其他服务号码，免费电话号码，或者您需要转移到团队的多 999 用户电话号码，您需要手动提交端口顺序。<br/><br/>
>   当您手动使用提供保证书端口的电话号码时，请确保选择了正确的电话号码类型。 您必须提交独立的操作端口订单每种类型的电话号码要转移。</br><br/>
>   因为我们想要测试移植过程使用与相同的付费电话号码 （按钮） 的电话号码的数量，您需要确保的付费电话号码*不*包括端口连接的特定电话号码。

#### <a name="step-4"></a>第 4 步

在租户管理门户中，转到**支持**选项卡，创建和提交服务请求。 将已完成的保证书文件，安排与您当前的服务提供商迁移关联的电话号码。 若要选择最适合您组织的大小的服务请求方法，请参阅[手动提交自定义服务请求](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request)。

支持请求接收到之后，Microsoft 技术支持将跟进基于通信方法选择和状态和完成数字移植过程的下一步行动的建议。

#### <a name="step-5"></a>第 5 步

数确认为具有在 Office 365 的新服务数字上已移植后，为指定数量的音频会议服务转到租户管理门户\> **Skype 业务管理中心为** \> **的声音**。 在**电话号码**选项卡上，将新服务号码分配音频会议服务。

> [!NOTE]
> 但在撰写本文时，此任务将大量新服务分配给音频会议，通过 Skype 业务管理中心完成此任务的管理。

#### <a name="step-6"></a>第 6 步

既然已指定给音频会议服务的端口的服务号码，拨打该号码，并确认您听到以下会议服务问候语：

>   "欢迎使用音频会议中心。 请输入会议 ID 跟英镑。"


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>决定将到端口，需要按国家/地区的国内服务号码。</li><li>决定您是否会将任何免费的电话号码。</li><li>确定将使用哪个 LOA 模板。</li><li>确定您当前的运营商 （丢失载体） 是否允许电话号码的碎片 （即允许部分端口订单）。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>收集所需的信息并准备 LOAs。</li><li>下载并完成所需的保证书模板。</li><li>提交服务和/或免费电话号码的移植请求。</li><li>通过将他们分配到音频会议服务以拨入访问执行测试验证端口号，确认他们工作的按照本部分前面第 6 步中所述。</li></ul></td></tr>
</table>
   

### <a name="document-service-number-porting-test-results"></a>文档服务号码移植测试结果

完成所有数字移植测试后，创建一个报表，总结测试结果，在下一步筹划指导委员会审查期间呈现。

#### <a name="site-a-number-porting-test-summary-report"></a>站点 a： 数移植测试摘要报告

> [!TIP]
> 下面是示例测试摘要报告模板可供审阅在下一次指导委员会会议期间时使用板载音频会议服务到决定在试验阶段。

**服务编号移植**

**结果摘要**：&nbsp;&nbsp;&nbsp;& #9744;通过&nbsp;&nbsp; &nbsp; & #9744;部分&nbsp;&nbsp; &nbsp; & #9744;失败 

<table>
<tr><th colspan="2">测试亮点 </th></tr>
<tr><td>待定</td><td>待定</td></tr>
<tr><th colspan="2">测试的缺点  </th></tr>  
<tr><td>**问题**： 待定</td><td>**修正：**待定</td></tr>
<tr><th colspan="2">拦截器标识 </td></tr>
<tr><td>**窗口**： 待定</td><td>**修正**： 待定</td></tr>
</table>

> [!TIP]
> 为便于进一步讨论在最终指导委员会评审过程，可以使用提供的[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)更新的[测试结果矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)记录并突出显示需要补救的附加测试环节。


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估是否提交以进行迁移的服务号码被成功地移植到音频会议服务。</li><li>评估是否能够为音频会议服务分配服务端口的号。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>记录您的号码移植测试结果。</li><li>执行升级和修正计划来解决与数字的移植过程中，您遇到的问题。</li><li>安排评审测试的摘要结果指导委员会会议。</li><li>提供测试摘要结果向指导委员会，以查明任何需要修正。</li></ul></td></tr>
</table>



<a name="execute-your-test-plan-for-audio-conferencing"></a>执行音频会议的测试计划
---------------------------------------------

既然您已经定义了测试计划下, 一步是遍历测试用例，将重点放在评估音频会议管理和用户体验功能范围内。 实际测试开始之前，请验证下列测试系统必备组件位于适当位置。

### <a name="audio-conferencing-testing-prerequisites"></a>音频会议测试系统必备组件

-   业务用例定义的音频会议服务。

-   已确定主要利益相关者。

-   音频会议服务所需的许可提供，并且已指派给作用域中的用户组。

-   已标识组织站点和作用域中的用户组的列表。

-   专用和共享音频会议拨入号码的列表 — — 与组织站点和作用域中的用户的语言首选项 — — 已标识和配置。

-   [通信片尾](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已经被设置为您的组织能够提供免费的会议桥接电话号码和支持会议访问国际拨出方案。

-   已标识和范围 （PIN 长度、 入口/出口通知，启用通知首选项） 中的所有用户配置音频会议会议网桥的设置。

-   租户拨号计划设置的作用域中的所有用户的都支持音频会议拨出方案已确定，配置，和应用。

-   已标识和配置作用域中所有用户的音频会议策略。

-   已标识和配置作用域中所有用户的音频会议法规遵从性要求。

### <a name="document-audio-conferencing-test-case-passfail-status"></a>记录音频会议测试用例通过/失败状态

在测试用例来评估的管理团队和用户范围中的音频会议功能，跟踪结果的每个测试用例，以反映通过部分/失败状态，以及缺陷分配 ID，以防出现未预料到的问题。

#### <a name="audio-conferencing-test-case-status"></a>音频会议测试用例的状态

> [!TIP]
> 下面是示例测试用例状态您可以使用模板对文档测试结果审在下一次指导委员会会议期间时到板载音频会议服务决定在试验阶段。


| 测试用例 ID                             | 测试用例的标题                             | 测试用例说明                                                                            | 测试用例结果摘要 | 已分配的缺陷 ID （如果适用）                                                                          |
|------------------------------------------|---------------------------------------------|---------------------------------------------------------|---------------------------|-------------------------------------------------------------------------------------------------------------|
| 1                                        | 计划团队音频会议会议 | 安排联机会议和验证会议桥显示在邀请中。 |  & #9744;传递<br/>& #9744;分部<br/> & #9744;失败   | RHM 启用，用户拨入的坐标不填充通过团队 Outlook 外接程序计划 |


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估范围中的音频会议功能的网站的高层次测试用例通过/失败状态。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档完成在作用域中的所有测试用例的测试用例状态结果。</li><li>安排评审测试的摘要结果指导委员会会议。</li><li>存在测试用例状态会导致指导委员会，以查明任何需要修正。</li></ul></td></tr>
</table>


### <a name="document-audio-conferencing-testing-result-summary"></a>测试结果摘要的文档音频会议

网站已完成所有范围内支持音频会议功能的测试用例后，文档时决定在试验阶段启用音频会议服务指导委员会会议期间审查的结果。

#### <a name="site-a-audio-conferencing-test-case-summary-report"></a>站点 a： 音频会议测试案例摘要报告：

> [!TIP]
> 下面是示例测试摘要报告模板，可以通过检查在下一次指导委员会会议期间时到板载音频会议服务决定在试验阶段。

**团队音频会议**

**结果摘要**：&nbsp;&nbsp;&nbsp;& #9744;通过&nbsp;&nbsp; &nbsp; & #9744;部分&nbsp;&nbsp; &nbsp; & #9744;失败 

<table>
<tr><th colspan="2">测试亮点 </th></tr>
<tr><td>待定</td><td>待定</td></tr>
<tr><th colspan="2">测试的缺点  </th></tr>  
<tr><td>**问题**： 待定</td><td>**修正：**待定</td></tr>
<tr><th colspan="2">拦截器标识 </td></tr>
<tr><td>**窗口**： 待定</td><td>**修正**： 待定</td></tr>
</table>


> [!TIP]
> 为便于进一步讨论在最终指导委员会评审过程，可以使用提供的[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)更新的[测试结果矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)记录并突出显示需要修正的其他区域。



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>评估范围中的音频会议功能的网站高级测试汇总的结果。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>完成所有测试用例结果之后的文档测试用例的摘要报告。</li><li>安排评审测试的摘要结果指导委员会会议。</li><li>存在的测试摘要结果向指导委员会，以查明任何需要修正。</li></ul></td></tr>
</table>


<a name="present-and-report-audio-conferencing-test-findings"></a>显示和报告音频会议测试结果
---------------------------------------------------

毕竟已完成的测试活动和低影响的任何缺陷都已解决、 安排与指定测试的风险承担者最终结束会议。 在会上，地址：

-   状态摘要

-   高光/缺点

-   吸取的经验教训

-   总体建议 — — 继续试验阶段或重新评估测试结果？

-   测试矩阵结果 （这些应完全记录在一个附录）

#### <a name="test-plan-deliverables"></a>测试计划可交付结果：

> [!TIP]
> 下面是一个示例测试计划可交付结果模板，您可以使用文档条件实现签收和退出测试阶段，或暂停测试直到所有发现的问题得到完全解决所需。

| 状态摘要               | 高光/缺点 | 吸取的经验教训 | 关闭建议 |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>测试用例的 TBD %的通过率</li><li>传递的所有测试</li></ul> | 待定                  | 待定             | 进入试运行       |


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>决策点</td><td><ul><li>决定测试的状态摘要。</li><li>确定测试的亮点和缺点。</li><li>确定吸取的经验教训。</li><li>如果有，请决定操作保留，哪些补救措施。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档测试摘要结果包括：<ul><li>状态摘要</li><li>高光/缺点</li><li>吸取的经验教训</li></ul></li><li>安排评审测试结果最终指导委员会会议。</li><li>存在测试摘要结果期间一个指导委员会，审查以获得最终签收有关退出测试阶段。</li></ul></td></tr>
</table>


