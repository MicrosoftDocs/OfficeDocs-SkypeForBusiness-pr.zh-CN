---
title: 配置策略的 Skype 业务服务器 2015年的压力和性能工具
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 业务服务器 2015年压力和性能工具 Skype 的的策略配置。
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>配置策略的 Skype 业务服务器 2015年的压力和性能工具
 
业务服务器 2015年压力和性能工具 Skype 的的策略配置。
  
有几个政策和其他区域，您可以配置在 Skype 的业务服务器 2015 之前运行的压力和性能工具,：
  
- [存档策略](configuring-policies.md#ArchivingPolicy)
    
- [会议策略](configuring-policies.md#ConferencingPolicy)
    
- [联系人的策略](configuring-policies.md#ContactsPolicy)
    
- [联合身份验证策略](configuring-policies.md#FederationPolicy)
    
- [调用许可控制策略](configuring-policies.md#CACPolicy)
    
- [语音路由规则](configuring-policies.md#VoiceRoutingRules)
    
- [会议助理应用程序](configuring-policies.md#ConfAttendantApp)
    
- [服务器调用公园服务](configuring-policies.md#ServerCallParkServ)
    
- [紧急电话](configuring-policies.md#EmergencyCalls)
    
- [配置响应组应用程序](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>存档策略
<a name="ArchivingPolicy"> </a>

如果您有在您 Skype 业务服务器拓扑中部署存档服务器，您可以查看 ArchivingPolicy.ps1 脚本。 如果需要进一步的帮助，查看存档和 Web 会议 cmdlet。
  
## <a name="conferencing-policy"></a>会议策略
<a name="ConferencingPolicy"> </a>

对于会议，我们有 MeetingPolicy.ps1 脚本。 如果需要进一步的协助，签出的 Web 会议 cmdlet。
  
## <a name="contacts-policy"></a>联系人的策略
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 脚本将需要检查的示例。 IM 和状态 cmdlet 将帮助如果您需要进一步的参考。
  
## <a name="federation-policy"></a>联合身份验证策略
<a name="FederationPolicy"> </a>

联合身份验证的示例脚本是 FederationPolicy.ps1。 这些 cmdlet 来审查，如果需要进一步的洞察力，将边缘服务器、 联盟和外部访问。
  
## <a name="call-admission-control-policy"></a>调用许可控制策略
<a name="CACPolicy"> </a>

此策略，您可以引用 BandwidthPolicy.ps1。 调用许可控制 cmdlet 都有进一步的信息也。
  
## <a name="voice-routing-rules"></a>语音路由规则
<a name="VoiceRoutingRules"> </a>

您将需要 RoutingRules.ps1 示例脚本为语音路由。 在配置这些规则时，记下电话上下文 （即 /Location 配置文件或 /SimpleName） 和内部/外部区域代码，以便您可以在创建用户时指定它们。 您也需要它们 （专门为 PSTN UC 和 UC PSTN） 的 LyncPerfTool 配置过程。
  
例如，在下图中的 UserProfileGenerator.exe 的 LocationProfile 值应使用调用**New CsDialPlan** cmdlet RoutingRules.ps1 示例中的 SimpleName 参数：
  
![Skype for Business“加载配置”工具，“语音方案”选项卡，注意事项的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
有关详细信息，您可以查看企业语音 cmdlet。
  
## <a name="conference-attendant-application"></a>会议助理应用程序
<a name="ConfAttendantApp"> </a>

首先查看 ConferenceAutoAttendantConfiguration.ps1 脚本。 您需要记 ConferencingAutoAttendant 电话号码 (默认为 1121111111)，以便您可以将其输入 LyncPerfTool 配置工具用于配置生成过程，如下所示：
  
![显示会议加载级别和电话号码的“语音方案”选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
您可以找到更多详细信息在会议和拨入会议 cmdlet。
  
## <a name="server-call-park-service"></a>服务器调用公园服务
<a name="ServerCallParkServ"> </a>

这实际上是默认情况下禁用。 如果您需要对此进行测试，您可以查看 CallParkConfiguration.ps1 的示例脚本。 此外，检查出调用应用程序公园 cmdlet，根据需要。
  
## <a name="emergency-calls"></a>紧急电话
<a name="EmergencyCalls"> </a>

您将需要执行以下步骤来配置压力和性能测试的紧急电话：
  
1. 设置了紧急电话的语音路由。 可以使用 RoutingRules.ps1 脚本，并举例说明如何设置此语音路由在注释"**到 PSTN 路由 E911** "下检查。
    
    > [!CAUTION]
    > 在 RoutingRules.ps1 中的命令示例有包括 119 比 911 号号码模式。 您应该避免使用 911 （或实际本地紧急电话号码） 以在负载测试过程中防止意外求助电话您本地的紧急运算符。 请记住，这种配置是出于模拟目的只 ！ 
  
2. 通过填写的值 UserProvisioningTool，**位置信息服务配置**选项卡上配置地址，如下图所示：
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 当您输入的所有内容到 UserProvisioningTool 时，请单击**生成 LIS 配置文件**按钮。
    
4. 现在将生成端口、 子网、 交换机和无线访问点 (Wap) 的 CSV 文件，以及压力和性能工具的 XML 文件。 使用 LisConfiguration.ps1 脚本配置 (LIS) 的位置信息服务时，可以输入使用 CSV 文件。 若要执行此操作，您需要将 Locations0.xml 文件移动到同一文件夹中的压力和性能工具可执行文件 (LyncPerfTool.exe)。 这将允许您运行配置 （拨号计划） 方案的位置。
    
## <a name="configuring-response-group-application"></a>配置响应组应用程序
<a name="ConfigResponseGroupApp"> </a>

示例脚本是 ResponseGroupConfiguration.ps1。 也有一些响应组应用 cmdlet 以查看有关配置的详细信息。 下面的关系图将给出几种配置详细信息：
  
![显示现有测试工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

