---
title: 自动助理&调用队列历史报告
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 了解如何使用呼叫质量仪表板 Power BI 报表查看自动助理和呼叫队列历史数据。
ms.openlocfilehash: ec345a66a06b03bb9926ff74ceac7b85b31a0190
ms.sourcegitcommit: 850038f2248c1ea412f7b5daca26c0598baffa3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2022
ms.locfileid: "67443339"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自动助理&调用队列历史报告

Teams 自动助理&呼叫队列历史报表 Power BI 模板提供以下三个报表：

- [自动助理](media/cqd-teams-aa-cq-historical-report-sample-aa.png) - 显示针对进入自动助理的呼叫的分析。
- [呼叫队列](media/cqd-teams-aa-cq-historical-report-sample-cq.png) - 显示对进入呼叫队列的呼叫的分析。
- [代理时间线](media/cqd-teams-aa-cq-historical-report-sample-at.png) - 显示代理在呼叫队列调用中处于活动状态的时间线视图。

这些报表使用 [来自呼叫质量仪表板](CQD-Power-BI-query-templates.md) 数据存储的数据。 这些报告允许组织报告自动助理和呼叫队列正在处理的呼叫数。  这些报表还提供对调用队列中的代理性能的见解。

### <a name="v163-published-on-august-24-2022"></a>V1.63 发布于 2022 年 8 月 24 日

## <a name="prerequisites"></a>先决条件

### <a name="power-bi-desktop"></a>Power BI Desktop
需要安装Power BI Desktop。 可以从 [Microsoft Windows 应用商店](https://aka.ms/pbidesktopstore)安装它。

可以使用免费版本的Power BI Desktop。 最低兼容版本为 2020 年 9 月)  (2.85.681.0。

### <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限

用于查看历史报表的帐户需要具有访问 CQD 数据管道的权限。 有关详细信息，请参阅 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>安装 

以下步骤假定你已在计算机上安装Power BI Desktop，并且帐户具有访问 CQD 数据管道所需的权限。

执行以下步骤：

- 下载 [CQD Power BI 查询模板](https://www.microsoft.com/download/details.aspx?id=102291) 并将 zip 文件保存到计算机上的目录。

- 双击 zip 文件以将其打开。

- 双击“CQD Teams 自动助理&呼叫队列历史报告 V1.60.pbit”模板文件。 应启动Power BI Desktop。

- 系统将提示你选择 CQD 数据管道区域。 选择租户所在的区域。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="选择 CQD 数据管道区域的屏幕截图。":::

- 可以使用 [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet 获取租户所在的区域。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 区域将显示 **/** 在上述示例中，其中区域为：noam

 - 报表将随示例数据一起启动。
 
 - 若要查看自己的数据，请在Power BI Desktop中的“查询”下的“开始”选项卡中选择 **“刷新**”。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="选择刷新选项的屏幕截图。":::

- 系统会提示你登录。 选择 **组织帐户** ，然后选择 **“登录**”。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="显示登录名的屏幕截图。":::

- 选择 **“连接”** 并观看数据刷新。

## <a name="data-latency-and-aa--cq-analytics"></a>数据延迟和 AA & CQ 分析

数据通常在呼叫完成后 30 分钟内可用;但是，有时可能需要几个小时才能显示数据。 

必须刷新数据才能查看任何新数据。

## <a name="customization"></a>定制 

可以自定义报表的某些可视化效果方面，例如添加或删除要在各种可视化效果中显示的字段、更改图表类型等。

报表包含当前可用的所有数据指标。

### <a name="change-color-schema"></a>更改颜色架构 

以下步骤假定你已完成安装步骤。

执行以下步骤：
- 选择功能区上的 **“视图”选项卡** 。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="选择“视图”选项卡以更改配色方案的屏幕截图。":::

- 从下拉列表中选择颜色架构。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="显示各种配色方案的屏幕截图。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自动助理和呼叫队列历史报告定义

### <a name="cloud-auto-attendant-analytics"></a>云自动助理分析

#### <a name="report-description"></a>报表说明

|报表部分                          |说明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|传入呼叫源<sup>1</sup>        |由内部/外部呼叫源分发调用            |
|目录搜索方法                 |按搜索类型分发调用                              |
|调用方操作计数                     |按呼叫期间使用的号码操作分配调用       |
|AA 中的平均秒数                   |调用方在 AA 中花费的平均秒数                 |
|平均调用方操作                  |调用方在 AA 中执行的平均操作数               |
|调用结果                            |按最终调用状态分配呼叫                         |
|报表的下半部分                 |呼叫流细分                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡            |报表名称     |源表名称            |全局筛选器                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|自动助理        |fAutoAttendant        |AutoAttendant                |无                                   |

|报表部分                                  |字段 () 使用                              |应用的筛选器     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期选择器                                   |AAStartTime                                |无                |
|时间范围选择器                             |AAStartHour                                |无                |
|自动助理                                  |AA 名称                                    |无                |
|传入呼叫源<sup>1</sup>                |呼叫类型<br>TotalCallCount (度量值) 总和 |外部调用：呼叫类型为外部<br>内部调用：呼叫类型为内部 |
|目录搜索方法                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod 是abs_search_dtmf或abs_search_name    |
|调用方操作计数                             |AACallerActionCount<br>TotalCallCount      |无                                                             |
|AA 中的平均秒数                           |AAChainDuration (度量值)                   |无                                                             |
|平均调用方操作                          |AACallerActionCount (度量值)               |无                                                             |
|调用结果                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |无                                       |
|报表的下半部分                         |AA 名称<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>呼叫类型<br>MM-DD<br>TotalCallCount |无       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名称                                 |文本                     |附加到自动助理的资源帐户的名称<br><br>如果 **aa_test@microsoft.com** 完整的资源帐户名称，则此值将为： **aa_test** |
|AACallerActionCount                     |整数             |汇总：总和<br>呼叫期间由自动助理中的调用方选择的操作计数  |
|AACallerActionCount (度量值)           |整数             |与上面相同，如果没有调用而不是空白，则为 0                              |
|AACallFlow                              |文本                     |封装自动助理呼叫的不同状态 -可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |文本                     |最终调用结果--可能的值：<br><br>§ failed_to_establish_media (无法建立呼叫的媒体部分) <br>§ failover_to_operator (调用通常由于系统错误) <br>§ oaa_chain_too_long (AA) 中腿部过多<br>§ oaa_session_too_long (AA 会话持续时间过长) <br>§ service_declined (AA 不接受呼叫) <br>§ service_terminated (AA 配置断开呼叫或呼叫挂起) <br>§ terminated_automatic_selection (AA 配置断开调用) <br>§ terminated_no_operator (调用因错误而终止，未定义运算符)  <br>§ terminated_transfer_failed (调用因传输失败而终止 - 通常为外部号码) <br>§ transfer_in_progress (AA->AA 传输) <br>§ transferred_to_operator (调用已转移到操作员 - 通常是由于用户错误) <br>§ transferred_to_receptionist (与transferred_to_operator) 相同<br>§ transferred_to_self (调用返回到 AA 的开头 - 通常从菜单公告选项) <br>§ transferred_to_shared_voicemail (呼叫已转移到共享语音邮件) <br>§ transferred_to_user (呼叫已传输给用户 - 包括呼叫队列) <br>§ 未知 (发生未知情况) <br>§ user_terminated (调用方挂起)  |
|AA 呼叫图例                          |文本                     |基于 AACallResult 设置图例项                               |
|AAChainDuration                         |小数           |汇总：总和<br>自动助理呼叫的持续时间                     |
|AAChainDuration (度量值)                |小数           |与上面相同，如果没有调用而不是空白，则为 0              |
|AAChainIndex                            |文本                     |                                                                         |
|AAConnectivityType                      |文本                     |调用类型--可能的值：<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |文本                     |呼叫中涉及的自动助理数                               |
|AADirectorySearchMethod                 |文本                     |上一个通讯簿搜索方法--可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |小数           |自动助理呼叫开始时间                                           |
|AAStartTime                             |日期/时间                |自动助理呼叫开始时间                                           |
|AATransferAction                        |文本                     |调用传输目标类型--可能的值：<br><br>§ 应用程序 - 语音应用程序实体<br>§ external_pstn<br>§ hunt_group - 呼叫队列实体<br>§ orgaa - 自动助理实体<br>§ shared_voicemail<br>§ 未知<br>§ 用户 |
|呼叫类型<sup>1</sup>                   |文本                     |调用类型--可能的值：<br><br>§ 外部<br>§ 内部           |
|IsAAInvolved                            |文本                     |始终 1                                                                 |
|MM-DD                                   |文本                     |自动助理呼叫月日                                            |
|PSTNMinutes                             |整数             |汇总：总和<br>总分钟使用量                                     |
|TotalCallCount                          |整数             |汇总：总和<br>Always 1 - 用于提供所有调用的总和            |
|TotalCallCount (度量值) 总和         |整数             |与上面相同，如果没有调用而不是空白，则为 0              |


### <a name="cloud-call-queue-analytics"></a>云呼叫队列分析

#### <a name="report-description"></a>报表说明

|报表部分                          |说明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|传入呼叫源<sup>1</sup>        |由内部/外部呼叫源分发调用             |
|平均等待时间 (秒)              |接听和放弃呼叫的等待时间                          |
|调用卷和代理选择加入计数      |按呼叫队列分配呼叫/最大代理选择加入计数  |
|调用结果                            |按调用结果分配调用                               |
|放弃的呼叫                         |通过呼叫队列分发放弃的呼叫                     |
|平均会话长度 (秒)         |调用长度（以秒为单位）按调用结果分组                      |
|呼叫溢出/超时目标      |超时或溢出的调用的分布                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡            |报表名称                                   |源表名称                               |全局筛选器       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|呼叫队列            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |无                |

|报表部分                      |表 -> 字段 () 使用                |应用的筛选器       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期选择器                       |fCallQueueAnalytics ->日期           |无                  |
|时间范围选择器                 |fCallQueueAnalytics -> CQHour         |无                  |
|调用队列资源帐户         |fCallQueueAnalytics -> CQ 名称        |无                  |
|传入呼叫源<sup>1</sup>    |fCallQueueAnalytics ->调用计数总和 (度量值) <br>fCallQueueAnalytics -> 调用类型    |外部调用：呼叫类型为外部<br>内部调用：呼叫类型为内部 |
|Avg Wait Time (秒) -Before Answered |fCallQueueFinalStateAction ->平均 CQ 持续时间 (度量值)  |呼叫队列呼叫结果agent_joined_conference或transferred_to_agent|
|Avg 等待时间 (秒) -弃用前 |fCallQueueFinalStateAction ->平均通话持续时间 (度量值)  |呼叫队列呼叫结果未agent_joined_conference、transferred_to_agent、溢出、timed_out |
|调用卷和代理Opt-In计数   |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->呼叫队列代理选择加入计数<br>fCallQueueAnalytics -> CQ 名称<br>fCallQueueAnalytics ->日期 |无 |
|放弃的呼叫                     |fCallQueueAnalytics ->日期<br>fCallQueueAnalytics -> TotalCallCount | 呼叫队列调用结果图例已放弃 |
|平均会话长度 (秒)     |fCallQueueFinalStateAction ->平均呼叫队列持续时间 (秒) <br>呼叫队列调用结果图例 |平均呼叫队列持续时间 (秒) > 0 |
|呼叫溢出/超时目标  |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->调用队列目标类型<br>fCallQueue 目标类型图例 |呼叫队列目标类型图例不包含已放弃和代理应答 |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|呼叫计数                              |整数             |汇总：总和<br>通话的数量                                          |
|呼叫队列代理计数                  |整数             |汇总：总和<br>在调用队列中配置的代理数            |
|呼叫队列代理选择加入计数           |整数             |汇总：总和<br>选择加入呼叫队列的代理数              |
|呼叫队列调用结果                  |文本                     |呼叫队列调用最终状态 - 可能的值：<br><br>§ agent_joined_conference (接听会议模式呼叫) <br>§ 已拒绝<br>§ 已断开连接<br>§ 错误<br>§ 失败<br>§ 无效<br>§ 溢出 (溢出条件满足) <br>§ timed_out (超时条件满足) <br>§ transferred_to_agent (应答传输模式调用 {default})  |
|呼叫队列调用结果图例           |文本                     |基于呼叫队列结果设置图例项                             |
|呼叫队列目标类型                  |文本                     |***调用重定向目标类型--可能的值：***<br><br>§ ApplicationEndpoint<br>§ 邮箱<br>§ 其他<br>§ 用户 |
|呼叫队列目标类型图例           |文本                     |基于呼叫队列目标类型设置图例项                        |
|呼叫类型<sup>1</sup>                   |文本                     |调用类型--可能的值：<br><br>§ 外部<br>§ 内部             |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|CQ 小时                                 |整数             |呼叫队列呼叫开始时间                                                 |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)                                  | 
|DateTimeCQName                          |文本                     |用于在 fCallQueueFinalStateAction 上进行筛选的唯一键                     |
|PSTN 连接类型                  |文本                     |调用类型--可能的值：<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN 总分钟数                      |整数             |汇总：总和<br>PSTN 调用的总分钟数                       |
|调用计数 (度量值) 总和             |整数             |但是，当未调用时，呼叫计数将相同为 0                          |
|TotalCallCount (度量值)                 |整数             |汇总：总和<br>呼叫计数                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 字段说明

|名称                                    |数据类型                |说明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通话持续时间 (秒)          |小数           |汇总：总和<br>放弃呼叫的平均通话持续时间（以秒为单位）    |
|平均呼叫队列持续时间 (秒)        |小数           |汇总：总和<br>应答呼叫的平均等待时间（以秒为单位）           |
|平均通话持续时间 (度量值)   |整数             |与平均通话持续时间 (秒相同) 但是，如果没有调用，则为 0   |
|平均 CQ 持续时间 (度量值)     |整数             |与平均呼叫队列持续时间 (秒) 但是，如果没有呼叫，则为 0 |
|呼叫计数                              |整数             |汇总：总和<br>通话的数量                                         |
|呼叫队列调用结果                  |文本                     |呼叫队列调用最终状态 - 可能的值：<br><br>§ agent_joined_conference (接听会议模式呼叫) <br>§ 已拒绝<br>§ 已断开连接<br>§ 错误<br>§ 失败<br>§ 无效<br>§ 溢出 (溢出条件满足) <br>§ timed_out (超时条件满足) <br>§ transferred_to_agent (应答传输模式调用 {default} |
|呼叫队列调用结果图例           |文本                     |基于呼叫队列调用结果设置图例项                      |
|调用队列最终状态操作           |文本                     |调用队列最终操作 -- 可能的值：<br><br>§ 断开 (timed_out调用) <br>§ disconnect_with_busy (溢出的呼叫) <br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ 其他<br>§ 语音邮件                |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)                                  |
|DateTimeCQName                          |文本                     |用于在 fCallQueueFinalStateAction 上进行筛选的唯一键                     |
|IsAbandoned                             |True/false               |如此 如果代理未接听呼叫                                   |


### <a name="cloud-call-queue-agent-timeline"></a>云呼叫队列代理时间线

#### <a name="report-description"></a>报表说明

|报表部分                                          |说明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|代理的呼叫数                                |通过呼叫队列和代理分发呼叫                |
|按代理和所有队列进行分发                     |代理和呼叫队列的调用分布                |
|表 (右下)                                     |按代理分配具有平均和总通话持续时间的调用 |
|代理) 的平均呼叫持续时间 (秒                |代理调用的平均持续时间 (秒) 秒                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡            |报表名称           |源表名称         |全局筛选器       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|代理时间线        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |无                |


|报表部分                                |字段 () 使用                         |应用的筛选器       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日期选择器                                 |Datetime                              |无                  |
|代理用户名选择器                       |代理名称                            |无                  |
|呼叫队列资源帐户选择器          |CQ 名称                               |无                  |
|代理的呼叫数                      |代理名称<br>呼叫计数<br>Hour      |无                  |
|按代理和呼叫队列进行分发          |代理名称<br>平均通话持续时间 (秒) <br>呼叫计数<br>CQ 名称 |无                      |
|左下角                                   |代理名称<br>平均通话持续时间 (秒) <br>呼叫计数<br>呼叫持续时间 (分钟) <br>CQ 名称<br>Hour<br>MM-DD | 无 |
|代理) 的平均呼叫持续时间 (秒      |代理名称<br>平均通话持续时间 (秒)  | 无 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|代理名称                              |文本                     |用户 UPN<br>如果 user@microsoft.com 完整用户 **名，则** 此值将为： **用户** |
|平均通话持续时间 (秒)          |小数           |汇总：总和<br>应答呼叫队列呼叫的平均持续时间（以秒为单位） |
|呼叫计数                              |整数             |汇总：总和<br>代理应答的呼叫数     |
|呼叫持续时间 (分钟)                  |整数             |汇总：总和<br>应答呼叫队列呼叫的总呼叫持续时间（以分钟为单位）， (舍入到最接近的分钟)   |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|日期                                    |日期                     |通话日期                                             |
|Datetime                                |Datetime                 |通话日期                                             |
|Hour                                    |整数             |通话时间                                             |
|MM-DD                                   |文本                     |通话的月份和日期                                    |


> [!NOTE]
> 当呼叫到达第一个呼叫队列时，如果该队列中已等待的呼叫数已达到 **呼叫溢出处理** 限制，如果重定向选项将新呼叫发送到第二个呼叫队列，则第二个呼叫队列中的代理将显示为在此报表的第一个呼叫队列中。 

## <a name="known-issues"></a>已知问题

- 呼叫队列和自动助理由资源帐户的 ID 而不是呼叫队列/自动助理名称显示。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 仪表板中只有 28 天的历史记录可用，因为呼叫队列/自动助理数据被视为个人数据，并且受数据隐私保留策略的约束。

- 在某些情况下，云呼叫队列代理时间线报表上的代理应答呼叫计数可能不同于 Teams 客户端呼叫历史记录中显示的呼叫数。 Teams 客户端调用历史记录正确。 支持部门正在调查，但目前估计没有时间进行修复。

- <sup>1</sup> 自动助理和呼叫队列图中的 **传入呼叫源** 显示最终呼叫腿源，而不是初始呼叫腿源。 例如，如果自动助理收到外部呼叫并将呼叫转移到另一个自动助理或呼叫队列，则 **传入呼叫源** 将报告为内部呼叫源。

## <a name="version-history"></a>版本历史记录
|版本  |发布日期     |文件名                                                           |说明                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.63     |2022 年 8 月 24 日    |CQD Teams 自动助理&调用队列历史报告 V1.63.pbit |请参阅：<br>CQD Teams 自动助理&呼叫队列历史报告 - 更改下载的 zip 文件中的Log.docx以获取更改列表                                                                             |
|1.60     |2022 年 7 月 22 日      |CQD Teams 自动助理&调用队列历史报告 V1.60.pbit |请参阅：<br>CQD Teams 自动助理&呼叫队列历史报告 - 更改下载的 zip 文件中的Log.docx以获取更改列表                                                                             |
|1.00     |2020 年 11 月 5 日   |CQ 和 AA 组合分析 20201105.pbit                         |初始版本                                     |



