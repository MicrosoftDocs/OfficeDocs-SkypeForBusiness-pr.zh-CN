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
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d1ba7-103">配置策略的 Skype 的业务服务器 2015年压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="d1ba7-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d1ba7-104">业务服务器 2015年压力和性能工具的 Skype 的策略配置。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="d1ba7-105">有多个策略，您可以在 Skype for 配置业务服务器 2015年之前运行压力和性能工具的其他方面：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="d1ba7-106">存档策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="d1ba7-107">会议策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="d1ba7-108">联系人策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="d1ba7-109">联合身份验证策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="d1ba7-110">呼叫允许控制策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="d1ba7-111">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="d1ba7-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="d1ba7-112">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="d1ba7-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="d1ba7-113">服务器呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="d1ba7-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="d1ba7-114">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="d1ba7-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="d1ba7-115">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="d1ba7-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="d1ba7-116">存档策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-116">Archiving policy</span></span>
<span data-ttu-id="d1ba7-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-117"></span></span>

<span data-ttu-id="d1ba7-118">如果必须在您 Skype 企业服务器拓扑中部署存档服务器，您可以查看 ArchivingPolicy.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="d1ba7-119">如果需要进一步的协助，签出的存档和 Web 会议的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="d1ba7-120">会议策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-120">Conferencing policy</span></span>
<span data-ttu-id="d1ba7-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-121"></span></span>

<span data-ttu-id="d1ba7-122">对于会议，我们已 MeetingPolicy.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="d1ba7-123">如果需要进一步的协助，签出的 Web 会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="d1ba7-124">联系人策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-124">Contacts policy</span></span>
<span data-ttu-id="d1ba7-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-125"></span></span>

<span data-ttu-id="d1ba7-126">ContactsPolicy.ps1 脚本将查看您所需的示例。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="d1ba7-127">IM 和状态 cmdlet 将帮助如果需要进一步的引用。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="d1ba7-128">联合身份验证策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-128">Federation policy</span></span>
<span data-ttu-id="d1ba7-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-129"></span></span>

<span data-ttu-id="d1ba7-130">联合身份验证的示例脚本是 FederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="d1ba7-131">若要查看，如果需要进一步的洞察力 cmdlet 将边缘服务器、 联盟和外部访问。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="d1ba7-132">呼叫允许控制策略</span><span class="sxs-lookup"><span data-stu-id="d1ba7-132">Call Admission Control policy</span></span>
<span data-ttu-id="d1ba7-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-133"></span></span>

<span data-ttu-id="d1ba7-134">此策略，可以引用 BandwidthPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="d1ba7-135">呼叫允许控制 cmdlet 都将具有进一步的信息以及。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="d1ba7-136">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="d1ba7-136">Voice Routing rules</span></span>
<span data-ttu-id="d1ba7-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-137"></span></span>

<span data-ttu-id="d1ba7-138">您将需要 RoutingRules.ps1 示例脚本，为语音路由。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="d1ba7-139">当您正在配置这些规则时，注意的电话上下文 （即，/Location 配置文件或 /SimpleName） 和内部/外部区域代码，以便您可以创建用户时指定它们。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="d1ba7-140">您还需要这些 LyncPerfTool （特别是对于 PSTN UC 和 UC-PSTN） 的配置过程中。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="d1ba7-141">例如，对 RoutingRules.ps1 示例中的**新建 CsDialPlan** cmdlet 的调用中的 SimpleName 参数应使用在下图中的 UserProfileGenerator.exe LocationProfile 值：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business“加载配置”工具，“语音方案”选项卡，注意事项的高级设置。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="d1ba7-143">有关详细信息，您可以查看的企业语音 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="d1ba7-144">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="d1ba7-144">Conference Attendant application</span></span>
<span data-ttu-id="d1ba7-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-145"></span></span>

<span data-ttu-id="d1ba7-146">首次查看 ConferenceAutoAttendantConfiguration.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="d1ba7-147">您需要注意的 ConferencingAutoAttendant 电话号码 (默认情况下 1121111111)，以便您可以将其输入 LyncPerfTool 配置工具配置生成时，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![显示会议加载级别和电话号码的“语音方案”选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="d1ba7-149">您将找到更多详细信息，在会议和电话拨入式会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="d1ba7-150">服务器呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="d1ba7-150">Server Call Park service</span></span>
<span data-ttu-id="d1ba7-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-151"></span></span>

<span data-ttu-id="d1ba7-152">默认情况下，这是实际禁用。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-152">This is actually disabled by default.</span></span> <span data-ttu-id="d1ba7-153">如果您需要对此进行测试，则可以查看 CallParkConfiguration.ps1 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="d1ba7-154">此外，签出的呼叫寄存应用程序 cmdlet，根据需要。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="d1ba7-155">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="d1ba7-155">Emergency calls</span></span>
<span data-ttu-id="d1ba7-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-156"></span></span>

<span data-ttu-id="d1ba7-157">您将需要执行以下步骤来配置压力和性能测试用于紧急呼叫：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="d1ba7-158">设置紧急呼叫的语音路由。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="d1ba7-159">您可以使用 RoutingRules.ps1 脚本，并举例说明如何设置该语音路由的注释"**路由到 PSTN 的 E911** "下检查。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d1ba7-160">RoutingRules.ps1 中的示例命令具有包括 119，而不是 911 的数量的号码模式。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="d1ba7-161">您应避免使用 911 （或实际本地紧急电话号码） 您负载测试过程中阻止意外呼叫您的本地紧急运算符。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="d1ba7-162">请记住，此配置仅用于模拟 ！</span><span class="sxs-lookup"><span data-stu-id="d1ba7-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="d1ba7-163">下图中所示填写 UserProvisioningTool，**位置信息服务配置**选项卡上的值，在配置地址：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="d1ba7-165">当您已输入所有 UserProvisioningTool 时，单击**生成 LIS 配置文件**按钮。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="d1ba7-166">现在将生成 CSV 文件的端口、 子网、 交换机和无线访问点 (Wap)，以及压力和性能工具 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="d1ba7-167">配置与 LisConfiguration.ps1 脚本的位置信息服务 (LIS) 时，可用于输入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="d1ba7-168">若要执行此操作，您需要将 Locations0.xml 文件移动到与压力和性能工具可执行 (LyncPerfTool.exe) 相同的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="d1ba7-169">这会让您运行配置文件 （拨号计划） 的方案的位置。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="d1ba7-170">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="d1ba7-170">Configuring Response Group application</span></span>
<span data-ttu-id="d1ba7-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ba7-171"></span></span>

<span data-ttu-id="d1ba7-172">示例脚本是 ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="d1ba7-173">也有响应组应用程序 cmdlet 可查看有关配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d1ba7-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="d1ba7-174">下图将介绍一些配置详细信息：</span><span class="sxs-lookup"><span data-stu-id="d1ba7-174">The following diagram will show some of the configuration details:</span></span>
  
![显示现有测试工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

