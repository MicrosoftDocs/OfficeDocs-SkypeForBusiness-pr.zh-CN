---
title: 数据集合的做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft 收集人口普查、 用法和错误的数据，了解如何使用 Skype 业务和用户遇到问题的地方。 数据用于产品的改进计划。
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="d4cab-104">Skype 业务和 Microsoft 小组数据集合做法</span><span class="sxs-lookup"><span data-stu-id="d4cab-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="d4cab-105">Skype 的业务服务器 2015年、 Skype 业务在线，Skype 业务和 Microsoft 小组应用程序以及收集数据以帮助 Microsoft 了解这些产品的使用方式和发生何种错误，例如登录错误。</span><span class="sxs-lookup"><span data-stu-id="d4cab-105">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="d4cab-106">此信息可以帮助我们了解使用模式、 规划新的功能，并排除和解决问题的区域。</span><span class="sxs-lookup"><span data-stu-id="d4cab-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="d4cab-107">虽然会自动收集一些有用的数据，可以只收集其他数据时管理和/或用户选择允许它。</span><span class="sxs-lookup"><span data-stu-id="d4cab-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="d4cab-108">数据收集落在这三个类别：</span><span class="sxs-lookup"><span data-stu-id="d4cab-108">Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="d4cab-109">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-109">Census data</span></span>
    
- <span data-ttu-id="d4cab-110">使用率数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-110">Usage data</span></span>
    
- <span data-ttu-id="d4cab-111">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="d4cab-112">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-112">Census data</span></span>

<span data-ttu-id="d4cab-113">人口普查数据获得只是为了提供、 支持和提高业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="d4cab-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="d4cab-114">Microsoft 的小组和 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="d4cab-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="d4cab-115">它包括环境信息，如设备和操作系统版本以及区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="d4cab-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="d4cab-116">它还包括登录尝试和失败的计数器。</span><span class="sxs-lookup"><span data-stu-id="d4cab-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="d4cab-117">人口普查数据收集的特定示例如下：</span><span class="sxs-lookup"><span data-stu-id="d4cab-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="d4cab-118">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4cab-118">**Data type**</span></span>|<span data-ttu-id="d4cab-119">**示例**</span><span class="sxs-lookup"><span data-stu-id="d4cab-119">**Example**</span></span>|<span data-ttu-id="d4cab-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="d4cab-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4cab-121">应用程序名</span><span class="sxs-lookup"><span data-stu-id="d4cab-121">AppName</span></span>  <br/> |<span data-ttu-id="d4cab-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="d4cab-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="d4cab-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="d4cab-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="d4cab-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="d4cab-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="d4cab-125">OSName</span><span class="sxs-lookup"><span data-stu-id="d4cab-125">OSName</span></span>  <br/> |<span data-ttu-id="d4cab-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="d4cab-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="d4cab-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="d4cab-127">OSVersion</span></span>  <br/> |<span data-ttu-id="d4cab-128">8.3</span><span class="sxs-lookup"><span data-stu-id="d4cab-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="d4cab-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="d4cab-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="d4cab-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="d4cab-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="d4cab-131">用户 Id</span><span class="sxs-lookup"><span data-stu-id="d4cab-131">UserID</span></span>  <br/> |<span data-ttu-id="d4cab-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="d4cab-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="d4cab-133">ID 进行哈希计算两次： 一次客户端上，再次对遥测服务。</span><span class="sxs-lookup"><span data-stu-id="d4cab-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="d4cab-134">哈希可确保该 ID 不能链接到特定的用户。</span><span class="sxs-lookup"><span data-stu-id="d4cab-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="d4cab-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="d4cab-135">DeviceID</span></span>  <br/> |<span data-ttu-id="d4cab-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="d4cab-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="d4cab-137">设备 ID 是随机生成一次设备上并发送到遥测服务的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d4cab-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="d4cab-138">人口普查数据不包含任何信息可用于标识您的组织或用户。</span><span class="sxs-lookup"><span data-stu-id="d4cab-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="d4cab-139">[Skype 业务隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d4cab-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="d4cab-140">人口普查数据默认是打开的并且不能由管理员或最终用户关闭。</span><span class="sxs-lookup"><span data-stu-id="d4cab-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="d4cab-141">使用率数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-141">Usage data</span></span>

<span data-ttu-id="d4cab-142">使用率数据包括调用次数、 发送或接收即时消息的数量、 加入会议的数量、 频率使用，功能和稳定性问题等信息。</span><span class="sxs-lookup"><span data-stu-id="d4cab-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="d4cab-143">使用率数据可能包含的信息可用于标识您的组织，如 contoso.com。下面是收集使用数据的一些特定示例：</span><span class="sxs-lookup"><span data-stu-id="d4cab-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="d4cab-144">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4cab-144">**Data type**</span></span>|<span data-ttu-id="d4cab-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="d4cab-145">**Example**</span></span>|<span data-ttu-id="d4cab-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="d4cab-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4cab-147">发送即时消息</span><span class="sxs-lookup"><span data-stu-id="d4cab-147">IM Sent</span></span>  <br/> |<span data-ttu-id="d4cab-148">12</span><span class="sxs-lookup"><span data-stu-id="d4cab-148">12</span></span>  <br/> ||
|<span data-ttu-id="d4cab-149">收到的即时消息</span><span class="sxs-lookup"><span data-stu-id="d4cab-149">IM Received</span></span>  <br/> |<span data-ttu-id="d4cab-150">5</span><span class="sxs-lookup"><span data-stu-id="d4cab-150">5</span></span>  <br/> ||
|<span data-ttu-id="d4cab-151">加入会议 （尝试）</span><span class="sxs-lookup"><span data-stu-id="d4cab-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="d4cab-152">5</span><span class="sxs-lookup"><span data-stu-id="d4cab-152">5</span></span>  <br/> ||
|<span data-ttu-id="d4cab-153">加入会议 （成功）</span><span class="sxs-lookup"><span data-stu-id="d4cab-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="d4cab-154">4</span><span class="sxs-lookup"><span data-stu-id="d4cab-154">4</span></span>  <br/> ||
|<span data-ttu-id="d4cab-155">调用/会议纪要</span><span class="sxs-lookup"><span data-stu-id="d4cab-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="d4cab-156">30 分钟</span><span class="sxs-lookup"><span data-stu-id="d4cab-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="d4cab-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="d4cab-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="d4cab-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d4cab-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="d4cab-159">这是在 Office 365 中注册的组织名称和传输以明文形式，这意味着它不进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="d4cab-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="d4cab-160">使用率数据不包含任何标识用户的信息。</span><span class="sxs-lookup"><span data-stu-id="d4cab-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="d4cab-161">使用率数据集在默认情况下，但内部部署的管理员可以将其关闭业务服务器 2015年在 Skype 上使用 DisableAutomaticSendTracing 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="d4cab-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015.</span></span> <span data-ttu-id="d4cab-162">关闭此设置会影响组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d4cab-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="d4cab-163">有关更多信息，请参见[配置客户端中业务服务器 2015年的 Skype 的引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d4cab-163">See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="d4cab-164">最终用户不能启用使用率数据集合打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="d4cab-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="d4cab-165">Skype 会议应用程序和连接的启动器 web 页，控制遥测的方法是通过此策略：</span><span class="sxs-lookup"><span data-stu-id="d4cab-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="d4cab-166">一组 CsWebServiceConfiguration MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="d4cab-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="d4cab-167">此策略的默认为 false，因此遥测集合，默认情况下处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="d4cab-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="d4cab-168">此设置是每个池，并控制所有用户都使用 Skype 会议应用程序连接到该服务器上主持会议。</span><span class="sxs-lookup"><span data-stu-id="d4cab-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="d4cab-169">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="d4cab-169">Error reporting data</span></span>

<span data-ttu-id="d4cab-170">错误报告数据可以包括性能和可靠性、 设备配置、 网络连接质量、 错误代码、 错误日志和异常有关的信息。</span><span class="sxs-lookup"><span data-stu-id="d4cab-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="d4cab-171">下面是错误的一些特定报告收集的数据示例：</span><span class="sxs-lookup"><span data-stu-id="d4cab-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="d4cab-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4cab-172">**Data type**</span></span>|<span data-ttu-id="d4cab-173">**示例**</span><span class="sxs-lookup"><span data-stu-id="d4cab-173">**Example**</span></span>|<span data-ttu-id="d4cab-174">**说明**</span><span class="sxs-lookup"><span data-stu-id="d4cab-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4cab-175">消息传送方向</span><span class="sxs-lookup"><span data-stu-id="d4cab-175">Message direction</span></span>  <br/> |<span data-ttu-id="d4cab-176">传入</span><span class="sxs-lookup"><span data-stu-id="d4cab-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="d4cab-177">会话状态</span><span class="sxs-lookup"><span data-stu-id="d4cab-177">Conversation state</span></span>  <br/> |<span data-ttu-id="d4cab-178">空闲</span><span class="sxs-lookup"><span data-stu-id="d4cab-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="d4cab-179">对话线程 ID</span><span class="sxs-lookup"><span data-stu-id="d4cab-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="d4cab-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="d4cab-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="d4cab-181">用户 Id</span><span class="sxs-lookup"><span data-stu-id="d4cab-181">UserID</span></span>  <br/> |<span data-ttu-id="d4cab-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="d4cab-182">amosmarble</span></span> <br/> |<span data-ttu-id="d4cab-183">该 ID 发送明文，遥测服务前将其进行哈希处理中</span><span class="sxs-lookup"><span data-stu-id="d4cab-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="d4cab-184">错误报告数据还可能包含个人身份信息，例如用户的 IP 地址和会话初始化协议统一资源标识符 (SIP URI)。</span><span class="sxs-lookup"><span data-stu-id="d4cab-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="d4cab-185">[Skype 业务隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的什么收集的详细说明，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d4cab-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="d4cab-186">错误报告要求以下两点：</span><span class="sxs-lookup"><span data-stu-id="d4cab-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="d4cab-187">在服务器上或在租户管理中心 （这是默认状态），DisableAutomaticSendTracing 组策略设置被设置为 False。</span><span class="sxs-lookup"><span data-stu-id="d4cab-187">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="d4cab-188">有关更多信息，请参见[配置客户端中业务服务器 2015年的 Skype 的引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d4cab-188">See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="d4cab-189">最终用户分别选择使用从常规选项卡 （单击齿轮图标和选项对话框将打开并显示常规选项卡） 在 Skype 业务客户端。</span><span class="sxs-lookup"><span data-stu-id="d4cab-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![齿轮图标](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype 业务数据收集复选框，在选项 > 常规的对话框](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="d4cab-192">对于 Skype 会议应用，MeetingUxEnableTelemetry 还控制错误报告，虽然对 Windows 的崩溃，Watson 设置控制上载的故障信息。</span><span class="sxs-lookup"><span data-stu-id="d4cab-192">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="d4cab-193">正如您在桌面客户端对话框中看到没有 Skype 会议应用程序的任何用户设置。</span><span class="sxs-lookup"><span data-stu-id="d4cab-193">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="d4cab-194">有关更多信息，请参见[在 Skype 为业务设置常规选项](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。</span><span class="sxs-lookup"><span data-stu-id="d4cab-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="d4cab-195">您可以查看[设置的 Skype 的在线业务网络](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)来设置您的网络。</span><span class="sxs-lookup"><span data-stu-id="d4cab-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="d4cab-196">如果您使用的 Office 365 的 21Vianet 在中国运行，请参阅[设置业务在线由 21Vianet Skype 的网络](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="d4cab-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d4cab-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="d4cab-197">Related topics</span></span>
[<span data-ttu-id="d4cab-198">客户体验改善计划</span><span class="sxs-lookup"><span data-stu-id="d4cab-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="d4cab-199">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="d4cab-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
