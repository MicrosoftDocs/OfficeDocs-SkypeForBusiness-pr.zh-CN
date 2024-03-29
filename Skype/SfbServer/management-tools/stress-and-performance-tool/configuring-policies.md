---
title: Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 适用于 2015 Skype for Business Server和性能工具的策略配置。
---

# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool
 
适用于 2015 Skype for Business Server和性能工具的策略配置。
  
在运行压力和性能工具之前，可以在 Skype for Business Server 2015 中配置多个策略和其他区域：
  
- [存档策略](configuring-policies.md#ArchivingPolicy)
    
- [会议策略](configuring-policies.md#ConferencingPolicy)
    
- [联系人策略](configuring-policies.md#ContactsPolicy)
    
- [联合策略](configuring-policies.md#FederationPolicy)
    
- [呼叫允许控制策略](configuring-policies.md#CACPolicy)
    
- [语音路由规则](configuring-policies.md#VoiceRoutingRules)
    
- [会议助理应用程序](configuring-policies.md#ConfAttendantApp)
    
- [服务器呼叫管理服务](configuring-policies.md#ServerCallParkServ)
    
- [紧急呼叫](configuring-policies.md#EmergencyCalls)
    
- [配置响应组应用程序](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>存档策略
<a name="ArchivingPolicy"> </a>

如果您的存档服务器部署在 Skype for Business Server 拓扑中，则您可查看该ArchivingPolicy.ps1脚本。 如果您需要进一步的帮助，请查看存档和 Web 会议 cmdlet。
  
## <a name="conferencing-policy"></a>会议策略
<a name="ConferencingPolicy"> </a>

对于会议，我们具有MeetingPolicy.ps1脚本。 如果您需要进一步的帮助，请查看 Web 会议 cmdlet。
  
## <a name="contacts-policy"></a>联系人策略
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1脚本将是需要查看的示例。 如果您需要进一步的引用，IM 和状态 cmdlet 将提供帮助。
  
## <a name="federation-policy"></a>联合策略
<a name="FederationPolicy"> </a>

联合身份验证的示例脚本FederationPolicy.ps1。 需要查看的 cmdlet 包括边缘服务器、联盟和外部访问（如果需要进一步见解）。
  
## <a name="call-admission-control-policy"></a>呼叫允许控制策略
<a name="CACPolicy"> </a>

你可以引用BandwidthPolicy.ps1策略的一个策略。 呼叫允许控制 cmdlet 还将包含更多信息。
  
## <a name="voice-routing-rules"></a>语音路由规则
<a name="VoiceRoutingRules"> </a>

需要语音路由RoutingRules.ps1示例脚本。 配置这些规则时，请记下电话上下文 (即 /Location Profile 或 /SimpleName) 和内部/外部区号，以便可以在创建用户时指定它们。 在 LyncPerfTool 配置过程中，您还需要这些 (专用于 PSTN-UC 和 UC-PSTN) 。
  
例如，对 RoutingRules.ps1 示例中 **New-CsDialPlan** cmdlet 的调用中的 SimpleName 参数应该用于以下示例图中的 LocationProfile UserProfileGenerator.exe：
  
![Skype for Business加载配置工具、语音方案选项卡、对话的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
有关详细信息，你可以查看企业语音 cmdlet。
  
## <a name="conference-attendant-application"></a>会议助理应用程序
<a name="ConfAttendantApp"> </a>

首先查看ConferenceAutoAttendantConfiguration.ps1脚本。 默认情况下，您需要记下 ConferencingAutoAttendant 电话号码)  (1121111111，以便你可以将电话号码输入 LyncPerfTool 配置工具以生成配置，如下所示：
  
![显示会议负载级别和电话号码的"语音方案"选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
有关详细信息，请参阅会议和电话拨入式会议 cmdlet。
  
## <a name="server-call-park-service"></a>服务器呼叫管理服务
<a name="ServerCallParkServ"> </a>

默认情况下，这实际上是禁用的。 如果需要测试CallParkConfiguration.ps1，请查看示例脚本。 此外，根据需要查看呼叫管理应用程序 cmdlet。
  
## <a name="emergency-calls"></a>紧急呼叫
<a name="EmergencyCalls"> </a>

你需要执行以下步骤来配置紧急呼叫的压力和性能测试：
  
1. 为紧急呼叫设置语音路由。 可以使用此RoutingRules.ps1脚本，并检查注释" **Route E911 to PSTN** "下，了解如何设置此语音路由的示例。
    
    > [!CAUTION]
    > 本示例中的示例RoutingRules.ps1包含数字 119 而不是 911 的号码模式。 应避免使用 911 (或实际本地紧急号码) ，以免在负载测试期间意外呼叫本地紧急接线员。 请记住，此配置仅供模拟！ 
  
2. 通过填写 UserProvisioningTool 中"位置 **信息服务配置** "选项卡上的值来配置地址，如下图所示：
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 在 UserProvisioningTool 中输入所有内容后，单击"生成 **LIS 配置文件"** 按钮。
    
4. 现在，将生成端口、子网、交换机和无线访问点 (WAPs) 的 CSV 文件，以及用于 Stress and Performance 工具的 XML 文件。 在使用 LIS 脚本配置位置信息服务 (，可以使用 CSV) 进行LisConfiguration.ps1操作。 为此，你需要将 Locations0.xml 文件移动到与 Stress and Performance Tool 可执行 (LyncPerfTool.exe 文件相同的) 。 这将让你在拨号计划中运行 (配置文件) 方案。
    
## <a name="configuring-response-group-application"></a>配置响应组应用程序
<a name="ConfigResponseGroupApp"> </a>

示例脚本ResponseGroupConfiguration.ps1。 还需要查看响应组应用程序 cmdlet，了解进一步的配置详细信息。 下图将显示一些配置详细信息：
  
![显示要测试的现有工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

