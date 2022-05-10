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
description: 了解如何使用呼叫质量仪表板Power BI报表查看自动助理和呼叫队列历史数据。
ms.openlocfilehash: 66394094f51d58344f151b8ebb7059c2e390c089
ms.sourcegitcommit: 56d529cdbd8d8733350625316082f339ae8d66c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2022
ms.locfileid: "65294093"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自动助理&调用队列历史报告

Teams自动助理&呼叫队列历史报告Power BI模板提供以下三个报告：

- [自动助理](media/cqd-teams-aa-cq-historical-report-sample-aa.png) - 显示针对进入自动助理的呼叫的分析。
- [呼叫队列](media/cqd-teams-aa-cq-historical-report-sample-cq.png) - 显示对进入呼叫队列的呼叫的分析。
- [代理时间线](media/cqd-teams-aa-cq-historical-report-sample-at.png) - 显示代理在呼叫队列调用中处于活动状态的时间线视图。

这些报表使用 [来自呼叫质量仪表板](CQD-Power-BI-query-templates.md) 数据存储的数据。 这些报告允许组织报告自动助理和呼叫队列正在处理的呼叫数。  这些报表还提供对调用队列中的代理性能的见解。

## <a name="prerequisites"></a>先决条件

### <a name="power-bi-desktop"></a>Power BI Desktop
需要安装Power BI Desktop。 可以从 [Microsoft Windows Store](https://aka.ms/pbidesktopstore) 安装它。

可以使用免费版本的Power BI Desktop。 最低兼容版本为 2020 年 9 月)  (2.85.681.0。

### <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限

用于查看历史报表的帐户需要具有访问 CQD 数据管道的权限。 有关详细信息，请参阅 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>安装 

以下步骤假定你已在计算机上安装Power BI Desktop，并且帐户具有访问 CQD 数据管道所需的权限。

执行以下步骤：

- 下载 [CQD Power BI查询模板](https://www.microsoft.com/download/details.aspx?id=102291)，并将 zip 文件保存到计算机上的目录。

- 双击 zip 文件以将其打开。

- 双击“CQ 和 AA 组合分析 20201105.pbit”模板文件。 应启动Power BI Desktop。

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

- 然后，系统会提示你登录。 选择 **组织帐户** ，然后选择 **“登录**”。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="显示登录名的屏幕截图。":::

- 选择 **连接** 并观看数据刷新。

## <a name="data-latency-and-aa--cq-analytics"></a>数据延迟和 AA & CQ 分析

数据将在 30 分钟内在 CQD 数据管道中提供。

必须刷新数据才能查看新的分析数据。 

## <a name="customization"></a>定制 

可以自定义报表的某些可视化效果方面，例如添加或删除要在各种可视化效果中显示的字段、更改图表类型等。

无法向报表添加更多数据字段。

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
|传入呼叫源 <sup>1</sup>        |由内部/外部呼叫源分发调用             |
|目录搜索方法总计          |按搜索类型分发调用                               |
|调用方操作                           |通过呼叫接收器分发呼叫                             |
|调用结果                             |按最终调用状态分配呼叫                          |
|调用方操作计数                     |按呼叫期间使用的号码操作分配调用        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡            |报表名称     |全局筛选器                          |
|:---------------------|:---------------------|:--------------------------------------|
|自动助理        |fAutoAttendant        |AAStartTime 在过去 28 天内 |


|报表名称            |源表名称            |处理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant， <br>#“筛选行” = Table.SelectRows (源，每个真实) ， <br>#“Auto Attendant” = Table.AddColumn (#“Filtered Rows”， “AA Name”， each List.First (Text.Split ([AAIdentity]， “@”) ) ) ， <br>#“Changed Type” = Table.TransformColumnTypes (#“Auto Attendant”，{{“AAStartTime”， type datetime}}) ， <br>#“Remove Columns” = Table.RemoveColumns (#“Changed Type”，{“AAIdentity”})  |


|报表部分                                  |字段 () 使用                              |应用的筛选器     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期选择器                                   |AAStartTime                                |无                |
|自动助理                                  |AA 名称                                    |无                |
|传入呼叫源 <sup>1</sup>                |呼叫类型<br>TotalCallCount                |外部调用：呼叫类型为外部<br>内部调用：呼叫类型为内部 |
|目录搜索方法总计                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod 是abs_search_dtmf或abs_search_name    |
|调用方操作                                  |AATransferAction<br>TotalCallCount         |无                                                             |
|AA 中的平均秒数<br>平均调用方操作 |AAChainDuration<br>AACallerActionCount     |无                                                             |
|调用结果                                    |AACallResult<br>TotalCallCount             |无                                                             |
|调用方操作计数                            |AACallerActionCount<br>TotalCallCount      |无                                                             |
|报表的下半部分                         |AA 名称<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>呼叫类型<br>TotalCallCount |无                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名称                                 |文本                     |附加到自动助理的资源帐户的名称<br><br>如果 **aa_test@microsoft.com** 完整的资源帐户名称，则此值将为： **aa_test** |
|AACallerActionCount                     |整数             |汇总：总和<br>呼叫期间由自动助理中的调用方选择的操作计数  |
|AACallFlow                              |文本                     |封装自动助理呼叫的不同状态 -可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |文本                     |最终调用结果--可能的值：<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ 未知<br>§ user_terminated |
|AAChainDuration                         |小数           |汇总：总和<br>自动助理呼叫的持续时间                     |
|AAChainIndex                            |文本                     |                                                                         |
|AAConnectivityType                      |文本                     |调用类型--可能的值：<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |文本                     |呼叫中涉及的自动助理数                               |
|AADirectorySearchMethod                 |文本                     |上一个通讯簿搜索方法--可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日期/时间                |自动助理呼叫开始时间                                           |
|AATransferAction                        |文本                     |调用传输目标类型--可能的值：<br><br>***§ 应用程序 - 语音应用程序实体**_<br>§ external_pstn<br>_*_§ hunt_group - 呼叫队列实体_*_<br>_*_§ orgaa - 组织自动助理实体_**<br>§ shared_voicemail<br>§ 未知<br>§ 用户 |
|呼叫类型 <sup>1</sup>                   |文本                     |调用类型--可能的值：<br><br>§ 外部<br>§ 内部         |
|IsAAInvolved                            |文本                     |始终 1                                                                 |
|PSTNMinutes                             |整数             |汇总：总和<br>总分钟使用量                                     |
|TotalCallCount                          |整数             |汇总：总和<br>Always 1 - 用于提供所有调用的总和            |


### <a name="cloud-call-queue-analytics"></a>云呼叫队列分析

#### <a name="report-description"></a>报表说明

|报表部分                          |说明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|传入呼叫源 <sup>1</sup>        |按内部/外部调用源分配呼叫              |
|呼叫量                             |按呼叫队列分配呼叫                                |
|调用方结果                           |按调用结果分配呼叫                                |
|超时/溢出调用总操作数      |未转发 (通过调用结果放弃) 调用的分布       |
|传输/转发目标总计          |通过调用结果转发的调用的分布                      |
|放弃的调用比率                   |成功调用计数与放弃调用计数的比率                        |
|平均会话长度 (秒)         |呼叫长度（以秒为单位）按放弃/成功调用分组       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡         |报表名称                                                          |全局筛选器 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|呼叫队列         |日期<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |无          |
 
|报表名称            |源表名称            |处理       |
|:----------------------------|:----------------------------|:----------------|
|日期                        |日期                        |无             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics， <br>#“Remove Columns” = Table.RemoveColumns (Source，{“Call Count”， “Call Queue Call Result”， “Date”， “PSTN 连接类型”， “呼叫队列目标类型”， “PSTN 总分钟数”}) ，<br>Distinct = Table.Distinct (#“Removed Columns”)  |
|fCallQueueAnalytics          |CallQueueAnalytics           |无             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |无             |

|报表部分                      |表 -> 字段 () 使用                |应用的筛选器       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期选择器                       |Date -> DateTime                     |无                  |
|呼叫队列标识                 |dCQ-CQIdentity ->调用队列标识 |无                  |
|传入呼叫源 <sup>1</sup>    |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics -> 调用类型    |外部调用：呼叫类型为外部<br>内部调用：呼叫类型为内部 |
|Avg 等待时间                    |fCallQueueFinalStateAction ->平均通话持续时间 (秒)  |传输前：呼叫队列呼叫结果agent_joined_conference或transferred_to_agent<br>挂起前：呼叫队列呼叫结果未agent_joined_conference或transferred_to_agent |
|调用结果                         |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->呼叫队列调用结果 | 无 |
|超时/溢出调用总操作数 |fCallQueueFinalStateAction ->调用计数<br>fCallQueueFinalStateAction ->调用队列最终状态操作 |呼叫队列最终状态操作未转发 |
|Transfer/Forard 目标总计       |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->调用队列目标类型 |无 |
|调用卷                        |fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->呼叫队列标识<br>fCallQueueAnalytics ->日期 |无 |
|放弃的呼叫                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics ->调用计数<br>fCallQueueAnalytics ->日期<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned 为 True |
|平均会话长度 (秒)     |fCallQueueFinalStateAction ->平均通话持续时间<br>fCallQueueFinalStateAction ->日期<br>fCallQueueFinalStateAction -> IsAbandoned |无 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|呼叫队列标识                     |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|呼叫计数                              |整数             |汇总：总和<br>通话的数量                                          |
|呼叫队列调用结果                  |文本                     |呼叫队列调用最终状态 -- 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒绝<br>§ 已断开连接<br>§ 错误<br>§ 失败<br>§ 无效<br>§ 溢出<br>§ timed_out<br>§ transferred_to_agent |
|呼叫队列标识                     |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|呼叫队列目标类型                  |文本                     |***调用重定向目标类型--可能的值：***<br><br>§ ApplicationEndpoint<br>§ 邮箱<br>§ 其他<br>§ 用户 |
|呼叫类型 <sup>1</sup>                   |文本                     |调用类型--可能的值：<br><br>§ 外部<br>§ 内部           |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)  (UTC)                            | 
|IsAbandoned                             |True/false               |如此 如果代理未接听呼叫                                   |
|PSTN 连接类型                  |文本                     |调用类型--可能的值：<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN 总分钟数                      |整数             |汇总：总和<br>PSTN 调用的总分钟数                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 度量值说明

|名称                                    |数据类型                |说明                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***放弃呼叫百分比***                 |百分比               |度量值：放弃的呼叫数/总呼叫数    |
|总呼叫数                             |整数             |度量值：求和代理接听呼叫        |
|TotalCallCount                          |整数             |度量值：总和 (调用计数)                  |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 字段说明

|名称                                    |数据类型                |说明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通话持续时间 (秒)          |小数           |汇总：总和<br>平均通话持续时间（以秒为单位） |
|呼叫计数                              |整数             |汇总：总和<br>通话的数量                  |
|呼叫队列调用结果                  |文本                     |呼叫队列调用最终状态 - 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒绝<br>§ 已断开连接<br>§ 错误<br>§ 失败<br>§ 无效<br>§ 溢出<br>§ timed_out<br>§ transferred_to_agent |
|调用队列最终状态操作           |文本                     |调用队列最终操作 -- 可能的值：<br><br>§ 断开 (timed_out调用) <br>§ disconnect_with_busy (溢出的呼叫) <br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ 其他<br>§ 语音邮件 |
|呼叫队列标识                     |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)  (UTC)    |
|IsAbandoned                             |True/false               |如此 如果代理未接听呼叫           |


### <a name="cloud-call-queue-agent-timeline"></a>云呼叫队列代理时间线

#### <a name="report-description"></a>报表说明

|报表部分                                          |说明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|#代理调用                                        |按呼叫队列和代理分配呼叫                 |
|代理和呼叫队列) 的总呼叫持续时间 (秒   |代理和呼叫队列调用的总持续时间 (秒)      |
|按代理名称) 的平均呼叫持续时间 (秒           |代理调用的平均持续时间 (秒) 秒                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>向 CQD 表和字段映射报告

|“报表”选项卡         |报表名称        |全局筛选器 |
|:------------------|:-------------------------|:-------------|
|代理时间线     |fAgentTimelineAnalytics   |无          |
 
|报表名称            |源表名称            |处理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics， <br>#“Changed Type” = Table.TransformColumnTypes (Source，{{“Call Count”， Int64.Type}， {“Call Duration (Minute) ”， Int64.Type}， {“Average Call Duration (Second) ”， type number}， {“Date”， type date}}) |

|报表部分                                |字段 () 使用                         |应用的筛选器       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|代理名称                                    |代理名称                            |无                  |
|呼叫队列名称                               |呼叫队列名称                       |无                  |
|#Calls代理                               |代理名称<br>呼叫计数<br>日期      |无                  |
|按代理和呼叫队列进行分发          |代理名称<br>呼叫计数<br>呼叫持续时间 (分钟) <br>呼叫队列名称 |无                      |
|左下角                                   |代理名称<br>平均通话持续时间 (秒) <br>呼叫计数<br>呼叫持续时间 (分钟) <br>呼叫队列名称 | 无 |
|代理名称) 的平均呼叫持续时间 (秒 |代理名称<br>平均通话持续时间 (秒) <br>呼叫计数<br>呼叫持续时间 (分钟) <br>呼叫队列名称 | 无 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|代理名称                              |文本                     |用户 UPN<br>如果 user@microsoft.com 完整用户 **名，则** 此值将为： **用户** |
|平均通话持续时间 (秒)           |小数           |汇总：总和<br>应答呼叫队列呼叫的平均持续时间（以秒为单位） |
|呼叫计数                              |整数             |汇总：总和<br>向代理发出的调用数     |
|呼叫持续时间 (分钟)                   |整数             |汇总：总和<br>应答呼叫队列呼叫的总呼叫持续时间（以分钟为单位）， (舍入到最接近的分钟)   |
|呼叫队列名称                         |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 **cq_test@microsoft.com**，则此值将为： **cq_test** |
|日期                                    |日期                     |                                                    |


> [!NOTE]
> 1) 此报表从代理的角度显示呼叫计数，因此此报表上的呼叫计数总数通常高于 **云呼叫队列分析** 报表上的呼叫总数。 队列中的每个调用在应答之前，可以至少向一个或多个代理显示一次。 向代理提供的每个呼叫队列调用都会计入此报表，即使代理未答复。 这两个报表之间的呼叫计数差异更明显，因为 **服务员路由** 选项为每个调用的每个代理都响铃。 
> 2) 当呼叫第一次到达第一个呼叫队列时，如果该队列中已等待的呼叫数超过 **呼叫溢出处理** 限制，如果重定向选项将呼叫发送到第二个呼叫队列，则第二个呼叫队列中的代理将显示为在此报告中的第一个呼叫队列中。 

## <a name="known-issues"></a>已知问题

- 呼叫队列和自动助理由资源帐户的 ID 而不是呼叫队列/自动助理名称显示。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 仪表板中只有 28 天的历史记录可用，因为呼叫队列/自动助理数据被视为个人数据，并且受数据隐私保留策略的约束。

- 在某些情况下，云呼叫队列代理时间线报表上的代理应答呼叫计数可能不同于Teams客户端呼叫历史记录中显示的呼叫数。 Teams客户端调用历史记录是正确的。 支持部门正在调查，但目前估计没有时间进行修复。

- <sup>1</sup> 自动助理和呼叫队列图中的 **传入呼叫源** 显示最终呼叫腿源，而不是初始呼叫腿源。 例如，如果自动助理收到外部呼叫并将呼叫转移到另一个自动助理或呼叫队列，则 **传入呼叫源** 将报告为内部呼叫源。
