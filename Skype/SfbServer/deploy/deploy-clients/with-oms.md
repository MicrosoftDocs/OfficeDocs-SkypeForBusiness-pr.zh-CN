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
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="d18eb-103">使用 OMS 部署 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="d18eb-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="d18eb-104">本文讨论如何使用 Microsoft 操作管理套件集成的、 端到端方式部署 Skype 的空间系统 v2 设备的管理。</span><span class="sxs-lookup"><span data-stu-id="d18eb-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="d18eb-p101">可通过配置 Microsoft Operations Management Suite (OMS) 来提供能够帮助你管理 Skype 会议室设备的基本遥测。当管理解决方案成熟时，可以购买其他数据和管理功能，以创建更详细的设备性能视图。</span><span class="sxs-lookup"><span data-stu-id="d18eb-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="d18eb-107">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d18eb-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="d18eb-108">配置用于 OMS 管理的设备 </span><span class="sxs-lookup"><span data-stu-id="d18eb-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="d18eb-109">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="d18eb-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="d18eb-110">在 OMS 中定义 SRS v2 视图</span><span class="sxs-lookup"><span data-stu-id="d18eb-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="d18eb-111">查找并记录设备位置、功能和配置</span><span class="sxs-lookup"><span data-stu-id="d18eb-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="d18eb-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-112"></span></span>

<span data-ttu-id="d18eb-p102">第一步是创建一个详细数据库，包括系统中的所有设备、设备功能和配置的详细信息及其位置。在小到中型组织中，电子表格足以完成此任务。如果你在大型组织工作，可能需要考虑资产管理工具和第三方服务。重要的是要记录每台设备的位置和所有相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="d18eb-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="d18eb-117">完成该工作后，可以使用此信息来派发技术员并管理设备修补程序和升级。</span><span class="sxs-lookup"><span data-stu-id="d18eb-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="d18eb-118">配置用于 OMS 管理的设备 </span><span class="sxs-lookup"><span data-stu-id="d18eb-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="d18eb-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-119"></span></span>

<span data-ttu-id="d18eb-120">SRS 的每个设备，请按照[连接 Windows Azure 中的日志分析服务的计算机](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="d18eb-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="d18eb-121">配置 OMS 以收集设备事件日志</span><span class="sxs-lookup"><span data-stu-id="d18eb-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="d18eb-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-122"></span></span>

<span data-ttu-id="d18eb-123">您将需要特殊的配置，OMS SRS 设备在[Windows 事件日志数据源日志分析中的](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)使用的步骤中收集事件日志。</span><span class="sxs-lookup"><span data-stu-id="d18eb-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="d18eb-124">SRS 的事件日志，以选择是 Skype 的空间系统，您应该检查所有类型的选项框： 错误、 警告和信息。</span><span class="sxs-lookup"><span data-stu-id="d18eb-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="d18eb-125">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="d18eb-125">Map custom fields</span></span>
<span data-ttu-id="d18eb-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-126"></span></span>

<span data-ttu-id="d18eb-127">拼贴[中 OMS 的 SRS v2 定义视图](with-oms.md#Views)中创建之前，您需要创建视图的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="d18eb-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="d18eb-128">创建自定义字段的详细信息，请参阅[日志分析中的自定义字段](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields)。</span><span class="sxs-lookup"><span data-stu-id="d18eb-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="d18eb-129">使用如下所示的映射，OMS 将自动添加 _CF 时定义新的字段。</span><span class="sxs-lookup"><span data-stu-id="d18eb-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d18eb-130">请记住，所有 JSON 和 OMS 字段都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d18eb-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="d18eb-131">**自定义字段映射**</span><span class="sxs-lookup"><span data-stu-id="d18eb-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="d18eb-132">**JSON 字段**</span><span class="sxs-lookup"><span data-stu-id="d18eb-132">**JSON field**</span></span>|<span data-ttu-id="d18eb-133">**OMS 的自定义字段**</span><span class="sxs-lookup"><span data-stu-id="d18eb-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d18eb-134">说明</span><span class="sxs-lookup"><span data-stu-id="d18eb-134">Description</span></span>  <br/> |<span data-ttu-id="d18eb-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="d18eb-136">ResourceState</span></span>  <br/> |<span data-ttu-id="d18eb-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-138">操作名称</span><span class="sxs-lookup"><span data-stu-id="d18eb-138">OperationName</span></span>  <br/> |<span data-ttu-id="d18eb-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="d18eb-140">OperationResult</span></span>  <br/> |<span data-ttu-id="d18eb-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-142">OS</span><span class="sxs-lookup"><span data-stu-id="d18eb-142">OS</span></span>  <br/> |<span data-ttu-id="d18eb-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="d18eb-144">OSVersion</span></span>  <br/> |<span data-ttu-id="d18eb-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-146">别名</span><span class="sxs-lookup"><span data-stu-id="d18eb-146">Alias</span></span>  <br/> |<span data-ttu-id="d18eb-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-148">显示名称</span><span class="sxs-lookup"><span data-stu-id="d18eb-148">DisplayName</span></span>  <br/> |<span data-ttu-id="d18eb-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="d18eb-150">AppVersion</span></span>  <br/> |<span data-ttu-id="d18eb-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="d18eb-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="d18eb-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="d18eb-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="d18eb-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="d18eb-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="d18eb-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="d18eb-156">在 OMS 中定义 SRS v2 视图</span><span class="sxs-lookup"><span data-stu-id="d18eb-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="d18eb-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-157"></span></span>

<span data-ttu-id="d18eb-158">收集数据并映射自定义字段后，可以使用 OMS 视图设计器开发包含图块的仪表板来监控 SRS v2 事件。</span><span class="sxs-lookup"><span data-stu-id="d18eb-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="d18eb-159">使用视图设计器创建下面的拼贴，请参阅[使用视图设计器中以创建日志分析中的自定义视图](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer)所需。</span><span class="sxs-lookup"><span data-stu-id="d18eb-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="d18eb-160">创建可显示运行状况良好的设备的图块</span><span class="sxs-lookup"><span data-stu-id="d18eb-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="d18eb-161">定义该用例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-161">Define the case:</span></span> 
    
    <span data-ttu-id="d18eb-162">此图块显示在过去 10 分钟内发送过检测信号消息的所有设备。</span><span class="sxs-lookup"><span data-stu-id="d18eb-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="d18eb-163">分配组图块 </span><span class="sxs-lookup"><span data-stu-id="d18eb-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d18eb-164">选中新组框</span><span class="sxs-lookup"><span data-stu-id="d18eb-164">Check the new group box</span></span>
    
4. <span data-ttu-id="d18eb-165">添加图块图例文本</span><span class="sxs-lookup"><span data-stu-id="d18eb-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="d18eb-166">输入图块查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="d18eb-167">输入列表查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="d18eb-168">定义列标题名称</span><span class="sxs-lookup"><span data-stu-id="d18eb-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d18eb-169">定义列标题值</span><span class="sxs-lookup"><span data-stu-id="d18eb-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="d18eb-170">输入导航查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="d18eb-171">创建可显示具有连接问题的设备的图块</span><span class="sxs-lookup"><span data-stu-id="d18eb-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="d18eb-172">定义该用例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-172">Define the case:</span></span> 
    
    <span data-ttu-id="d18eb-p106">此图块显示在过去 10 分钟内未发送检测信号消息的所有设备。这些设备可能遇到网络连接问题、Exchange 连接问题或 Skype for Business 连接问题。</span><span class="sxs-lookup"><span data-stu-id="d18eb-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="d18eb-175">分配组图块 </span><span class="sxs-lookup"><span data-stu-id="d18eb-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d18eb-176">不要选中新组框。</span><span class="sxs-lookup"><span data-stu-id="d18eb-176">Do not check the new group box.</span></span> <span data-ttu-id="d18eb-177">你在创建图块 1 时已执行此操作，无需再次执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d18eb-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d18eb-178">添加图块图例文本</span><span class="sxs-lookup"><span data-stu-id="d18eb-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="d18eb-179">输入图块查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="d18eb-180">输入列表查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="d18eb-181">定义列标题名称</span><span class="sxs-lookup"><span data-stu-id="d18eb-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="d18eb-182">定义列标题值</span><span class="sxs-lookup"><span data-stu-id="d18eb-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="d18eb-183">输入导航查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="d18eb-184">列出具有硬件错误的设备 </span><span class="sxs-lookup"><span data-stu-id="d18eb-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="d18eb-185">定义该用例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-185">Define the case:</span></span> 
    
   <span data-ttu-id="d18eb-186">该拼贴显示发送一条消息，指示一个或多个硬件组件问题，在最后 10 分钟内的所有设备。</span><span class="sxs-lookup"><span data-stu-id="d18eb-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="d18eb-187">分配组图块 </span><span class="sxs-lookup"><span data-stu-id="d18eb-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d18eb-188">不要选中新组框。</span><span class="sxs-lookup"><span data-stu-id="d18eb-188">Do not check the new group box.</span></span> <span data-ttu-id="d18eb-189">你在创建图块 1 时已执行此操作，无需再次执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d18eb-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d18eb-190">图块图例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="d18eb-191">图块查询</span><span class="sxs-lookup"><span data-stu-id="d18eb-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="d18eb-192">列表查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="d18eb-193">列标题名称：</span><span class="sxs-lookup"><span data-stu-id="d18eb-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d18eb-194">列标题值：</span><span class="sxs-lookup"><span data-stu-id="d18eb-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="d18eb-195">导航查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="d18eb-196">列出具有应用错误的设备 </span><span class="sxs-lookup"><span data-stu-id="d18eb-196">List devices with an App error</span></span>

1. <span data-ttu-id="d18eb-197">定义该用例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-197">Define the case:</span></span> 
    
   <span data-ttu-id="d18eb-198">此图块显示在过去 10 分钟内报告一个或多个应用组件错误的所有 SRS 设备</span><span class="sxs-lookup"><span data-stu-id="d18eb-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="d18eb-199">分配组图块 </span><span class="sxs-lookup"><span data-stu-id="d18eb-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d18eb-200">不要选中新组框。</span><span class="sxs-lookup"><span data-stu-id="d18eb-200">Do not check the new group box.</span></span> <span data-ttu-id="d18eb-201">你在创建图块 1 时已执行此操作，无需再次执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d18eb-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d18eb-202">图块图例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="d18eb-203">图块查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="d18eb-204">列表查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="d18eb-205">列标题名称：</span><span class="sxs-lookup"><span data-stu-id="d18eb-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="d18eb-206">列标题值：</span><span class="sxs-lookup"><span data-stu-id="d18eb-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="d18eb-207">导航查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="d18eb-208">列出需要重新启动的设备</span><span class="sxs-lookup"><span data-stu-id="d18eb-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="d18eb-209">定义该用例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-209">Define the case:</span></span> 
    
   <span data-ttu-id="d18eb-210">此图块显示在过去 24 小时内已重新启动的所有 SRS 设备以及重新启动次数</span><span class="sxs-lookup"><span data-stu-id="d18eb-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="d18eb-211">分配组图块 </span><span class="sxs-lookup"><span data-stu-id="d18eb-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="d18eb-212">不要选中新组框。</span><span class="sxs-lookup"><span data-stu-id="d18eb-212">Do not check the new group box.</span></span> <span data-ttu-id="d18eb-213">你在创建图块 1 时已执行此操作，无需再次执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d18eb-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d18eb-214">图块图例：</span><span class="sxs-lookup"><span data-stu-id="d18eb-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="d18eb-215">图块查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="d18eb-216">列表查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="d18eb-217">列标题名称：</span><span class="sxs-lookup"><span data-stu-id="d18eb-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d18eb-218">列标题值：</span><span class="sxs-lookup"><span data-stu-id="d18eb-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="d18eb-219">导航查询：</span><span class="sxs-lookup"><span data-stu-id="d18eb-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="d18eb-p111">这便完成了视图创建。当前可用的警报都将在上述一个或多个图块中得到反映。</span><span class="sxs-lookup"><span data-stu-id="d18eb-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="d18eb-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d18eb-222">See also</span></span>
<span data-ttu-id="d18eb-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="d18eb-223"></span></span>

#### 

[<span data-ttu-id="d18eb-224">规划与 OMS 的 Skype 的空间系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="d18eb-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="d18eb-225">管理与 OMS 的 Skype 的空间系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="d18eb-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

