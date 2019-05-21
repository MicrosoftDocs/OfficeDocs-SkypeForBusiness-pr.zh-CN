---
title: 为 Skype for Business Server 2015 配置策略应力和性能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Skype for business Server 2015 的策略配置应力和性能工具。
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299749"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>为 Skype for Business Server 2015 配置策略应力和性能工具
 
Skype for business Server 2015 的策略配置应力和性能工具。
  
在运行 "压力和性能" 工具之前, 您可以在 Skype for Business Server 2015 中配置多个策略和其他区域:
  
- [存档策略](configuring-policies.md#ArchivingPolicy)
    
- [会议策略](configuring-policies.md#ConferencingPolicy)
    
- [联系人策略](configuring-policies.md#ContactsPolicy)
    
- [联合身份验证策略](configuring-policies.md#FederationPolicy)
    
- [呼叫许可控制策略](configuring-policies.md#CACPolicy)
    
- [语音路由规则](configuring-policies.md#VoiceRoutingRules)
    
- [会议助理应用程序](configuring-policies.md#ConfAttendantApp)
    
- [服务器呼叫寄存服务](configuring-policies.md#ServerCallParkServ)
    
- [紧急电话](configuring-policies.md#EmergencyCalls)
    
- [配置响应组应用程序](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>存档策略
<a name="ArchivingPolicy"> </a>

如果在 Skype for Business Server 拓扑中部署了存档服务器, 则可以查看 ArchivingPolicy 脚本。 如果需要更多帮助, 请查看存档和 Web 会议 cmdlet。
  
## <a name="conferencing-policy"></a>会议策略
<a name="ConferencingPolicy"> </a>

对于会议, 我们有 MeetingPolicy 脚本。 如果需要更多帮助, 请查看 Web 会议 cmdlet。
  
## <a name="contacts-policy"></a>联系人策略
<a name="ContactsPolicy"> </a>

ContactsPolicy 脚本将是你需要查看的示例。 如果需要进一步参考, IM 和状态 cmdlet 将会有所帮助。
  
## <a name="federation-policy"></a>联合身份验证策略
<a name="FederationPolicy"> </a>

联盟的示例脚本为 FederationPolicy。 要查看的 cmdlet (如果需要进一步了解) 将是边缘服务器、联合身份验证和外部访问。
  
## <a name="call-admission-control-policy"></a>呼叫许可控制策略
<a name="CACPolicy"> </a>

你可以引用此策略的 BandwidthPolicy。 呼叫许可控制 cmdlet 还将提供进一步的信息。
  
## <a name="voice-routing-rules"></a>语音路由规则
<a name="VoiceRoutingRules"> </a>

你将需要用于语音路由的 RoutingRules 示例脚本。 配置这些规则时, 请注意手机上下文 (即/Location 配置文件或/SimpleName) 和内部/外部区域代码, 以便你可以在创建用户时指定它们。 您还将在 LyncPerfTool 配置期间 (特别是 PSTN-UC 和 UC) 中需要它们。
  
例如, RoutingRules 中的**CsDialPlan** Cmdlet 调用示例中的 SimpleName 参数应用于 UserProfileGenerator 下图中的 LocationProfile 值:。)
  
![Skype for Business“加载配置”工具，“语音方案”选项卡，注意事项的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
有关详细信息, 您可以查看企业语音 cmdlet。
  
## <a name="conference-attendant-application"></a>会议助理应用程序
<a name="ConfAttendantApp"> </a>

首先查看 ConferenceAutoAttendantConfiguration 脚本。 您将需要记下 ConferencingAutoAttendant 电话号码 (默认情况下为 1121111111), 以便您可以将其输入到 LyncPerfTool 配置工具中以进行配置生成, 如下所示:
  
![显示会议加载级别和电话号码的“语音方案”选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
您将在会议和电话拨入式会议 cmdlet 中找到更多详细信息。
  
## <a name="server-call-park-service"></a>服务器呼叫寄存服务
<a name="ServerCallParkServ"> </a>

默认情况下, 这是默认禁用的。 如果需要测试, 可以查看 CallParkConfiguration 示例脚本。 此外, 请根据需要查看 "呼叫驻留" 应用程序 cmdlet。
  
## <a name="emergency-calls"></a>紧急电话
<a name="EmergencyCalls"> </a>

您需要执行以下步骤来配置紧急呼叫的压力和性能测试:
  
1. 设置紧急呼叫的语音路线。 你可以使用 RoutingRules 脚本, 并检查注释 " **Route E911 到 PSTN** ", 以获取有关如何设置此语音路由的示例。
    
    > [!CAUTION]
    > RoutingRules 中的示例命令具有数字模式, 其中包含数字119而不是911。 应避免使用 911 (或实际的本地紧急号码), 以防止在负载测试期间意外呼叫本地紧急操作员。 请记住, 此配置仅供模拟之用! 
  
2. 通过填写 UserProvisioningTool 中的**位置信息服务 "配置**" 选项卡上的值来配置地址, 如下图所示:
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 在 UserProvisioningTool 中输入所有内容后, 单击 "**生成 Iis 配置文件**" 按钮。
    
4. 现在, 将生成用于端口、子网、开关和无线访问点 (WAPs) 的 CSV 文件, 以及用于压力和性能工具的 XML 文件。 在使用 LisConfiguration 脚本配置位置信息服务 (.LIS) 时, 你可以使用 CSV 文件进行输入。 若要执行此操作, 你需要将 Locations0 文件移动到压力和性能工具可执行文件 (LyncPerfTool) 所在的文件夹。 这将允许你运行位置配置文件 (拨号计划) 方案。
    
## <a name="configuring-response-group-application"></a>配置响应组应用程序
<a name="ConfigResponseGroupApp"> </a>

示例脚本为 ResponseGroupConfiguration。 还有用于查看进一步配置详细信息的响应组应用程序 cmdlet。 下图将显示一些配置详细信息:
  
![显示现有测试工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

