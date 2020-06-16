---
title: 配置各种策略
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8270452893e6e2e531eed86d730a1ea4f9f604fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="482ef-102">配置各种策略</span><span class="sxs-lookup"><span data-stu-id="482ef-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="482ef-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="482ef-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="482ef-104">配置各种策略</span><span class="sxs-lookup"><span data-stu-id="482ef-104">Configuring the Various Policies</span></span>

<span data-ttu-id="482ef-105">下面是在运行 Lync Server 2013 压力和性能工具之前，您可以在 Lync Server 2013 拓扑中配置的各种策略。</span><span class="sxs-lookup"><span data-stu-id="482ef-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="482ef-106">配置存档策略</span><span class="sxs-lookup"><span data-stu-id="482ef-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="482ef-107">请参阅示例脚本 ArchivingPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="482ef-108">仅当在拓扑中部署存档服务器时，才需要使用此脚本。</span><span class="sxs-lookup"><span data-stu-id="482ef-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="482ef-109">有关详细信息，请参阅 Lync server 2013 文档和 cmdlet 帮助以了解如何[在 Lync server 2013 中存档和监视 cmdlet](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="482ef-110">配置会议策略</span><span class="sxs-lookup"><span data-stu-id="482ef-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="482ef-111">请参阅示例脚本 MeetingPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="482ef-112">有关详细信息，请参阅 lync server 2013 中的 Lync Server 2013 文档和 cmdlet Help for [Web 会议 cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="482ef-113">配置联系人策略</span><span class="sxs-lookup"><span data-stu-id="482ef-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="482ef-114">请参阅本示例 ContactsPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="482ef-115">有关详细信息，请参阅 lync server 2013 文档和 cmdlet Help for [IM 和状态 cmdlet 在 Lync server 2013 中](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="482ef-116">配置联合身份验证策略</span><span class="sxs-lookup"><span data-stu-id="482ef-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="482ef-117">请参阅本示例 FederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="482ef-118">有关详细信息，请参阅 lync server 2013 中的 "Lync Server 2013 文档" 和 "cmdlet 帮助"。 2013 Lync server 中的 "[边缘服务器 cmdlet](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) " 和 "[联盟和外部访问" cmdlet](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="482ef-119">配置呼叫允许控制策略</span><span class="sxs-lookup"><span data-stu-id="482ef-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="482ef-120">请参阅本示例 BandwidthPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="482ef-121">有关详细信息，请参阅 lync server [2013 中呼叫允许控制的](https://technet.microsoft.com/library/gg398529\(v=ocs.15\))"lync server 2013 文档概述" 和 " [lync server 2013 中的呼叫允许控制 Cmdlet](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))的 cmdlet 帮助"。</span><span class="sxs-lookup"><span data-stu-id="482ef-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="482ef-122">配置语音路由规则</span><span class="sxs-lookup"><span data-stu-id="482ef-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="482ef-123">请参阅本示例 RoutingRules.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="482ef-124">配置语音路由规则时，请注意电话上下文（即/Location Profile 或/SimpleName）和内部/外部区域代码，以便您可以在创建用户时和在 LyncPerfTool 配置期间（专门针对 PSTN-uc 和 UC-PSTN）指定它们。</span><span class="sxs-lookup"><span data-stu-id="482ef-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="482ef-125">例如，RoutingRules.ps1 示例中**grant-csdialplan** cmdlet 的调用中的 SimpleName 参数应用于 UserProfileGenerator.exe 的下图中的 LocationProfile 值。</span><span class="sxs-lookup"><span data-stu-id="482ef-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="482ef-126">![示例语音路由规则。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "示例语音路由规则。")</span><span class="sxs-lookup"><span data-stu-id="482ef-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="482ef-127">有关详细信息，请参阅 lync server 2013 文档和 cmdlet Help for [Enterprise Voice cmdlet In Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="482ef-128">配置会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="482ef-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="482ef-129">请参阅本示例 ConferenceAutoAttendantConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="482ef-130">记下 ConferencingAutoAttendant 电话号码（默认情况下为1121111111），以便您可以将其键入到 LyncPerf 工具配置工具中，以便生成配置。</span><span class="sxs-lookup"><span data-stu-id="482ef-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="482ef-131">![配置会议助理应用程序](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "配置会议助理应用程序")</span><span class="sxs-lookup"><span data-stu-id="482ef-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="482ef-132">有关详细信息，请参阅 lync server 2013 中的 Lync Server 2013 文档和 cmdlet 帮助中的[Web 会议](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))Cmdlet 和[lync server 2013 中的电话拨入式会议 cmdlet](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="482ef-133">配置 Lync Server 呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="482ef-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="482ef-134">默认情况下，呼叫寄存处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="482ef-134">Call Park is disabled by default.</span></span> <span data-ttu-id="482ef-135">请参阅本示例 CallParkConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="482ef-136">有关详细信息，请参阅 lync server 2013 文档和 cmdlet Help for the [Lync server 2013 中的呼叫寄存应用程序 cmdlet](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="482ef-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="482ef-137">配置紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="482ef-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="482ef-138">执行以下步骤，为紧急呼叫配置压力和性能测试。</span><span class="sxs-lookup"><span data-stu-id="482ef-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="482ef-139">设置紧急呼叫的语音路由。</span><span class="sxs-lookup"><span data-stu-id="482ef-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="482ef-140">有关设置此语音路由的示例，请参阅注释 "Route E911 to PSTN" 下的 RoutingRules.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="482ef-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="482ef-141">RoutingRules.ps1 中的示例命令有一个数字模式，其中包含数字119而不是911。</span><span class="sxs-lookup"><span data-stu-id="482ef-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="482ef-142">应避免使用911（或实际的本地紧急号码），以防止在负载测试期间意外调用本地紧急操作员。</span><span class="sxs-lookup"><span data-stu-id="482ef-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="482ef-143">此配置仅用于模拟目的。</span><span class="sxs-lookup"><span data-stu-id="482ef-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="482ef-144">通过填写 UserProvisioningTool 中的 " **iis** " 选项卡上的值来配置地址，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="482ef-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="482ef-145">![配置位置信息服务。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "配置位置信息服务。")</span><span class="sxs-lookup"><span data-stu-id="482ef-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="482ef-146">单击 "**生成 Iis 配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="482ef-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="482ef-147">将生成用于端口、子网、交换机和无线访问点（Wap）的 CSV 文件，以及 Lync Server 2013 压力和性能工具的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="482ef-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="482ef-148">在使用 LisConfiguration.ps1 脚本配置位置信息服务（.LIS）时，CSV 文件将用作输入（在同一文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="482ef-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="482ef-149">将生成的 Locations0.xml 文件移动到 Lync Server 2013 压力和性能工具可执行文件（LyncPerfTool.exe）的文件夹中，这将运行位置配置文件（拨号计划）方案。</span><span class="sxs-lookup"><span data-stu-id="482ef-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="482ef-150">创建、启用、配置和禁用用户</span><span class="sxs-lookup"><span data-stu-id="482ef-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="482ef-151">应在运行以下脚本之前创建所有用户。</span><span class="sxs-lookup"><span data-stu-id="482ef-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="482ef-152">按照[Create users And Contacts](create-users-and-contacts.md) to create users 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="482ef-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="482ef-153">有关详细信息，请参阅 Lync Server 2013 cmdlet 文档，[获取 get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))、 [get-csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))和[get-csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="482ef-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="482ef-154">配置响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="482ef-154">Configuring Response Group application</span></span>

<span data-ttu-id="482ef-155">请参阅本示例 ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="482ef-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="482ef-156">有关详细信息，请参阅 lync server 2013 文档和 cmdlet Help for [Response server 2013 中的响应组应用程序 cmdlet](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))。若要查看响应组应用程序配置，请参阅 `https://<poolfqdn>/RgsConfig/` ，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="482ef-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="482ef-157">![响应组配置工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "响应组配置工具。")</span><span class="sxs-lookup"><span data-stu-id="482ef-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

