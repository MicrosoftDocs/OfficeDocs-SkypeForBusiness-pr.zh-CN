---
title: 编制 Microsoft Teams 成功计划文档
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择部署模型，开发有责任的、有责任的（RACI）矩阵，创建执行和管理计划。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ef741290a4d669084ad55335d0a08ec1c9ffd5c
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515989"
---
# <a name="document-my-success-plan"></a>记录成功计划

本文概述了正确记录云语音部署的要求。 通过在规划云语音部署时定义和记录所有决策点和下一步操作，您可以确保所有利益干系人和项目团队成员都在提供成功的结果中进行调整。 

## <a name="execution-planning"></a>执行计划 

在定义了如何通过组织中的呼叫计划解决方案实现音频会议或电话系统后，您需要规划实施项目的执行。

如果你的组织只有一个或两个网站，你可能不需要完成本文中提供的所有详细信息，但你应该通读它以指导你的方法。

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>部署模型 

与转换组织中人员工作方式的任何技术实现一样，选择执行部署的正确方式将大大影响云语音实现的成功。

潜在的部署模型包括以下内容：

-   **每个网站：** 此模型适用于组织地理位置分散的情况，并且分支具有大量员工。 但是，此部署模型可能会中断部门员工在多个地点分布的部门内的通信。

-   **每个部门**：此模型通常是适用于中等规模公司的更佳选项，可确保所涉及的部门具有相同的体验。

-   **一次全公司：** 此模型通常是小型公司的最佳选择，其中所有员工都可以从部署的第一天获得相同的体验。


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定适用于你的组织的团队部署执行模型。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录你选择的团队部署执行模型，并包括业务和技术论证。</li></ul></td></tr></table>

## <a name="raci-modeling"></a>RACI 建模

若要确保对项目中的哪些人负责你对项目的负责，请使用责任作业矩阵（也称为 "RACI"），即 "负责"、"有责任的"、"咨询" 和 "已通知"-矩阵。 列出负责每个任务的人员或组，以及要在决策制定过程中咨询的利益干系人，以及在整个项目执行过程中通知的风险承担者的每个决策和操作。

以下是云语音实现的 RACI 矩阵的示例。

| 活动/角色                                         | 项目主管 | 协作主管/架构师 | 顾问 | 变更管理/采用专业人员 | 业务单位代表 |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| 计划演示动员会调用                     | R、A         | C                            |            |                                       |                               |
| 设置通话质量仪表板                         | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | C                            | R、A       |                                       |                               |
| 在动员通话期间共享发现问卷 | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | C                            | R、A       |                                       |                               |
| 构想阶段动员                                | R、A         | C                            |            |                                       |                               |
| 业务使用案例研讨会                           | A            |                              |            | R                                     | C                             |
| 查看 "发现调查表"                    |              | R、A                         | C          |                                       |                               |
| 体系结构研讨会                                 | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | R、A                         | C          |                                       |                               |
| 采纳用户方案构想阶段研讨会       | C            | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。                            | A          | R                                     |                               |
| 采纳成功研讨会                             |              |                              | R、A       | C                                     |                               |
| 客户端和设备准备情况研讨会                  | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            |                              | R、A       | C                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定与云语音实现项目相关的活动/角色。</li><li>确定要分配给云语音实现项目的责任分配矩阵（RACI 矩阵）的团队或人员。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录 RACI 矩阵。</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>季度执行计划

若要在可管理的工作块中执行云语音部署，我们建议你根据目标密钥结果（OKRs）、你选择的部署模型和你的组织的项目执行功能来创建季度语音部署。

这样，您就可以按季度跟踪进度，根据需要修订计划，并根据组织的执行容量部署云语音功能。

如果你的组织只有一个或两个网站，你可能不需要季度执行计划，因为你希望在短时间内完全部署。

下面是云语音实现的 Envision 阶段的季度执行计划的示例。

| 站点/部门                            | 员工数 | 音频会议 | 电话系统                    | 要执行的季度 |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| 美国：纽约                             | 2000                | 是                | 具有通话套餐的电话系统 | 第1季度 CY2018          |
| 爱尔兰：都柏林                          | 300                 | 是                | 具有通话套餐的电话系统 | 第1季度 CY2018          |
| 奥地利：维也纳                          | 500                 | 是                | 电话系统直接路由     | 第2季度 CY2018          |
| 意大利： Milan                             | 200                 | 是                | 不适用                             | 第2季度 CY2018          |
| 南美洲：巴西                    | 1500                | 是                | 电话系统直接路由     | 第2季度 CY2018          |
| 印度：新德里                             | 7000                | 是                | 不适用                             | 第3季度 CY2018          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定 "季度执行计划" 以实现目标键结果（OKRs）。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录季度执行计划。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>沟通和管理计划

若要让项目利益干系人与部署进度保持最新，你需要制定一套计划，了解如何在核心项目团队成员以及利益干系人讨论与项目状态相关的问题？针对已建立的 KSIs、操作指标和战略目标的项目里程碑、阻止和各种评价。

下面是您可以在云语音实现项目中利用的通信和管理计划的示例。

| 类型                                        | 目的                                                                                                                                                      | 者 | 天/时间                                     | 位置             | 会议所有者 |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Project standup 通话                       | 项目状态的同步，跟踪关键里程碑和阻止程序                                                                                           | TBA          | 星期一、星期二、星期三、星期四下午5点 PST | 虚拟              | TBA           |
| 每周筹划指导委员会                   | 查看云语音项目的状态，向主管人员报告，提出需要管理人员帮助解决的问题                                        | TBA          | 每个星期五上午11点 PST                        | 虚拟              | TBA           |
| 每月项目业务/操作评审 | 通过扩展的利益干系人、主要联系点和执行发起人检查项目状态;查看部署计划、KSIs 和操作指标 | TBA          | 每月的第二个星期二                       | 虚拟或个人 | TBA           |
| 季度商业考评（QBR）             | 检查项目状态并根据战略目标、KSIs 和运营指标查看进度;必要时重新访问计划                                 | TBA          | 每个季度的最后一个星期四                | 人            | TBA           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定通信和监管计划，包括定期状态更新（每天、每周、每月或每季度）的频率、用于实施状态更新会议的方法和每个会议的所有者。</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录通信和管理计划。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>完成我的成功计划

成功计划是你在构想阶段创建的文档的摘要。

成功计划为项目团队提供了项目团队，其中包括 FastTrack 或部署合作伙伴-通过使用呼叫计划服务实施音频会议或电话系统，可实现组织的目标的充足信息。

通常情况下，成功计划包含以下主要部分，这些主要部分将通过构想阶段进行了处理：

-   业务案例

-   服务就绪

-   服务决策

-   执行计划

-   采用计划

-   运营计划

### <a name="business-case"></a>业务案例

业务使用案例、利益干系人、OKRs 和 KSIs、风险登记和项目日程表的列表通常构成了业务案例所需的大量信息。 应将这些内容记录为成功计划的一部分。

### <a name="service-readiness"></a>服务就绪

你的环境评估提供初始信息，以确定你的组织的技术准备情况，以便通过呼叫计划实现音频会议和/或电话系统。

此处包括您的服务准备情况评估以及用于解决通过环境评估发现的需要补救的领域的计划。

### <a name="service-decisions"></a>服务决策

记录如何为组织的通话计划服务技术实施计划音频会议或电话系统。

### <a name="execution-plan"></a>执行计划

记录如何计划项目在整个组织中实现解决方案的执行。

### <a name="adoption-plan"></a>采用计划

在执行采纳准备情况评估后，项目团队需要提出一套全面的沟通计划、一个培训计划以及预启动、启动和启动后的采纳活动计划。

标识支持采纳活动（如传单、欢迎电子邮件和培训资料）的资源，以及满足组织要求所需的自定义。

从[Microsoft 团队客户成功工具包](https://www.microsoft.com/download/details.aspx?id=54244)下载采纳活动的模板。

### <a name="operational-plan"></a>运营计划

映射操作角色的操作将建立角色和职责，以及分配给每个操作角色的团队，您将需要支持音频会议的实现。

您需要完成此操作并将运营计划作为成功计划的一部分包括在内，以确保解决方案的操作准备就绪。

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定你将如何记录整个成功计划，以便提供云语音工作负荷。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>确认成功计划的所有组件均已记录。</li><li>将成功计划的单个组件聚合到单个摘要文档中（可选）。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
