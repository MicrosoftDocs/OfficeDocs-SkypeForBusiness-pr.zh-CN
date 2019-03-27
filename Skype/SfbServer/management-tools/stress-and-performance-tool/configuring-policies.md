---
title: 配置策略的 Skype 的业务服务器 2015年压力和性能工具
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 业务服务器 2015年压力和性能工具的 Skype 的策略配置。
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881205"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>配置策略的 Skype 的业务服务器 2015年压力和性能工具
 
业务服务器 2015年压力和性能工具的 Skype 的策略配置。
  
有多个策略，您可以在 Skype for 配置业务服务器 2015年之前运行压力和性能工具的其他方面：
  
- [存档策略](configuring-policies.md#ArchivingPolicy)
    
- [会议策略](configuring-policies.md#ConferencingPolicy)
    
- [联系人策略](configuring-policies.md#ContactsPolicy)
    
- [联合身份验证策略](configuring-policies.md#FederationPolicy)
    
- [呼叫允许控制策略](configuring-policies.md#CACPolicy)
    
- [语音路由规则](configuring-policies.md#VoiceRoutingRules)
    
- [会议助理应用程序](configuring-policies.md#ConfAttendantApp)
    
- [服务器呼叫寄存服务](configuring-policies.md#ServerCallParkServ)
    
- [紧急呼叫](configuring-policies.md#EmergencyCalls)
    
- [配置响应组应用程序](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>存档策略
<a name="ArchivingPolicy"> </a>

如果必须在您 Skype 企业服务器拓扑中部署存档服务器，您可以查看 ArchivingPolicy.ps1 脚本。 如果需要进一步的协助，签出的存档和 Web 会议的 cmdlet。
  
## <a name="conferencing-policy"></a>会议策略
<a name="ConferencingPolicy"> </a>

对于会议，我们已 MeetingPolicy.ps1 脚本。 如果需要进一步的协助，签出的 Web 会议 cmdlet。
  
## <a name="contacts-policy"></a>联系人策略
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 脚本将查看您所需的示例。 IM 和状态 cmdlet 将帮助如果需要进一步的引用。
  
## <a name="federation-policy"></a>联合身份验证策略
<a name="FederationPolicy"> </a>

联合身份验证的示例脚本是 FederationPolicy.ps1。 若要查看，如果需要进一步的洞察力 cmdlet 将边缘服务器、 联盟和外部访问。
  
## <a name="call-admission-control-policy"></a>呼叫允许控制策略
<a name="CACPolicy"> </a>

此策略，可以引用 BandwidthPolicy.ps1。 呼叫允许控制 cmdlet 都将具有进一步的信息以及。
  
## <a name="voice-routing-rules"></a>语音路由规则
<a name="VoiceRoutingRules"> </a>

您将需要 RoutingRules.ps1 示例脚本，为语音路由。 当您正在配置这些规则时，注意的电话上下文 （即，/Location 配置文件或 /SimpleName） 和内部/外部区域代码，以便您可以创建用户时指定它们。 您还需要这些 LyncPerfTool （特别是对于 PSTN UC 和 UC-PSTN） 的配置过程中。
  
例如，对 RoutingRules.ps1 示例中的**新建 CsDialPlan** cmdlet 的调用中的 SimpleName 参数应使用在下图中的 UserProfileGenerator.exe LocationProfile 值：
  
![Skype for Business“加载配置”工具，“语音方案”选项卡，注意事项的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
有关详细信息，您可以查看的企业语音 cmdlet。
  
## <a name="conference-attendant-application"></a>会议助理应用程序
<a name="ConfAttendantApp"> </a>

首次查看 ConferenceAutoAttendantConfiguration.ps1 脚本。 您需要注意的 ConferencingAutoAttendant 电话号码 (默认情况下 1121111111)，以便您可以将其输入 LyncPerfTool 配置工具配置生成时，如下所示：
  
![显示会议加载级别和电话号码的“语音方案”选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
您将找到更多详细信息，在会议和电话拨入式会议 cmdlet。
  
## <a name="server-call-park-service"></a>服务器呼叫寄存服务
<a name="ServerCallParkServ"> </a>

默认情况下，这是实际禁用。 如果您需要对此进行测试，则可以查看 CallParkConfiguration.ps1 示例脚本。 此外，签出的呼叫寄存应用程序 cmdlet，根据需要。
  
## <a name="emergency-calls"></a>紧急呼叫
<a name="EmergencyCalls"> </a>

您将需要执行以下步骤来配置压力和性能测试用于紧急呼叫：
  
1. 设置紧急呼叫的语音路由。 您可以使用 RoutingRules.ps1 脚本，并举例说明如何设置该语音路由的注释"**路由到 PSTN 的 E911** "下检查。
    
    > [!CAUTION]
    > RoutingRules.ps1 中的示例命令具有包括 119，而不是 911 的数量的号码模式。 您应避免使用 911 （或实际本地紧急电话号码） 您负载测试过程中阻止意外呼叫您的本地紧急运算符。 请记住，此配置仅用于模拟 ！ 
  
2. 下图中所示填写 UserProvisioningTool，**位置信息服务配置**选项卡上的值，在配置地址：
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 当您已输入所有 UserProvisioningTool 时，单击**生成 LIS 配置文件**按钮。
    
4. 现在将生成 CSV 文件的端口、 子网、 交换机和无线访问点 (Wap)，以及压力和性能工具 XML 文件。 配置与 LisConfiguration.ps1 脚本的位置信息服务 (LIS) 时，可用于输入 CSV 文件。 若要执行此操作，您需要将 Locations0.xml 文件移动到与压力和性能工具可执行 (LyncPerfTool.exe) 相同的文件夹。 这会让您运行配置文件 （拨号计划） 的方案的位置。
    
## <a name="configuring-response-group-application"></a>配置响应组应用程序
<a name="ConfigResponseGroupApp"> </a>

示例脚本是 ResponseGroupConfiguration.ps1。 也有响应组应用程序 cmdlet 可查看有关配置的详细信息。 下图将介绍一些配置详细信息：
  
![显示现有测试工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

