---
title: 使用 OMS 部署 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何使用 Microsoft 操作管理套件集成的、 端到端方式部署 Skype 的空间系统 v2 设备的管理。
ms.openlocfilehash: 3d42f0777059870872e871c25591f16c103b5939
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>使用 OMS 部署 Skype 会议室系统 v2 管理
 
本文讨论了如何设置和使用 Microsoft 操作管理套件部署 Skype 的空间系统 v2 设备集成的、 端到端管理。
  
您可以配置 Microsoft 操作管理套件提供基本遥测和警报可帮助您管理 Skype 会议室内设备。 随着您的管理解决方案逐渐成熟，您可能决定部署更多的数据和管理功能，以创建设备的可用性和性能的详细的视图。

通过遵循本指南，可以使用类似下面的示例仪表板以获取设备的可用性、 应用程序和硬件健康状况和 Skype 的空间系统 v2 应用程序版本分发报告的详细的状态。

![SRS v2 的示例 OMS 视图](../../media/Deploy_OMS_1.png "SRS v2 的示例 OMS 视图")
  
你需要在高级别执行以下任务：


1.  [验证操作管理套件配置](with-oms.md#validate_OMS)
2.  [配置测试设备的操作管理套件管理设置](with-oms.md#configure_test_devices)
3.  [映射自定义字段](with-oms.md#Custom_fields)
4.  [定义操作管理套件中的测试的 Skype 的空间系统 v2 视图](with-oms.md#Define_Views)
5.  [定义警报](with-oms.md#Alerts)
6.  [将所有设备都配置为操作管理套件](with-oms.md#configure_all_devices)
7.  [配置其他操作管理套件解决方案](with-oms.md#Solutions)

> [!IMPORTANT]
> 最小配置，运营管理套件可以监视计算机运行 Windows 操作系统的系统，虽然仍有需要在开始将代理部署到所有系统，Skype 房间之前采取一些 Skype 的空间系统特定步骤设备。
> 因此，我们强烈建议您执行所有配置步骤按正确的顺序进行受控制的设置和配置。 最终结果的质量很大程度取决于初始配置的质量。

## <a name="validate-operations-management-suite-configuration"></a>验证操作管理套件配置
<a name="validate_OMS"> </a>

您需要操作管理套件工作区，开始从 Skype 的空间系统设备收集日志。 工作区是一个独特的日志分析环境具有其自己的数据存储库、 数据源和解决方案。 如果您已经有一个现有的日志分析工作区，您可能会使用它来监视 Skype 的空间系统部署或者您可以创建特定于您 Skype 的空间系统监视一个专用的日志分析工作区需要。

如果您需要创建新的日志分析功能区，按照文章[创建日志分析在 Azure 门户工作区](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)中的说明

> [!NOTE]
> 要使用操作管理套件日志分析，您需要有有效的 Azure 预订。 如果您没有订阅了 Azure，可以作为起始点来创建[免费试用订阅](https://azure.microsoft.com/free)。


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-event-logs"></a>配置操作的管理套件来收集 Skype 的空间系统事件日志

日志分析只收集设置中指定的 Windows 事件日志中的事件。 为每个日志中，收集到仅选定的严重级别的事件。

您需要配置操作管理套件来收集监视 Skype 的空间系统设备和应用程序状态所需的日志。 Skype 的空间系统 v2 设备使用 Skype 的空间系统事件日志。

若要配置操作的管理套件来收集 Skype 的空间系统事件，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![事件日志设置](../../media/Deploy_OMS_2.png "事件日志设置")


> [!IMPORTANT]
> 选择 Skype 的空间系统事件日志中，然后再选择**错误**、**警告**和**信息**的复选框。

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>配置操作管理套件设置为测试设备
<a name="configure_test_devices"> </a>

您需要准备操作管理套件能够监视 Skype 的空间系统相关的事件。 启动时，您需要将操作管理套件代理部署到只是一个或两个 Skype 的空间系统设备物理访问，有那些测试设备生成一些数据并将其推到日志分析区。

### <a name="install-operations-management-suite-agents-to-test-devices"></a>安装操作管理套件代理来测试设备

使用[连接的 Windows Azure 中的日志分析服务的计算机](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows)中提供的说明将操作管理套件代理部署到测试设备。 这篇文章提供了有关部署 Microsoft 监视代理的 Windows 中，获取操作管理套件区 ID 说明的步骤的详细的信息和主键以获得 Skype 的空间系统设备连接到您操作管理套件部署和验证的代理连接到日志分析的步骤。

### <a name="generate-sample-skype-room-systems-events"></a>生成示例 Skype 的空间系统事件

操作管理套件代理部署到测试设备上后，请验证需要的事件日志数据收集通过日志分析。

1.  登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。

2.  列出由 Skype 的空间系统设备生成的事件：
    1.  转到**日志搜索**和使用查询来检索包含自定义字段的记录。
    2.  示例查询：`Event | where Source == "SRS-App"`

3.  请确保查询返回包含成功检测信号事件的日志记录。

4.  生成一个硬件问题，并验证操作管理套件中的记录所需的事件。
    1.  拔下其中一个测试 Skype 的空间系统系统上的外围设备。 这可能是摄像机、 扬声器、 麦克风或前面房间显示
    2.  等待 10 分钟来填充操作管理套件中的测试的事件日志。
    3.  使用查询列表中的硬件错误事件：`Event | where EventID == 3001`

5.  生成的应用程序问题，并验证所需的事件的记录。
    1.  修改空间系统 Skype 应用程序配置，并键入不正确的会话启动协议 (SIP) 地址/密码对。
    2.  等待 10 分钟来填充操作管理套件中的测试的事件日志。
    3.  使用查询列表应用程序的错误事件：`Event | where EventID == 2001`

> [!IMPORTANT]
> 这些示例事件日志，然后才能配置自定义字段是必需的。 不进入下一步骤，直到收集了所需的事件日志。

## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

使用自定义字段来从事件日志中提取特定的数据。 您需要定义将与拼贴、 仪表板视图和警报稍后使用的自定义字段。 请参阅[日志分析中的自定义字段](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields)和熟悉概念之前开始创建您的自定义字段。

要提取自定义域从捕获的事件日志，请执行以下步骤：

1.  登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。

2.  列出由 Skype 的空间系统设备生成的事件：
    1.  转到**日志搜索**和使用查询来检索包含自定义字段的记录。
    2.  示例查询：`Event | where Source == "SRS-App"`

3.  选择一个记录，选择按钮的左边，然后启动域提取向导。

![字段提取向导](../../media/Deploy_OMS_3.png "字段提取向导")

4.  突出显示您想要从 RenderedDescription 中提取，并提供一个字段标题的数据。 表 1 中提供了您应该使用的字段名称。

![自定义字段定义](../../media/Deploy_OMS_4.png "自定义字段定义")

5.  使用表 1 中所示的映射。 操作管理套件将自动添加**\_CF**时定义新的字段的字符串。

> [!IMPORTANT]
> 请记住 JSON 和操作管理套件的所有字段都是区分大小写。

> 在下表中应注意的 EventID 复选框的状态。 请确保您确认此操作管理套件成功提取自定义字段值的复选框的状态。
> ![自定义字段定义](../../media/Deploy_OMS_5.png "自定义字段定义") 

**表 1**

| **JSON 字段**               | **OMS 的自定义字段**       | **事件 ID** |
|------------------------------|----------------------------|-----------------|
| 说明                  | SRSEventDescription_CF     | 未选中    |
| ResourceState                | SRSResourceState_CF        | 未选中    |
| 操作名称                | SRSOperationName_CF        | 未选中    |
| OperationResult              | SRSOperationResult_CF      | 未选中    |
| OS                           | SRSOSVersion_CF            | 未选中    |
| OSVersion                    | SRSOSLongVersion_CF        | 未选中    |
| 别名                        | SRSAlias_CF                | 未选中    |
| 显示名称                  | SRSDisplayName_CF          | 未选中    |
| AppVersion                   | SRSAppVersion_CF           | 未选中    |
| IPv4Address                  | SRSIPv4Address_CF          | 未选中    |
| IPv6Address                  | SRSIPv6Address_CF          | 未选中    |
| 前面的房间显示状态 | SRSFORDStatus_CF           | 3001            |
| 相机状态                | SRSCameraStatus_CF         | 3001            |
| 会议麦克风状态 | SRSConfMicrophoneStatus_CF | 3001            |
| 会议演讲者状态    | SRSConfSpeakerStatus_CF    | 3001            |
| 默认扬声器状态       | SRSDefaultSpeakerStatus_CF | 3001            |
| 运动传感器状态         | SRSMotionSensorStatus_CF   | 3001            |
| HDMI 接收状态           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>定义操作管理套件中的测试的 Skype 的空间系统 v2 视图
<a name="Define_Views"> </a>

收集数据和自定义字段映射后，可以使用操作管理套件视图设计器开发包含各种拼贴来监视 Skype 的空间系统 v2 事件的仪表板。 使用视图设计器创建以下图块。 有关详细信息，请参阅[使用视图设计器中以创建日志分析中的自定义视图](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> 应为正常工作的仪表板拼贴完成本指南中前面的步骤。


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>通过使用导入方法创建 Skype 的空间系统 v2 仪表板

您可以导入操作管理套件的仪表板并开始立即监视您的设备。 采用以下步骤来导入仪表板：

1.  下载[的仪表板](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview)。
2.  登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。
3.  打开**视图设计器**。
4.  选择**导入**，然后再选择**SkypeRoomSystems_v2.omsview**文件。
5.  选择**保存**。

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>手动创建一个 Skype 的空间系统 v2 仪表板

或者，您可以创建自己的仪表板并添加要监视的拼贴。

#### <a name="configure-the-overview-tile"></a>配置概述平铺
1.  打开**视图设计器**。
2.  选择**概述拼贴**，然后再从库中选择**两个数字**。
3.  平铺**Skype 的空间系统**的名称。
4.  定义**第一个拼贴**：<br>
    **图例：**在最近一个月内至少一次发送检测信号的设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定义**第二个图块**：<br>
    **图例：**在过去一小时内发送检测信号的活动设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  选择**应用**。

### <a name="create-a-tile-that-displays-active-devices"></a>创建平铺视图，显示活动设备
1.  选择**查看仪表板**开始添加您拼贴。
2.  从库中选择**数量和列表**
3.  定义的**常规**属性：<br>
    **组标题：**检测信号状态<br>
    **新组：**选择
4.  定义**平铺**属性：<br>
    **图例：**活动设备 （在最后 20 分钟内发送检测信号）<br>
    **平铺查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定义**列表**的属性：<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定义**的列标题**：<br>
    **名称：**显示名称<br>
    **值：**最后一次心跳
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>创建平铺视图显示具有连接问题的设备
1.  从库中选择**编号与列表**，然后添加一个新图块。
2.  定义的**常规**属性：<br>
    **组标题：**保留为空<br>
    **新组：**未选中
3.  定义**平铺**属性：<br>
    **图例：**非活动设备 （没有在最后 20 分钟内发送心跳消息）<br>
    **平铺查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定义**列表**的属性：<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定义**的列标题**：<br>
    **名称：**显示名称<br>
    **值：**最后一次心跳
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>创建平铺视图显示设备具有硬件错误

1.  从库中选择**编号与列表**，然后添加一个新图块。
2.  定义的**常规**属性：<br>
    **组标题：**硬件<br>
    **新组：**选择
3.  定义**平铺**属性：<br>
    **图例：**在最后一个小时出现硬件错误的设备 <br>
    **平铺查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性：<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  定义**的列标题**：<br>
    **名称：**显示名称<br>
    **值：**最后一个错误
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-skype-room-systems-application-versions"></a>创建平铺视图显示 Skype 的空间系统的应用程序版本

1.  从库中选择**油炸圈饼和列表**，然后添加一个新图块。
2.  定义的**常规**属性：<br>
    **组标题：**Skype 的空间系统 v2 应用程序详细信息 <br>
    **新组：**选择
3.  定义的**标头**属性：<br>
    **标题：**应用程序版本<br>
    **副标题：**运行特定应用程序版本的设备
4.  定义的**油炸圈饼**属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **使文本居中：**设备<br>
    **操作：**总和
5.  定义**列表**的属性。<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图表：**选择<br>
    **使迷你图：**未选中
6.  定义**的列标题**。<br>
    **名称：**显示名称<br>
    **值：**保留为空
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>创建平铺视图显示应用程序错误的设备

1.  从库中选择**编号与列表**，然后添加一个新图块。
2.  定义的**常规**属性。<br>
    **组标题：**保留为空<br>
    **新组：**未选中
3.  定义**平铺**属性。<br>
    **图例：**在最后一个小时出现应用程序错误的设备<br>
    **平铺查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性。<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义**的列标题**。<br>
    **名称：**显示名称<br>
    **值：**最后一个错误
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>创建平铺视图显示设备，已经重新启动

1.  从库中选择**编号与列表**，然后添加一个新图块。
2.  定义的**常规**属性。<br>
    **组标题：**保留为空<br>
    **新组：**未选中
3.  定义**平铺**属性。<br>
    **图例：**设备中的最后 24 小时和重新启动的次数位置重新启动应用程序<br>
    **平铺查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性。<br>
    **列出查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定义**的列标题**。<br>
    **名称：**显示名称<br>
    **值：**重新启动的次数
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择**应用**，然后**关闭**。
8.  选择**保存**以保存您的仪表板。

现在，您已经完成创建您的视图。

您可以使用 Microsoft 操作管理套件门户或操作管理套件为[Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r)、 [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)或[Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone)的移动客户端来访问您的视图。

## <a name="configure-alerts-in-operations-management-suite"></a>配置警报操作管理套件中的测试
<a name="Alerts"></a>当 Skype 的空间系统设备遇到问题，Microsoft 操作管理套件可引发警报，通知管理员提供此问题的详细信息。

操作管理套件包括通过定期计划的日志搜索运行内置报警机制。 如果日志搜索的结果符合某些特定条件，则创建警报记录。

![OMS 警报机制](../../media/Deploy_OMS_6.png "OMS 警报机制")

该规则可以自动运行一个或多个操作，主动通知您的警报或调用另一个过程。 操作管理套件的警报可能的选项包括：
-   发送电子邮件
-   调用外部进程通过 HTTP POST 请求
-   从 runbook 开始在 Azure 自动化服务

请参阅[了解警报日志分析中的](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)更多地了解操作管理套件中的警报。

> [!NOTE]
> 下面的示例在 Skype 的空间系统设备生成一个硬件或应用程序错误时发送电子邮件警报。 


### <a name="configure-an-email-alert-for-skype-room-systems-hardware-issues"></a>配置电子邮件警报，Skype 的空间系统硬件问题

配置通知规则，检查硬件问题必须在最后一个小时内的 Skype 的空间系统设备。
1.  登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。

2.  选择**日志搜索**。

3.  输入下面的查询，然后选择**运行**。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  执行查询后，选择**警报**。 这将打开**添加警报规则**页。

5.  使用以下信息配置警报设置：<br>
    **规则名称：**Skype 的空间系统硬件故障警报<br>
    **说明：**在最后一个小时内遇到硬件问题的设备的列表<br>
    **严重：**关键<br>
    **查询：**使用预填充的搜索查询<br>
    **时间段：** 1 小时<br>
    **通知频率：** 1 小时<br>
    **的结果数：**大于 0<br>
    **电子邮件主题：**Skype 的空间系统硬件故障警报<br>
    **的收件人：**包含用分号分隔的电子邮件地址<br>

6.  选择**保存**。

### <a name="configure-an-email-alert-for-skype-room-systems-application-issues"></a>配置电子邮件警报的 Skype 的空间系统的应用程序问题

配置的预警规则，检查应用程序的问题必须在最后一个小时内的 Skype 的空间系统设备。
1.  选择**日志搜索**。

2.  输入下面的查询，然后选择**运行**。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  执行查询后，选择**警报**。 这将打开**添加警报规则**页。

4.  使用以下信息配置警报设置：<br>
    **规则名称：**Skype 的空间系统应用程序失败警报<br>
    **说明：**在最后一个小时内遇到应用程序问题的设备的列表<br>
    **严重：**关键<br>
    **查询：**使用预填充的搜索查询<br>
    **时间段：** 1 小时<br>
    **通知频率：** 1 小时<br>
    **的结果数：**大于 0<br>
    **电子邮件主题：**Skype 的空间系统应用程序失败警报<br>
    **的收件人：**包含用分号分隔的电子邮件地址

5.  选择**保存**。

现在您已经完成定义警报。 通过使用上面的示例，您可以定义其他通知。

生成警报时，您将收到一封电子邮件，其中列出了在最后一个小时内出现问题的设备。

![示例 OMS 警报电子邮件](../../media/Deploy_OMS_7.png "示例 OMS 警报电子邮件")

使用警报设置页面可以修改现有的警报配置，或可以禁用或删除警报。

![OMS 的警报设置](../../media/Deploy_OMS_8.png "OMS 的警报设置")

> [!NOTE]
> 您可能需要使用 Azure 门户添加或修改操作管理套件的通知如果您操作管理套件的工作区配置为扩展到 Azure 的运营管理套件警报。 有关更多详细信息，请参阅[扩展到 Azure 的 OMS 门户的通知](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend)。

## <a name="configure-all-devices-for-operations-management-suite"></a>将所有设备都配置为操作管理套件
<a name="configure_all_devices"></a>在配置的面板和警报后，您可以设置和配置所有的 Skype 的空间系统设备来完成监视部署操作管理套件代理。

虽然可以安装并在每个设备上手动配置操作管理套件代理，我们极力建议您利用现有的软件部署工具和方法。

如果您正在第一次构建 Skype 的空间系统设备，可以作为生成过程的一部分进行操作管理套件代理程序安装和配置步骤。 有关详细信息，请参阅[安装的代理，使用命令行](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>通过使用组策略对象部署操作管理套件代理

如果实现操作管理套件之前，已经部署了 Skype 的空间系统设备，可以使用提供的脚本来设置和使用 Active Directory 组策略来配置代理。

1.  创建一个共享的网络路径和到**域计算机**组授予读访问权限。

2.  下载操作管理套件代理用于 Windows 中的 64 位版本<http://go.microsoft.com/fwlink/?LinkID=517476>

3.  将安装软件包的内容解压缩到网络共享。
    1.  打开一个命令提示符窗口，并执行**MMASetup AMD64.exe /c**
    2.  指定您刚创建的共享和提取内容。

4.  创建新的组策略对象并将其分配给组织单位 Skype 的空间系统的计算机帐户的位置。

5.  配置 PowerShell 执行策略：
    1.  编辑新创建的组策略对象并导航到计算机配置\\策略\\管理模板\\Windows 组件\\Windows PowerShell
    2.  启用**脚本执行打开**并设置为**允许本地脚本**的**执行策略**。

6.  将启动脚本配置为：
    1.  复制下面的脚本并将其保存为安装 OMSAgent.ps1。
    2.  修改 WorkspaceId、 WorkspaceKey 和 SetupPath 参数，以匹配您的配置。
    3.  编辑相同的组策略对象并导航到计算机配置\\策略\\Windows 设置\\脚本 （启动/关机）
    4.  双击以选择**启动**，并选择**PowerShell 脚本**。
    5.  选择**显示文件**，然后将该**安装 OMSAgent.ps1**文件复制到该文件夹。
    6.  选择**添加**，然后**浏览**。
    7.  选择您刚才复制的 ps1 脚本。

7.  Skype 的空间系统设备应安装和使用第二个重新启动配置 Microsoft 监视代理。


    ```
    # Install-OMSAgent.ps1
    <# 
    Date:        04/20/2018 
    Script:      Install-OMSAgent.ps1 
    Version:     1.0
    #> 
    
    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"
    
    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"
    
    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"
    
    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log  
    
    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'
    
    # Check if the Microsoft Monitoring agent is installed 
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }
    
    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    } 
    
    Stop-Transcript 
    
    ```
    
> [!NOTE]
> 当您需要重新配置代理程序，将其移动到另一个工作区，或在初始安装后修改代理设置时，您可以参考文章[管理和维护的日志分析代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage)。

## <a name="additional-solutions"></a>更多解决方案
<a name="Solutions"> </a>

操作管理套件提供内置的解决方案，通过其[解决方案库](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions)，以进一步帮助您监控您的环境。 我们强烈建议将[预警管理](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)和[代理健康](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth)解决方案添加到您的操作管理套件工作区。

![OMS 视图](../../media/Deploy_OMS_9.png "OMS 视图")

> [!NOTE]
> 代理运行状况解决方案可以帮助您识别过时或断开操作管理套件代理在您的环境，和警报管理解决方案提供了有关在给定时间段内已引发的警报的详细信息。

## <a name="see-also"></a>另请参阅

#### 
[规划与 OMS 的 Skype 的空间系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[管理与 OMS 的 Skype 的空间系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)