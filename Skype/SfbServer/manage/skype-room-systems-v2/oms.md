---
title: 使用 OMS 管理 Skype 会议室系统 v2 设备
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/19/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
description: 本文讨论如何使用 Microsoft Operations Management Suite 以集成的端到端方式管理 Skype 会议室系统 v2 设备。
ms.openlocfilehash: 7c36203dd6f6a90ccdab801bc66ff31c4319a6e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2-devices-with-oms"></a>使用 OMS 管理 Skype 会议室系统 v2 设备
 
本文讨论如何使用 Microsoft Operations Management Suite 以集成的端到端方式管理 Skype 会议室系统 v2 设备。 
  
您可以配置 Microsoft 操作管理套件 (OMS) 提供可帮助您管理会议房间设备 （请参见[计划 Skype 的空间系统 v2 管理与 OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)和[部署 Skype 的空间系统 v2 管理与 OMS 的 Skype 的基本遥测](../../deploy/deploy-clients/with-oms.md)以了解详细信息)。 当管理解决方案成熟时，可以购买其他数据和管理功能，以创建更详细的设备性能视图。
  
## <a name="understand-the-log-entries"></a>了解日志条目
<a name="Telemetry"> </a>

当 SRS 应用在 Windows 事件日志中记录相应信息时，下列事件描述会每五分钟插入到事件日志描述字段中。 OMS 代理将这些报告传递给 OMS，其解析到您在[部署 Skype 的空间系统 OMS v2 管理](../../deploy/deploy-clients/with-oms.md)中创建仪表板。 使用仪表板可以查看单个日志条目，以根据需要确定行动方案。 
  
事件 ID 2000 和 3000 指示相关设备按预期运行。事件 ID 2001 和 3001 指示发现问题。事件 ID 4000 在下列情况下可能需要执行相应操作：与你设置的基线或组织中部署的其他设备相比，出现频率高于预期。
  
通过了解这些事件描述，可以快速提醒你出现了什么问题，并让你可以开始进行进一步的故障排除操作。
  
|**事件 ID<br/>级别**|**事件行为**|**事件描述**|
|:-----|:-----|:-----|
|2000  <br/> 信息  <br/> | 这是正常的信号事件。 每隔 5 分钟，SRS v2 检查它登录到 Skype 的业务，并具有网络和交换连接。 如果 3 个因素均为 true，则每 5 分钟将事件 ID 2000 写入到事件日志中，直到设备脱机或者有一个或多个条件不再满足。 <br/> |  {"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias@contoso.com","DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IP v6 address"} <br/> 在该示例中，所有信号条件均满足，SRS v2 设备标记为正常。如果存在错误，则应用会改为记录事件 ID 2001。  <br/> |
|2001  <br/> 错误  <br/> |这是应用错误事件。 SRS v2 每 5 分钟检查一次是否已登录到 Skype for Business 以及是否具有网络连接和 Exchange 连接。 如果一个或多个因素不为 true，则每 5 分钟将事件 ID 2001 写入事件日志，直到设备脱机或者再次满足所有条件。  <br/> |  {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ","ResourceState":"Unhealthy","OperationName":"Heartbeat","OperationResult":"Fail","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"","DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}<br/> 在该示例中，SRS v2 确定网络连接状态正常，且应用已连接到 Exchange，但粗体部分指示应用未连接到 Skype for Business。 这可能是设备或主机上的配置问题。  <br/> 网络状态显示为正常或不正常。如果状态不正常，可能是存在网络问题或者设备已拔出（但很可能还存在 Exchange 和 Skype for Business 错误）。<br/> Exchange 的状态将显示为已连接或下列选项之一： 已断开连接，连接、 AutodiscoveryError （最常见的错误），GeneralError 或 ServerVersionNotSupported。 如果状态是连接，等待下一步的健康消息发送，有其他错误参考问题在解决 Exchange 问题方面的经验与管理。  <br/> 登录状态（指示应用已登录到 Skype for Business）将显示为正常或不正常。如果状态为不正常，请派遣技术人员做进一步调查。<br/> |
|3000  <br/> 信息  <br/> |此事件验证硬件检查已运行且发现要健康。 配置硬件组件，如前面的房间显示、 麦克风、 扬声器和相机每隔 5 分钟 SRS v2 检查连接并运行正常。 如果所有组件均正常，则将在事件日志中写入事件 ID 3000。 该事件将继续以每 5 分钟一次的频率写入，直到连接的设备出现问题。  <br/> |{"Description":"HardwareCheckEngine is healthy.","ResourceState":"Healthy", "OperationName":"HardwareCheckEngine","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@contoso.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}  <br/> 在该示例中，所有硬件检查均通过。 如果存在错误，则应用会改为记录事件 ID 3001。  <br/> |
|3001  <br/> 错误事件  <br/> |这是硬件错误事件。 SRS 应用有一个进程负责每 5 分钟检查一次连接的硬件组件（会议室前面的显示器、麦克风、扬声器和摄像头）的运行状况。 如果有一个或多个组件不正常，则将在事件日志中写入事件 ID 3001。 该事件将继续以每 5 分钟一次的频率写入，直到设备问题被修复。  <br/> |{"说明":"**前的房间显示状态： 不正常。** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy. ","ResourceState":"Unhealthy","OperationName":"HardwareCheckEngine","OperationResult":"Fail","OS":"Windows 10","OSVersion":"10.0.14393.1198","Alias":"alias@contoso.com","DisplayName":"Yosemite conference room","AppVersion":"2.0.58.0","IPv4Address":"10.10.10.10","IPv6Address":"IPv6Address","IPv4Address2":"10.10.10.10"} <br/>  外围硬件显示为正常或不正常。 <br/> 在该示例中，在会议室前面配置了两个显示器，目前两个显示器均不可用。 会议麦克风状态不正常，这可能有多种原因。 由于至少有一个资源未通过检查，因此 ResourceState 显示为不正常。 请派遣技术人员做进一步调查。  <br/> |
|4000  <br/> 信息  <br/> |这是应用重启事件。 每次应用重启时，都会将此事件记录到 Windows 事件日志中。  <br/> | {"Description":"App restarts.","ResourceState":"Healthy","OperationName":"Restart","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@domain.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"} <br/> Skype for Business 应用可能会因为多种原因重启。 在考虑到功率波动和电源故障等已知问题的前提下，将相同大楼和不同大楼中的设备重启频率进行比较，因为这样可能可以为解决基础设施问题提供提示。  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="Telemetry"> </a>

#### 

[规划与 OMS 的 Skype 的空间系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[部署与 OMS 的 Skype 的空间系统 v2 管理](../../deploy/deploy-clients/with-oms.md)

