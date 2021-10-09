---
title: 自动助理 &队列历史报告
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
description: 了解如何使用呼叫质量仪表板Power BI报表来查看自动助理和呼叫队列历史数据。
ms.openlocfilehash: 4594a673225a167e762bcfee63067f70e7fe10b4
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249554"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自动助理 &队列历史报告

CQD Teams 自动助理 &调用队列历史Power BI模板提供以下三个报告：

- [自动助理](media/cqd-teams-aa-cq-historical-report-sample-aa.png) - 显示对进入自动助理的呼叫的分析。
- [呼叫队列](media/cqd-teams-aa-cq-historical-report-sample-cq.png) - 显示对进入呼叫队列的呼叫的分析。
- [代理时间线](media/cqd-teams-aa-cq-historical-report-sample-at.png) - 显示呼叫队列调用中处于活动状态的代理的时间线视图。

这些报告使用来自呼叫质量仪表板 [数据存储](CQD-Power-BI-query-templates.md) 的数据。 它们允许组织报告自动助理和呼叫队列正在处理的呼叫数。  它们还提供有关调用队列中代理性能的见解。

## <a name="prerequisites"></a>先决条件

### <a name="power-bi-desktop"></a>Power BI Desktop
需要安装Power BI Desktop。 可以从 Microsoft Store [Windows安装](https://aka.ms/pbidesktopstore)它。

可以使用免费版本的 Power BI Desktop。 最低兼容版本为 2020 年 9 月 (2.85.681.0) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限

用于查看 AA & CQ Analytics 历史报告的帐户需要具有访问 CQD 数据管道的权限。 有关详细信息，请参阅 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>安装 

以下步骤假定你已在计算机上Power BI Desktop应用程序，并且帐户具有访问 CQD 数据管道所需的权限。

执行以下步骤：

- 下载[CQD Power BI查询模板](https://www.microsoft.com/download/details.aspx?id=102291)，将 zip 文件保存到计算机的目录。

- 双击 zip 文件以打开它。

- 双击"CQ 和 AA 组合分析 20201105.pbit"模板文件，Power BI Desktop启动。

- 系统会提示选择 CQD 数据管道区域。 选择租户所在的区域。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="选择 CQD 数据管道区域屏幕截图。":::

- 可以使用 [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet 获取租户所在的区域。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 区域将显示在 后，如 **/** 上例所示，其中区域为：noam

 - 报告将随示例数据一起启动。
 
 - 若要查看自己的数据，请在"开始"选项卡上的"查询"下选择"Power BI Desktop"。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="选择刷新选项的屏幕截图。":::

- 然后，系统会提示你登录。 选择 **"组织帐户**"，然后选择"**登录"。**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="显示登录的屏幕截图。":::

- 选择 **连接** 并观看数据刷新。

## <a name="data-latency-and-aa--cq-analytics"></a>数据延迟和 AA & CQ 分析

数据将在 30 分钟内在 CQD 数据管道中提供。

必须刷新数据，以查看新的分析数据。 

## <a name="customization"></a>自定义 

可以自定义报表的某些可视化效果方面，例如添加或删除要显示在各种可视化效果中的字段、更改图表类型等。

不能向报表添加其他数据字段。

### <a name="change-color-schema"></a>更改颜色架构 

以下步骤假定已完成安装步骤。

执行以下步骤：
- 选择 **功能区上的** "视图"选项卡。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="选择"视图"选项卡以更改配色方案屏幕截图。":::

- 从下拉列表中选择颜色架构。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="显示各种配色方案的屏幕截图。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自动助理和调用队列历史报告定义

### <a name="cloud-auto-attendant-analytics"></a>云自动助理分析

#### <a name="report-description"></a>报表说明

|报表部分                          |说明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|传入呼叫源<sup>1</sup>        |按内部/外部调用源分布调用             |
|目录搜索方法总计          |按搜索类型分布的调用数                               |
|调用方操作                           |呼叫接收者调用的分布                             |
|通话结果                             |按最终调用状态对调用的分布                          |
|调用方操作计数                     |按呼叫期间使用的数量操作对呼叫进行分布        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>报告到 CQD 表和字段映射

|"报表"选项卡            |报表表名称     |全局筛选器                          |
|:---------------------|:---------------------|:--------------------------------------|
|自动助理        |fAutoAttendant        |AAStartTime 过去 28 天内 |


|报表表名称            |源表名称            |正在处理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant， <br>#"筛选的行" = Table.SelectRows (Source，每个 true) ， <br>#"自动助理" = Table.AddColumn (#"Filtered Rows"， "AA Name"， each List.First (Text.Split ([AAIdentity]， "@") ) ) ， <br>#"Changed Type" = Table.TransformColumnTypes (#"自动助理"，{{"AAStartTime"， type datetime}}) ， <br>#"Removed Columns" = Table.RemoveColumns (#"Changed Type"，{"AAIdentity"})  |


|报表部分                                  |已 (字段) 字段                              |应用的筛选器     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期选择器                                   |AAStartTime                                |无                |
|自动助理                                  |AA 名称                                    |无                |
|传入呼叫源<sup>1</sup>                |呼叫类型<br>TotalCallCount                |外部呼叫：呼叫类型为外部<br>内部呼叫：呼叫类型为内部 |
|目录搜索方法总计                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod abs_search_dtmf 或 abs_search_name    |
|调用方操作                                  |AATransferAction<br>TotalCallCount         |无                                                             |
|AA 中的平均秒数<br>平均调用方操作 |AAChainDuration<br>AACallerActionCount     |无                                                             |
|调用结果                                    |AACallResult<br>TotalCallCount             |无                                                             |
|调用方操作计数                            |AACallerActionCount<br>TotalCallCount      |无                                                             |
|报表的下半部分                         |AA 名称<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>呼叫类型<br>TotalCallCount |无                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名称                                 |text                     |附加到 自动助理 的资源帐户自动助理<br><br>如果完整资源帐户名称 aa_test@microsoft.com则此值为 **：aa_test** |
|AACallerActionCount                     |全数             |汇总：总和<br>呼叫方在呼叫期间自动助理的操作计数  |
|AACallFlow                              |text                     |封装调用的不同自动助理状态 - 可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |text                     |最终调用结果 - 可能的值：<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ unknown<br>§ user_terminated |
|AAChainDuration                         |十进制数           |汇总：总和<br>通话持续时间（自动助理                     |
|AAChainIndex                            |text                     |                                                                         |
|AAConnectivityType                      |text                     |调用类型 - 可能的值：<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |text                     |呼叫中涉及的自动助理数                               |
|AADirectorySearchMethod                 |text                     |最后一种通讯簿搜索方法 - 可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日期/时间                |自动助理通话开始时间                                           |
|AATransferAction                        |text                     |呼叫转接目标类型 - 可能的值：<br><br>***§ 应用程序 - 语音应用程序实体**_<br> § <br> external_pstn_§ hunt_group - 调用 *_队列实体_* _<br>_ * _§ orgaa - 自动助理 实体_**<br>§ shared_voicemail<br>§ unknown<br>§ user |
|呼叫类型<sup>1</sup>                   |text                     |调用类型 - 可能的值：<br><br>§ 外部<br>§ 内部         |
|IsAAInvolved                            |text                     |始终为 1                                                                 |
|PSTNMinutes                             |全数             |汇总：总和<br>总分钟使用量                                     |
|TotalCallCount                          |全数             |汇总：总和<br>始终为 1 - 用于提供所有调用的总和            |


### <a name="cloud-call-queue-analytics"></a>云呼叫队列分析

#### <a name="report-description"></a>报表说明

|报表部分                          |说明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|传入呼叫源<sup>1</sup>        |按内部/外部呼叫源分布呼叫              |
|呼叫量                             |按呼叫队列分布的呼叫                                |
|调用方结果                           |按通话结果分布的呼叫                                |
|超时/溢出调用总数操作      |未转发的 (已) 结果的呼叫分布       |
|转移/转发目标总计          |按呼叫结果转发的呼叫分布                      |
|已放弃的通话比率                   |成功与放弃的呼叫计数的比率                        |
|平均会话长度 (秒)         |按放弃/成功调用分组的呼叫长度（以秒数表示）       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>报告到 CQD 表和字段映射

|"报表"选项卡         |报表表名称                                                          |全局筛选器 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|呼叫队列         |日期<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |无          |
 
|报表表名称            |源表名称            |正在处理       |
|:----------------------------|:----------------------------|:----------------|
|日期                        |日期                        |无             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics， <br>#"Removed Columns" = Table.RemoveColumns (Source，{"Call Count"， "Call Queue Call Result"， "Date"， "PSTN Connectivity Type"， "Call Queue Target Type"， "PSTN Total Minutes"}) ，<br>Distinct = Table.Distinct (#"Removed Columns")  |
|fCallQueueAnalytics          |CallQueueAnalytics           |无             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |无             |

|报表部分                      |表 -> 字段 () 已用                |应用的筛选器       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期选择器                       |Dates -> DateTime                     |无                  |
|调用队列标识                 |dCQ-CQIdentity ->调用队列标识 |无                  |
|传入呼叫源<sup>1</sup>    |fCallQueueAnalytics ->呼叫计数<br>fCallQueueAnalytics ->呼叫类型    |外部呼叫：呼叫类型为外部<br>内部呼叫：呼叫类型为内部 |
|平均等待时间                    |fCallQueueFinalStateAction ->平均呼叫持续时间 (秒)  |转接之前：呼叫队列呼叫结果agent_joined_conference或transferred_to_agent<br>挂断之前：呼叫队列呼叫结果agent_joined_conference或transferred_to_agent |
|通话结果                         |fCallQueueAnalytics ->呼叫计数<br>fCallQueueAnalytics ->呼叫队列呼叫结果 | 无 |
|超时/溢出调用总数操作 |fCallQueueFinalStateAction ->调用计数<br>fCallQueueFinalStateAction ->调用队列最终状态操作 |调用队列最终状态操作未转发 |
|传输/Forard 目标总计       |fCallQueueAnalytics ->呼叫计数<br>fCallQueueAnalytics ->队列目标类型 |无 |
|呼叫量                        |fCallQueueAnalytics ->呼叫计数<br>fCallQueueAnalytics ->调用队列标识<br>fCallQueueAnalytics -> Date |无 |
|已放弃的呼叫                     |fCallQueueAnalytics -> %已放弃的调用<br>fCallQueueAnalytics ->呼叫计数<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned 为 True |
|平均会话长度 (秒)     |fCallQueueFinalStateAction ->平均呼叫持续时间<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |无 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|调用队列标识                     |text                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 cq_test@microsoft.com则此值为 **：cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|呼叫计数                              |全数             |汇总：总和<br>通话的数量                                          |
|呼叫队列呼叫结果                  |text                     |调用队列调用最终状态 - 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒绝<br>§ disconnected<br>§ 错误<br>§ 失败<br>§ 无效<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|调用队列标识                     |text                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 cq_test@microsoft.com则此值为 **：cq_test** |
|调用队列目标类型                  |text                     |***调用重定向目标类型 -- 可能的值：***<br><br>§ ApplicationEndpoint<br>§ 邮箱<br>§ 其他<br>§ 用户 |
|呼叫类型<sup>1</sup>                   |text                     |调用类型 - 可能的值：<br><br>§ 外部<br>§ 内部           |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (utc)  (UTC)                            | 
|IsAbandoned                             |true/false               |如果代理未应答调用，则为 True                                   |
|PSTN 连接类型                  |text                     |调用类型 - 可能的值：<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN 总分钟数                      |全数             |汇总：总和<br>PSTN 呼叫的总分钟数                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 度量说明

|名称                                    |数据类型                |说明                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***已放弃的调用百分比***                 |百分比               |度量值：TotalCallCount/Total Calls<br>成功与放弃的呼叫计数的比率    |
|总呼叫                             |全数             |度量值：总和代理应答的调用数        |
|TotalCallCount                          |全数             |度量值：调用 (总和)                  |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 字段说明

|名称                                    |数据类型                |说明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均呼叫持续时间 (秒)          |十进制数           |汇总：总和<br>平均呼叫持续时间（以秒数表示） |
|呼叫计数                              |全数             |汇总：总和<br>通话的数量                  |
|呼叫队列呼叫结果                  |text                     |调用队列调用最终状态 - 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒绝<br>§ disconnected<br>§ 错误<br>§ 失败<br>§ 无效<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|调用队列最终状态操作           |text                     |调用队列最终操作 - 可能的值：<br><br>§ disconnect<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ 语音邮件 |
|调用队列标识                     |text                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 cq_test@microsoft.com则此值为 **：cq_test** |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (utc)  (UTC)    |
|IsAbandoned                             |true/false               |如果代理未应答调用，则为 True           |


### <a name="cloud-call-queue-agent-timeline"></a>云呼叫队列代理时间线

#### <a name="report-description"></a>报表说明

|报表部分                                          |说明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|代理调用的个次                                        |按呼叫队列和代理分布呼叫                 |
|代理和 (队列) 总呼叫持续时间   |代理 (呼叫) 呼叫的总持续时间（秒）     |
|按代理名称 (平均) 秒数           |代理 (呼叫) 的平均持续时间) 秒数                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>报告到 CQD 表和字段映射

|"报表"选项卡         |报表表名称        |全局筛选器 |
|:------------------|:-------------------------|:-------------|
|代理时间线     |fAgentTimelineAnalytics   |无          |
 
|报表表名称            |源表名称            |正在处理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics， <br>#"Changed Type" = Table.TransformColumnTypes (Source，{{"Call Count"， Int64.Type}， {"Call Duration (Minute) "， Int64.Type}， {"Average Call Duration (Second) "， type number}， {"Date"， type date}}}) |

|报表部分                                |已 (字段) 字段                         |应用的筛选器       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|代理名称                                    |代理名称                            |无                  |
|呼叫队列名称                               |呼叫队列名称                       |无                  |
|#Calls代理                               |代理名称<br>呼叫计数<br>日期      |无                  |
|按代理和呼叫队列分布          |代理名称<br>呼叫计数<br>通话持续时间 (分钟) <br>呼叫队列名称 |无                      |
|左下角                                   |代理名称<br>平均呼叫持续时间 (秒) <br>呼叫计数<br>通话持续时间 (分钟) <br>呼叫队列名称 | 无 |
|按代理名称 (呼叫) 的平均呼叫持续时间 |代理名称<br>平均呼叫持续时间 (秒) <br>呼叫计数<br>通话持续时间 (分钟) <br>呼叫队列名称 | 无 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 字段说明

|名称                                    |数据类型                |说明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|代理名称                              |text                     |用户 UPN<br>如果输入 **完整的用户名** user@microsoft.com 则此值为 **：user** |
|平均呼叫持续时间 (秒)           |十进制数           |汇总：总和<br>呼叫队列调用的平均持续时间（以秒数） |
|呼叫计数                              |全数             |汇总：总和<br>代理处理的调用数                    |
|通话持续时间 (分钟)                   |全数             |汇总：总和<br>呼叫队列呼叫的总呼叫持续时间（分钟）  |
|呼叫队列名称                         |text                     |附加到呼叫队列的资源帐户的名称<br><br>如果完整资源帐户名称 cq_test@microsoft.com则此值为 **：cq_test** |
|日期                                    |date                     |                                                    |


> [!NOTE]
> 1) 此报告从代理的角度来看显示呼叫计数，因此此报告中的呼叫计数总计通常高于云呼叫队列 **分析** 报表上的调用总数。 在应答队列之前，队列中的每个调用可以至少呈现给一个或多个代理一次。 呈现给代理的每次呼叫队列调用都会计入此报告，即使该呼叫未由代理应答。 这两个报告之间的呼叫计数差异通过 **Attendant** 路由选项更加明显，该选项将每个呼叫的每个代理都响铃。 
> 2) 当呼叫首次到达第一个呼叫队列时，如果已在该队列中等待的呼叫数超出了呼叫溢出处理限制，并且重定向选项将呼叫发送到第二个呼叫队列，则第二个呼叫队列中的代理将在此报告的第一个呼叫队列中显示。 

## <a name="known-issues"></a>已知问题

- 呼叫队列和自动助理按资源帐户的 ID 而不是呼叫队列/自动助理名称显示。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 仪表板中仅提供 28 天的历史记录，因为呼叫队列/自动助理数据被视为个人数据，并受数据隐私保留策略的约束。

- <sup>1</sup> **自动助理和** 呼叫队列图中的传入呼叫源显示最终呼叫段源，而不是初始呼叫段源。 例如，如果自动助理接收外部呼叫，将呼叫转接到另一个自动助理或呼叫队列，则传入呼叫源将报告为"内部"。
