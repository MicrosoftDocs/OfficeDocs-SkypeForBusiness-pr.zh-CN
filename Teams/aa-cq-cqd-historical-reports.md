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
ms.openlocfilehash: dad1fa07d476aa5bcfa1e39818d9d7a01b7fdc56
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845909"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>自动助理和呼叫队列历史报告

>[!NOTE]
> GCC HIgh 和 DOD 客户应继续使用 V1.63 的 [自动助理&呼叫队列历史报告 (CQD) ](aa-cq-cqd-historical-reports-v163.md)。

此 Power BI 模板提供三个报表，使组织能够报告自动助理和呼叫队列正在处理的呼叫数。  它还提供代理性能见解。

## <a name="v305-published-on-january-9-2023"></a>V3.0.5 已发布于 2023 年 1 月 9 日

Teams 自动助理&呼叫队列历史报告 Power BI 模板提供以下三个报表：

- [自动助理](media/aa-cq-historical-report-sample-aa-v305.png)报表显示传入自动助理的呼叫的分析。
- [“呼叫队列](media/aa-cq-historical-report-sample-cq-v305.png)”报表显示对进入呼叫队列的呼叫的分析。
- [代理时间线](media/aa-cq-historical-report-sample-at-v305.png)报表显示呼叫队列调用中处于活动状态的代理的时间线视图。

这些报表使用语音应用程序分析收集器 (VAAC) 服务中的数据。

## <a name="v3xx-prerequisites"></a>V3.x.x 先决条件

### <a name="power-bi-desktop"></a>Power BI Desktop

需要安装Power BI Desktop。 你可以从 [Microsoft Windows 应用商店](https://aka.ms/pbidesktopstore)安装并使用免费版本。

最低兼容版本为 2.85.681.0 (2020 年 9 月) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限

虽然此版本的报表不使用通话质量仪表板 (CQD) 数据管道，但用于查看历史数据的帐户仍需要访问通话质量仪表板。 有关详细信息，请参阅 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

同时将 **“查看报表”** 和“ **查看 EUII”字段** 设置为 **“是** ”的任何 CQD 角色都将正常工作。

- 此要求将在将来的版本中删除。

## <a name="v3xx-installation"></a>V3.x.x 安装 

以下步骤假定已在计算机上安装了 Power BI Desktop，并且帐户具有访问 CQD 数据管道所需的权限。

执行以下步骤：

1. 在计算机上下载并保存 [Teams 自动助理&呼叫队列历史报告V3.0.5.zip](https://www.microsoft.com/download/details.aspx?id=104623) 文件。

2. 打开 zip 文件。

3. 打开 `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` 模板文件。 Power BI Desktop应启动。

4. 系统将提示你选择 **数据源**。  选择条目 `api.interfaces.records.teams.microsoft.com` 。

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="选择 api.interfaces.records.teams.microsoft.com Data Soure 的屏幕截图":::

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
|AA 开始时间 UTC                       |日期/时间                |自动助理呼叫开始时间 - UTC                                                     |
|AACallerActionCount                     |整数             |汇总：总和<br>呼叫期间呼叫者在自动助理中选择的操作计数  |
|AACallerActionCount (Measure)            |整数             |与 AACallerActionCount 相同，但如果没有调用而不是空白，则为 0                |
|AACallFlow                              |文本                     |请参阅自动助理维度 -> AutoAttendantCallFlow                                   |
|AACallResult                            |文本                     |请参阅自动助理维度 -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |文本                     |基于 AACallResult 设置图例项                                               |
|AAChainDuration                         |十进制数           |汇总：总和<br>自动助理中的呼叫持续时间                                     |
|AAChainDuration (Measure)                |十进制数           |与 AAChainDuration 相同，但如果没有调用而不是空，则为 0                    |
|AAChainIndex                            |整数             |                                                                                         |
|AAConnectivityType                      |文本                     |请参阅常见维度 -> PSTNConnectivityType                                            |
|AACount                                 |整数             |呼叫中涉及的自动助理数                                               |
|AADirectorySearchMethod                 |文本                     |请参阅自动助理维度 -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |文本                     |基于 AADirectorySearchMethod 设置图例项                                    |
|AAStartHour                             |整数             |自动助理呼叫开始时间                                                           |
|AAStartTime                             |日期/时间                |自动助理呼叫开始时间                                                           |
|AATransferAction                        |文本                     |请参阅自动助理维度 -> AutoAttendantTransferAction                             |
|调用持续时间秒                   |整数             |通话持续时间                                                                            |
|本地呼叫结束时间                     |日期/时间                |呼叫结束时间 - 基于运行报告) 的计算机的时区的本地 (                    |
|呼叫结束时间 UTC                       |日期/时间                |呼叫结束时间 - UTC                                                                      |
|本地呼叫开始时间                   |日期/时间                |呼叫开始时间 - 基于运行报表的计算机的时区的本地 ()                   |
|呼叫开始时间 UTC                     |日期/时间                |呼叫开始时间 - UTC                                                                    |
|呼叫类型<sup>1</sup>                   |文本                     |请参阅通用维度 -> PSTNCallType                                                    |
|ConferenceID                            |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|DialogID                                |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|DocumentID                              |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|MM-DD                                   |文本                     |自动助理呼叫月-天                                                            |
|PSTNMinutes                             |整数             |汇总：总和<br>总分钟使用量                                                     |
|TotalCallCount (度量值) 的总和         |整数             |与 TotalCallCount 相同，但如果没有调用而不是空，则为 0                     |
|TotalCallCount                          |整数             |汇总：总和<br>始终 1 - 用于提供所有调用的总和                            |


### <a name="cloud-call-queue-analytics-report"></a>云呼叫队列分析报告

#### <a name="report-description"></a>报告说明

|报告部分                          |说明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|传入呼叫源                    |按内部/外部调用源分配呼叫             |
|平均等待时间 (秒)              |等待应答和放弃的呼叫                         |
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

|名称                                    |数据类型                |说明                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|调用计数                              |整数             |汇总：总和<br>通话的数量                                                        |
|调用持续时间秒                   |整数             |通话持续时间                                                                            |
|本地呼叫结束时间                     |日期/时间                |呼叫结束时间 - 基于运行报告) 的计算机的时区的本地 (                    |
|呼叫结束时间 UTC                       |日期/时间                |呼叫结束时间 - UTC                                                                      |
|呼叫队列代理计数                  |整数             |汇总：总和<br>呼叫队列中配置的代理数                          |
|呼叫队列代理选择加入计数           |整数             |汇总：总和<br>选择加入呼叫队列的代理数                            |
|呼叫队列调用结果                  |文本                     |请参阅呼叫队列维度 -> CallQueueCallResult                                         |
|呼叫队列调用结果图例           |文本                     |基于呼叫队列结果设置图例项                                          |
|呼叫队列目标类型                  |文本                     |请参阅呼叫队列维度 -> CallQueueTargetType                                         |
|调用队列目标类型图例           |文本                     |基于呼叫队列目标类型设置图例项                                     |
|本地呼叫开始时间                   |日期/时间                |呼叫开始时间 - 基于运行报表的计算机的时区的本地 ()                   |
|呼叫开始时间 UTC                     |日期/时间                |呼叫开始时间 - UTC                                                                    |
|呼叫类型                               |文本                     |请参阅通用维度 -> PSTNCallType                                                    |
|ConferenceID                            |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果 **cq_test@microsoft.com** 完整的资源帐户名称，则此值将为： **cq_test** |
|CQ 小时                                 |整数             |呼叫队列呼叫开始小时                                                               |
|日期                                    |日期/时间                |呼叫队列呼叫开始日期和时间 (小时)                                                | 
|DateTimeCQName                          |文本                     |用于筛选 fCallQueueFinalStateAction 的唯一键                                   |
|DialogID                                |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|DocumentID                              |文本                     |用于故障排除目的 - 在开票时提供此信息       |
|PSTN 连接类型                  |文本                     |请参阅公共维度 -> PSTNConnectivityType                                            |
|PSTN 总分钟数                      |整数             |汇总：总和<br>PSTN 呼叫的总分钟数使用情况                                     |
|调用计数 (度量) 的总和             |整数             |与呼叫计数相同，但是如果没有调用，则为 0                                        |
|TotalCallCount (Measure)                 |整数             |汇总：总和<br>调用计数                                                             |


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
|呼叫持续时间 (分钟)                  |整数             |汇总：总和<br>已应答呼叫队列呼叫的总呼叫持续时间（以分钟为单位 (舍入为最接近的分钟)   |
|应答的呼叫                          |整数             |代理应答的呼叫数                        |
|未接听呼叫                      |整数             |代理未接听的呼叫数                    |
|CQ 名称                                 |文本                     |附加到呼叫队列的资源帐户的名称<br><br>如果 **cq_test@microsoft.com** 完整的资源帐户名称，则此值将为： **cq_test** |
|日期                                    |日期                     |呼叫日期                                             |
|Datetime                                |Datetime                 |呼叫日期                                             |
|Hour                                    |整数             |通话时间                                             |
|MM-DD                                   |文本                     |调用的月份和日期                                    |
|总调用计数                        |整数             |汇总：总和<br>向代理显示的调用数     |

> [!NOTE]
> 当呼叫到达第一个呼叫队列时，如果已在该队列中等待的呼叫数已达到 **呼叫溢出处理** 限制，并且重定向选项将新呼叫发送到第二个呼叫队列，则第二个呼叫队列中的代理将显示为在此报表上的第一个呼叫队列中。 

## <a name="known-issues"></a>已知问题

- **“呼叫队列**”报表上的 **“呼叫结果”** 视觉对象可能会报告大量 **_“未知_**”呼叫。 这是由于支持人员正在努力更正的呼叫分类问题造成的。  这只是一个呼叫分类问题，系统已成功处理这些调用。

- 仅报告接听呼叫的第一个自动助理或呼叫队列中的呼叫和呼叫者操作。  当一个自动助理转移到另一个自动助理) 或链接呼叫队列 (当一个呼叫队列转移到另一个呼叫队列) 时，链接式自动助理中的呼叫和调用方操作 (。 

- 呼叫队列和自动助理由资源帐户的 ID 而不是呼叫队列或自动助理名称显示。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 仪表板中只有 28 天的历史记录可用，因为呼叫队列和自动助理数据被视为个人数据，并受数据隐私保留策略的约束。

- 在某些情况下， **云呼叫队列代理时间线** 报表上的代理应答呼叫计数可能与 Teams 客户端呼叫历史记录中显示的呼叫数不同。 Teams 客户端呼叫历史记录正确。 支持人员正在调查，但目前估计没有可用的修复时间。

## <a name="customization"></a>定制 

可以自定义报表的某些可视化效果方面，例如添加或删除要显示在各种可视化效果中的字段、更改图表类型等。

### <a name="change-color-schema"></a>更改颜色架构 

以下步骤假定你已完成安装步骤。

执行以下步骤：

1. 选择功能区上的 **“视图”选项卡** 。

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="选择“视图”选项卡以更改配色方案的屏幕截图。":::

2. 从下拉列表中选择颜色架构。

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="显示各种配色方案的屏幕截图。":::
  
## <a name="dimensions-and-measurements"></a>尺寸和度量值

可以使用以下尺寸和度量值。

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
|FirstIsCaller<br> (布尔)                              |                               |[第一终结点和第二终结点分类](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br> (文本)                                      |                               |用户主体名称 (UPN) 第一终结点的用户        |
|Hour<br> (文本)                                          |                               |小时呼叫已启动 (UTC)                                            |
|Minute<br> (文本)                                        |                               | (UTC) 开始的分钟呼叫                                         |
|PSTNCallDuration<br> (整数)                      |                               |通话持续时间                                              |
|PSTNCallType<br> (文本)                                  |                               |                                                                  |
|                                                       |外部                       |呼叫来自租户外部                            |
|                                                       |内部                       |呼叫来自租户内部                             |
|PSTNConnectivityType<sup>1</sup><br> (文本)              |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|第二个<br> (文本)                                        |                               |第二次呼叫已 (UTC) 启动                                         |
|SecondUPN<br> (文本)                                     |                               |用户主体名称 (UPN) 第二终结点的用户       |
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
|AutoAttendantChainDurationInSecs<br> (实数)       |                               |                                                                  |
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
|CallQueueDurationSeconds<br> (实数)               |                               |呼叫队列中的呼叫持续时间                                   |
|CallQueueFinaleStateAction<br> (文本)                    |                               |呼叫队列最终操作                                           |
|                                                       |断开                     |time_out调用                                                    |
|                                                       |disconnect_with_busy           |溢出调用                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |向前                        |呼叫已转接到用户或从外部转接                        |
|                                                       |shared_voicemail               |呼叫已发送到共享语音邮件                                 |
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

### <a name="constructing-a-valid-query"></a>构造有效的查询

有效的查询由 JSON 对象中的多个属性组成：

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>必填字段

- 筛选器：用于筛选 VAAC 返回的数据
- - DataModelName 应为受支持的维度之一
- - 值应采用正确的格式 (datetime、string、number 等) 
- - 操作：
- - - 0 - 等于
- - - 1 - 不等于
- - - 2 - 包含
- - - 3 - 开头
- - - 4 - 大于
- - - 5 - 大于或等于
- - - 6 - 小于
- - - 7 - 小于或等于
- - - 8 - 不包含
- - - 9 - 不以 开头

- 尺寸：
- - DataModelName 应为受支持的维度之一

- 测量：
- - DataModelName 应该是受支持的度量值之一

- 参数：目前仅支持 UserAgent。

- LimitResultRowsCount：VAAC 返回的最大行数

## <a name="accessing-vaac-outside-of-power-bi"></a>在 Power BI 外部访问 VAAC

可以访问 RESTful 应用程序的任何应用程序都可以访问 VAAC API。  在下面的示例中，将使用 [Postman](https://www.postman.com/) 。

### <a name="preparation"></a>制备

1. 下载 [Postman](https://www.postman.com/)。
1. 解压缩下载的 [zip 文件说明中的文件](#v3xx-installation)。`sync_pstn_avs-analytics.zip`
1. 将文件夹导入 Postman。 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="显示导入已完成的屏幕截图":::

### <a name="accessing-vaac-using-postman"></a>使用 Postman 访问 VAAC

1. 选择右上角的“**_无环境_**”下拉列表中的“**VAAC - msit**”。
2. 在左侧栏杆菜单中选择“ **环境** ”。
3. 在“**全局**”下选择“**VAAC - msit**”。
4. 将 **userName**、 **password** 和 **tenantId** 替换为适用的凭据。
5. 单击右上角的“ **全部重置** ”。
6. 单击“**保存**”。

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="显示配置的用户名、密码和租户 ID 字段的屏幕截图":::

7. 在左侧栏菜单上选择 **“集合** ”。
8. 选择 **“配置 API 访问令牌 - 生产** ”，然后导航到“ **正文** ”选项卡。
9. 单击“ **发送**”。

将返回访问令牌。

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="显示返回访问令牌的结果的屏幕截图":::

如果未返回访问令牌，请检查凭据，使其具有 [足够的权限](#permissions-to-access-the-cqd-pipeline)。

10. 选择“ **VAAC ConfigAPI Prod** ”并导航到“ **参数** ”选项卡。

- [压缩](#compress-the-json-query) 查询，如下所示
- [URL 对](#url-encode-the-compressed-json-query) 压缩结果进行编码，如下所示

11. 填写 [查询](#constructing-a-valid-query) 字符串。
12. 单击“ **发送**”。

### <a name="reading-the-result"></a>读取结果

提交输入后，会出现以下几个可能的结果：

- 如果输入无效，将返回具有实际原因的错误消息
- 如果输入有效，则结果将如下所示：

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="显示包含 dataResult 字段的查询结果的屏幕截图":::

在这种情况下，数据将按照查询维度和度量属性中请求的顺序位于“dataResult”字段中。

### <a name="compress-the-json-query"></a>压缩 JSON 查询

VAAC API 仅接受 GZip 压缩或 Base64 编码的字符串作为输入。

查找使用 GZIP 或 Base64 压缩 JSON Blob 的任何网站。

- GZIP： (https://www.multiutil.com/text-to-gzip-compress/)
- Base64： (https://www.multiutil.com/text-to-base64-converter/)

GZIP 输出应如下所示：
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

Base64 输出应如下所示：
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>URL-Encode压缩的 JSON 查询

GZIP 或 Base64 压缩的 JSON 查询必须 [经过 URL 编码](https://meyerweb.com/eric/tools/dencoder/)。

GZIP URL 编码的输出将如下所示：
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

Base64 URL 编码的输出将如下所示：
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>版本 3.x.x 历史记录

有关更改的详细列表，请参阅：Teams 自动助理&呼叫队列历史报告 - 下载的 zip 文件中的更改Log.docx 

|版本  |发布日期     |文件名                                                    |说明                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |2023 年 1 月 9 日    |Teams 自动助理&呼叫队列历史报告 V3.0.5 |改进了呼叫溢出/超时目标和代理时间线视觉对象  |
|3.0.4    |2022 年 11 月 18 日  |Teams 自动助理&呼叫队列历史报告 V3.0.4 |更正了错误，改进了调用分类，添加了图例             |
|3.0.3    |2022 年 11 月 8 日   |Teams 自动助理&呼叫队列历史报告 V3.0.3 |更正了错误，添加了文档链接，优化了查询            |
|3.0.1    |2022 年 10 月 26 日   |Teams 自动助理&呼叫队列历史报告 V3.0.1 |删除了测试数据源条目                                       |
|3.0.0    |2022 年 10 月 25 日   |Teams 自动助理&呼叫队列历史报告 V3.0.0 |新建后端数据源                                                 |
