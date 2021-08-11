---
title: 使用 CQD Power BI报表查看自动助理 &队列历史报告
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
description: 了解如何使用呼叫质量仪表板Power BI报表来查看自动助理呼叫队列历史数据。
ms.openlocfilehash: 844ab5caee23cb504420925c9f13bc261d4d839cce19f7ae557d4637562a963e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331084"
---
# <a name="what-are-the-requirements"></a>要求是什么？ 
需要安装Power BI Desktop。 可以从 Microsoft store [Windows安装它](https://aka.ms/pbidesktopstore)。

可以使用免费版本的 Power BI Desktop。 最低兼容版本为 2020 年 9 月 (2.85.681.0) 。

## <a name="permissions-to-access-the-cqd-pipeline"></a>访问 CQD 管道的权限
用于查看 AA & CQ Analytics 历史报告的帐户需要具有访问 CQD 数据管道的权限。 有关详细信息，请参阅 [CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 访问角色。

## <a name="installation"></a>安装 
以下步骤假定已在计算机上安装Power BI Desktop，并且帐户具有访问 CQD 数据管道所需的权限。

请执行以下步骤：
- 下载[CQD Teams 自动助理 &队列历史报告模板](./aa-cq-cqd-historical-reports.md)，并将其保存到计算机的目录。

- 双击模板，Power BI Desktop启动。

- 系统会提示选择 CQD 数据管道区域。 选择租户所在的区域。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="管理中心内"呼叫质量仪表板"Teams屏幕截图":::

 - 可以使用 Get-CsTenant Skype for Business Online PS cmdlet (查看) 。ServiceInstance 输出。 
 区域将显示在 /之后，如以下示例所示： 
 
   区域为 noam 的 microsoftcommunicationsonline/noam-4a-s7。
   
 - 报告将随示例数据一起启动。
 
 - 若要查看自己的数据，请单击"开始"选项卡中"查询"下的"Power BI Desktop"。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="管理中心内"呼叫质量仪表板"Teams屏幕截图":::

- 然后，系统会提示你登录。 选择 **"组织帐户**"，然后选择"**登录"。**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="管理中心内"呼叫质量仪表板"Teams屏幕截图":::

- 选择 **连接** 并观看数据刷新。

## <a name="data-latency-any-aa--cq-analytics"></a>数据延迟 任何 AA & CQ 分析
数据将在 30 分钟内在 CQD 数据管道中提供。

必须刷新数据，以查看新的分析数据。 

## <a name="customization"></a>自定义 
可以自定义报表的某些可视化方面，例如添加或删除要显示在各种可视化效果中的字段、更改图表类型等。

不能添加报告中提供的数据字段外的其他数据字段。

### <a name="change-color-schema"></a>更改颜色架构 
以下步骤假定已完成安装步骤。

请执行以下步骤：
- 选择 **功能区上的** "视图"选项卡。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="管理中心内"呼叫质量仪表板"Teams屏幕截图":::

- 从下拉列表中选择颜色架构。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="管理中心内"呼叫质量仪表板"Teams屏幕截图":::


## <a name="cqd-fields-description"></a>CQD 字段说明

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自动助理标识                 |string                   |附加到 AA 的资源帐户的名称<br>示例：aa_test@microsoft.com|
|自动助理链开始时间         |datetime                 |AA 链开始时间                    |
|自动助理目录搜索方法  |string                   |最后一个通讯簿搜索方法        |
|自动助理传输操作          |string                   |呼叫转接目标类型<br>可能的值：<br>§ unknown - 未指定实体类型<br>§ user - 用户实体<br>§ orgaa - 自动助理实体<br>§ hunt_group - 调用队列实体<br>§ 应用程序 - 语音应用程序实体<br>§ external_pstn - 外部 PSTN 实体<br>§ shared_voicemail - 共享语音邮件实体|
|自动助理通话结果              |string                   |调用结果：<br>§ 未知 - 调用设置或传输失败，服务未收到任何有意义的失败原因 <br>§ transferred_to_user - 通过"按名字/分机拨叫"或配置的"菜单选项"将呼叫转接到用户 <br>§ transferred_to_operator - 呼叫已转接到配置的操作员，例如，如果为 AA 配置了接线员数小时 <br>§ failover_to_operator - 传输失败或名称识别在三次尝试后不起作用时回退到运算符<br>§ user_terminated - 调用方已终止呼叫 <br>§ service_declined - 按服务拒绝的调用，如果服务无法提取自动助理配置，则可能会发生这种情况 <br>§ service_terminated - 后端服务终止了调用，如果目标传输失败且未将任何运算符配置为回退， <br>§ failed_to_establish_media - 调用方和服务之间的媒体建立失败 <br>§ terminated_no_operator - 名称识别在三次尝试后失败，并且未配置运算符 <br>§ terminated_transfer_failed - 转移到目标失败且未配置运算符 <br>§ terminated_automatic_selection - 如果未在几个小时内或之后配置任何操作，则调用将默认终止 <br>§ transferred_to_shared_voicemail - 将呼叫转接到共享语音邮件（如果已配置为目标） <br>§ oaa_chain_too_long - 当自动助理连续超过五个自动助理时，呼叫将终止以避免可能的呼叫循环 <br>§ oaa_session_too_long - 调用超出了允许的最大会话长度并且已退出 |
|自动助理呼叫Flow                |string                   |封装调用的不同自动助理状态<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 公告|
|是否自动助理涉及              |Boolean                  |指示 AA 是否参与呼叫 |
|自动助理调用方操作计数      |int                      |调用方使用的操作计数         |
|自动助理链持续时间秒数   |int                      |AA 中的通话持续时间                 |
|呼叫队列呼叫结果                  |String                   |调用队列调用最终状态<br>可能的值：<br>§ 错误<br>§ 已拒绝<br>§ overflown<br>§ 失败<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|调用队列最终状态操作           |String                   |调用队列最终操作<br>可能的值：<br>§ forward<br>§ disconnect<br>§ 语音邮件<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other|
|调用队列标识                     |String                   |附加到 CQ 的资源帐户的名称<br>示例：aa_test@microsoft.com|
|呼叫队列是会议模式           |Boolean                  |如果在 CQ 上启用了会议模式，设置为 1 |
|调用队列目标类型                  |String                   |预期的调用重定向目标类型     |
|从呼叫队列标识转移    |Boolean                  |附加到 CQ 的资源帐户的名称，从中传输此调用<br>示例：aa_test@microsoft.com|
|调用队列代理选择加入计数           |int                      |调用时此队列可用的代理计数 |
|调用队列代理计数                  |int                      |在调用时分配到此队列的代理的计数 |
|是否涉及调用队列                  |Boolean                  |如果调用队列被涉及到此调用中，则等于 1 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI 数据模型维度

|名称                                    |数据类型                |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名称                                   |string                   |自动助理 ID (资源帐户 ID)  |
|AACallFlow                              |string                   |封装调用的不同自动助理状态<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>公告 |
|AACallResult                            |string                   |调用自动助理结果：<br>§ 未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 配置错误<br>§ service_terminated – 内部 AA 错误<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |string                   |调用自动助理持续时间（以秒数）  |
|AACount                                 |string                   |涉及自动助理的数         |
|AADirectorySearchMethod                 |string                   |调用中使用的搜索方法：<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |string                   |呼叫时间（UTC）                            |
|AATransferAction                        |string                   |呼叫接收者：<br>§ unknown - 未指定实体类型<br>§ user - 用户实体<br>§ AA - 组织自动助理实体<br>§ CQ - 调用队列实体<br>§ 应用程序 - 语音应用程序实体<br>§ external_pstn - 外部 PSTN 实体<br>§ shared_voicemail - 共享语音邮件实体      |
|PSTNMinutes                             |int                      |总分钟使用量                          |
|呼叫队列呼叫结果                  |string                   |调用队列调用最终状态<br>可能的值：<br>§ 错误<br>§ 已拒绝<br>§ overflown<br>§ 失败<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|调用队列标识                     |string                   |附加到 CQ 的资源帐户的名称     |
|调用队列目标类型                  |string                   |预期的调用重定向目标类型：<br>§ 用户<br>§ 应用程序终结点<br>§ 其他     |
|呼叫队列呼叫结果                  |string                   |调用队列调用最终状态<br>可能的值：<br>§ 错误<br>§ 已拒绝<br>§ overflown<br>§ 失败<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|调用队列最终状态操作           |string                   |调用队列最终操作<br>可能的值：<br>§ forward<br>§ disconnect<br>§ 语音邮件<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other             |
|代理名称                              |string                   |用户 UPN               |


### <a name="measures"></a>衡量指标

|名称                                      |类型                       |说明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |呼叫期间 AA 中用户选择的操作数  |
|PSTNMinutes                             |int                      |总分钟使用量                                  |
|TotalCallCount                          |int                      |通话数                                          |
|平均呼叫持续时间 (秒)          |int                      |呼叫队列调用的总持续时间（以秒数表示）     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI图形说明自动助理

|名称                                      |描述                            |
|:---------------------------------------|:--------------------------------------|
|传入呼叫源                    |按内部/外部呼叫源分布呼叫      |
|目录搜索方法总计          |按搜索类型分布的呼叫                         |
|调用方操作                           |呼叫接收者调用的分布                       |
|通话结果                             |按最终调用状态表示的呼叫分布                    |
|调用方操作计数                     |呼叫期间使用的按号码操作进行呼叫的分布  |


### <a name="call-queue"></a>呼叫队列

|名称                                      |描述                            |
|:---------------------------------------|:--------------------------------------|
|传入呼叫源                    |按内部/外部呼叫源分布呼叫         |
|呼叫量                             |按呼叫队列分布的呼叫                            |
|调用方结果                           |按通话结果分布的呼叫                            |
|超时/溢出调用总数操作      |按呼叫结果 () 的未转发呼叫的分布   |
|转移/转发目标总计          |按呼叫结果转发的呼叫分布                  |
|已放弃的通话比率                   |成功与放弃的呼叫计数的比率                    |
|平均会话长度 (秒)         |按放弃/成功调用分组的呼叫长度（以秒数表示）   |



### <a name="agent-timeline"></a>代理时间线

|名称                                                      |描述                            |
|:-------------------------------------------------------|:--------------------------------------|
|代理调用的个次                                        |按呼叫队列和代理分布呼叫                 |
|代理和 (队列) 总呼叫持续时间   |代理 (呼叫队列) 的总持续时间（秒）     |
|按代理名称 (平均) 秒数            |代理 (呼叫) 的平均持续时间（秒）                  |



## <a name="known-issues"></a>已知问题
- 目前，呼叫队列和自动助理显示资源帐户 ID，而不是呼叫队列/自动助理名称。  若要显示自动助理或呼叫队列的所有流量，必须选择分配给自动助理或呼叫队列的所有资源帐户。

- 目前，只有 28 天的历史记录在仪表板中可用，因为呼叫队列/自动助理数据被视为最终用户可识别信息，并受数据隐私保留策略的约束。
