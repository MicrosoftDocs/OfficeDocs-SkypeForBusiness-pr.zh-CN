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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Skype for business Server 2015 的策略配置应力和性能工具。
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816191"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a5d17-103">为 Skype for Business Server 2015 配置策略应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="a5d17-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="a5d17-104">Skype for business Server 2015 的策略配置应力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="a5d17-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="a5d17-105">在运行 "压力和性能" 工具之前，您可以在 Skype for Business Server 2015 中配置多个策略和其他区域：</span><span class="sxs-lookup"><span data-stu-id="a5d17-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="a5d17-106">存档策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="a5d17-107">会议策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="a5d17-108">联系人策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="a5d17-109">联合身份验证策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="a5d17-110">呼叫许可控制策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="a5d17-111">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="a5d17-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="a5d17-112">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="a5d17-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="a5d17-113">服务器呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="a5d17-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="a5d17-114">紧急电话</span><span class="sxs-lookup"><span data-stu-id="a5d17-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="a5d17-115">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="a5d17-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="a5d17-116">存档策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-116">Archiving policy</span></span>
<span data-ttu-id="a5d17-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="a5d17-118">如果在 Skype for Business Server 拓扑中部署了存档服务器，则可以查看 ArchivingPolicy 脚本。</span><span class="sxs-lookup"><span data-stu-id="a5d17-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="a5d17-119">如果需要更多帮助，请查看存档和 Web 会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5d17-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="a5d17-120">会议策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-120">Conferencing policy</span></span>
<span data-ttu-id="a5d17-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="a5d17-122">对于会议，我们有 MeetingPolicy 脚本。</span><span class="sxs-lookup"><span data-stu-id="a5d17-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="a5d17-123">如果需要更多帮助，请查看 Web 会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5d17-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="a5d17-124">联系人策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-124">Contacts policy</span></span>
<span data-ttu-id="a5d17-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="a5d17-126">ContactsPolicy 脚本将是你需要查看的示例。</span><span class="sxs-lookup"><span data-stu-id="a5d17-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="a5d17-127">如果需要进一步参考，IM 和状态 cmdlet 将会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="a5d17-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="a5d17-128">联合身份验证策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-128">Federation policy</span></span>
<span data-ttu-id="a5d17-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="a5d17-130">联盟的示例脚本为 FederationPolicy。</span><span class="sxs-lookup"><span data-stu-id="a5d17-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="a5d17-131">要查看的 cmdlet （如果需要进一步了解）将是边缘服务器、联合身份验证和外部访问。</span><span class="sxs-lookup"><span data-stu-id="a5d17-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="a5d17-132">呼叫许可控制策略</span><span class="sxs-lookup"><span data-stu-id="a5d17-132">Call Admission Control policy</span></span>
<span data-ttu-id="a5d17-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="a5d17-134">你可以引用此策略的 BandwidthPolicy。</span><span class="sxs-lookup"><span data-stu-id="a5d17-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="a5d17-135">呼叫许可控制 cmdlet 还将提供进一步的信息。</span><span class="sxs-lookup"><span data-stu-id="a5d17-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="a5d17-136">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="a5d17-136">Voice Routing rules</span></span>
<span data-ttu-id="a5d17-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="a5d17-138">你将需要用于语音路由的 RoutingRules 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a5d17-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="a5d17-139">配置这些规则时，请注意手机上下文（即/Location 配置文件或/SimpleName）和内部/外部区域代码，以便你可以在创建用户时指定它们。</span><span class="sxs-lookup"><span data-stu-id="a5d17-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="a5d17-140">您还将在 LyncPerfTool 配置期间（特别是 PSTN-UC 和 UC）中需要它们。</span><span class="sxs-lookup"><span data-stu-id="a5d17-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="a5d17-141">例如，RoutingRules 中的**CsDialPlan** Cmdlet 调用示例中的 SimpleName 参数应用于 UserProfileGenerator 下图中的 LocationProfile 值：。）</span><span class="sxs-lookup"><span data-stu-id="a5d17-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business“加载配置”工具，“语音方案”选项卡，注意事项的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="a5d17-143">有关详细信息，您可以查看企业语音 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5d17-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="a5d17-144">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="a5d17-144">Conference Attendant application</span></span>
<span data-ttu-id="a5d17-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="a5d17-146">首先查看 ConferenceAutoAttendantConfiguration 脚本。</span><span class="sxs-lookup"><span data-stu-id="a5d17-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="a5d17-147">您将需要记下 ConferencingAutoAttendant 电话号码（默认情况下为1121111111），以便您可以将其输入到 LyncPerfTool 配置工具中以进行配置生成，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5d17-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![显示会议加载级别和电话号码的“语音方案”选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="a5d17-149">您将在会议和电话拨入式会议 cmdlet 中找到更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a5d17-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="a5d17-150">服务器呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="a5d17-150">Server Call Park service</span></span>
<span data-ttu-id="a5d17-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="a5d17-152">默认情况下，这是默认禁用的。</span><span class="sxs-lookup"><span data-stu-id="a5d17-152">This is actually disabled by default.</span></span> <span data-ttu-id="a5d17-153">如果需要测试，可以查看 CallParkConfiguration 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a5d17-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="a5d17-154">此外，请根据需要查看 "呼叫驻留" 应用程序 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5d17-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="a5d17-155">紧急电话</span><span class="sxs-lookup"><span data-stu-id="a5d17-155">Emergency calls</span></span>
<span data-ttu-id="a5d17-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="a5d17-157">您需要执行以下步骤来配置紧急呼叫的压力和性能测试：</span><span class="sxs-lookup"><span data-stu-id="a5d17-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="a5d17-158">设置紧急呼叫的语音路线。</span><span class="sxs-lookup"><span data-stu-id="a5d17-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="a5d17-159">你可以使用 RoutingRules 脚本，并检查注释 " **Route E911 到 PSTN** "，以获取有关如何设置此语音路由的示例。</span><span class="sxs-lookup"><span data-stu-id="a5d17-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a5d17-160">RoutingRules 中的示例命令具有数字模式，其中包含数字119而不是911。</span><span class="sxs-lookup"><span data-stu-id="a5d17-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="a5d17-161">应避免使用911（或实际的本地紧急号码），以防止在负载测试期间意外呼叫本地紧急操作员。</span><span class="sxs-lookup"><span data-stu-id="a5d17-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="a5d17-162">请记住，此配置仅供模拟之用！</span><span class="sxs-lookup"><span data-stu-id="a5d17-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="a5d17-163">通过填写 UserProvisioningTool 中的**位置信息服务 "配置**" 选项卡上的值来配置地址，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="a5d17-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="a5d17-165">在 UserProvisioningTool 中输入所有内容后，单击 "**生成 Iis 配置文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a5d17-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="a5d17-166">现在，将生成用于端口、子网、开关和无线访问点（WAPs）的 CSV 文件，以及用于压力和性能工具的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a5d17-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="a5d17-167">在使用 LisConfiguration 脚本配置位置信息服务（.LIS）时，你可以使用 CSV 文件进行输入。</span><span class="sxs-lookup"><span data-stu-id="a5d17-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="a5d17-168">若要执行此操作，你需要将 Locations0 文件移动到压力和性能工具可执行文件（LyncPerfTool）所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a5d17-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="a5d17-169">这将允许你运行位置配置文件（拨号计划）方案。</span><span class="sxs-lookup"><span data-stu-id="a5d17-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="a5d17-170">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="a5d17-170">Configuring Response Group application</span></span>
<span data-ttu-id="a5d17-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a5d17-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="a5d17-172">示例脚本为 ResponseGroupConfiguration。</span><span class="sxs-lookup"><span data-stu-id="a5d17-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="a5d17-173">还有用于查看进一步配置详细信息的响应组应用程序 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5d17-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="a5d17-174">下图将显示一些配置详细信息：</span><span class="sxs-lookup"><span data-stu-id="a5d17-174">The following diagram will show some of the configuration details:</span></span>
  
![显示现有测试工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

