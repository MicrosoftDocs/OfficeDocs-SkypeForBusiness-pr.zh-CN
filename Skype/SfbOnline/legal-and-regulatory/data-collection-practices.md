---
title: 数据集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
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
description: Microsoft 收集统计、 使用和错误的数据，以了解如何使用 for Business 的 Skype 和其中用户遇到问题。 使用的数据来规划产品改进。
ms.openlocfilehash: 37073ad92933e03b9b05c7d3c8d9cd427276cc5b
ms.sourcegitcommit: c63e7a8a746d427a1c886e8dca4d631c851e417c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="69d2f-104">Skype 的业务和 Microsoft 团队数据集做法</span><span class="sxs-lookup"><span data-stu-id="69d2f-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="69d2f-105">Skype 的业务服务器 2015年、 业务 online，以及应用程序业务和 Microsoft 团队的 Skype Skype 收集数据以帮助 Microsoft 了解如何使用这些产品以及哪些类型的错误，例如，登录错误发生。</span><span class="sxs-lookup"><span data-stu-id="69d2f-105">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="69d2f-106">此信息可以帮助我们了解使用模式、 规划新功能，并排除和修复问题的区域。</span><span class="sxs-lookup"><span data-stu-id="69d2f-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="69d2f-107">时自动收集的某些使用率数据，可以仅收集其他数据时的管理和/或用户选择允许它。</span><span class="sxs-lookup"><span data-stu-id="69d2f-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="69d2f-108">数据收集分为以下三个类别：</span><span class="sxs-lookup"><span data-stu-id="69d2f-108">Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="69d2f-109">统计数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-109">Census data</span></span>
    
- <span data-ttu-id="69d2f-110">使用率数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-110">Usage data</span></span>
    
- <span data-ttu-id="69d2f-111">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="69d2f-112">统计数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-112">Census data</span></span>

<span data-ttu-id="69d2f-113">获取统计数据只是为了提供、 支持，以及改进业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="69d2f-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="69d2f-114">Microsoft 团队和 Skype for Business 联机。</span><span class="sxs-lookup"><span data-stu-id="69d2f-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="69d2f-115">它包括环境的信息，如设备和操作系统版本和区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="69d2f-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="69d2f-116">它还包括尝试登录时和失败的计数器。</span><span class="sxs-lookup"><span data-stu-id="69d2f-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="69d2f-117">下面是一些特定收集的统计数据的示例：</span><span class="sxs-lookup"><span data-stu-id="69d2f-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="69d2f-118">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="69d2f-118">**Data type**</span></span>|<span data-ttu-id="69d2f-119">**示例**</span><span class="sxs-lookup"><span data-stu-id="69d2f-119">**Example**</span></span>|<span data-ttu-id="69d2f-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="69d2f-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69d2f-121">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="69d2f-121">AppName</span></span>  <br/> |<span data-ttu-id="69d2f-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="69d2f-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="69d2f-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="69d2f-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="69d2f-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="69d2f-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="69d2f-125">OSName</span><span class="sxs-lookup"><span data-stu-id="69d2f-125">OSName</span></span>  <br/> |<span data-ttu-id="69d2f-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="69d2f-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="69d2f-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="69d2f-127">OSVersion</span></span>  <br/> |<span data-ttu-id="69d2f-128">8.3</span><span class="sxs-lookup"><span data-stu-id="69d2f-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="69d2f-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="69d2f-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="69d2f-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="69d2f-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="69d2f-131">用户 Id</span><span class="sxs-lookup"><span data-stu-id="69d2f-131">UserID</span></span>  <br/> |<span data-ttu-id="69d2f-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="69d2f-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="69d2f-133">ID 哈希处理两次： 客户端上一次并再次遥测服务。</span><span class="sxs-lookup"><span data-stu-id="69d2f-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="69d2f-134">哈希值计算可确保不能链接到特定用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="69d2f-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="69d2f-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="69d2f-135">DeviceID</span></span>  <br/> |<span data-ttu-id="69d2f-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="69d2f-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="69d2f-137">设备 ID 是随机生成一次在设备上并发送到遥测服务的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69d2f-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="69d2f-138">统计数据不包含任何标识您的组织或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="69d2f-139">请参阅[业务隐私声明的 Skype](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="69d2f-140">统计数据位于默认情况下，不能通过 admins 凭据或最终用户关闭。</span><span class="sxs-lookup"><span data-stu-id="69d2f-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="69d2f-141">使用率数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-141">Usage data</span></span>

<span data-ttu-id="69d2f-142">使用率数据包括如进行的呼叫数、 发送或接收 Im 数、 加入的会议数、 的功能使用，频率和稳定性问题的信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="69d2f-143">使用率数据可能包含标识您的组织，例如，contoso.com 的信息。下面是一些特定收集使用率数据的示例：</span><span class="sxs-lookup"><span data-stu-id="69d2f-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="69d2f-144">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="69d2f-144">**Data type**</span></span>|<span data-ttu-id="69d2f-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="69d2f-145">**Example**</span></span>|<span data-ttu-id="69d2f-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="69d2f-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69d2f-147">发送的 IM</span><span class="sxs-lookup"><span data-stu-id="69d2f-147">IM Sent</span></span>  <br/> |<span data-ttu-id="69d2f-148">12</span><span class="sxs-lookup"><span data-stu-id="69d2f-148">12</span></span>  <br/> ||
|<span data-ttu-id="69d2f-149">接收 IM</span><span class="sxs-lookup"><span data-stu-id="69d2f-149">IM Received</span></span>  <br/> |<span data-ttu-id="69d2f-150">5</span><span class="sxs-lookup"><span data-stu-id="69d2f-150">5</span></span>  <br/> ||
|<span data-ttu-id="69d2f-151">加入会议 （尝试）</span><span class="sxs-lookup"><span data-stu-id="69d2f-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="69d2f-152">5</span><span class="sxs-lookup"><span data-stu-id="69d2f-152">5</span></span>  <br/> ||
|<span data-ttu-id="69d2f-153">加入会议 （成功）</span><span class="sxs-lookup"><span data-stu-id="69d2f-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="69d2f-154">4</span><span class="sxs-lookup"><span data-stu-id="69d2f-154">4</span></span>  <br/> ||
|<span data-ttu-id="69d2f-155">会议呼叫/分钟</span><span class="sxs-lookup"><span data-stu-id="69d2f-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="69d2f-156">30 分钟</span><span class="sxs-lookup"><span data-stu-id="69d2f-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="69d2f-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="69d2f-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="69d2f-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="69d2f-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="69d2f-159">这是在 Office 365 中注册的组织的名称，以明文，这意味着不经过模糊处理传输。</span><span class="sxs-lookup"><span data-stu-id="69d2f-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="69d2f-160">使用率数据不包含任何标识用户的信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="69d2f-161">使用率数据集默认情况下，但本地管理员可以将其关闭业务服务器 2015 Skype 上使用 DisableAutomaticSendTracing 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="69d2f-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015.</span></span> <span data-ttu-id="69d2f-162">关闭此设置将影响组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="69d2f-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="69d2f-163">有关详细信息，请参阅[中的业务服务器 2015 Skype 的配置客户端引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。</span><span class="sxs-lookup"><span data-stu-id="69d2f-163">See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="69d2f-164">打开或关闭，最终用户无法启用使用率数据集。</span><span class="sxs-lookup"><span data-stu-id="69d2f-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="69d2f-165">Skype 会议应用程序和联接启动器网页，控制遥测的方法是通过此策略：</span><span class="sxs-lookup"><span data-stu-id="69d2f-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="69d2f-166">通过 Set-cswebserviceconfiguration MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="69d2f-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="69d2f-167">此策略默认为 false，因此默认情况下关闭为遥测集合。</span><span class="sxs-lookup"><span data-stu-id="69d2f-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="69d2f-168">此设置是每个池，并控制与 Skype 会议应用程序连接到该服务器上承载会议的所有用户。</span><span class="sxs-lookup"><span data-stu-id="69d2f-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="69d2f-169">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="69d2f-169">Error reporting data</span></span>

<span data-ttu-id="69d2f-170">错误报告数据可以包括有关性能和可靠性、 设备配置、 网络连接质量，错误代码、 错误日志和异常的信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="69d2f-171">下面是一些特定错误报告收集的数据的示例：</span><span class="sxs-lookup"><span data-stu-id="69d2f-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="69d2f-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="69d2f-172">**Data type**</span></span>|<span data-ttu-id="69d2f-173">**示例**</span><span class="sxs-lookup"><span data-stu-id="69d2f-173">**Example**</span></span>|<span data-ttu-id="69d2f-174">**说明**</span><span class="sxs-lookup"><span data-stu-id="69d2f-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69d2f-175">消息方向</span><span class="sxs-lookup"><span data-stu-id="69d2f-175">Message direction</span></span>  <br/> |<span data-ttu-id="69d2f-176">传入</span><span class="sxs-lookup"><span data-stu-id="69d2f-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="69d2f-177">会话状态</span><span class="sxs-lookup"><span data-stu-id="69d2f-177">Conversation state</span></span>  <br/> |<span data-ttu-id="69d2f-178">空闲时间</span><span class="sxs-lookup"><span data-stu-id="69d2f-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="69d2f-179">对话线程 ID</span><span class="sxs-lookup"><span data-stu-id="69d2f-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="69d2f-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="69d2f-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="69d2f-181">用户 Id</span><span class="sxs-lookup"><span data-stu-id="69d2f-181">UserID</span></span>  <br/> |<span data-ttu-id="69d2f-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="69d2f-182">amosmarble</span></span> <br/> |<span data-ttu-id="69d2f-183">ID 是以明文形式，其之前将其存储遥测服务进行哈希处理发送</span><span class="sxs-lookup"><span data-stu-id="69d2f-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="69d2f-184">错误报告数据可能还包含个人身份信息，例如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI)。</span><span class="sxs-lookup"><span data-stu-id="69d2f-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="69d2f-185">请参阅[业务隐私声明的 Skype](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的什么收集的详细说明。</span><span class="sxs-lookup"><span data-stu-id="69d2f-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="69d2f-186">错误报告需要以下两项：</span><span class="sxs-lookup"><span data-stu-id="69d2f-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="69d2f-187">在服务器上或租户管理员中心 （这是默认状态） DisableAutomaticSendTracing 组策略设置设置为 False。</span><span class="sxs-lookup"><span data-stu-id="69d2f-187">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="69d2f-188">有关详细信息，请参阅[中的业务服务器 2015 Skype 的配置客户端引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。</span><span class="sxs-lookup"><span data-stu-id="69d2f-188">See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="69d2f-189">最终用户分别选择中常规选项卡 （齿轮图标和选项对话框将打开常规选项卡显示与单击） 从加入 Skype 业务客户端。</span><span class="sxs-lookup"><span data-stu-id="69d2f-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![齿轮图标](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype 选项中的业务数据集复选框 > 常规对话框](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="69d2f-192">对于 Skype 会议应用程序，MeetingUxEnableTelemetry 还将控制错误报告，但对 Windows 上崩溃，Watson 设置控制上载崩溃信息。</span><span class="sxs-lookup"><span data-stu-id="69d2f-192">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="69d2f-193">在桌面客户端对话框中看到如 Skype 会议应用程序没有用户设置。</span><span class="sxs-lookup"><span data-stu-id="69d2f-193">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="69d2f-194">有关详细信息，请参阅[Skype for Business 中的常规设置选项](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。</span><span class="sxs-lookup"><span data-stu-id="69d2f-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="69d2f-195">您可以看到[设置业务 online Skype 的网络](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)设置您的网络。</span><span class="sxs-lookup"><span data-stu-id="69d2f-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="69d2f-196">如果您使用的 Office 365 21Vianet 在中国由操作，请参阅[设置您的业务 online 由 21Vianet Skype 的网络](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="69d2f-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="69d2f-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="69d2f-197">Related topics</span></span>
[<span data-ttu-id="69d2f-198">客户体验改善计划</span><span class="sxs-lookup"><span data-stu-id="69d2f-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="69d2f-199">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="69d2f-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
