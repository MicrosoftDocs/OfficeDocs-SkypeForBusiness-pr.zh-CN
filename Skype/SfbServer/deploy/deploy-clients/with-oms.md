---
title: 使用 OMS 部署 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何使用 Microsoft 操作管理套件集成的、 端到端方式部署 Skype 的空间系统 v2 设备的管理。
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>使用 OMS 部署 Skype 会议室系统 v2 管理
 
本文讨论如何使用 Microsoft 操作管理套件集成的、 端到端方式部署 Skype 的空间系统 v2 设备的管理。 
  
可通过配置 Microsoft Operations Management Suite (OMS) 来提供能够帮助你管理 Skype 会议室设备的基本遥测。当管理解决方案成熟时，可以购买其他数据和管理功能，以创建更详细的设备性能视图。
  
你需要在高级别执行以下任务：
  
1. [配置用于 OMS 管理的设备 ](with-oms.md#config_devices)
    
2. [映射自定义字段](with-oms.md#Custom_fields)
    
3. [在 OMS 中定义 SRS v2 视图](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>查找并记录设备位置、功能和配置
<a name="find_devices"> </a>

第一步是创建一个详细数据库，包括系统中的所有设备、设备功能和配置的详细信息及其位置。在小到中型组织中，电子表格足以完成此任务。如果你在大型组织工作，可能需要考虑资产管理工具和第三方服务。重要的是要记录每台设备的位置和所有相关详细信息。
  
完成该工作后，可以使用此信息来派发技术员并管理设备修补程序和升级。
  
## <a name="configure-devices-for-oms-management"></a>配置用于 OMS 管理的设备 
<a name="config_devices"> </a>

SRS 的每个设备，请按照[连接 Windows Azure 中的日志分析服务的计算机](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)中的说明进行操作。
  
## <a name="configure-oms-to-collect-device-event-logs"></a>配置 OMS 以收集设备事件日志
<a name="config_devices"> </a>

您将需要特殊的配置，OMS SRS 设备在[Windows 事件日志数据源日志分析中的](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)使用的步骤中收集事件日志。 SRS 的事件日志，以选择是 Skype 的空间系统，您应该检查所有类型的选项框： 错误、 警告和信息。
  
## <a name="map-custom-fields"></a>映射自定义字段
<a name="Custom_fields"> </a>

拼贴[中 OMS 的 SRS v2 定义视图](with-oms.md#Views)中创建之前，您需要创建视图的自定义字段。 创建自定义字段的详细信息，请参阅[日志分析中的自定义字段](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields)。
  
使用如下所示的映射，OMS 将自动添加 _CF 时定义新的字段。 
  
> [!IMPORTANT]
> 请记住，所有 JSON 和 OMS 字段都区分大小写。 
  
**自定义字段映射**

|**JSON 字段**|**OMS 的自定义字段**|
|:-----|:-----|
|说明  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|操作名称  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|别名  <br/> |SRSAlias_CF  <br/> |
|显示名称  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>在 OMS 中定义 SRS v2 视图
<a name="Views"> </a>

收集数据并映射自定义字段后，可以使用 OMS 视图设计器开发包含图块的仪表板来监控 SRS v2 事件。 使用视图设计器创建下面的拼贴，请参阅[使用视图设计器中以创建日志分析中的自定义视图](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer)所需。
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>创建可显示运行状况良好的设备的图块

1. 定义该用例： 
    
    此图块显示在过去 10 分钟内发送过检测信号消息的所有设备。
    
2. 分配组图块  
    
   ```
   SRS v2
   ```

3. 选中新组框
    
4. 添加图块图例文本
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. 输入图块查询
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. 输入列表查询
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. 定义列标题名称
    
   ```
   Display Name
   ```

8. 定义列标题值
    
   ```
   Last HB
   ```

9. 输入导航查询
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>创建可显示具有连接问题的设备的图块

1. 定义该用例： 
    
    此图块显示在过去 10 分钟内未发送检测信号消息的所有设备。这些设备可能遇到网络连接问题、Exchange 连接问题或 Skype for Business 连接问题。
    
2. 分配组图块  
    
   ```
   SRS v2
   ```

3. 不要选中新组框。 你在创建图块 1 时已执行此操作，无需再次执行此操作。
    
4. 添加图块图例文本
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. 输入图块查询
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. 输入列表查询
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. 定义列标题名称
    
   ```
   Device Name
   ```

8. 定义列标题值 
    
   ```
   Last HB
   ```

9. 输入导航查询
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>列出具有硬件错误的设备 

1. 定义该用例： 
    
   该拼贴显示发送一条消息，指示一个或多个硬件组件问题，在最后 10 分钟内的所有设备。 
    
2. 分配组图块  
    
   ```
   SRS v2
   ```

3. 不要选中新组框。 你在创建图块 1 时已执行此操作，无需再次执行此操作。
    
4. 图块图例： 
    
   ```
   Devices with a Hardware Error
   ```

5. 图块查询
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. 列表查询：
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. 列标题名称： 
    
   ```
   Display Name
   ```

8. 列标题值： 
    
   ```
   Last Error
   ```

9. 导航查询： 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>列出具有应用错误的设备 

1. 定义该用例： 
    
   此图块显示在过去 10 分钟内报告一个或多个应用组件错误的所有 SRS 设备
    
2. 分配组图块  
    
   ```
   SRS v2
   ```

3. 不要选中新组框。 你在创建图块 1 时已执行此操作，无需再次执行此操作。
    
4. 图块图例： 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. 图块查询： 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. 列表查询： 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. 列标题名称： 
    
   ```
   Device Name
   ```

8. 列标题值： 
    
   ```
   Last Error
   ```

9. 导航查询：
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>列出需要重新启动的设备

1. 定义该用例： 
    
   此图块显示在过去 24 小时内已重新启动的所有 SRS 设备以及重新启动次数
    
2. 分配组图块  
    
  ```
  SRS v2
  ```

3. 不要选中新组框。 你在创建图块 1 时已执行此操作，无需再次执行此操作。
    
4. 图块图例： 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. 图块查询： 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. 列表查询： 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. 列标题名称： 
    
   ```
   Display Name
   ```

8. 列标题值： 
    
   ```
   Number of restarts
   ```

9. 导航查询： 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

这便完成了视图创建。当前可用的警报都将在上述一个或多个图块中得到反映。
## <a name="see-also"></a>另请参阅
<a name="Views"> </a>

#### 

[规划与 OMS 的 Skype 的空间系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[管理与 OMS 的 Skype 的空间系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)

