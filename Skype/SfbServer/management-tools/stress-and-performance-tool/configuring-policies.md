---
title: 为 Skype for Business Server 2015 压力和性能工具配置策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 压力和性能工具的策略配置。
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815032"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a4a35-103">为 Skype for Business Server 2015 压力和性能工具配置策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="a4a35-104">Skype for Business Server 2015 压力和性能工具的策略配置。</span><span class="sxs-lookup"><span data-stu-id="a4a35-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="a4a35-105">在运行压力和性能工具之前，可以在 Skype for Business Server 2015 中配置多个策略和其他区域：</span><span class="sxs-lookup"><span data-stu-id="a4a35-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="a4a35-106">存档策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="a4a35-107">会议策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="a4a35-108">联系人策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="a4a35-109">联盟策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="a4a35-110">呼叫允许控制策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="a4a35-111">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="a4a35-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="a4a35-112">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="a4a35-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="a4a35-113">服务器呼叫管理服务</span><span class="sxs-lookup"><span data-stu-id="a4a35-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="a4a35-114">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="a4a35-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="a4a35-115">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="a4a35-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="a4a35-116">存档策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-116">Archiving policy</span></span>
<span data-ttu-id="a4a35-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="a4a35-118">如果你在 Skype for Business Server 拓扑中部署了存档服务器，你可以查看ArchivingPolicy.ps1脚本。</span><span class="sxs-lookup"><span data-stu-id="a4a35-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="a4a35-119">如果您需要进一步帮助，请查看存档和 Web 会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4a35-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="a4a35-120">会议策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-120">Conferencing policy</span></span>
<span data-ttu-id="a4a35-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="a4a35-122">对于会议，我们有MeetingPolicy.ps1脚本。</span><span class="sxs-lookup"><span data-stu-id="a4a35-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="a4a35-123">如果您需要进一步帮助，请查看 Web 会议 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4a35-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="a4a35-124">联系人策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-124">Contacts policy</span></span>
<span data-ttu-id="a4a35-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="a4a35-126">ContactsPolicy.ps1脚本将是你需要查看的示例。</span><span class="sxs-lookup"><span data-stu-id="a4a35-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="a4a35-127">如果需要进一步引用，IM 和状态 cmdlet 将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="a4a35-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="a4a35-128">联盟策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-128">Federation policy</span></span>
<span data-ttu-id="a4a35-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="a4a35-130">联合身份验证的示例脚本FederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="a4a35-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="a4a35-131">需要查看的 cmdlet（如果需要进一步见解）将是边缘服务器、联盟和外部访问。</span><span class="sxs-lookup"><span data-stu-id="a4a35-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="a4a35-132">呼叫允许控制策略</span><span class="sxs-lookup"><span data-stu-id="a4a35-132">Call Admission Control policy</span></span>
<span data-ttu-id="a4a35-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="a4a35-134">你可以引用BandwidthPolicy.ps1策略。</span><span class="sxs-lookup"><span data-stu-id="a4a35-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="a4a35-135">呼叫允许控制 cmdlet 还将包含更多信息。</span><span class="sxs-lookup"><span data-stu-id="a4a35-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="a4a35-136">语音路由规则</span><span class="sxs-lookup"><span data-stu-id="a4a35-136">Voice Routing rules</span></span>
<span data-ttu-id="a4a35-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="a4a35-138">你需要语音路由RoutingRules.ps1示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a4a35-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="a4a35-139">配置这些规则时，请记下电话上下文 (即 /Location Profile 或 /SimpleName) 和 Internal/External Area Codes，以便您可以在创建用户时指定它们。</span><span class="sxs-lookup"><span data-stu-id="a4a35-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="a4a35-140">在 LyncPerfTool 配置过程中，您还需要 (PSTN-UC 和 UC-PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="a4a35-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="a4a35-141">例如，对 RoutingRules.ps1 示例中 **New-CsDialPlan** cmdlet 的调用中的 SimpleName 参数应该用于以下图表的 LocationProfile UserProfileGenerator.exe：</span><span class="sxs-lookup"><span data-stu-id="a4a35-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business load configuration tool， voice scenarios tab， Advanced settings for Conversations.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="a4a35-143">有关详细信息，你可以查看企业语音 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4a35-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="a4a35-144">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="a4a35-144">Conference Attendant application</span></span>
<span data-ttu-id="a4a35-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="a4a35-146">首先查看ConferenceAutoAttendantConfiguration.ps1脚本。</span><span class="sxs-lookup"><span data-stu-id="a4a35-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="a4a35-147">默认情况下，您需要记下 ConferencingAutoAttendant 电话号码 (11211111111111) ，以便你可以将电话号码输入 LyncPerfTool 配置工具以生成配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4a35-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![显示会议负载级别和电话号码的"语音方案"选项卡。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="a4a35-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a4a35-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="a4a35-150">服务器呼叫管理服务</span><span class="sxs-lookup"><span data-stu-id="a4a35-150">Server Call Park service</span></span>
<span data-ttu-id="a4a35-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="a4a35-152">默认情况下，这实际上是禁用的。</span><span class="sxs-lookup"><span data-stu-id="a4a35-152">This is actually disabled by default.</span></span> <span data-ttu-id="a4a35-153">如果需要测试CallParkConfiguration.ps1，请查看示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a4a35-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="a4a35-154">此外，根据需要查看呼叫管理应用程序 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4a35-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="a4a35-155">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="a4a35-155">Emergency calls</span></span>
<span data-ttu-id="a4a35-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="a4a35-157">你需要执行以下步骤来配置紧急呼叫的压力和性能测试：</span><span class="sxs-lookup"><span data-stu-id="a4a35-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="a4a35-158">为紧急呼叫设置语音路由。</span><span class="sxs-lookup"><span data-stu-id="a4a35-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="a4a35-159">您可以使用此RoutingRules.ps1脚本，并检查注释 **"Route E911 to PSTN"** 下，查看如何设置此语音路由的示例。</span><span class="sxs-lookup"><span data-stu-id="a4a35-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a4a35-160">该示例命令RoutingRules.ps1包含数字 119 而不是 911 的编号模式。</span><span class="sxs-lookup"><span data-stu-id="a4a35-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="a4a35-161">应避免使用 911 (或实际本地紧急号码) 以避免在负载测试期间意外呼叫本地紧急接线员。</span><span class="sxs-lookup"><span data-stu-id="a4a35-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="a4a35-162">请记住，此配置仅供模拟！</span><span class="sxs-lookup"><span data-stu-id="a4a35-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="a4a35-163">通过填写 UserProvisioningTool 中"位置 **信息** 服务配置"选项卡上的值来配置地址，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="a4a35-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![显示地址、子网、交换机和端口数的用户设置工具。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="a4a35-165">在 UserProvisioningTool 中输入所有内容后，单击"生成 **LIS 配置文件"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4a35-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="a4a35-166">现在，将生成端口、子网、交换机和无线访问点 (WAPs) 的 CSV 文件，以及压力和性能工具的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a4a35-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="a4a35-167">在将位置信息服务与 (LIS) 一起配置时，可以使用 CSV LisConfiguration.ps1输入。</span><span class="sxs-lookup"><span data-stu-id="a4a35-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="a4a35-168">为此，你需要将 Locations0.xml 文件移动到与 Stress and Performance Tool 可执行文件相同的文件夹 (LyncPerfTool.exe) 。</span><span class="sxs-lookup"><span data-stu-id="a4a35-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="a4a35-169">这将让你在拨号计划 (配置文件) 方案。</span><span class="sxs-lookup"><span data-stu-id="a4a35-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="a4a35-170">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="a4a35-170">Configuring Response Group application</span></span>
<span data-ttu-id="a4a35-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a4a35-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="a4a35-172">示例脚本ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="a4a35-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="a4a35-173">此外，还需要查看响应组应用程序 cmdlet，了解进一步的配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4a35-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="a4a35-174">下图将显示一些配置详细信息：</span><span class="sxs-lookup"><span data-stu-id="a4a35-174">The following diagram will show some of the configuration details:</span></span>
  
![显示要测试的现有工作流的响应组配置工具。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

