---
title: 部署 Microsoft 团队聊天室管理使用 Azure 监视器
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何部署 Microsoft 团队聊天室设备的管理方式集成的端到端使用 Azure 监视器。
ms.openlocfilehash: 599cbb7abce2b20dac27ffebacb041062a254905
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013107"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>部署 Microsoft 团队聊天室管理使用 Azure 监视器

本文讨论如何设置和部署的 Microsoft 团队聊天室设备集成的端到端管理使用 Azure 监视器。

您可以配置内 Azure 监视器提供基本遥测日志分析和通知将帮助您管理会议室内设备的 Microsoft 团队聊天室。 随着您管理解决方案逐渐成熟，您可能决定部署其他数据和管理功能，以创建设备的可用性和性能的详细的视图。

按照本指南，您可以使用类似下面的示例仪表板获取设备可用性、 应用程序和硬件运行状况和 Microsoft 团队聊天室应用程序和操作系统版本分发报告的详细的状态。

![示例日志分析视图的 Microsoft 团队会议室](../../media/Deploy-Azure-Monitor-1.png "示例日志分析视图的 Microsoft 团队会议室")

你需要在高级别执行以下任务：


1.  [验证日志分析配置](azure-monitor.md#validate_LogAnalytics)
2.  [配置日志分析管理安装程序测试设备](azure-monitor.md#configure_test_devices)
3.  [映射自定义字段](azure-monitor.md#Custom_fields)
4.  [日志分析中定义的 Microsoft 团队聊天室视图](azure-monitor.md#Define_Views)
5.  [定义通知](azure-monitor.md#Alerts)
6.  [将所有设备都配置为监控](azure-monitor.md#configure_all_devices)
7.  [配置其他 Azure 监视解决方案](azure-monitor.md#Solutions)

> [!IMPORTANT]
> 使用最少的配置，Azure 监视器日志分析可以监视运行 Windows 操作系统的计算机，但仍有需要在开始部署到所有 Microsoft 团队的代理之前执行一些 Microsoft 团队聊天室特定步骤聊天室设备。
> 因此，我们强烈建议您受控的安装和配置正确的顺序执行所有配置步骤。 最终结果的质量很大程度取决于的初始配置的质量。

## <a name="validate-log-analytics-configuration"></a>验证日志分析配置
<a name="validate_LogAnalytics"> </a>

您需要具有要开始从 Microsoft 团队聊天室设备收集日志的日志分析工作区。 工作区是使用其自己的数据存储库、 数据源和解决方案的唯一日志分析环境。 如果您已有现有日志分析工作区，您可能使用它来监视您的 Microsoft 团队聊天室部署或或者，您可以创建专用的日志分析工作区特定监控需要您 Microsoft 团队 room。

如果您需要创建新的日志分析工作区，请按照[创建 Azure 门户中的日志分析工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)一文中的说明

> [!NOTE]
> 若要使用日志分析与 Azure 监视器，您需要具有活动的 Azure 订阅。 如果您没有 Azure 订阅，您可以创建[免费的试用订阅](https://azure.microsoft.com/free)作为起点。

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>配置日志分析收集 Microsoft 团队聊天室事件日志

日志分析仅收集在设置中指定的 Windows 事件日志中的事件。 为每个日志中，会收集仅将所选的严重级别的事件。

您需要配置日志分析收集监视 Microsoft 团队聊天室设备和应用程序状态所需的日志。 Microsoft 团队聊天室设备使用**Skype 会议室系统**事件日志。

配置日志分析收集的 Microsoft 团队聊天室事件，请参阅[在 Azure 监视器中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![事件日志设置](../../media/Deploy-Azure-Monitor-2.png "事件日志设置")

> [!IMPORTANT]
> 配置 Windows 事件日志设置并输入**Skype 会议室系统**作为事件日志名称，然后选中的**错误**、**警告**和**信息**复选框。

## <a name="configure-test-devices-for-azure-monitoring"></a>为 Azure 监控配置测试设备
<a name="configure_test_devices"> </a>

您需要准备日志分析能够监视 – 与 Microsoft 团队聊天室相关的事件。 启动时，您需要将 Microsoft 监控代理部署到只是一个或两个 Microsoft 团队聊天室设备必须物理访问，并实现这些测试设备生成一些数据，并将其推送到日志分析工作区。

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>安装 Microsoft 监控代理到测试设备

使用[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的说明，将 Microsoft 监控代理部署到测试设备上。 本文提供有关部署监控代理的 Windows 的步骤的详细的信息，获取日志分析***工作区 ID***和***主关键字***的说明，以获取 Microsoft 团队聊天室设备连接到您的 Azure 监视部署和步骤验证代理连接到日志分析实例。

### <a name="generate-sample-microsoft-teams-rooms-events"></a>生成示例 Microsoft 团队聊天室事件

Microsoft 监控代理部署到测试设备后，验证 Azure 监视器，收集所需的事件日志数据。

> [!NOTE]
> Microsoft 监控代理，在安装后重新启动设备，并确保已启动的 Microsoft 团队聊天室会议应用程序，以便它可以到事件日志中生成的新事件。

1.  登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。

2.  列出检测信号事件生成的 Microsoft 团队聊天室设备：
    1.  选择您的工作区并转到**日志**查询用于检索的自定义域会为 Microsoft 团队房间检测信号记录。
    2.  示例查询：`Event | where Source == "SRS-App" and EventID == 2000`

3.  确保查询返回包含由 Microsoft 团队会议室的会议应用程序生成的事件的日志记录。

4.  生成硬件问题，并验证 Azure 日志分析中的记录所需的事件。
    1.  拔下测试 Microsoft 团队聊天室系统上的外围设备之一。 这可能是照相机、 免提电话、 麦克风或前端聊天室显示
    2.  等待事件日志中 Azure 日志分析填充 10 分钟。
    3.  使用列表硬件错误事件查询：`Event | where Source == "SRS-App" and EventID == 3001`

5.  生成应用程序问题，并验证的记录所需的事件。
    1.  修改 Microsoft 团队聊天室应用程序配置，并键入正确的会话初始协议 (SIP) 地址中的密码对。
    2.  等待事件日志中 Azure 日志分析填充 10 分钟。
    3.  使用查询的列表应用程序错误事件：`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 这些示例事件日志是必需的然后才能配置自定义字段。 不继续下一步，直到您已收集所需的事件日志。

## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

使用自定义域从事件日志中提取特定的数据。 您需要定义将与您的图块数为单位、 仪表板视图和通知更高版本使用的自定义字段。 请参阅[日志分析中的自定义域](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)和熟悉概念开始创建自定义域之前。

提取自定义域超出捕获的事件日志，请按照下列步骤：

1.  登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。

2. 列出由 Microsoft 团队聊天室设备生成的事件：
   1.  转到**日志**并使用查询来检索将具有自定义字段的记录。
   2.  示例查询：`Event | where Source == "SRS-App" and EventID == 2000`

3. 选择记录之一，选择向左，按钮并启动字段提取向导。
4. 突出显示您希望从 RenderedDescription 提取并提供字段标题的数据。 表 1 中提供了应使用的字段名称。

   ![自定义字段定义](../../media/Deploy-Azure-Monitor-4.png "自定义字段定义")

5. 使用*表 1*中显示的映射。 将自动追加日志分析**\_CF**时定义的新字段的字符串。

> [!IMPORTANT]
> 请记住 JSON 和日志分析的所有字段，都都区分大小写。
> 
> 请注意下表列出了每个自定义字段所需的查询。 您需要使用日志分析的正确的查询成功提取自定义字段值。
> 
 ![自定义字段定义](../../media/Deploy-Azure-Monitor-5.png "自定义字段定义")

**表 1**

| **JSON 字段**                   | **日志分析自定义字段** | **事件 ID** | **用于提取的查询**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 说明                      | SRSEventDescription         | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| ResourceState                    | SRSResourceState            | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| OperationName                    | SRSOperationName            | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| OperationResult                  | SRSOperationResult          | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| OS                               | SRSOSVersion                | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| 别名                            | SRSAlias                    | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| DisplayName                      | SRSDisplayName              | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| AppVersion                       | SRSAppVersion               | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年 |
| 会议麦克风状态     | SRSConfMicrophoneStatus     | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| 会议扬声器状态        | SRSConfSpeakerStatus        | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| 默认扬声器状态           | SRSDefaultSpeakerStatus     | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| 摄像机状态                    | SRSCameraStatus             | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| 前面的聊天室显示状态     | SRSFORDStatus               | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| 运动传感器状态             | SRSMotionSensorStatus       | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |
| HDMI 引入状态               | SRSHDMIIngestStatus         | **3001**     | 事件\|其中源 = ="SR 应用程序"和 EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>日志分析中定义的 Microsoft 团队聊天室视图
<a name="Define_Views"> </a>

收集数据并自定义字段映射后，您可以使用视图设计器开发包含各种平铺监视 Microsoft 团队聊天室事件仪表板。 使用视图设计器创建下面的图块数为单位。 有关详细信息，请参阅[创建使用日志分析中的视图设计器的自定义视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 应可以正常运行仪表板图块完成本指南中的上一步骤。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>使用的导入方法创建的 Microsoft 团队聊天室仪表板

可以导入的 Microsoft 团队聊天室仪表板并开始快速监视您的设备。 执行以下步骤以导入仪表板：

1.  获取[SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)仪表板文件。
2.  登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。
3.  打开**视图设计器**。
4.  选择**导入**，，然后选择**SkypeRoomSystems_v2.omsview**文件。
5.  选择**保存**。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手动创建 Microsoft 团队聊天室仪表板

此外，您可以创建自己的仪表板并添加您想要监视的图块。

#### <a name="configure-the-overview-tile"></a>配置概述图块

1.  打开**视图设计器**。
2.  选择**概述图块**，并从库选择**两个数字**。
3.  名称平铺**Microsoft 团队聊天室**。
4.  定义**第一个图块**：<br>
    **图例：** 至少执行一次在上个月内发送检测信号的设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定义**第二个图块**：<br>
    **图例：** 发送检测信号的最后一个小时内的活动设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  选择**应用**。

### <a name="create-a-tile-that-displays-active-devices"></a>创建活动设备将显示一个图块

1.  选择**视图仪表板**开始添加您的图块数为单位。
2.  从库中选择**数字 & 列表**
3.  定义**常规**属性：<br>
    **组标题：** 检测信号状态<br>
    **新组：** 选择
4.  定义**平铺**属性：<br>
    **图例：** 活动设备 （检测信号发送前 20 分钟内）<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定义**列表**的属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定义**列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 最后一个检测信号
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>创建具有连接问题的设备将显示一个图块

1.  从库中，选择**号码 & 列表**，然后添加新的平铺。
2.  定义**常规**属性：<br>
    **组标题：** 将保留为空<br>
    **新组：** 未选定
3.  定义**平铺**属性：<br>
    **图例：** 非活动设备 （发送前 20 分钟内无检测信号消息）<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定义**列表**的属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定义**列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 最后一个检测信号
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>创建具有硬件错误的设备将显示一个图块

1.  从库中，选择**号码 & 列表**，然后添加新的平铺。
2.  定义**常规**属性：<br>
    **组标题：** 硬件状态<br>
    **新组：** 选择
3.  定义**平铺**属性：<br>
    **图例：** 最后一个小时内遇到硬件错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义**列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 最后一个错误
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>创建显示 Microsoft 团队聊天室操作系统版本拼贴

1.  从库中选择**圆环 & 列表**，然后添加新的平铺。
2.  定义**常规**属性：<br>
    **组标题：** 操作系统详细信息<br>
    **新组：** 选择
3.  定义**标头**属性：<br>
    **标题：** 操作系统版本<br>
    **副标题：** 运行特定操作系统版本的设备
4.  定义**圆环**属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **使文本居中：** 设备<br>
    **操作：** Sum
5.  定义**列表**的属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图：** 选择<br>
    **启用迷你图：** 未选定
6.  定义**列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 将保留为空
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>创建显示 Microsoft 团队聊天室应用程序版本拼贴

1.  从库中选择**圆环 & 列表**，然后添加新的平铺。
2.  定义**常规**属性：<br>
    **组标题：** Microsoft 团队聊天室应用程序详细信息<br>
    **新组：** 选择
3.  定义**标头**属性：<br>
    **标题：** 应用程序版本<br>
    **副标题：** 设备运行特定应用程序版本
4.  定义**圆环**属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **使文本居中：** 设备<br>
    **操作：** Sum
5.  定义**列表**的属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图：** 选择<br>
    **启用迷你图：** 未选定
6.  定义**列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 将保留为空
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>创建具有应用程序错误的设备将显示一个图块

1.  从库中，选择**号码 & 列表**，然后添加新的平铺。
2.  定义**常规**属性。<br>
    **组标题：** 将保留为空<br>
    **新组：** 未选定
3.  定义**平铺**属性。<br>
    **图例：** 设备所遇最后一个小时内的应用程序错误<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义**列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 最后一个错误
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择**应用**，然后**关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>创建显示已重新启动设备拼贴

1.  从库中，选择**号码 & 列表**，然后添加新的平铺。
2.  定义**常规**属性。<br>
    **组标题：** 将保留为空<br>
    **新组：** 未选定
3.  定义**平铺**属性。<br>
    **图例：** 其中已重新启动应用程序中的最后一个 24 小时和重新启动次数的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**的属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定义**列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 重新启动次数
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择**应用**，然后**关闭**。
8.  选择**保存**以保存您的仪表板。

现在您已完成创建您的视图。

## <a name="configure-alerts-in-azure-monitor"></a>在 Azure 监视器中配置警报
<a name="Alerts"> </a>

Azure 监视器可引发警报的 Microsoft 团队聊天室控制台遇到问题时通知管理员。

Azure 监视器包括通过计划的日志搜索定期运行的内置警报机制。 如果日志搜索的结果与某个特定条件匹配，则创建警报的记录。

规则可以自动运行主动通知您通知或调用其他进程的一个或多个操作。 通知可能的选项包括：
-   发送电子邮件
-   调用外部进程通过 HTTP POST 请求
-   Azure 自动化服务中启动 runbook

请参阅[日志 Azure 监视器中的通知](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)以详细了解如何在 Azure 监视器的警报。

> [!NOTE]
> Microsoft 团队聊天室设备生成硬件或应用程序错误时，以下示例将发送电子邮件通知。

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>配置电子邮件通知 Microsoft 团队聊天室硬件问题

配置通知的规则，检查 Microsoft 团队聊天室设备的最后一个小时内已遇到硬件问题。
1.  登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。

2. 导航到您的日志分析工作区并选中**通知**，然后选择**新的通知规则**

3. 选择**添加条件**和**自定义日志搜索**

4.  搜索查询文本框中输入以下查询。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  配置通知的逻辑设置：<br>
    **基于：** 结果数<br>
    **条件：** 更高版本然后<br>
    **Treshold:** 0<br>

6. 配置评估设置并选择**完成**: <br>
    **时间段 （以分钟为单位）：** 60<br>
    **频率 （以分钟为单位）：** 60<br>

7. 配置操作组：
    1.  选择**创建新**
    2.  提供适当的*操作组名*和*短名称*字段的名称。
    3.  指定一个唯一的*操作名称*并选择**电子邮件/SMS/推送/语音**，然后选择**编辑详细信息**。
    4.  选择电子邮件复选框并提供个人或组将接收通知的电子邮件地址。
    5.  您还可以提供您的电话号码，以获得通知使用 SMS，和 / 或语音呼叫。
    6. 选择**确定**。

8. **自定义操作**如果您要重写通知电子邮件的主题行。

9. 指定规则名称和说明。<br>
    **规则名称：** Microsoft 团队聊天室硬件故障警报<br>
    **说明：** 遇到硬件问题的最后一个小时内的设备的列表<br>

10. 选择的预期的严重性并确保启用规则。

11. 选择**创建通知规则**。

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>配置电子邮件通知 Microsoft 团队聊天室应用程序问题

重复同一过程，但使用应用程序问题遇到的最后一个小时内的列表设备将以下查询。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

现在您已完成定义通知。 您可以使用上面的示例定义其他通知。

生成警报时，您将获取电子邮件，其中列出遇到问题的最后一个小时内的设备。

![示例 Azure 监视器通知电子邮件](../../media/Deploy-Azure-Monitor-6.png "示例 Azure 监视器通知电子邮件")

## <a name="configure-all-devices-for-azure-monitoring"></a>为 Azure 监控配置的所有设备
<a name="configure_all_devices"></a>配置仪表板和通知后，您可以设置和配置 Microsoft 监控代理以完成监控部署的所有 Microsoft 团队聊天室设备上。

尽管您可以安装，并在每个设备上手动配置 Microsoft 监控代理，但强烈建议您利用现有软件部署工具和方法。

如果您正在构建的第一次的 Microsoft 团队聊天室设备，您可能想要包括 Microsoft 监控代理安装和配置步骤生成过程的一部分。 有关详细信息，请参阅[安装使用命令行的代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>使用组策略对象 (GPO) 部署 Microsoft 监控代理

如果您已经部署 Microsoft 团队聊天室设备实现 Azure 监控之前，您可以使用提供的脚本设置和使用 Active Directory 组策略对象配置代理。

1.  创建共享的网络路径，并向**域计算机**组授予读取访问权限。

2.  下载 Microsoft 监控代理用于 Windows 的从 64 位版本<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  安装程序包的内容解压到网络共享。
    1.  打开命令提示符窗口，并执行**MMASetup AMD64.exe /c**
    2.  指定您刚创建的共享和提取内容。

4.  创建新的组策略对象，并将其分配给 Microsoft 团队聊天室计算机帐户的位置的组织单位。

5.  配置 PowerShell 执行策略：
    1.  编辑新创建的组策略对象，并导航到计算机配置\\策略\\管理模板\\Windows 组件\\Windows PowerShell
    2.  启用**脚本执行打开**并**允许本地**脚本设置**执行策略**。

6.  配置启动脚本：
    1.  复制以下脚本并将其保存为安装 MMAgent.ps1。
    2.  修改 WorkspaceId、 WorkspaceKey 和 SetupPath 参数，以匹配您的配置。
    3.  编辑相同的组策略对象，并导航到计算机配置\\策略\\Windows 设置\\脚本 （启动/关机）
    4.  双击可选择**启动**中，，然后选择**PowerShell 脚本**。
    5.  选择**显示文件**，然后将**安装 MMAgent.ps1**文件复制到该文件夹。
    6.  选择**添加**，然后**浏览**。
    7.  选择您刚复制的 ps1 脚本。

7.  Microsoft 团队聊天室设备应安装和配置第二个重新启动 Microsoft 监控代理。

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> 当您需要重新配置代理、 将其移至不同的工作区中，或在初始安装后修改代理设置时，您可以参考文章[管理和维护日志分析代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)。

## <a name="additional-solutions"></a>其他解决方案
<a name="Solutions"> </a>

Azure 监视器提供通过其[解决方案库](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)来进一步帮助监视您的环境的内置管理解决方案。 我们强烈建议将[警报管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[Azure 日志分析代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到您的工作区。

> [!NOTE]
> 代理运行状况解决方案可帮助您确定您的环境中已过时或断开 Microsoft 监控代理和警报管理解决方案提供了有关已引发的给定期间内的警报的详细信息。

## <a name="see-also"></a>另请参阅

[规划 Microsoft 团队聊天室管理使用 Azure 监视器](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[管理使用 Azure 监视器的 Microsoft 团队聊天室设备](../../manage/skype-room-systems-v2/azure-monitor.md)