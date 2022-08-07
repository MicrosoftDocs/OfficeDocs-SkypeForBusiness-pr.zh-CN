---
title: 使用 Azure Monitor 部署Microsoft Teams 会议室监视
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何使用 Azure Monitor 以集成的端到端方式部署对Microsoft Teams 会议室的监视。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b6d1931b0a1818b5146f6ac0e02c225fea3af52
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267447"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>使用 a0/a0 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::

本文讨论如何使用:::no-loc text="Azure Monitor":::设备设置和部署集成的端到端监视:::no-loc text="Microsoft Teams Rooms":::。

你可以在内部:::no-loc text="Azure Monitor":::进行:::no-loc text="Log Analytics":::配置，以提供可帮助你管理:::no-loc text="Microsoft Teams Rooms":::的基本遥测和警报。 随着管理解决方案的成熟，你可能会决定部署其他数据和管理功能，以创建更详细的设备可用性和性能视图。

按照本指南，可以使用类似于以下示例的仪表板获取有关设备可用性、应用程序和硬件运行状况以及 :::no-loc text="Microsoft Teams Rooms"::: 应用程序和操作系统版本分发的详细状态报告。

![Microsoft Teams 会议室的示例 Log Analytics 视图的屏幕截图。](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 会议室的示例 Log Analytics 视图")

你需要在高级别执行以下任务：


1. [验证 :::no-loc text="Log Analytics"::: 配置](azure-monitor-deploy.md#validate_LogAnalytics)
2. [为管理设置配置测试设备:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#configure_test_devices)
3. [映射自定义字段](azure-monitor-deploy.md#Custom_fields)
4. [在其中 :::no-loc text="Microsoft Teams Rooms"::: 定义视图 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [定义警报](azure-monitor-deploy.md#Alerts)
6. [配置所有设备以进行监视](azure-monitor-deploy.md#configure_all_devices)
7. [配置其他 :::no-loc text="Azure Monitor"::: 解决方案](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 尽管在配置最少的情况下， :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics":::可以监视运行:::no-loc text="Windows":::操作系统的计算机，但是在开始将代理部署到所有:::no-loc text="Microsoft Teams Rooms":::设备之前，还需要执行一些:::no-loc text="Microsoft Teams Rooms":::特定于特定的步骤。
> 因此，我们强烈建议你按正确的顺序为受控设置和配置执行所有配置步骤。 最终结果的质量在很大程度上取决于初始配置的质量。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>验证 :::no-loc text="Log Analytics"::: 配置
<a name="validate_LogAnalytics"> </a>

你需要有一个 :::no-loc text="Log Analytics"::: 工作区来开始从 :::no-loc text="Microsoft Teams Rooms":::中收集日志。 工作区是一个独特的 :::no-loc text="Log Analytics"::: 环境，具有自己的数据存储库、数据源和解决方案。 如果已有一个:::no-loc text="Log Analytics":::工作区，则可以使用它来监视:::no-loc text="Microsoft Teams Rooms":::部署，也可以创建特定于监视需求的:::no-loc text="Microsoft Teams Rooms":::专用:::no-loc text="Log Analytics":::工作区。

如果需要创建新:::no-loc text="Log Analytics":::工作区，请按照[门户中“创建工作区”一:::no-loc text="Log Analytics":::文中的:::no-loc text="Azure":::](/azure/azure-monitor/learn/quick-create-workspace)说明操作

> [!NOTE]
> 若要与之配合:::no-loc text="Azure Monitor":::使用:::no-loc text="Log Analytics":::，需要有一个活动:::no-loc text="Azure":::订阅。 :::no-loc text="Azure":::如果没有订阅，可以创建[免费试用版订阅](https://azure.microsoft.com/free)作为起点。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>配置 :::no-loc text="Log Analytics"::: 以收集 :::no-loc text="Microsoft Teams Rooms"::: 事件日志

:::no-loc text="Log Analytics"::: 仅从 :::no-loc text="Windows"::: 设置中指定的事件日志中收集事件。 对于每个日志，仅收集具有所选分级的事件。

需要配置 :::no-loc text="Log Analytics"::: 以收集监视 :::no-loc text="Microsoft Teams Rooms"::: 设备和应用程序状态所需的日志。 :::no-loc text="Microsoft Teams Rooms":::**:::no-loc text="Skype Room System":::** 使用事件日志。

若要配置 :::no-loc text="Log Analytics"::: 以收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，请参阅 [:::no-loc text="Windows"::: 事件日志数据源 :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![事件日志设置的屏幕截图。](../media/Deploy-Azure-Monitor-2.png "事件日志设置")

> [!IMPORTANT]
> 配置 :::no-loc text="Windows"::: 事件日志设置并输入 **:::no-loc text="Skype Room System":::** 为事件日志名称，然后选中 **“错误**”、“ **警告**”和 **“信息”** 复选框。

## <a name="configure-test-devices-for-azure-monitoring"></a>为 Azure 监视配置测试设备
<a name="configure_test_devices"> </a>

需要做好准备 :::no-loc text="Log Analytics"::: 才能监视 :::no-loc text="Microsoft Teams Rooms":::与事件相关的事件。 首先，需要将代理部署 :::no-loc text="Microsoft Monitoring"::: 到一个或两 :::no-loc text="Microsoft Teams Rooms"::: 个具有物理访问权限的设备，并获取这些测试设备以生成一些数据并将其推送到 :::no-loc text="Log Analytics"::: 工作区。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>安装 :::no-loc text="Microsoft Monitoring"::: 代理以测试设备

:::no-loc text="Microsoft Monitoring":::使用[连接:::no-loc text="Windows":::计算机中提供的说明将代理部署到:::no-loc text="Log Analytics"::::::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows)测试设备。 本文提供有关部署 :::no-loc text="Microsoft Monitoring"::: 代理的 :::no-loc text="Windows":::步骤、获取 :::no-loc text="Log Analytics"::: ***工作区 ID** _ 和 _ *_primary key_** 以使 :::no-loc text="Microsoft Teams Rooms"::: 设备连接到部署 :::no-loc text="Azure Monitor"::: 的步骤以及验证与实例的代理连接的 :::no-loc text="Log Analytics"::: 步骤的详细信息。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>生成示例 :::no-loc text="Microsoft Teams Rooms"::: 事件

将 :::no-loc text="Microsoft Monitoring"::: 代理部署到测试设备后，验证是否已收集 :::no-loc text="Azure Monitor":::所需的事件日志数据。

> [!NOTE]
> 安装代理后 :::no-loc text="Microsoft Monitoring"::: 重新启动设备，并确保 :::no-loc text="Microsoft Teams Rooms"::: 会议应用已启动，以便它可以在事件日志中生成新事件。

1.  登录到 [:::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com) 并转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2.  列出设备 :::no-loc text="Microsoft Teams Rooms"::: 生成的检测信号事件：
    1.  选择工作区并转到 **日志** ，并使用查询检索将具有自定义字段的 :::no-loc text="Microsoft Teams Rooms":::检测信号记录。
    2.  示例查询： `Event | where Source == "SRS-App" and EventID == 2000`

3.  确保查询返回包含会议应用生成的事件的 :::no-loc text="Microsoft Teams Rooms"::: 日志记录。

4.  生成硬件问题，并验证是否已 :::no-loc text="Azure Log Analytics":::登录所需的事件。
    1.  在测试 :::no-loc text="Microsoft Teams Rooms"::: 系统上拔下其中一个外围设备。 这可能是相机、扬声器、麦克风或前厅显示
    2.  等待 10 分钟，以便在其中填充 :::no-loc text="Azure Log Analytics":::事件日志。
    3.  使用查询列出硬件错误事件： `Event | where Source == "SRS-App" and EventID == 3001`

5.  生成应用程序问题，并验证是否已记录所需的事件。
    1.  修改:::no-loc text="Microsoft Teams Rooms":::帐户配置，并键入错误的Email/密码对。
    2.  等待 10 分钟，以便在其中填充 :::no-loc text="Azure Log Analytics":::事件日志。
    3.  使用查询列出应用程序错误事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 在配置自定义字段之前，需要这些示例事件日志。 在收集所需的事件日志之前，请勿继续执行下一步。

## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

使用自定义字段从事件日志中提取特定数据。 需要定义稍后将用于磁贴、仪表板视图和警报的自定义字段。 在开始创建自定义字段之前，请参阅自 [定义字段 :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) 并熟悉这些概念。

若要从捕获的事件日志中提取自定义字段，请执行以下步骤：

1.  登录到 [:::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com) 并转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2. 列出设备生成 :::no-loc text="Microsoft Teams Rooms"::: 的事件：
   1.  转到 **日志** 并使用查询检索将具有自定义字段的记录。
   2.  示例查询： `Event | where Source == "SRS-App" and EventID == 2000`

3. 选择其中一条记录，选择左侧的按钮，然后启动字段提取向导。
4. 突出显示要从 RenderedDescription 中提取的数据并提供字段标题。 表 1 中提供了应使用的字段名称。
5. 使用 *表 1* 中显示的映射。 :::no-loc text="Log Analytics"::: 定义新字段时，将自动追加 **\_CF** 字符串。

> [!IMPORTANT]
> 请记住，所有 JSON 和 :::no-loc text="Log Analytics"::: 字段都区分大小写。
> 
> 请注意下表中每个自定义字段所需的查询。 需要使用正确的查询 :::no-loc text="Log Analytics"::: 来成功提取自定义字段值。
> 
**表 1**

| **JSON 字段**                   | **:::no-loc text="Log Analytics"::: 自定义字段** | **事件 ID** | **用于提取的查询**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 说明                      | SRSEventDescription         | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| ResourceState                    | SRSResourceState            | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| OperationName                    | SRSOperationName            | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| OperationResult                  | SRSOperationResult          | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| OS                               | SRSOSVersion                | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| 别名                            | SRSAlias                    | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| DisplayName                      | SRSDisplayName              | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| AppVersion                       | SRSAppVersion               | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | \|源 == “SRS-App” 和 EventID == 2000 的事件 |
| 会议麦克风状态     | SRSConfMicrophoneStatus     | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| 会议发言人状态        | SRSConfSpeakerStatus        | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| 默认说话人状态           | SRSDefaultSpeakerStatus     | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| 相机状态                    | SRSCameraStatus             | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| 会议室前显示状态     | SRSFORDStatus               | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| 运动传感器状态             | SRSMotionSensorStatus       | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |
| HDMI 引入状态               | SRSHDMIIngestStatus         | **3001**     | \|源 == “SRS-App” 和 EventID == 3001 的事件 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>在其中 :::no-loc text="Microsoft Teams Rooms"::: 定义视图 :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

收集数据并映射自定义字段后，可以使用视图设计器开发包含各种磁贴的仪表板来监视 :::no-loc text="Microsoft Teams Rooms"::: 事件。 使用视图设计器创建以下磁贴。 有关详细信息，请参阅[使用视图设计器在:::no-loc text="Log Analytics":::其中创建自定义视图](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 本指南中的前面步骤应已完成，以便仪表板磁贴正常工作。
>
> [!IMPORTANT]
> [Azure Monitor 中的视图设计器于 2023 年 8 月 31 日停用，2020 年 11](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) 月 30 日已禁用创建和克隆功能。 可以改用工作簿。 有关视图设计器过渡到工作簿的详细信息，请参阅 [包含预设视图设计器模板的快速入](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)门。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手动创建Microsoft Teams 会议室仪表板

或者，可以创建自己的仪表板，并仅添加要监视的磁贴。

#### <a name="configure-the-overview-tile"></a>配置“概述”磁贴

1.  打开 **视图设计器**。
2.  选择 **“概述”磁贴**，然后从库中选择 **两个数字** 。
3.  将磁贴 **:::no-loc text="Microsoft Teams Rooms":::** 命名为 。
4.  定义 **第一个磁贴**：<br>
    **传说：** 在上个月内至少发送一次检测信号的设备<br>
    **查询：** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定义 **第二个磁贴**：<br>
    **传说：** 在过去一小时内发送检测信号的活动设备<br>
    **查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  选择 **“应用**”。

### <a name="create-a-tile-that-displays-active-devices"></a>创建显示活动设备的磁贴

1.  选择 **“视图仪表板** ”以开始添加磁贴。
2.  从库 **中选择“数字&”列表**
3.  定义 **常规** 属性：<br>
    **组标题：** 检测信号状态<br>
    **新组：** 选择
4.  定义 **磁贴** 属性：<br>
    **传说：** 在过去 20 分钟内发送 (检测信号的活动设备) <br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定义 **列表** 属性：<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定义 **列标题**：<br>
    **名字：** 计算机名称<br>
    **价值：** 上次检测信号
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **“应用**”，然后 **关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>创建显示有连接问题的设备的磁贴

1.  从库 **中选择“数字&”列表** ，然后添加新磁贴。
2.  定义 **常规** 属性：<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义 **磁贴** 属性：<br>
    **传说：** 非活动设备 (在过去 20 分钟内未发送检测信号消息) <br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定义 **列表** 属性：<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定义 **列标题**：<br>
    **名字：** 计算机名称<br>
    **价值：** 上次检测信号
6.  定义 **导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 **“应用**”，然后 **关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>创建显示有硬件错误的设备的磁贴

1.  从库 **中选择“数字&”列表** ，然后添加新磁贴。
2.  定义 **常规** 属性：<br>
    **组标题：** 硬件状态<br>
    **新组：** 选择
3.  定义 **磁贴** 属性：<br>
    **传说：** 在过去一小时内遇到硬件错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性：<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义 **列标题**：<br>
    **名字：** 计算机名称<br>
    **价值：** 上次错误
6.  定义 **导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 **“应用**”，然后 **关闭**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>创建显示 :::no-loc text="Microsoft Teams Rooms"::: 操作系统版本的磁贴

1.  从库 **中选择甜甜圈&列表** ，然后添加新磁贴。
2.  定义 **常规** 属性：<br>
    **组标题：** 操作系统详细信息<br>
    **新组：** 选择
3.  定义 **标头** 属性：<br>
    **标题：** 操作系统版本<br>
    **字幕：** 运行特定 OS 版本的设备
4.  定义 **Donut** 属性：<br>
    **查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **中心文本：** 设备<br>
    **操作：** 和
5.  定义 **列表** 属性。<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 选择<br>
    **启用迷你图：** 未选中
6.  定义 **列标题**。<br>
    **名字：** 计算机名称<br>
    **价值：** 留空
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **“应用** ”，然后 **关闭**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>创建显示 :::no-loc text="Microsoft Teams Rooms"::: 应用程序版本的磁贴

1.  从库 **中选择甜甜圈&列表** ，然后添加新磁贴。
2.  定义 **常规** 属性：<br>
    **组标题：** :::no-loc text="Microsoft Teams Rooms"::: 应用程序详细信息<br>
    **新组：** 选择
3.  定义 **标头** 属性：<br>
    **标题：** 应用程序版本<br>
    **字幕：** 运行特定应用程序版本的设备
4.  定义 **Donut** 属性：<br>
    **查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **中心文本：** 设备<br>
    **操作：** 和
5.  定义 **列表** 属性。<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 选择<br>
    **启用迷你图：** 未选中
6.  定义 **列标题**。<br>
    **名字：** 计算机名称<br>
    **价值：** 留空
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **“应用** ”，然后 **关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>创建显示应用程序错误的设备的磁贴

1.  从库 **中选择“数字&”列表** ，然后添加新磁贴。
2.  定义 **常规** 属性。<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义 **磁贴** 属性。<br>
    **传说：** 在过去一小时内遇到应用程序错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性。<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义 **列标题**。<br>
    **名字：** 计算机名称<br>
    **价值：** 上次错误
6.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 **“应用** ”，然后 **关闭**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>创建显示已重启的设备的磁贴

1.  从库 **中选择“数字&”列表** ，然后添加新磁贴。
2.  定义 **常规** 属性。<br>
    **组标题：** 留空<br>
    **新组：** 未选中
3.  定义 **磁贴** 属性。<br>
    **传说：** 应用程序在过去 24 小时内重启的设备，以及重启次数<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性。<br>
    **列出查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定义 **列标题**。<br>
    **名字：** 计算机名称<br>
    **价值：** 重启次数
6.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 **“应用** ”，然后 **关闭**。
8.  选择 **“保存** ”以保存仪表板。

现在，你已完成创建视图。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>在中配置警报 :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 当控制台遇到问题时 :::no-loc text="Microsoft Teams Rooms"::: ，可以引发警报以通知管理员。

:::no-loc text="Azure Monitor"::: 包括一个内置警报机制，该机制定期在计划的日志搜索中运行。 如果日志搜索的结果与某些特定条件匹配，则会创建警报记录。

然后，规则可以自动运行一个或多个操作，以主动通知你警报或调用另一个进程。 包含警报的可能选项包括：
-   发送电子邮件
-   通过 HTTP POST 请求调用外部进程
-   在服务中 :::no-loc text="Azure Automation"::: 启动 Runbook

请参阅 [日志警报 :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) ，了解有关警报的 :::no-loc text="Azure Monitor":::详细信息。

> [!NOTE]
> 以下示例在设备生成硬件或应用程序错误时 :::no-loc text="Microsoft Teams Rooms"::: 发送电子邮件警报。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>为 :::no-loc text="Microsoft Teams Rooms"::: 硬件问题配置电子邮件警报

配置一个警报规则，用于检查 :::no-loc text="Microsoft Teams Rooms"::: 在过去一小时内遇到硬件问题的设备。
1.  登录到 [:::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com) 并转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2. 导航到:::no-loc text="Log Analytics":::工作区并选择 **“警报”**，然后选择 **“新建警报规则**”

3. 选择 **“添加条件**”，然后 **选择“自定义日志搜索**”

4.  在“搜索查询”文本框中输入以下查询。<br>
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
    **阈值：** 0<br>

6. 配置评估设置并选择 **“完成**” <br>
    **周期 (分钟) ：** 60<br>
    **频率 (分钟) ：** 60<br>

7. 配置操作组：
    1.  选择 **“新建”**
    2.  为 *操作组名称* 和 *短名称* 字段提供合适的名称。
    3.  指定唯一 *的操作名称*，然后选择 **Email/SMS/Push/Voice**，然后选择 **“编辑详细信息**”。
    4.  选 **中Email** 复选框，并提供将接收警报的人员或组的电子邮件地址。
    5.  还可以提供电话号码以通过短信、语音呼叫或两者均获得通知。
    6. 选择 **“确定**”。

8. 如果想要覆盖警报电子邮件的主题行，请 **自定义操作**。

9. 指定规则名称和说明。<br>
    **规则名称：** :::no-loc text="Microsoft Teams Rooms"::: 硬件故障警报<br>
    **描述：** 在最后一小时内遇到硬件问题的设备列表<br>

10. 选择预期的严重性，并确保已启用规则。

11. 选择 **“创建警报规则**”。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>为 :::no-loc text="Microsoft Teams Rooms"::: 应用程序问题配置电子邮件警报

重复相同的过程，但使用以下查询列出在过去一小时内遇到应用程序问题的设备。

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

现在，你已完成警报的定义。 可以使用上面的示例定义其他警报。

生成警报时，你将收到一封电子邮件，其中列出了在最后一小时内遇到问题的设备。

![示例 :::no-loc text="Azure Monitor"::: 警报电子邮件] (./media/Deploy-Azure-Monitor-6.png“示例 :::no-loc text="Azure Monitor"::: 警报电子邮件”) 

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>为其配置所有设备 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a>配置仪表板和警报后，可以在所有:::no-loc text="Microsoft Teams Rooms":::设备上设置和配置:::no-loc text="Microsoft Monitoring":::代理以完成监视部署。

尽管可以在每个设备上手动安装和配置 :::no-loc text="Microsoft Monitoring"::: 代理，但我们强烈建议你利用现有的软件部署工具和方法。

如果是首次生成 :::no-loc text="Microsoft Teams Rooms"::: 设备，可能需要在生成过程中包括 :::no-loc text="Microsoft Monitoring"::: 代理设置和配置步骤。 有关详细信息，请参阅 [使用命令行安装代理](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring":::使用 组策略 对象 (GPO) 部署代理

如果在实现:::no-loc text="Azure Monitoring":::之前已部署:::no-loc text="Microsoft Teams Rooms":::设备，则可以使用提供的脚本来设置和配置代理，方法是使用:::no-loc text="Active Directory":::组策略对象。

1.  创建共享网络路径并授予对 **域计算机** 组的读取访问权限。

2.  从中下载代理:::no-loc text="Windows":::的 :::no-loc text="Microsoft Monitoring"::: 64 位版本<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  将安装程序包的内容提取到网络共享中。
    1.  打开命令提示符窗口，然后 **执行MMASetup-AMD64.exe /c**
    2.  指定刚创建的共享并提取内容。

4.  创建新的组策略对象，并将其分配给计算机帐户所在的:::no-loc text="Microsoft Teams Rooms":::组织单位。

5.  配置 PowerShell 执行策略：
    1.  编辑新创建的组策略对象并导航到计算机配置\\策略\\管理模板\\:::no-loc text="Windows":::组件\\ :::no-loc text="Windows PowerShell":::
    2.  启 **用“打开脚本执行** ”并将 **执行** 策略设置为 **允许本地脚本**。

6.  配置启动脚本：
    1.  复制以下脚本并将其另存为Install-MMAgent.ps1。
    2.  修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数以匹配配置。
    3.  编辑同一组策略对象并导航到计算机配置\\策略\\:::no-loc text="Windows":::设置\\脚本 (启动/关闭) 
    4.  双击以选择 **“启动**”，然后选择 **“PowerShell 脚本**”。
    5.  选择 **“显示文件**”，然后将 **Install-MMAgent.ps1** 文件复制到该文件夹。
    6.  选择 **“添加**”，然后 **浏览**。
    7.  选择刚复制的 ps1 脚本。

7.  :::no-loc text="Microsoft Teams Rooms"::: 应通过第二次重新启动来安装和配置 :::no-loc text="Microsoft Monitoring"::: 代理。

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
> 当需要重新配置代理、将其移动到其他工作区或在初始安装后修改代理设置时，可以参阅“[管理和维护:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage)代理”一文。

## <a name="additional-solutions"></a>其他解决方案
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: 通过其 [解决方案库](/azure/azure-monitor/insights/solutions) 提供内置的管理解决方案，以进一步帮助你监视环境。 强烈建议将[警报管理和](/azure/azure-monitor/platform/alert-management-solution)[:::no-loc text="Azure Log Analytics":::代理运行状况](/azure/azure-monitor/insights/solution-agenthealth)解决方案也添加到工作区。

> [!NOTE]
> 代理运行状况解决方案可帮助你识别环境中过时或损坏 :::no-loc text="Microsoft Monitoring"::: 的代理，警报管理解决方案提供有关在给定时间段内引发的警报的详细信息。

## <a name="see-also"></a>另请参阅

[使用:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
