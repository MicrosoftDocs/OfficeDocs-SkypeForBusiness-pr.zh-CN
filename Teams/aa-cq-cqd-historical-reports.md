---
title: 更新了自动助理和呼叫队列历史报告
author: DaniEASmith
ms.author: danismith
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
description: 了解如何使用更新的 Teams 自动助理&呼叫队列历史报告 Power BI 报表来查看自动助理和呼叫队列历史数据。
ms.openlocfilehash: 780d6057960c96713ac67be3e189d7982fd2fa46
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176689"
---
# <a name="updated-auto-attendant-and-call-queue-historical-reports"></a>更新了自动助理和呼叫队列历史报告

>[!NOTE]
> GCC HIgh 和 DOD 客户应继续使用 V1.63 的 [自动助理&呼叫队列历史报告 (CQD) ](aa-cq-cqd-historical-reports-v163.md)。

此 Power BI 模板提供三个报表，使组织能够报告自动助理和呼叫队列正在处理的呼叫数。  它还提供代理性能见解。

## <a name="v304-published-on-november-18-2022"></a>V3.0.4 于 2022 年 11 月 18 日发布

Teams 自动助理&呼叫队列历史报告 Power BI 模板提供以下三个报表：

- [自动助理](media/aa-cq-historical-report-sample-aa-v304.png)报表显示传入自动助理的呼叫的分析。
- [“呼叫队列](media/aa-cq-historical-report-sample-cq-v304.png)”报表显示对进入呼叫队列的呼叫的分析。
- [代理时间线](media/aa-cq-historical-report-sample-at-v304.png)报表显示呼叫队列调用中处于活动状态的代理的时间线视图。

这些报表使用语音应用程序分析收集器 (VAAC) 服务中的数据。

## <a name="v3xx-prerequisites"></a>V3.x.x 先决条件

### <a name="power-bi-desktop"></a>Power BI Desktop

需要安装Power BI Desktop。 你可以从 [Windows 应用商店安装并使用Microsoft](https://aka.ms/pbidesktopstore)免费版本。

最低兼容版本为 2.85.681.0 (2020 年 9 月) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限

虽然此版本的报表不使用通话质量仪表板 (CQD) 数据管道，但用于查看历史数据的帐户仍需要访问通话质量仪表板。 有关详细信息，请参阅 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

- 此要求将在将来的版本中删除。

## <a name="v3xx-installation"></a>V3.x.x 安装 

以下步骤假定已在计算机上安装了 Power BI Desktop，并且帐户具有访问 CQD 数据管道所需的权限。

执行以下步骤：

1. 在计算机上下载并保存 [Teams 自动助理&呼叫队列历史报告V3.0.4.zip](https://www.microsoft.com/download/details.aspx?id=104623) 文件。

2. 打开 zip 文件。

3. 打开 `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` 模板文件。 Power BI Desktop应启动。

4. 系统将提示你选择 **数据源**。  选择条目 `api.interfaces.records.teams.microsoft.com` 。

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="选择 api.interfaces.records.teams.microsoft.com Data Soure 的屏幕截图":::

5. 系统将提示你使用帐户登录。 选择“ **组织帐户**”，然后选择“ **登录**”。

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="显示 V3.0.0 登录名的屏幕截图。":::

6. 选择“ **连接**”，数据将刷新。

> [!NOTE]
> 如果使用 v1.63 或更低版本，则 v3.x.x 尝试从 VAAC 检索数据时可能会遇到错误。  若要解决此错误，必须从 Power BI 中清除任何以前的凭据。
> 
> 1. 打开 v3.x.x 模板以清除错误。 
> 1. 选择 **“文件** > **选项”&“设置”** > **“数据源设置**”。
> 1. 选择“ **清除权限”** 下拉列表，然后选择“ **清除所有权限**”。
> 1. 清除模板后关闭模板，然后重启 Power BI。 系统将要求你再次授权。 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>自动助理和呼叫队列分析的数据延迟

数据通常在调用完成后的 30 分钟内可用;但是，在某些情况下，可能需要几个小时才能显示数据。 

必须刷新数据才能看到任何新数据。

## <a name="customization"></a>定制 

可以自定义报表的某些可视化效果方面，例如添加或删除要显示在各种可视化效果中的字段、更改图表类型等。

报表包含当前可用的所有数据指标。

### <a name="change-color-schema"></a>更改颜色架构 

以下步骤假定你已完成安装步骤。

执行以下步骤：

1. 选择功能区上的 **“视图”选项卡** 。

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="选择“视图”选项卡以更改配色方案的屏幕截图。":::

2. 从下拉列表中选择颜色架构。

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="显示各种配色方案的屏幕截图。":::
  
## <a name="dimensions-and-measurements"></a>尺寸和度量值

### <a name="common-dimensions"></a>通用维度

这些维度对自动助理和呼叫队列都是通用的：

|名称 (类型)                                             |可能的值                |说明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br> (文本)                                  |GUID                           |呼叫标识符                                                   |
|日期<br> (DateTime)                                      |                               |呼叫日期 (UTC)                                                 |
|DialogId<br> (文本)                                      |GUID                           |呼叫标识符                                                   |
|DocumentId<br> (文本)                                    |GUID                           |呼叫标识符                                                   |
|持续时间<br> (整数)                              |                               |调用持续时间（秒）                                      |
|EndTime<br> (DateTime)                                   |                               |utc) 结束时间调用 (                                             |
|FirstIsCaller<br> (布尔)                              |                               |                                                                  |
|FirstUPN<br> (文本)                                      |                               |                                                                  |
|Hour<br> (文本)                                          |                               |小时呼叫已启动 (UTC)                                            |
|Minute<br> (文本)                                        |                               | (UTC) 开始的分钟呼叫                                         |
|PSTNCallDuration<br> (整数)                      |                               |                                                                  |
|PSTNCallType<br> (文本)                                  |                               |                                                                  |
|                                                       |外部                       |                                                                  |
|                                                       |内部                       |                                                                  |
|PSTNConnectivityType<sup>1</sup><br> (文本)              |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|第二个<br> (文本)                                        |                               |第二次呼叫已 (UTC) 启动                                         |
|SecondUPN<br> (文本)                                     |                               |                                                                  |
|TenantId<br> (文本)                                      |                               |租户 ID                                                         |
|时间 戳<br> (DateTime)                                 |                               |时间记录是 (UTC) 写入的                                     |
|UserStartTimeUTC<br> (DateTime)                          |                               |时间调用已 (UTC) 启动                                           |

- <sup>1</sup> **PSTNConnectivityType** 将显示最终呼叫腿源，而不是初始调用腿源。 例如，如果自动助理接到外部呼叫并将呼叫转接到另一个自动助理或呼叫队列， **则传入呼叫源** 将报告为 **“内部**”。


### <a name="auto-attendant-dimensions"></a>自动助理维度

|名称 (类型)                                             |可能的值                |说明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br> (文本)                         |                               |封装自动助理呼叫的不同状态          |
|                                                       |abs_search                     |                                                                  |
|                                                       |公告                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br> (文本)                       |                               |最终调用结果                                                 |
|                                                       |failed_to_establish_media      |无法建立呼叫的媒体部分             |
|                                                       |failover_to_operator           |呼叫通常由于系统错误而转接给操作员      |
|                                                       |oaa_chain_too_long             |AA 中的腿太多                                           |
|                                                       |oaa_session_too_long           |AA 会话持续时间太长                                    |
|                                                       |service_declined               |AA 未接受呼叫                                         |
|                                                       |service_terminated             |AA 配置断开呼叫或呼叫挂起             |
|                                                       |terminated_automatic_selection |AA 配置断开调用的连接                           |
|                                                       |terminated_no_operator         |由于错误未定义运算符而全部终止                   |
|                                                       |terminated_transfer_failed     |呼叫因转移失败而终止 - 通常为外部号码 |
|                                                       |transfer_in_progress           |AA->AA 传输                                                   |
|                                                       |transferred_to_operator        |呼叫已转接给操作员                                  |
|                                                       |transferred_to_cq              |呼叫已转移到呼叫队列                                |
|                                                       |transferred_to_receptionist    |与transferred_to_operator相同                                   |
|                                                       |transferred_to_self            |调用已返回到 AA 的开头                          |
|                                                       |transferred_to_shared_voicemail |呼叫已转移到共享语音邮件                         |
|                                                       |transferred_to_user            |呼叫已转接到用户                                    |
|                                                       |未知                        |出现未知情况                                 |
|                                                       |user_terminated                |呼叫者挂断                                                    |
|AutoAttendantCallerActionCounts<br> (整数)       |                               |                                                                  |
|AutoAttendantChairDurationInSecs<br> (实数)       |                               |                                                                  |
|AutoAttendantChainIndex<br> (整数)               |                               |                                                                  |
|AutoAttendantChainStartTime<br> (DateTime)               |                               |                                                                  |
|AutoAttendantCount<br> (整数)                    |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br> (文本)            |                               |目录搜索方法                                           |
|                                                       |abs_search_dtmf                |触摸色调                                                        |
|                                                       |abs_search_voice               |语音                                                             |
|AutoAttendantIdentity<br> (文本)                         |                               |资源帐户 URI 调用已到达                              |
|AutoAttendantTransferAction<br> (文本)                   |                               |呼叫转移目标类型                                         |
|                                                       |机 管 局                             |已转移到 AA                                              |
|                                                       |重庆                             |传输到 CQ                                               |
|                                                       |external_pstn                  |已转移到外部号码                                 |
|                                                       |共享语音邮件               |已转移到共享语音邮件                                   |
|                                                       |未知                        |未知操作                                                    |
|HasAA<br> (布尔)                                      |                               |调用中是否涉及 AA                                            |


### <a name="call-queue-dimensions"></a>调用队列维度

|名称 (类型)                                             |可能的值                |说明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br> (整数)                   |                               |呼叫队列中的代理数                                    |
|CallQueueAgentOptInCount<br> (整数)              |                               |选择加入呼叫队列的代理数                           |
|CallQueueCallResult<br> (文本)                           |                               |呼叫队列调用最终状态                                       |
|                                                       |agent_joined_conference        |呼叫应答 - 会议模式 CQ                                |
|                                                       |拒绝                       |                                                                  |
|                                                       |断开                   |                                                                  |
|                                                       |错误                          |                                                                  |
|                                                       |失败                         |                                                                  |
|                                                       |无效                        |                                                                  |
|                                                       |overflown                      |满足溢出条件                                            |
|                                                       |timed_out                      |满足超时条件                                             |
|                                                       |transferred_to_agent           |呼叫应答 - 转移模式 CQ                                  |
|CallQueueDurationSeconds<br> (实数)               |                               |                                                                  |
|CallQueueFinaleStateAction<br> (文本)                    |                               |呼叫队列最终操作                                           |
|                                                       |断开                     |time_out调用                                                    |
|                                                       |disconnect_with_busy           |溢出调用                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |向前                        |                                                                  |
|                                                       |shared_voicemail               |                                                                  |
|                                                       |其他                          |                                                                  |
|                                                       |语音 信箱                      |                                                                  |
|CallQueueIdentity<br> (文本)                             |                               |资源帐户 URI 调用已到达                              |
|CallQueueTargetType<br> (文本)                           |                               |呼叫重定向目标                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |邮箱                        |                                                                  |
|                                                       |其他                          |                                                                  |
|                                                       |电话                          |                                                                  |
|                                                       |用户                           |                                                                  |
|HasCQ<br> (布尔)                                      |                               |呼叫中是否涉及 CQ                                            |
|TransferredFromCallQueueIdentity<br> (文本)              |                               |                                                                  |

### <a name="measurements"></a>测量

|名称 (类型)                                             |可能的值                |说明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br> (实数)   |                               |                                                                  |
|AvgCallDuration<br> (实数)                        |                               |                                                                  |
|AvgCallQueueDurationSeconds<br> (实数)            |                               |                                                                  |
|PSTNTotalMinutes<br> (实数)                       |                               |                                                                  |
|TotalAudioStreamDuration<br> (实数)               |                               |                                                                  |
|TotalCallCount<br> (整数)                        |                               |                                                                  |

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自动助理和呼叫队列历史报告定义

### <a name="cloud-auto-attendant-analytics-report"></a>云自动助理分析报告

#### <a name="report-description"></a>报告说明

|报告部分                          |说明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|传入呼叫源                    |按内部/外部调用源分配呼叫            |
|目录搜索方法                 |按搜索类型分配调用                              |
|调用方操作计数                     |呼叫期间使用的按号码操作分配呼叫       |
|AA 中的平均秒数                   |调用方在 AA 中花费的平均秒数                 |
|平均调用方操作                  |调用方在 AA 中执行的平均操作数               |
|调用结果                            |按最终调用状态分配呼叫                         |
|报表的下半部分                 |呼叫流细分                                               |

#### <a name="report-visual-and-field-mapping"></a>报表视觉对象和字段映射

|“报表”选项卡            |报表表名称     |全局筛选器                          |
|:---------------------|:---------------------|:--------------------------------------|
|自动助理        |fAutoAttendant        |无                                   |

|报告部分                               |已使用字段 ()                                                                                     |应用的筛选器 |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|日期选择器                                |AAStartTime                                                                                      |无       |
|时间范围选择器                          |AAStartHour                                                                                      |无       |
|自动助理资源帐户             |AA 名称                                                                                          |无       |
|传入呼叫源                         |呼叫类型<br>TotalCallCount 的总和         |外部调用：调用类型为外部<br>内部调用：调用类型为内部 |
|目录搜索方法                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod abs_search_dtmf或abs_search_name    |
|调用方操作计数                          |AACallerActionCount<br>TotalCallCount                                                            |无       |
|AA 中的平均秒数                        |AAChainDuration                                                                                  |无       |
|平均调用方操作                       |AACallerActionCount                                                                              |无       |
|调用结果                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |无       |
|报表的下半部分                      |MM-DD<br>AA 名称<br>AACallFlow<br>呼叫类型<br>AACallResult<br>TotalCallCount<br>AAChainDuration |无       |

#### <a name="fautoattendant-field-description"></a>fAutoAttendant 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名称                                 |文本                     |附加到自动助理的资源帐户的名称<br><br>如果 **aa_test@microsoft.com** 了完整的资源帐户名称，则此值将为： **aa_test** |
|AACallerActionCount                     |整数             |汇总：总和<br>呼叫期间呼叫者在自动助理中选择的操作计数  |
|AACallerActionCount (Measure)            |整数             |与上述相同，但如果没有调用而不是空，则为 0                              |
|AACallFlow                              |文本                     |请参阅自动助理维度 -> AutoAttendantCallFlow                                   |
|AACallResult                            |文本                     |请参阅自动助理维度 -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |文本                     |基于 AACallResult 设置图例项                                               |
|AAChainDuration                         |十进制数           |汇总：总和<br>自动助理中的呼叫持续时间                                     |
|AAChainDuration (Measure)                |十进制数           |与上述相同，但如果没有调用而不是空，则为 0                              |
|AAChainIndex                            |文本                     |                                                                                         |
|AAConnectivityType                      |文本                     |                                                                                         |
|AACount                                 |文本                     |呼叫中涉及的自动助理数                                               |
|AADirectorySearchMethod                 |文本                     |请参阅自动助理维度 -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |文本                     |基于 AADirectorySearchMethod 设置图例项                                    |
|AAStartHour                             |十进制数           |自动助理呼叫开始时间                                                           |
|AAStartTime                             |日期/时间                |自动助理呼叫开始时间                                                           |
|AATransferAction                        |文本                     |请参阅自动助理维度 -> AutoAttendantTransferAction                             |
|呼叫类型<sup>1</sup>                   |文本                     |请参阅通用维度 -> PSTNCallType                                                    |
|MM-DD                                   |文本                     |自动助理呼叫月-天                                                            |
|PSTNMinutes                             |整数             |汇总：总和<br>总分钟使用量                                                     |
|TotalCallCount                          |整数             |汇总：总和<br>始终 1 - 用于提供所有调用的总和                            |
|TotalCallCount (度量值) 的总和         |整数             |与上述相同，但如果没有调用而不是空，则为 0                              |


### <a name="cloud-call-queue-analytics-report"></a>云呼叫队列分析报告

#### <a name="report-description"></a>报告说明

|报告部分                          |说明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|传入呼叫源                    |按内部/外部调用源分配呼叫             |
|平均等待时间 (秒)              |等待应答和放弃的呼叫                          |
|呼叫量和代理选择加入计数      |按呼叫队列分配呼叫/最大代理选择加入计数  |
|调用结果                            |按调用结果分配调用                               |
|放弃的呼叫                         |按呼叫队列分配放弃的呼叫                     |
|平均会话长度 (秒)         |按呼叫结果分组的呼叫长度（以秒为单位）                      |
|呼叫溢出/超时目标      |超时或溢出的调用的分布                 |


#### <a name="report-visual-and-field-mapping"></a>报表视觉对象和字段映射

|“报表”选项卡            |报表表名称                                   |全局筛选器       |
|:---------------------|:---------------------------------------------------|:-------------------|
|呼叫队列            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |无                |

|报告部分                      |表 -> 字段 (已用)                 |应用的筛选器       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期选择器                       |fCallQueueAnalytics -> Date           |无                  |
|时间范围选择器                 |fCallQueueAnalytics -> CQHour         |无                  |
|呼叫队列资源帐户         |fCallQueueAnalytics -> CQ 名称        |无                  |
|传入呼叫源                |fCallQueueAnalytics ->调用计数 (度量值的总和)   |外部调用：调用类型为外部<br>内部调用：调用类型为内部 |
|平均等待时间 (秒) -Before Answered |fCallQueueFinalStateAction ->平均 CQ 持续时间 (度量值)  |呼叫队列调用结果agent_joined_conference或transferred_to_agent|
|平均等待时间 (秒) 放弃之前 |fCallQueueFinalStateAction ->平均调用持续时间 (度量值)  |呼叫队列调用结果未agent_joined_conference、transferred_to_agent、溢出、timed_out |
|呼叫音量和代理Opt-In计数   |fCallQueueAnalytics -> 调用计数<br>fCallQueueAnalytics ->呼叫队列代理选择加入计数<br>fCallQueueAnalytics -> CQ 名称<br>fCallQueueAnalytics -> Date |无 |
|放弃的呼叫                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | 已放弃呼叫队列调用结果图例 |
|平均会话长度 (秒)     |fCallQueueFinalStateAction ->平均调用队列持续时间 (sec) <br>呼叫队列调用结果图例 |平均呼叫队列持续时间 (sec) > 0 |
|呼叫溢出/超时目标  |fCallQueueAnalytics -> 调用计数<br>fCallQueueAnalytics ->呼叫队列目标类型<br>fCallQueue 目标类型图例 |呼叫队列目标类型图例不包含已放弃和代理应答 |


#### <a name="fcallqueueanalytics-field-description"></a>fCallQueueAnalytics 字段说明

|名称                                    |数据类型                |说明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|调用计数                              |整数             |汇总：总和<br>通话的数量                                          |
|呼叫队列代理计数                  |整数             |汇总：总和<br>呼叫队列中配置的代理数            |
|呼叫队列代理选择加入计数           |整数             |汇总：总和<br>选择加入呼叫队列的代理数              |
|呼叫队列调用结果                  |文本                     |请参阅呼叫队列维度 -> CallQueueCallResult                           |
|呼叫队列调用结果图例           |文本                     |基于呼叫队列结果设置图例项                            |
|呼叫队列目标类型                  |文本                     |请参阅呼叫队列维度 -> CallQueueTargetType                           |
|调用队列目标类型图例           |文本                     |基于呼叫队列目标类型设置图例项                       |
|呼叫类型                               |文本                     |请参阅通用维度 -> PSTNCallType                              |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果 **cq_test@microsoft.com** 完整的资源帐户名称，则此值将为： **cq_test** |
|CQ 小时                                 |整数             |呼叫队列呼叫开始小时                                                 |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)                                  | 
|DateTimeCQName                          |文本                     |用于筛选 fCallQueueFinalStateAction 的唯一键                     |
|PSTN 连接类型                  |文本                     |请参阅公共维度 -> PSTNConnectivityType                              |
|PSTN 总分钟数                      |整数             |汇总：总和<br>PSTN 呼叫的总分钟数使用情况                       |
|调用计数 (度量) 的总和             |整数             |与呼叫计数相同，但是如果没有调用，则为 0                          |
|TotalCallCount (Measure)                 |整数             |汇总：总和<br>调用计数                                               |


#### <a name="fcallqueuefinalstateaction-field-description"></a>fCallQueueFinalStateAction 字段说明

|名称                                    |数据类型                |说明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|平均调用持续时间 (秒)          |十进制数           |汇总：总和<br>已放弃呼叫的平均呼叫持续时间（秒）     |
|平均呼叫队列持续时间 (sec)        |十进制数           |汇总：总和<br>应答呼叫的平均等待时间（秒）       |
|平均调用持续时间 (度量值)   |整数             |与平均调用持续时间相同， (秒) 但如果没有调用，则为 0    |
|平均 CQ 持续时间 (度量)     |整数             |与平均呼叫队列持续时间相同， (秒) 如果没有调用，则为 0  |
|调用计数                              |整数             |汇总：总和<br>通话的数量                                          |
|呼叫队列调用结果                  |文本                     |请参阅呼叫队列维度 -> CallQueueCallResult                           |
|呼叫队列调用结果图例           |文本                     |基于呼叫队列调用结果设置图例项                       |
|调用队列最终状态操作           |文本                     |请参阅调用队列维度 -> CallQueueFinaleStateAction                    |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果 **cq_test@microsoft.com** 完整的资源帐户名称，则此值将为： **cq_test** |
|CQ 小时                                 |数字                   |通话发生的小时数
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)                                  |
|DateTimeCQName                          |文本                     |用于筛选 fCallQueueFinalStateAction 的唯一键                     |
|IsAbandoned                             |True/false               |如果代理未接听呼叫，则为 True                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>云呼叫队列代理时间线报告

#### <a name="report-description"></a>报告说明

|报告部分                                          |说明                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|按代理发出的调用数                                |按呼叫队列和代理分配呼叫                       |
|按代理和所有队列分发                     |按代理和呼叫队列分配呼叫                       |
|表格 (左下)                                      |按代理分配平均呼叫持续时间和总呼叫持续时间 |
|代理) 的平均呼叫持续时间 (秒 (右下角)  |代理调用的平均持续时间 (秒)                          |

#### <a name="report-visual-field-mapping"></a>报表视觉对象字段映射

|“报表”选项卡            |报表表名称           |全局筛选器       |
|:---------------------|:---------------------------|:-------------------|
|代理时间线        |fAgentTimelineAnalytics     |无                |


|报告部分                                |已使用字段 ()                          |应用的筛选器       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日期选择器                                 |Datetime                              |无                  |
|代理用户名选择器                       |代理名称                            |无                  |
|呼叫队列资源帐户选择器         |CQ 名称                               |无                  |
|按代理发出的调用数                      |调用计数<br>代理名称<br>日期<br>Hour      |无                  |
|按代理和呼叫队列分布          |代理名称<br>平均调用持续时间 (秒) <br>调用计数<br>CQ 名称 |无                      |
|左下角                                   |代理名称<br>平均调用持续时间 (秒) <br>调用计数<br>呼叫持续时间 (分钟) <br>CQ 名称<br>Hour<br>MM-DD | 无 |
|代理) 的平均调用持续时间 (秒      |代理名称<br>平均调用持续时间 (秒)  | 无 |

#### <a name="fagenttimelineanalytics-field-description"></a>fAgentTimelineAnalytics 字段说明

|名称                                    |数据类型                |说明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|代理名称                              |文本                     |用户 UPN<br>如果完整用户名 **user@microsoft.com**，则此值将为： **user** |
|平均调用持续时间 (秒)          |十进制数           |汇总：总和<br>应答呼叫队列调用的平均持续时间（秒） |
|调用计数                              |整数             |汇总：总和<br>代理应答的呼叫数     |
|呼叫持续时间 (分钟)                  |整数             |汇总：总和<br>已应答呼叫队列呼叫的总呼叫持续时间（以分钟为单位 (舍入为最接近的分钟)   |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果 **cq_test@microsoft.com** 完整的资源帐户名称，则此值将为： **cq_test** |
|日期                                    |日期                     |呼叫日期                                             |
|Datetime                                |Datetime                 |呼叫日期                                             |
|Hour                                    |整数             |通话时间                                             |
|MM-DD                                   |文本                     |调用的月份和日期                                    |


> [!NOTE]
> 当呼叫到达第一个呼叫队列时，如果已在该队列中等待的呼叫数已达到 **呼叫溢出处理** 限制，并且重定向选项将新呼叫发送到第二个呼叫队列，则第二个呼叫队列中的代理将显示为在此报表上的第一个呼叫队列中。 

## <a name="known-issues"></a>已知问题

- 呼叫队列和自动助理由资源帐户的 ID 而不是呼叫队列/自动助理名称显示。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 仪表板中只有 28 天的历史记录可用，因为呼叫队列/自动助理数据被视为个人数据，并受数据隐私保留策略的约束。

- 在某些情况下， **云呼叫队列代理时间线** 报表上的代理应答呼叫计数可能与 Teams 客户端呼叫历史记录中显示的呼叫数不同。 Teams 客户端呼叫历史记录正确。 支持人员正在调查，但目前估计没有可用的修复时间。

## <a name="version-3xx-history"></a>版本 3.x.x 历史记录

有关更改的详细列表，请参阅：Teams 自动助理&呼叫队列历史报告 - 下载的 zip 文件中的更改Log.docx 

|版本  |发布日期     |文件名                                                           |说明                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |2022 年 11 月 18 日  |Teams 自动助理&呼叫队列历史报告 V3.0.4        |更正了错误，改进了调用分类，添加了图例 |
|3.0.3    |2022 年 11 月 8 日   |Teams 自动助理&呼叫队列历史报告 V3.0.3        |更正了错误，添加了文档链接，优化了查询 |
|3.0.1    |2022 年 10 月 26 日   |Teams 自动助理&呼叫队列历史报告 V3.0.1        |删除了测试数据源条目                   |
|3.0.0    |2022 年 10 月 25 日   |Teams 自动助理&呼叫队列历史报告 V3.0.0        |新建后端数据源                             |
