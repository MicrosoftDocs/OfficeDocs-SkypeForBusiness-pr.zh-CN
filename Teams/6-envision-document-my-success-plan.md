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
description: 选择一个部署模型，根据 RACI (制定责任) ，创建执行和管理计划。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b891db54d7202eb24df969e3d510a4cc5d7c8be3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624814"
---
# <a name="document-my-success-plan"></a>记录成功计划

本文概述了正确记录云语音部署的要求。 通过在规划云语音部署时定义并记录所有决策点和下一步，可以确保所有利益干系人与项目团队成员一致，以成功实现成果。 

## <a name="execution-planning"></a>执行计划 

定义如何在组织中通过呼叫计划电话系统音频会议或音频会议后，需要规划实施项目的执行。

如果您的组织只有一个或两个网站，您可能不需要完成本文中提供的所有详细信息，但您应该通读它来指导您的方法。

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>部署模型 

与改变组织人员工作方式的任何技术实现一样，选择正确的部署方式将大大影响云语音实现的成功。

可能的部署模型包括：

-   **每个站点：** 此模型适用于组织地理位置分散且分支机构拥有大量员工的情况。 但是，此部署模型可能会中断部门内部的通信，部门员工分布在多个位置。

-   **按部门**：此模型通常是中型公司更好的选择，可确保相关部门具有相同的经验。

-   **一次全公司：** 此模型通常是小型公司的最佳选择，在小型公司中，所有员工从部署的第一天开始都获得相同的体验。


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定Teams适用于组织的部署执行模型。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录Teams部署执行模型，并包括业务和技术理由。</li></ul></td></tr></table>

## <a name="raci-modeling"></a>RACI 建模

为确保明确谁负责项目内容，请使用责任分配矩阵 (也称为 RACI-负责、负责、咨询并明智的矩阵) 。 列出每个任务负责和负责的一个或多个人员或组，以及决策过程中要咨询的利益干系人，以及在整个项目执行过程中向利益干系人通知每个决策和操作。

下面是云语音实现 RACI 矩阵的示例。

| 活动/角色                                         | 项目主管 | 协作主管/架构师 | 顾问 | 变更管理/采用专业人员 | 业务单位代表 |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| 程序演示开始呼叫                     | R、A         | C                            |            |                                       |                               |
| 设置呼叫质量仪表板                         | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | C                            | R、A       |                                       |                               |
| 在启动调用期间共享发现调查问卷 | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | C                            | R、A       |                                       |                               |
| 构想阶段开始                                | R、A         | C                            |            |                                       |                               |
| 业务用例研讨会                           | A            |                              |            | R                                     | C                             |
| 查看发现调查问卷                    |              | R、A                         | C          |                                       |                               |
| 体系结构研讨会                                 | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            | R、A                         | C          |                                       |                               |
| 采用用户方案构想阶段研讨会       | C            | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。                            | A          | R                                     |                               |
| 采用成功研讨会                             |              |                              | R、A       | C                                     |                               |
| 客户端和设备准备情况研讨会                  | 如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。            |                              | R、A       | C                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定与云语音实现项目相关的活动/角色。</li><li>根据云语音实现项目的 RACI 矩阵 (确定要分配到) 或人员。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录 RACI 矩阵。</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>季度执行计划

若要在可管理的工作区块中执行云语音部署，建议根据目标关键结果 (OKR) 、所选的部署模型以及组织的项目执行功能创建季度执行计划。

这样，可以按季跟踪进度、根据需要修订计划，以及根据组织的执行能力部署云语音功能。

如果组织只有一个或两个站点，可能不需要季度执行计划，因为预计在短时间内完全部署。

下面是云语音实现"构想"阶段的季度执行计划示例。

| 站点/分区                            | 员工数 | 音频会议 | 电话系统                    | 要执行的季度 |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| 美国：纽约                             | 2000                | 是                | 具有通话套餐的电话系统 | CY2018 年第 1 季度          |
| 爱尔兰：都柏林                          | 300                 | 是                | 具有通话套餐的电话系统 | CY2018 年第 1 季度          |
| 奥地利：奥地利                          | 500                 | 是                | 电话系统直接路由     | 第 2 季度 CY2018          |
| 意大利：意大利                             | 200                 | 是                | 不适用                             | 第 2 季度 CY2018          |
| 南美洲：巴西                    | 1500                | 是                | 电话系统直接路由     | 第 2 季度 CY2018          |
| 印度：巴基斯坦                             | 7000                | 是                | 不适用                             | Q3 CY2018          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定季度执行计划，以通过确定值 (关键) 。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录季度执行计划。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>通信和治理计划

若要使项目利益干系人随时了解部署进度，需要制定一个计划，规定核心项目工作组成员与利益干系人之间如何通信，以讨论与项目状态、关键里程碑、阻止程序以及针对已建立的 KSIS 对项目进行的各种评审相关的事项， 运营指标和业务目标。

下面是可以在云语音实现项目中利用的通信和管理计划的示例。

| 类型                                        | 目标                                                                                                                                                      | 参与者 | 天/时间                                     | 位置             | 会议所有者 |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Project支持呼叫                       | 同步项目状态，跟踪关键里程碑和阻止程序                                                                                           | TBA          | 星期一、星期二、星期三、星期四下午 5 点 PST | 虚拟              | TBA           |
| 每周指导委员会                   | 查看云语音项目的状态、向管理人员报告、提出需要高层帮助才能解决的问题                                        | TBA          | 每周五上午 11 点 PST                        | 虚拟              | TBA           |
| 每月项目业务/运营评审 | 与扩展的利益干系人、主要联系人和执行发起人一起检查项目状态;查看部署计划、KSIS 和操作指标 | TBA          | 月份第二个星期二                       | 虚拟或当场 | TBA           |
| QBR (季度业务)              | 检查项目状态，根据业务目标、KSIS 和运营指标查看进度;如果需要，请重新访问计划                                 | TBA          | 每个季度的最后一个星期四                | 当场            | TBA           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定通信和管理计划，包括日常状态更新的频率 (每日、每周、每月或每季度) 、用于召开状态更新会议的方法以及每个会议的所有者。</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录通信和治理计划。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>完成成功计划

成功计划是在"构想"阶段创建的文档摘要。

成功计划为项目团队（可能包括FastTrack合作伙伴）提供足够的信息，以实现组织实现音频会议或电话系统呼叫计划服务的目标。

一般情况下，成功计划包含以下主要部分，其中许多部分将在"构想"阶段完成：

-   业务案例

-   服务就绪

-   服务决策

-   执行计划

-   采用计划

-   运营计划

### <a name="business-case"></a>业务案例

业务用例、利益干系人列表、OKR 和 KSIS、风险注册和项目时间线通常包含业务案例所需的大部分信息。 应记录这些文档作为成功计划的一部分。

### <a name="service-readiness"></a>服务就绪

环境评估提供确定组织实现音频会议的技术准备情况所需的初始信息，以及/或电话系统呼叫计划。

此处包含服务准备情况评估和解决需要通过环境评估发现的修正领域的计划。

### <a name="service-decisions"></a>服务决策

使用呼叫计划服务技术实现电话系统计划音频会议或会议。

### <a name="execution-plan"></a>执行计划

记录如何计划项目的执行，以在整个组织中实施解决方案。

### <a name="adoption-plan"></a>采用计划

执行采用就绪性评估后，项目团队需要针对预启动、启动和发布后采用活动制定一套全面的沟通计划、培训计划和计划。

确定资源以支持采用活动，例如传单、欢迎电子邮件和培训材料，以及满足组织要求所需的任何自定义项。

从客户成功工具包 下载采用[Microsoft Teams模板](https://aka.ms/TeamsCustomerSuccess)。

### <a name="operational-plan"></a>运营计划

映射操作角色的运用将建立角色和责任，以及分配给每个操作角色的团队，你需要支持音频会议的实施。

需要完成此操作，并包含操作计划作为成功计划的一部分，以确保解决方案的操作就绪性。

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>决定如何记录传送云语音工作负荷的整个成功计划。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>确认成功计划的所有组件已记录。</li><li>将成功计划的单个组件聚合到单个摘要文档中， (可选) 。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
