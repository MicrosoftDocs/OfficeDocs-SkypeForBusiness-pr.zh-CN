---
title: 通过 Azure 监视器部署 Microsoft 团队聊天室管理
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文介绍如何使用 Azure 监视器以集成的端到端方式部署 Microsoft 团队聊天室设备的管理。
ms.openlocfilehash: e428b54f1a91c8443000dafa3270d2283dc1d029
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268814"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>部署:::no-loc text="Microsoft Teams Rooms":::管理:::no-loc text="Azure Monitor":::

本文介绍如何通过使用:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor":::设置和部署设备的集成端到端管理。

你可以在:::no-loc text="Log Analytics":::内部:::no-loc text="Azure Monitor":::进行配置，以提供可帮助你管理:::no-loc text="Microsoft Teams Rooms":::会议室设备的基本遥测和警报。 随着管理解决方案的成熟，你可能会决定部署其他数据和管理功能来创建更详细的设备可用性和性能视图。

通过遵循本指南，你可以使用仪表板（如以下示例）获取有关设备可用性、应用程序和硬件运行状况以及:::no-loc text="Microsoft Teams Rooms":::应用程序和操作系统版本分发的详细状态报告。

![示例:::no-loc text="Log Analytics":::视图的屏幕截图:::no-loc text="Microsoft Teams Rooms":::](../media/Deploy-Azure-Monitor-1.png "示例:::no-loc text="Log Analytics":::视图:::no-loc text="Microsoft Teams Rooms":::"）

你需要在高级别执行以下任务：


1. [验证:::no-loc text="Log Analytics":::配置](azure-monitor-deploy.md#validate_LogAnalytics)
2. [配置管理设置的:::no-loc text="Log Analytics":::测试设备](azure-monitor-deploy.md#configure_test_devices)
3. [映射自定义字段](azure-monitor-deploy.md#Custom_fields)
4. [定义:::no-loc text="Microsoft Teams Rooms":::视图:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [定义警报](azure-monitor-deploy.md#Alerts)
6. [配置用于监视的所有设备](azure-monitor-deploy.md#configure_all_devices)
7. [配置其他:::no-loc text="Azure Monitor":::解决方案](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 虽然使用最少的:::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics":::配置可以监视运行:::no-loc text="Windows":::操作系统的计算机，但在开始将代理:::no-loc text="Microsoft Teams Rooms":::部署到所有:::no-loc text="Microsoft Teams Rooms":::设备之前，仍需要执行一些特定步骤。
> 因此，我们强烈建议你按照正确的顺序执行所有配置步骤，以进行受控设置和配置。 最终结果的质量非常多取决于初始配置的质量。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>验证:::no-loc text="Log Analytics":::配置
<a name="validate_LogAnalytics"> </a>

需要具有:::no-loc text="Log Analytics":::工作区才能开始从:::no-loc text="Microsoft Teams Rooms":::设备收集日志。 工作区是具有自己:::no-loc text="Log Analytics":::的数据存储库、数据源和解决方案的独特环境。 如果你已有一个现有:::no-loc text="Log Analytics":::工作区，则可以使用它监视你:::no-loc text="Microsoft Teams Rooms":::的部署，或者你可以创建特定于:::no-loc text="Log Analytics":::你:::no-loc text="Microsoft Teams Rooms":::的监视需求的专用工作区。

如果需要创建新:::no-loc text="Log Analytics":::的工作区，请按照文章在[ :::no-loc text="Log Analytics"::: :::no-loc text="Azure":::门户中创建工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)中的说明进行操作

> [!NOTE]
> 若要:::no-loc text="Log Analytics":::使用:::no-loc text="Azure Monitor":::，您需要有有效:::no-loc text="Azure":::的订阅。 如果您没有:::no-loc text="Azure":::套餐，您可以创建[一个免费试用订阅](https://azure.microsoft.com/free)作为起点。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>配置:::no-loc text="Log Analytics":::以收集:::no-loc text="Microsoft Teams Rooms":::事件日志

:::no-loc text="Log Analytics":::仅收集在 "设置:::no-loc text="Windows"::: " 中指定的事件日志中的事件。 对于每个日志，仅收集具有选定严重性的事件。

你需要配置:::no-loc text="Log Analytics":::以收集监视:::no-loc text="Microsoft Teams Rooms":::设备和应用程序状态所需的日志。 :::no-loc text="Microsoft Teams Rooms":::设备使用**:::no-loc text="Skype Room System":::** 事件日志。

若要:::no-loc text="Log Analytics":::配置以收集:::no-loc text="Microsoft Teams Rooms":::事件，请参阅[ :::no-loc text="Windows":::事件日志中的:::no-loc text="Azure Monitor"::: "数据源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)"

![事件日志设置的屏幕截图](../media/Deploy-Azure-Monitor-2.png "事件日志设置")

> [!IMPORTANT]
> 配置:::no-loc text="Windows":::事件日志设置并输入**:::no-loc text="Skype Room System":::** "事件日志名称"，然后选择 "**错误**"、"**警告**" 和 "**信息**" 复选框。

## <a name="configure-test-devices-for-azure-monitoring"></a>配置用于 Azure 监视的测试设备
<a name="configure_test_devices"> </a>

您需要准备:::no-loc text="Log Analytics":::能够监视:::no-loc text="Microsoft Teams Rooms":::相关事件。 首先，你需要将代理部署:::no-loc text="Microsoft Monitoring":::到你具有物理访问权限的:::no-loc text="Microsoft Teams Rooms":::一个或两个设备，并且让这些测试设备生成一些数据并将其推送到:::no-loc text="Log Analytics":::工作区。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>安装:::no-loc text="Microsoft Monitoring":::代理以测试设备

使用 " :::no-loc text="Microsoft Monitoring"::: [将计算机连接:::no-loc text="Windows"::: :::no-loc text="Log Analytics":::到" 服务:::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的说明将代理部署到测试设备。 :::no-loc text="Microsoft Monitoring":::本文提供有关部署代理的:::no-loc text="Windows":::步骤的详细信息、获取:::no-loc text="Log Analytics"::: ***工作区 ID***的说明和用于获取:::no-loc text="Microsoft Teams Rooms":::连接到:::no-loc text="Azure Monitor":::部署的设备的:::no-loc text="Log Analytics"::: ***主键***，以及用于验证代理连接实例的步骤。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>生成示例:::no-loc text="Microsoft Teams Rooms":::事件

将:::no-loc text="Microsoft Monitoring":::代理部署到测试设备后，验证所需的事件日志数据是否由:::no-loc text="Azure Monitor":::收集。

> [!NOTE]
> 安装:::no-loc text="Microsoft Monitoring":::代理后重新启动设备，并确保启动:::no-loc text="Microsoft Teams Rooms":::会议应用，以便它可以在事件日志中生成新事件。

1.  登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。

2.  列出:::no-loc text="Microsoft Teams Rooms":::设备生成的检测信号事件：
    1.  选择您的工作区并转到 "**日志**" 并使用查询来检索包含自定义字段的检测信号:::no-loc text="Microsoft Teams Rooms":::记录。
    2.  示例查询：`Event | where Source == "SRS-App" and EventID == 2000`

3.  请确保查询返回包含:::no-loc text="Microsoft Teams Rooms":::会议应用生成的事件的日志记录。

4.  生成硬件问题，并验证是否已登录所需的事件:::no-loc text="Azure Log Analytics":::。
    1.  拔下测试:::no-loc text="Microsoft Teams Rooms":::系统上的其中一个外围设备。 这可能是相机、话筒、麦克风或前置房间显示
    2.  等待10分钟，以便填充事件日志:::no-loc text="Azure Log Analytics":::。
    3.  使用查询列出硬件错误事件：`Event | where Source == "SRS-App" and EventID == 3001`

5.  生成应用程序问题，并验证是否已记录所需的事件。
    1.  修改:::no-loc text="Microsoft Teams Rooms":::应用程序配置，并键入不正确的会话启动协议（SIP）地址/密码对。
    2.  等待10分钟，以便填充事件日志:::no-loc text="Azure Log Analytics":::。
    3.  使用查询列出应用程序错误事件：`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 在可以配置自定义字段之前，需要这些示例事件日志。 不要继续执行下一步操作，直到收集了所需的事件日志。

## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

使用自定义域从事件日志中提取特定数据。 你需要定义稍后将用于你的磁贴、仪表板视图和通知的自定义字段。 在开始创建自定义字段之前，请参阅[中:::no-loc text="Log Analytics":::的自定义字段](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)并熟悉概念。

若要从捕获的事件日志中提取自定义域，请按照下列步骤操作：

1.  登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。

2. 列出:::no-loc text="Microsoft Teams Rooms":::设备生成的事件：
   1.  转到 "**日志**" 并使用查询检索将具有自定义字段的记录。
   2.  示例查询：`Event | where Source == "SRS-App" and EventID == 2000`

3. 选择其中一个记录，选择左侧的按钮，然后启动 "字段提取向导"。
4. 突出显示要从 RenderedDescription 中提取的数据，并提供字段标题。 表1中提供了应使用的字段名称。

   ![自定义字段定义](../media/Deploy-Azure-Monitor-4.png "自定义字段定义")

5. 使用*表 1*中所示的映射。 :::no-loc text="Log Analytics":::定义新字段时，将自动追加** \_CF**字符串。

> [!IMPORTANT]
> 请记住，所有 JSON :::no-loc text="Log Analytics":::和字段都区分大小写。
> 
> 请注意下表中每个自定义域所需的查询。 您需要使用正确的:::no-loc text="Log Analytics":::查询来成功提取自定义域值。
> 
 ![自定义字段定义](../media/Deploy-Azure-Monitor-5.png "自定义字段定义")

**表1**

| **JSON 字段**                   | **:::no-loc text="Log Analytics":::自定义域** | **事件 ID** | **要与提取一起使用的查询**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 说明                      | SRSEventDescription         | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| ResourceState                    | SRSResourceState            | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OperationName                    | SRSOperationName            | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OperationResult                  | SRSOperationResult          | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OS                               | SRSOSVersion                | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| 别名                            | SRSAlias                    | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| DisplayName                      | SRSDisplayName              | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| AppVersion                       | SRSAppVersion               | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | 源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| 会议麦克风状态     | SRSConfMicrophoneStatus     | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 会议演讲者状态        | SRSConfSpeakerStatus        | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 默认扬声器状态           | SRSDefaultSpeakerStatus     | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 相机状态                    | SRSCameraStatus             | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 房间前显示状态     | SRSFORDStatus               | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 运动传感器状态             | SRSMotionSensorStatus       | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| HDMI 接收状态               | SRSHDMIIngestStatus         | **3001**     | 源\| = = "SRS-App" 和 EventID = = 3001 的事件 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>定义:::no-loc text="Microsoft Teams Rooms":::视图:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

收集数据并映射自定义字段后，可以使用 "视图设计器" 开发一个仪表板，其中包含用于:::no-loc text="Microsoft Teams Rooms":::监视事件的各种磁贴。 使用 "视图设计器" 创建以下图块。 有关详细信息，请参阅[使用视图设计器:::no-loc text="Log Analytics":::创建自定义视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 应完成本指南前面的步骤，仪表板图块才能正常工作。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>使用 import 方法创建 Microsoft 团队聊天室仪表板

您可以导入:::no-loc text="Microsoft Teams Rooms":::仪表板并快速开始监视设备。 执行以下步骤导入仪表板：

1.  获取[SkypeRoomSystems_v2 的 omsview](https://go.microsoft.com/fwlink/?linkid=835675)仪表板文件。
2.  登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。
3.  打开**视图设计器**。
4.  选择 "**导入**"，然后选择 " **SkypeRoomSystems_v2 的 omsview**文件。
5.  选择 "**保存**"。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手动创建 Microsoft 团队聊天室仪表板

或者，你可以创建自己的仪表板并仅添加你希望监视的磁贴。

#### <a name="configure-the-overview-tile"></a>配置概述图块

1.  打开**视图设计器**。
2.  选择 "**概述图块**"，然后从库中选择**两个数字**。
3.  命名磁贴**:::no-loc text="Microsoft Teams Rooms":::**。
4.  定义**第一个图块**：<br>
    **图例：** 在上个月内至少发送过一次检测信号的设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定义**第二个图块**：<br>
    **图例：** 在过去一小时内发送检测信号的活动设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  选择 "**应用**"。

### <a name="create-a-tile-that-displays-active-devices"></a>创建显示活动设备的磁贴

1.  选择 "**查看仪表板**" 以开始添加磁贴。
2.  从库中选择 "**编号" & 列表**
3.  定义**常规**属性：<br>
    **组标题：** 检测信号状态<br>
    **新组：** 处于
4.  定义**图块**属性：<br>
    **图例：** 活动设备（最近20分钟内发送的检测信号）<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定义**列表**属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定义**列标题**：<br>
    **名称：** 计算机名<br>
    **值：** 上次检测信号
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 "**应用**"，然后单击 "**关闭**"。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>创建显示有连接问题的设备的磁贴

1.  从库中选择 "**编号" & 列表**，然后添加新磁贴。
2.  定义**常规**属性：<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义**图块**属性：<br>
    **图例：** 非活动设备（最近20分钟内未发送检测信号消息）<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定义**列表**属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定义**列标题**：<br>
    **名称：** 计算机名<br>
    **值：** 上次检测信号
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 "**应用**"，然后单击 "**关闭**"。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>创建显示硬件出现错误的设备的磁贴

1.  从库中选择 "**编号" & 列表**，然后添加新磁贴。
2.  定义**常规**属性：<br>
    **组标题：** 硬件状态<br>
    **新组：** 处于
3.  定义**图块**属性：<br>
    **图例：** 过去一小时内遇到硬件错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义**列标题**：<br>
    **名称：** 计算机名<br>
    **值：** 上一个错误
6.  定义**导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 "**应用**"，然后单击 "**关闭**"。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>创建显示:::no-loc text="Microsoft Teams Rooms":::操作系统版本的磁贴

1.  从库中选择 "**同心圆 & 列表**"，然后添加新磁贴。
2.  定义**常规**属性：<br>
    **组标题：** 操作系统详细信息<br>
    **新组：** 处于
3.  定义**页眉**属性：<br>
    **标题：** 操作系统版本<br>
    **副标题：** 运行特定操作系统版本的设备
4.  定义**同心圆**属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **文本居中：** 台<br>
    **操作：** 量
5.  定义**列表**属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 处于<br>
    **启用迷你图：** 未选中
6.  定义**列标题**。<br>
    **名称：** 计算机名<br>
    **值：** 留空
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 "**应用**"，然后选择 "**关闭**"。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>创建显示:::no-loc text="Microsoft Teams Rooms":::应用程序版本的磁贴

1.  从库中选择 "**同心圆 & 列表**"，然后添加新磁贴。
2.  定义**常规**属性：<br>
    **组标题：** :::no-loc text="Microsoft Teams Rooms":::应用程序详细信息<br>
    **新组：** 处于
3.  定义**页眉**属性：<br>
    **标题：** 应用程序版本<br>
    **副标题：** 运行特定应用程序版本的设备
4.  定义**同心圆**属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **文本居中：** 台<br>
    **操作：** 量
5.  定义**列表**属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 处于<br>
    **启用迷你图：** 未选中
6.  定义**列标题**。<br>
    **名称：** 计算机名<br>
    **值：** 留空
7.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 "**应用**"，然后选择 "**关闭**"。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>创建显示有应用程序错误的设备的磁贴

1.  从库中选择 "**编号" & 列表**，然后添加新磁贴。
2.  定义**常规**属性。<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义**图块**属性。<br>
    **图例：** 过去一小时遇到应用程序错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义**列标题**。<br>
    **名称：** 计算机名<br>
    **值：** 上一个错误
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 "**应用**"，然后选择 "**关闭**"。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>创建显示已重新启动的设备的磁贴

1.  从库中选择 "**编号" & 列表**，然后添加新磁贴。
2.  定义**常规**属性。<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义**图块**属性。<br>
    **图例：** 在过去24小时内重新启动应用程序的设备以及重启次数<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定义**列表**属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定义**列标题**。<br>
    **名称：** 计算机名<br>
    **值：** 重启次数
6.  定义**导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 "**应用**"，然后选择 "**关闭**"。
8.  选择 "**保存**" 以保存仪表板。

现在，你已完成创建视图。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>在中配置警报:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::当:::no-loc text="Microsoft Teams Rooms":::控制台遇到问题时，可以引发通知以通知管理员。

:::no-loc text="Azure Monitor":::包括一种内置的警报机制，可按固定时间间隔通过计划的日志搜索进行运行。 如果日志搜索的结果符合某些特定条件，则会创建一条警告记录。

然后，该规则可以自动运行一个或多个操作，主动通知你警报或调用另一个进程。 警报的可能选项如下：
-   发送电子邮件
-   通过 HTTP POST 请求调用外部进程
-   在服务中:::no-loc text="Azure Automation":::启动 runbook

有关中:::no-loc text="Azure Monitor":::的警报的详细信息，请参阅[在中:::no-loc text="Azure Monitor":::记录警报](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)。

> [!NOTE]
> 以下示例将在:::no-loc text="Microsoft Teams Rooms":::设备生成硬件或应用程序错误时发送电子邮件警报。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>配置针对硬件问题的:::no-loc text="Microsoft Teams Rooms":::电子邮件警报

配置检查在过去一小时内:::no-loc text="Microsoft Teams Rooms":::遇到硬件问题的设备的警报规则。
1.  登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。

2. 导航到您:::no-loc text="Log Analytics":::的工作区并选择 "**通知**"，然后选择 "**新建通知规则**"

3. 选择 "**添加条件**"，然后选择 "**自定义日志搜索**"

4.  在 "搜索查询" 文本框中输入以下查询。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  配置警报逻辑设置：<br>
    **基于：** 结果数<br>
    **条件：** 大于<br>
    **Treshold：** 0<br>

6. 配置评估设置，然后选择 "**完成**"： <br>
    **周期（分钟）：** 60<br>
    **频率（分钟）：** 60<br>

7. 配置操作组：
    1.  选择 "**新建**"
    2.  为 "*操作组名称*" 和 "*短名称*" 字段提供合适的名称。
    3.  指定唯一的*操作名称*，选择 "**电子邮件/短信/短信/推/语音**"，然后选择 "**编辑详细信息**"。
    4.  选择 "电子邮件" 复选框，并提供将接收通知的人员或组的电子邮件地址。
    5.  您还可以提供您的电话号码以接收短信通知、语音通话或同时获得这两者。
    6. 选择 **"确定"**。

8. 如果想要替代预警电子邮件的主题行，请**自定义操作**。

9. 指定规则名称和说明。<br>
    **规则名称：** :::no-loc text="Microsoft Teams Rooms":::硬件故障警报<br>
    **说明：** 过去一小时内遇到硬件问题的设备的列表<br>

10. 选择预期的严重性，并确保规则已启用。

11. 选择 "**创建通知规则**"。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>为:::no-loc text="Microsoft Teams Rooms":::应用程序问题配置电子邮件警报

重复相同的过程，但使用以下查询列出过去一小时内遇到的应用程序问题的设备。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

现在，你已完成定义通知。 你可以使用上述示例定义其他警报。

生成警报时，你将收到一封电子邮件，其中列出了在过去一小时内遇到问题的设备。

![通知:::no-loc text="Azure Monitor":::电子邮件示例](../media/Deploy-Azure-Monitor-6.png "通知:::no-loc text="Azure Monitor":::电子邮件示例"）

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>配置所有设备:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a>配置仪表板和警报后，您可以在所有:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms":::设备上设置和配置代理以完成监视部署。

虽然你可以在每台设备:::no-loc text="Microsoft Monitoring":::上手动安装和配置代理，但我们强烈建议你充分利用现有软件部署工具和方法。

如果你是首次:::no-loc text="Microsoft Teams Rooms":::生成设备，你可能希望将:::no-loc text="Microsoft Monitoring":::代理设置和配置步骤包含在你的生成过程中。 有关详细信息，请参阅[使用命令行安装代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>使用:::no-loc text="Microsoft Monitoring":::组策略对象（GPO）部署代理

如果在实现:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::之前已部署了设备，则可以使用提供的脚本通过 " :::no-loc text="Active Directory":::组策略" 对象设置和配置代理。

1.  创建共享网络路径并向 "**域计算机**" 组授予 "读取" 访问权限。

2.  从下载64位版本的:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  将安装程序包的内容提取到网络共享中。
    1.  打开命令提示符窗口，然后执行**MMASetup-AMD64/c**
    2.  指定刚刚创建的共享，然后提取内容。

4.  创建新的组策略对象，并将其分配给:::no-loc text="Microsoft Teams Rooms":::计算机帐户所在的组织单位。

5.  配置 PowerShell 执行策略：
    1.  编辑新创建的组策略对象，并导航到 " \\计算机\\配置策略\\ :::no-loc text="Windows"::: " \\管理模板组件:::no-loc text="Windows PowerShell":::
    2.  启用 "**打开脚本执行**" 和 "设置**执行策略**" 以**允许本地脚本**。

6.  配置启动脚本：
    1.  复制以下脚本并将其另存为 Install-MMAgent。
    2.  修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数以匹配您的配置。
    3.  编辑相同的组策略对象并导航到 "计算机\\配置\\ :::no-loc text="Windows":::策略\\ " 设置脚本（启动/关闭）
    4.  双击以选择 "**启动**"，然后选择 " **PowerShell 脚本**"。
    5.  选择 "**显示文件**"，然后将**Install-MMAgent**文件复制到该文件夹。
    6.  选择 "**添加**"，然后单击 "**浏览**"。
    7.  选择您刚刚复制的 ps1 脚本。

7.  :::no-loc text="Microsoft Teams Rooms":::设备应在第二次:::no-loc text="Microsoft Monitoring":::重启时安装和配置代理。

```PowerShell
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
> 如果需要重新配置代理、将代理移到其他工作区或在初始安装后修改代理服务器设置，可以参阅[管理和维护:::no-loc text="Log Analytics":::代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)的文章。

## <a name="additional-solutions"></a>其他解决方案
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::通过其[解决方案库](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)提供内置管理解决方案，进一步帮助你监视你的环境。 我们强烈建议你将[警报管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[ :::no-loc text="Azure Log Analytics":::代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到你的工作区。

> [!NOTE]
> 代理运行状况解决方案可帮助你在你的环境:::no-loc text="Microsoft Monitoring":::内识别过时或损坏的代理，并且警报管理解决方案提供有关在给定期间内引发的警报的详细信息。

## <a name="see-also"></a>另请参阅

[计划:::no-loc text="Microsoft Teams Rooms":::管理与:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[管理:::no-loc text="Microsoft Teams Rooms":::设备:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
