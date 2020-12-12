---
title: 使用 Azure Monitor 部署 Microsoft Teams 会议室管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何使用 Azure Monitor 以集成式的端到端方式部署 Microsoft Teams 会议室设备的管理。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662097"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>部署 :::no-loc text="Microsoft Teams Rooms"::: 管理 :::no-loc text="Azure Monitor":::

本文讨论如何使用设置和部署集成的端到端 :::no-loc text="Microsoft Teams Rooms"::: 设备管理 :::no-loc text="Azure Monitor"::: 。

可以在其中 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 进行配置，以提供有助于管理会议室设备的基本遥测 :::no-loc text="Microsoft Teams Rooms"::: 和警报。 随着管理解决方案的成熟，你可能会决定部署其他数据和管理功能，以创建设备可用性和性能的更详细视图。

按照本指南操作，可以使用如下示例所示的仪表板获取有关设备可用性、应用程序和硬件运行状况以及应用程序和操作系统版本分发 :::no-loc text="Microsoft Teams Rooms"::: 的详细状态报告。

![Microsoft Teams 会议室的示例 Log Analytics 视图的屏幕截图](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 会议室的示例 Log Analytics 视图")

你需要在高级别执行以下任务：


1. [验证 :::no-loc text="Log Analytics"::: 配置](azure-monitor-deploy.md#validate_LogAnalytics)
2. [配置用于管理设置 :::no-loc text="Log Analytics"::: 的测试设备](azure-monitor-deploy.md#configure_test_devices)
3. [映射自定义字段](azure-monitor-deploy.md#Custom_fields)
4. [定义 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [定义警报](azure-monitor-deploy.md#Alerts)
6. [配置所有设备进行监视](azure-monitor-deploy.md#configure_all_devices)
7. [配置其他 :::no-loc text="Azure Monitor"::: 解决方案](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 尽管只需最少的配置，就可以监视运行操作系统的计算机，但在开始将代理部署到所有设备之前，仍然需要执行一些特定的 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: 步骤。
> 因此，强烈建议按照正确的顺序执行所有配置步骤，以便进行受控的设置和配置。 最终结果的质量在很大程度上取决于初始配置的质量。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>验证 :::no-loc text="Log Analytics"::: 配置
<a name="validate_LogAnalytics"> </a>

你需要有一 :::no-loc text="Log Analytics"::: 个工作区来开始从设备收集 :::no-loc text="Microsoft Teams Rooms"::: 日志。 工作区是具有其自己的数据存储库、数据源和解决方案 :::no-loc text="Log Analytics"::: 的独特环境。 如果已有一个工作区，可以使用它来监视部署，或者可以创建一个特定于监视需求的 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 专用工作区。

如果需要创建新工作区，请按照在门户 :::no-loc text="Log Analytics"::: 中创建工作区 [ :::no-loc text="Log Analytics"::: 一文的说明 :::no-loc text="Azure"::: 进行操作](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> 若要 :::no-loc text="Log Analytics"::: 与 :::no-loc text="Azure Monitor"::: 订阅一起使用，需要拥有一个活动 :::no-loc text="Azure"::: 订阅。 如果没有订阅，可以先创建一个免费试用 :::no-loc text="Azure"::: 订阅。 [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>配置为 :::no-loc text="Log Analytics"::: 收集 :::no-loc text="Microsoft Teams Rooms"::: 事件日志

:::no-loc text="Log Analytics"::: 仅从设置 :::no-loc text="Windows"::: 中指定的事件日志中收集事件。 对于每个日志，只会收集具有所选严重性的事件。

需要配置为 :::no-loc text="Log Analytics"::: 收集监视设备和应用程序状态 :::no-loc text="Microsoft Teams Rooms"::: 所需的日志。 :::no-loc text="Microsoft Teams Rooms"::: 设备使用 **:::no-loc text="Skype Room System":::** 事件日志。

若要 :::no-loc text="Log Analytics"::: 配置为收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，请参阅[ :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![事件日志设置的屏幕截图](../media/Deploy-Azure-Monitor-2.png "事件日志设置")

> [!IMPORTANT]
> 配置 :::no-loc text="Windows"::: 事件日志设置，输入 **:::no-loc text="Skype Room System":::** 为事件日志名称，然后选中"错误、警告和信息"复选框。

## <a name="configure-test-devices-for-azure-monitoring"></a>为 Azure 监视配置测试设备
<a name="configure_test_devices"> </a>

需要准备好 :::no-loc text="Log Analytics"::: 能够监视 :::no-loc text="Microsoft Teams Rooms"::: 与事件相关的事件。 首先，只需将代理部署到具有物理访问权限的一个或两个设备，然后让这些测试设备生成一些数据，并 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 推送到 :::no-loc text="Log Analytics"::: 工作区。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>安装 :::no-loc text="Microsoft Monitoring"::: 代理以测试设备

按照"将计算机连接到服务"中提供的说明，将代理 :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: 部署到测试设备 :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。 本文详细介绍了部署代理的步骤、获取工作区 ID _ 的说明、用于将设备连接到部署的主密钥，以及验证代理与实例的连接 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * **_**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 的步骤。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>生成 :::no-loc text="Microsoft Teams Rooms"::: 示例事件

将代理部署到测试设备后，验证是否收集 :::no-loc text="Microsoft Monitoring"::: 所需的事件日志数据 :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 安装代理后重新启动设备，并确保会议应用已启动，以便它可以在事件日志中 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 生成新事件。

1.  登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2.  列出设备生成的检测信号 :::no-loc text="Microsoft Teams Rooms"::: 事件：
    1.  选择工作区并转到 _ *Logs** 并使用查询来检索具有其自定义字段的检测信号记录 :::no-loc text="Microsoft Teams Rooms"::: 。
    2.  示例查询： `Event | where Source == "SRS-App" and EventID == 2000`

3.  确保查询返回包含会议应用生成的事件的 :::no-loc text="Microsoft Teams Rooms"::: 日志记录。

4.  生成硬件问题，并验证所需的事件已登录 :::no-loc text="Azure Log Analytics"::: 。
    1.  拔下测试系统上的一个外围设备 :::no-loc text="Microsoft Teams Rooms"::: 。 这可以是相机、免提电话、麦克风或前室显示器
    2.  等待 10 分钟，以填充事件日志 :::no-loc text="Azure Log Analytics"::: 。
    3.  使用查询列出硬件错误事件： `Event | where Source == "SRS-App" and EventID == 3001`

5.  生成应用程序问题，并验证是否记录了所需的事件。
    1.  修改 :::no-loc text="Microsoft Teams Rooms"::: 应用程序配置，并键入错误的会话启动协议 (SIP) /密码对。
    2.  等待 10 分钟，以填充事件日志 :::no-loc text="Azure Log Analytics"::: 。
    3.  使用查询列出应用程序错误事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 在配置自定义字段之前，需要这些示例事件日志。 在收集到所需的事件日志之前，不要继续执行下一步。

## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

使用自定义字段从事件日志中提取特定数据。 需要定义稍后用于磁贴、仪表板视图和警报的自定义字段。 在开始[创建自定义字段之前 :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)，请参阅"自定义"字段并熟悉相关概念。

若要从捕获的事件日志中提取自定义字段，请执行以下步骤：

1.  登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2. 列出设备生成的 :::no-loc text="Microsoft Teams Rooms"::: 事件：
   1.  转到 **"** 日志"并使用查询来检索具有自定义字段的记录。
   2.  示例查询： `Event | where Source == "SRS-App" and EventID == 2000`

3. 选择其中一条记录，选择左侧的按钮，然后启动字段提取向导。
4. 突出显示要从 RenderedDescription 提取的数据，并提供字段标题。 表 1 中提供了您应该使用的字段名称。
5. 使用表 *1 中所示的映射*。 :::no-loc text="Log Analytics":::将在定义新字段时自动追加 **\_ CF** 字符串。

> [!IMPORTANT]
> 请记住，所有 JSON :::no-loc text="Log Analytics"::: 和字段都区分大小写。
> 
> 请注意下表中每个自定义字段所需的查询。 需使用正确的查询来成功 :::no-loc text="Log Analytics"::: 提取自定义字段值。
> 
**表 1**

| **JSON 字段**                   | **:::no-loc text="Log Analytics"::: 自定义域** | **事件 ID** | **要用于提取的查询**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 说明                      | SRSEventDescription         | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| ResourceState                    | SRSResourceState            | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| OperationName                    | SRSOperationName            | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| OperationResult                  | SRSOperationResult          | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| OS                               | SRSOSVersion                | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| 别名                            | SRSAlias                    | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| DisplayName                      | SRSDisplayName              | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| AppVersion                       | SRSAppVersion               | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Source \| == "SRS-App" and EventID == 2000 的事件 |
| 会议麦克风状态     | SRSConfMicrophoneStatus     | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| 会议发言人状态        | SRSConfSpeakerStatus        | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| 默认发言人状态           | SRSDefaultSpeakerStatus     | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| 相机状态                    | SRSCameraStatus             | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| 会议室显示状态前     | SRSFORDStatus               | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| 运动传感器状态             | SRSMotionSensorStatus       | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |
| HDMI Ingest 状态               | SRSHDMIIngestStatus         | **3001**     | Source \| == "SRS-App" and EventID == 3001 的事件 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>定义 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

收集数据并映射自定义字段后，可以使用视图设计器开发包含各种磁贴的仪表板来 :::no-loc text="Microsoft Teams Rooms"::: 监视事件。 使用视图设计器创建以下磁贴。 有关详细信息，请参阅"使用[视图设计器 :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)在

> [!NOTE]
> 本指南中的先前步骤应已完成，仪表板磁贴应能正常工作。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>使用导入方法创建 Microsoft Teams 会议室仪表板

可以导入 :::no-loc text="Microsoft Teams Rooms"::: 仪表板并开始快速监视设备。 执行以下步骤导入仪表板：

1.  获取 [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) 仪表板文件。
2.  登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到 :::no-loc text="Log Analytics"::: 并选择工作区。
3.  打开 **视图设计器**。
4.  选择 **"导入**"，然后选择 **SkypeRoomSystems_v2.omsview** 文件。
5.  选择 **"保存"。**

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手动创建 Microsoft Teams 会议室仪表板

或者，你可以创建自己的仪表板并仅添加要监视的磁贴。

#### <a name="configure-the-overview-tile"></a>配置"概述"磁贴

1.  打开 **视图设计器**。
2.  选择 **"概述**"磁贴，然后 **从库中选择** 两个数字。
3.  为磁贴命名 **:::no-loc text="Microsoft Teams Rooms":::** 。
4.  定义第 **一个磁贴**：<br>
    **图例：** 在上个月至少发送一次检测信号的设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定义第 **二个磁贴**：<br>
    **图例：** 过去一小时内发送检测信号的活动设备<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  选择 **"应用"。**

### <a name="create-a-tile-that-displays-active-devices"></a>创建显示活动设备的磁贴

1.  选择 **"视图仪表板** "以开始添加磁贴。
2.  从 **&选择** 数字和数字列表
3.  定义 **"常规"** 属性：<br>
    **组标题：** 检测信号状态<br>
    **新建组：** 已选择
4.  定义 **磁贴** 属性：<br>
    **图例：** 活动设备 (20 分钟内发送的检测) <br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定义 **列表** 属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定义 **列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 上次检测信号
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **"应用**"，然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>创建一个磁贴，用于显示有连接问题的设备

1.  从 **库中&** 数字"，然后添加新磁贴。
2.  定义 **"常规"** 属性：<br>
    **组标题：** 留空<br>
    **新建组：** 未选择
3.  定义 **磁贴** 属性：<br>
    **图例：** 非活动设备 (最近 20 分钟内未发送检测信号) <br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定义 **列表** 属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定义 **列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 上次检测信号
6.  定义 **导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 **"应用**"，然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>创建一个磁贴，用于显示具有硬件错误的设备

1.  从 **库中&** 数字"，然后添加新磁贴。
2.  定义 **"常规"** 属性：<br>
    **组标题：** 硬件状态<br>
    **新建组：** 已选择
3.  定义 **磁贴** 属性：<br>
    **图例：** 过去一小时内遇到硬件错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性：<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义 **列标题**：<br>
    **名称：** 计算机名称<br>
    **值：** 上次错误
6.  定义 **导航查询**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 **"应用**"，然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>创建显示操作系统 :::no-loc text="Microsoft Teams Rooms"::: 版本的磁贴

1.  从 **库中&"** 按钮"，然后添加新磁贴。
2.  定义 **"常规"** 属性：<br>
    **组标题：** 操作系统详细信息<br>
    **新建组：** 已选择
3.  定义 **标头** 属性：<br>
    **标题：** 操作系统版本<br>
    **副标题：** 运行特定 OS 版本的设备
4.  定义 **Donut** 属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **居中文本：** 设备<br>
    **操作：** 总和
5.  定义 **列表** 属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 已选择<br>
    **启用迷你图：** 未选择
6.  定义 **列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 留空
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **"应用"，** 然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>创建显示应用程序 :::no-loc text="Microsoft Teams Rooms"::: 版本的磁贴

1.  从 **库中&"** 按钮"，然后添加新磁贴。
2.  定义 **"常规"** 属性：<br>
    **组标题：** :::no-loc text="Microsoft Teams Rooms"::: 应用程序详细信息<br>
    **新建组：** 已选择
3.  定义 **标头** 属性：<br>
    **标题：** 应用程序版本<br>
    **副标题：** 运行特定应用程序版本的设备
4.  定义 **Donut** 属性：<br>
    **查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **居中文本：** 设备<br>
    **操作：** 总和
5.  定义 **列表** 属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隐藏图形：** 已选择<br>
    **启用迷你图：** 未选择
6.  定义 **列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 留空
7.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  选择 **"应用"，** 然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>创建一个磁贴，用于显示具有应用程序错误的设备

1.  从 **库中&** 数字"，然后添加新磁贴。
2.  定义 **"常规"** 属性。<br>
    **组标题：** 留空<br>
    **新建组：** 未选择
3.  定义 **磁贴** 属性。<br>
    **图例：** 过去一小时内遇到应用程序错误的设备<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定义 **列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 上次错误
6.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  选择 **"应用"，** 然后选择"**关闭"。**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>创建显示已重启设备的磁贴

1.  从 **库中&** 数字"，然后添加新磁贴。
2.  定义 **"常规"** 属性。<br>
    **组标题：** 留空<br>
    **新建组：** 未选择
3.  定义 **磁贴** 属性。<br>
    **图例：** 过去 24 小时内重启应用程序的设备，以及重启次数<br>
    **图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定义 **列表** 属性。<br>
    **列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定义 **列标题**。<br>
    **名称：** 计算机名称<br>
    **值：** 重启次数
6.  定义 **导航查询**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  选择 **"应用"，** 然后选择"**关闭"。**
8.  选择 **"保存** "以保存仪表板。

现在，你已完成视图的创建。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>在 :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 当主机遇到问题时，可以 :::no-loc text="Microsoft Teams Rooms"::: 引发警报以通知管理员。

:::no-loc text="Azure Monitor"::: 包括内置警报机制，该机制定期运行计划的日志搜索。 如果日志搜索的结果与特定条件匹配，则创建警报记录。

然后，规则可以自动运行一个或多个操作，主动通知你警报或调用另一个进程。 警报的可能选项包括：
-   发送电子邮件
-   通过 HTTP POST 请求调用外部进程
-   在服务中启动 :::no-loc text="Azure Automation"::: Runbook

请参阅["日志警报 :::no-loc text="Azure Monitor"::: "，](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)了解有关以下操作中警报的信息 :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 以下示例在设备生成硬件或应用程序错误时 :::no-loc text="Microsoft Teams Rooms"::: 发送电子邮件警报。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>配置针对硬件问题 :::no-loc text="Microsoft Teams Rooms"::: 的电子邮件警报

配置一个警报规则，用于检查过去一小时内 :::no-loc text="Microsoft Teams Rooms"::: 遇到硬件问题的设备。
1.  登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到 :::no-loc text="Log Analytics"::: 并选择工作区。

2. 导航到 :::no-loc text="Log Analytics"::: 工作区，选择 **"警报** "，然后选择 **"新建警报规则"**

3. 选择 **"添加条件** "，然后选择 **"自定义日志搜索"**

4.  在"搜索查询"文本框中输入以下查询。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  配置警报逻辑设置：<br>
    **基于：** 结果数<br>
    **条件：** 大于则<br>
    **阈值：0**<br>

6. 配置评估设置，然后选择"**完成：** <br>
    **分钟 (分钟) ：60**<br>
    **频率 (分钟) ：60**<br>

7. 配置操作组：
    1.  选择 **"新建"**
    2.  为操作组名称和短 *名称字段**提供合适的* 名称。
    3.  指定唯一 *的操作名称，* 选择 **"电子邮件/短信/推送/语音**"，然后选择"**编辑详细信息"。**
    4.  选中 **"电子邮件** "复选框，并提供将接收通知的联系人或组的电子邮件地址。
    5.  您还可以提供电话号码，以便通过短信和/或语音呼叫获得通知。
    6. 选择 **"确定"。**

8. **如果要** 覆盖警报电子邮件的主题行，请自定义操作。

9. 指定规则名称和说明。<br>
    **规则名称：** :::no-loc text="Microsoft Teams Rooms"::: 硬件故障警报<br>
    **说明：** 过去一小时内遇到硬件问题的设备列表<br>

10. 选择预期的严重性，并确保启用规则。

11. 选择 **"创建警报规则"。**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>针对应用程序问题配置 :::no-loc text="Microsoft Teams Rooms"::: 电子邮件警报

重复相同的过程，但使用以下查询列出过去一小时内遇到应用程序问题的设备。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

现已完成定义警报。 可以使用上述示例定义其他警报。

生成警报时，你收到一封电子邮件，其中列出了过去一小时内遇到问题的设备。

![示例 :::no-loc text="Azure Monitor"::: 警报电子邮件] (./media/Deploy-Azure-Monitor-6.png"示例 :::no-loc text="Azure Monitor"::: 警报电子邮件") 

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>配置所有设备 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a>配置仪表板和警报后，可以在所有设备上设置和配置代理， :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 以完成监视部署。

虽然可以在每台设备上手动安装和配置代理，但我们强烈建议你利用现有 :::no-loc text="Microsoft Monitoring"::: 的软件部署工具和方法。

如果是首次生成设备，可能需要在生成过程中包括代理安装和 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 配置步骤。 有关详细信息，请参阅 [使用命令行安装代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>使用 :::no-loc text="Microsoft Monitoring"::: 组策略对象和 GPO (部署) 

如果在实施之前已部署设备，可以使用提供的脚本通过组策略对象 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 来设置和 :::no-loc text="Active Directory"::: 配置代理。

1.  创建共享网络路径，并授予对"域计算机" **组的读取** 访问权限。

2.  下载代理的 64 位 :::no-loc text="Microsoft Monitoring"::: 版本 :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  将安装包的内容提取到网络共享中。
    1.  打开命令提示符窗口，然后MMASetup-AMD64.exe **/c**
    2.  指定刚刚创建的共享，并提取内容。

4.  创建新的组策略对象，并将其分配给计算机帐户 :::no-loc text="Microsoft Teams Rooms"::: 所在的组织单位。

5.  配置 PowerShell 执行策略：
    1.  编辑新建的组策略对象并导航到计算机配置 \\ 策略 \\ 管理模板 \\ :::no-loc text="Windows"::: 组件 \\:::no-loc text="Windows PowerShell":::
    2.  启用"**启用脚本执行"，将****执行策略设置为****"允许本地脚本"。**

6.  配置启动脚本：
    1.  复制以下脚本并将其另存为Install-MMAgent.ps1。
    2.  修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数以匹配配置。
    3.  编辑同一组策略对象并导航到"计算机配置策略设置脚本 \\ \\ :::no-loc text="Windows"::: \\ " (/关闭) 
    4.  双击选择"启动 **"，** 然后选择 **"PowerShell 脚本"。**
    5.  选择 **"显示** 文件"，然后将Install-MMAgent.ps1 **文件复制到** 该文件夹。
    6.  选择 **"添加**"，然后选择"**浏览"。**
    7.  选择刚刚复制的 ps1 脚本。

7.  :::no-loc text="Microsoft Teams Rooms"::: 设备应在第二次 :::no-loc text="Microsoft Monitoring"::: 重新启动时安装和配置代理。

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
> 可以在需要 [重新配置代理、 :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 将其移到其他工作区或在初始安装后修改代理设置时，参阅"管理和维护代理"一文。

## <a name="additional-solutions"></a>其他解决方案
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: 通过其解决方案库提供内置管理解决方案 [，](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) 以进一步帮助监视环境。 强烈建议将警报[管理和](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)[ :::no-loc text="Azure Log Analytics"::: 代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到工作区。

> [!NOTE]
> 代理运行状况解决方案可帮助识别环境中过期或损坏的代理，警报管理解决方案提供有关给定时段内已引发 :::no-loc text="Microsoft Monitoring"::: 警报的详细信息。

## <a name="see-also"></a>另请参阅

[计划 :::no-loc text="Microsoft Teams Rooms"::: 管理 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[使用 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
