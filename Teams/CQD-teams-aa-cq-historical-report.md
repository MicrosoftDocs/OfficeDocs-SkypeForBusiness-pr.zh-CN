---
title: 使用 CQD Power BI 报表查看自动助理 & 呼叫队列历史记录报告
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解如何使用呼叫质量仪表板 Power BI 报表查看自动助理和呼叫队列历史记录数据。
ms.openlocfilehash: 874bb87a32895bdec29aab1b0aaee20bdecb0fc2
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908771"
---
# <a name="what-are-the-requirements"></a>有哪些要求？ 
您需要安装 Power BI Desktop。 你可以从 [Microsoft Windows 应用商店](https://aka.ms/pbidesktopstore)安装它。

你可以使用 Power BI Desktop 的免费版本。 最低兼容版本是 2.85.681.0 2020 年9月 () 。

## <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限
用于查看 AA & CQ Analytics 历史记录报告的帐户需要具有访问 CQD 数据管道的权限。 有关详细信息，请参阅 [CQD access 角色](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 。

## <a name="installation"></a>安装 
以下步骤假设你已在计算机上安装了 Power BI Desktop，并且你的帐户具有访问 CQD 数据管道所需的权限。

请执行以下步骤：
- 下载 [CQD 团队自动助理 & 呼叫队列历史报告模板](https://aka.ms/TAPAACQAnalytics) ，并将其保存到计算机上的目录中。
- 双击该模板，然后启动 Power BI Desktop。
- 系统将提示你选择 CQD 数据管道区域。 选择你的租户所在的地区。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

 - 你可以使用 Skype for Business Online cmdlet (CsTenant) 查看区域。ServiceInstance 输出。 
 该区域将在此示例中按如下方式显示：此示例中的 "microsoftcommunicationsonline/noam-4a-s7" 区域为 noam。
 - 报表将启动并提供示例数据。
 - 若要查看自己的数据，请单击 "开始" 选项卡中 "Power BI Desktop 中的查询" 下的 " **刷新** "。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

- 系统将提示您登录。 选择 " **组织帐户** "，然后选择 **"登录"** 。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

- 选择 " **连接** " 并查看数据刷新。

## <a name="data-latency-any-aa--cq-analytics"></a>数据延迟任何 AA & CQ 分析
数据将在30分钟内在 CQD 数据管道中可用。

你将必须刷新数据才能查看新的分析数据。 

## <a name="customization"></a>自定 
你可以自定义报表的某些可视化内容，例如添加或删除要显示在各种可视化效果中的字段，以及更改图表类型等。

不能添加报表中提供的其他数据字段，而不能添加其他数据字段。

### <a name="change-color-schema"></a>更改颜色架构 
以下步骤假设你已完成安装步骤。

请执行以下步骤：
- 在功能区上选择 " **视图" 选项卡** 。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

- 从下拉列表中选择颜色架构。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::


## <a name="cqd-fields-description"></a>CQD 域说明

|名称                                    |数据类型                |说明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|自动助理标识                 |型                   |附加到 AA 的资源帐户的名称<br>示例： aa_test@microsoft.com|
|自动助理链开始时间         |datetime                 |AA 链开始时间                    |
|自动助理目录搜索方法  |型                   |最后一个通讯簿搜索方法        |
|自动助理转接操作          |型                   |呼叫转移目标类型<br>可能的值：<br>§未知-未指定实体类型<br>§用户-用户实体<br>§ orgaa-组织的自动助理实体<br>第 hunt_group-通话队列实体<br>§应用程序-语音应用程序实体<br>§ external_pstn-外部 PSTN 实体<br>§ shared_voicemail-共享语音邮件实体|
|自动助理呼叫结果              |型                   |呼叫结果：<br>§未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自动助理呼叫流                |型                   |封装自动助理呼叫的不同状态<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>第节公告|
|是否涉及自动助理              |Boolean                  |指示是否涉及到通话中的 AA |
|自动助理呼叫方操作计数      |int                      |由呼叫者使用的操作计数         |
|自动助理链持续时间（秒）   |int                      |AA 中的通话持续时间                 |
|呼叫队列呼叫结果                  |String                   |呼叫队列呼叫最终状态<br>可能的值：<br>第节错误<br>第节已拒绝<br>§ overflown<br>§失败<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|呼叫队列最终状态操作           |String                   |呼叫队列最终操作<br>可能的值：<br>§前进<br>§断开连接<br>第节语音邮件<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§其他|
|通话队列标识                     |String                   |附加到 CQ 的资源帐户的名称<br>示例： aa_test@microsoft.com|
|通话队列为会议模式           |Boolean                  |如果在 CQ 上启用了会议模式，则设置为1 |
|呼叫队列目标类型                  |String                   |预期呼叫重定向目标类型     |
|从通话队列标识转移    |Boolean                  |附加到 CQ 的资源帐户的名称，此呼叫被转移到此呼叫<br>示例： aa_test@microsoft.com|
|通话队列代理选择次数           |int                      |通话时此队列可用的代理计数 |
|呼叫队列代理计数                  |int                      |通话时分配给此队列的代理的计数 |
|涉及通话队列                  |Boolean                  |如果呼叫队列涉及到此呼叫等于1 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI 数据模型维度

|名称                                    |数据类型                |说明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AA 名称                                   |型                   |自动助理 Id (资源帐户 Id)  |
|AACallFlow                              |型                   |封装自动助理呼叫的不同状态<br> abs_search<br> call_termination<br> call_transfer<br> main_menu<br> user_selection<br> speech_input_confirmation<br> first_level_menu<br> automatic_menu<br>声明 |
|AACallResult                            |型                   |自动助理呼叫的结果：<br>未知<br> transferred_to_user<br> transferred_to_operator<br> failover_to_operator<br> user_terminated<br> service_declined-AA 配置错误<br> service_terminated-内部 AA 错误<br> failed_to_establish_media<br> terminated_no_operator<br> terminated_transfer_failed<br> terminated_automatic_selection<br> transferred_to_shared_voicemail<br> oaa_chain_too_long<br> oaa_session_too_long          |
|AAChainDuration                         |型                   |自动助理通话的持续时间（秒）  |
|AACount                                 |型                   |自动助理的编号涉及呼叫         |
|AADirectorySearchMethod                 |型                   |通话中使用的搜索方法：<br> abs_search_dtmf<br> abs_search_extension<br> abs_search_name<br>UTC 格式的 AAStartTime 字符串调用时间      |
|AATransferAction                        |型                   |呼叫接收器：<br>未知-未指定实体类型<br>用户-用户实体<br> AA-组织的自动助理实体<br> CQ-通话队列实体<br>应用程序-语音应用程序实体<br> external_pstn-外部 PSTN 实体<br>shared_voicemail 共享的语音邮件实体      |
|PSTNMinutes                             |int                      |总分钟使用率                          |
|呼叫队列呼叫结果                  |型                   |呼叫队列呼叫最终状态<br>可能的值：<br>错误<br>拒绝<br> overflown<br>失败<br> timed_out<br> transferred_to_agent<br>agent_joined_conference    |
|通话队列标识                     |型                   |附加到 CQ 的资源帐户的名称     |
|呼叫队列目标类型                  |型                   |预期呼叫重定向目标类型：<br>用户<br>应用程序终结点<br>其他     |
|呼叫队列呼叫结果                  |型                   |呼叫队列呼叫最终状态<br>可能的值：<br>错误<br>拒绝<br> overflown<br>失败<br> timed_out<br> transferred_to_agent<br>agent_joined_conference           |
|呼叫队列最终状态操作           |型                   |呼叫队列最终操作<br>可能的值：<br>转发<br>断开连接<br>语音邮件<br> disconnect_with_busy<br> shared_voicemail<br> failed_to_accept_call<br>之外             |
|代理名称                              |型                   |用户 UPN               |


### <a name="measures"></a>衡量指标

|名称                                      |类型                       |说明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AACallerActionCount                     |int                        |通话期间在 AA 中由用户选择的操作数  |
|PSTNMinutes                             |int                      |总分钟使用率                                  |
|TotalCallCount                          |int                      |呼叫数                                          |
|平均通话持续时间 ( 秒)          |int                      |通话队列呼叫的总持续时间（秒）     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI graph 说明自动助理

|名称                                      |描述                            |
|---------------------------------------:|:-------------------------------------:|
|来电来源                    |由内部/外部呼叫源进行呼叫的分发      |
|目录搜索方法总计          |按搜索类型分配呼叫                         |
|呼叫方操作                           |通过呼叫接收器分配呼叫                       |
|呼叫结果                             |通过最终呼叫状态进行呼叫的分发                    |
|调用方操作计数                     |通话期间使用的电话号码分配  |


### <a name="call-queue"></a>通话队列

|名称                                      |描述                            |
|---------------------------------------:|:-------------------------------------:|
|来电来源                    |由内部/外部呼叫源进行呼叫的分发         |
|呼叫量                             |通过呼叫队列分配呼叫                            |
|呼叫者结果                           |通过呼叫结果分配呼叫                            |
|超时/溢出调用总操作      |未转发的分发 (通过调用结果放弃) 调用   |
|转移/转发目标总额          |通过呼叫结果转发的通话的分配                  |
|已放弃的通话比率                   |成功放弃的通话计数的比率                    |
|平均会话长度 (秒)         |按放弃/成功通话分组的呼叫长度（以秒为单位）   |



### <a name="agent-timeline"></a>代理日程表

|名称                                                      |描述                            |
|-------------------------------------------------------:|:-------------------------------------:|
|按代理拨打的通话次数                                        |通过呼叫队列和代理分配呼叫                 |
|代理和呼叫队列) 的通话总持续时间 (秒   |按代理和通话队列拨打的通话总持续时间 (秒)      |
|按代理名称) 的平均通话持续时间 (秒            |代理拨打的平均持续时间 (秒)                   |



## <a name="known-issues"></a>已知问题
- 目前，呼叫队列和自动助理显示资源帐户 Id，而不是呼叫队列/自动助理名称。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。
- 当前，仪表板中仅有28天的历史记录，因为通话队列/自动助理数据被视为最终用户身份信息，并且受数据隐私保留策略制约。
