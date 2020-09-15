---
title: 数据收集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 了解 Microsoft 如何收集人口普查、使用情况和错误数据，以了解团队和 Skype for business 使用情况和问题，以便规划产品改进。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651222"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="431af-103">Skype for Business 和 Microsoft 团队数据收集实践</span><span class="sxs-lookup"><span data-stu-id="431af-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="431af-104">Skype for business Server 和 skype for business Online，以及 Skype for business 和 Microsoft 团队应用，收集数据，以帮助 Microsoft 了解这些产品的使用情况以及出现的错误类型（如登录错误）。</span><span class="sxs-lookup"><span data-stu-id="431af-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="431af-105">此信息可帮助我们了解使用模式、规划新功能以及解决问题和解决问题方面的问题。</span><span class="sxs-lookup"><span data-stu-id="431af-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="431af-106">虽然自动收集某些使用数据，但仅当管理员和/或用户选择允许时，才可以收集其他数据。</span><span class="sxs-lookup"><span data-stu-id="431af-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="431af-107">数据收集分为以下三个类别：</span><span class="sxs-lookup"><span data-stu-id="431af-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="431af-108">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="431af-108">Census data</span></span>

- <span data-ttu-id="431af-109">使用情况数据</span><span class="sxs-lookup"><span data-stu-id="431af-109">Usage data</span></span>

- <span data-ttu-id="431af-110">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="431af-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="431af-111">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="431af-111">Census data</span></span>

<span data-ttu-id="431af-112">人口普查数据只是为了提供、支持和改进 Skype for Business 而购买的。</span><span class="sxs-lookup"><span data-stu-id="431af-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="431af-113">Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="431af-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="431af-114">它包括环境信息（如设备和操作系统版本）以及区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="431af-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="431af-115">它还包括用于登录尝试和失败的计数器。</span><span class="sxs-lookup"><span data-stu-id="431af-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="431af-116">下面是收集的人口统计数据的一些具体示例：</span><span class="sxs-lookup"><span data-stu-id="431af-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="431af-117">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="431af-117">**Data type**</span></span>|<span data-ttu-id="431af-118">**示例**</span><span class="sxs-lookup"><span data-stu-id="431af-118">**Example**</span></span>|<span data-ttu-id="431af-119">**注释**</span><span class="sxs-lookup"><span data-stu-id="431af-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="431af-120">AppName</span><span class="sxs-lookup"><span data-stu-id="431af-120">AppName</span></span>  <br/> |<span data-ttu-id="431af-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="431af-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="431af-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="431af-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="431af-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="431af-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="431af-124">OSName</span><span class="sxs-lookup"><span data-stu-id="431af-124">OSName</span></span>  <br/> |<span data-ttu-id="431af-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="431af-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="431af-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="431af-126">OSVersion</span></span>  <br/> |<span data-ttu-id="431af-127">8.3</span><span class="sxs-lookup"><span data-stu-id="431af-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="431af-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="431af-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="431af-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="431af-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="431af-130">UserID</span><span class="sxs-lookup"><span data-stu-id="431af-130">UserID</span></span>  <br/> |<span data-ttu-id="431af-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="431af-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="431af-132">该 ID 被散列两次：在客户端和遥测服务上再次执行。</span><span class="sxs-lookup"><span data-stu-id="431af-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="431af-133">哈希确保 ID 不能链接到特定用户。</span><span class="sxs-lookup"><span data-stu-id="431af-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="431af-134">Keyroutedeventargs.deviceid</span><span class="sxs-lookup"><span data-stu-id="431af-134">DeviceID</span></span>  <br/> |<span data-ttu-id="431af-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="431af-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="431af-136">设备 ID 是在设备上随机生成一次并发送到遥测服务的 GUID。</span><span class="sxs-lookup"><span data-stu-id="431af-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="431af-137">人口普查数据不包含任何标识您的组织或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="431af-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="431af-138">有关详细信息，请参阅 [Skype For Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="431af-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="431af-139">人口普查数据默认处于打开状态，并且不能由管理员或最终用户关闭。</span><span class="sxs-lookup"><span data-stu-id="431af-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="431af-140">使用情况数据</span><span class="sxs-lookup"><span data-stu-id="431af-140">Usage data</span></span>

<span data-ttu-id="431af-141">使用情况数据包括呼叫次数、发送或接收的即时消息数、已加入的会议数、所用功能的频率以及稳定性问题等信息。</span><span class="sxs-lookup"><span data-stu-id="431af-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="431af-142">使用数据可能包含标识您的组织的信息，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="431af-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="431af-143">下面是收集的使用数据的一些特定示例：</span><span class="sxs-lookup"><span data-stu-id="431af-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="431af-144">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="431af-144">**Data type**</span></span>|<span data-ttu-id="431af-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="431af-145">**Example**</span></span>|<span data-ttu-id="431af-146">**注释**</span><span class="sxs-lookup"><span data-stu-id="431af-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="431af-147">发送即时消息</span><span class="sxs-lookup"><span data-stu-id="431af-147">IM Sent</span></span>  <br/> |<span data-ttu-id="431af-148">至</span><span class="sxs-lookup"><span data-stu-id="431af-148">12</span></span>  <br/> ||
|<span data-ttu-id="431af-149">接收即时消息</span><span class="sxs-lookup"><span data-stu-id="431af-149">IM Received</span></span>  <br/> |<span data-ttu-id="431af-150">5</span><span class="sxs-lookup"><span data-stu-id="431af-150">5</span></span>  <br/> ||
|<span data-ttu-id="431af-151">加入会议 (尝试) </span><span class="sxs-lookup"><span data-stu-id="431af-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="431af-152">5</span><span class="sxs-lookup"><span data-stu-id="431af-152">5</span></span>  <br/> ||
|<span data-ttu-id="431af-153">加入会议 (成功) </span><span class="sxs-lookup"><span data-stu-id="431af-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="431af-154">4</span><span class="sxs-lookup"><span data-stu-id="431af-154">4</span></span>  <br/> ||
|<span data-ttu-id="431af-155">通话/会议分钟数</span><span class="sxs-lookup"><span data-stu-id="431af-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="431af-156">30分钟</span><span class="sxs-lookup"><span data-stu-id="431af-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="431af-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="431af-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="431af-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="431af-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="431af-159">这是在 Office 365 中注册的组织的名称，以明文形式发送，这意味着不会对其进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="431af-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="431af-160">使用情况数据不包含任何标识用户的信息。</span><span class="sxs-lookup"><span data-stu-id="431af-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="431af-161">默认情况下，使用情况数据收集处于打开状态，但本地管理员可以使用 Skype for Business 服务器上的 DisableAutomaticSendTracing 组策略设置将其关闭。</span><span class="sxs-lookup"><span data-stu-id="431af-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="431af-162">关闭此设置将影响组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="431af-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="431af-163">有关详细信息，请参阅 [配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 。</span><span class="sxs-lookup"><span data-stu-id="431af-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="431af-164">最终用户无法打开或关闭使用率数据收集。</span><span class="sxs-lookup"><span data-stu-id="431af-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="431af-165">对于 Skype 会议应用和联接启动器网页，控制遥测的方法是通过此策略：</span><span class="sxs-lookup"><span data-stu-id="431af-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="431af-166">此策略默认为 false，因此遥测集合在默认情况下处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="431af-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="431af-167">此设置为每个池，并控制连接到 Skype 会议应用的所有用户与该服务器上托管的会议。</span><span class="sxs-lookup"><span data-stu-id="431af-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="431af-168">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="431af-168">Error reporting data</span></span>

<span data-ttu-id="431af-169">错误报告数据可以包括有关性能和可靠性、设备配置、网络连接质量、错误代码、错误日志和异常的信息。</span><span class="sxs-lookup"><span data-stu-id="431af-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="431af-170">下面是收集的错误报告数据的一些特定示例：</span><span class="sxs-lookup"><span data-stu-id="431af-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="431af-171">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="431af-171">**Data type**</span></span>|<span data-ttu-id="431af-172">**示例**</span><span class="sxs-lookup"><span data-stu-id="431af-172">**Example**</span></span>|<span data-ttu-id="431af-173">**注释**</span><span class="sxs-lookup"><span data-stu-id="431af-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="431af-174">邮件方向</span><span class="sxs-lookup"><span data-stu-id="431af-174">Message direction</span></span>  <br/> |<span data-ttu-id="431af-175">拨</span><span class="sxs-lookup"><span data-stu-id="431af-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="431af-176">对话状态</span><span class="sxs-lookup"><span data-stu-id="431af-176">Conversation state</span></span>  <br/> |<span data-ttu-id="431af-177">着</span><span class="sxs-lookup"><span data-stu-id="431af-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="431af-178">对话线程 ID</span><span class="sxs-lookup"><span data-stu-id="431af-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="431af-179">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="431af-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="431af-180">UserID</span><span class="sxs-lookup"><span data-stu-id="431af-180">UserID</span></span>  <br/> |<span data-ttu-id="431af-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="431af-181">amosmarble</span></span> <br/> |<span data-ttu-id="431af-182">ID 以明文形式发送，在存储之前遥测服务哈希</span><span class="sxs-lookup"><span data-stu-id="431af-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="431af-183">错误报告数据还可能包含个人身份信息，如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI) 。</span><span class="sxs-lookup"><span data-stu-id="431af-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="431af-184">有关收集的内容的详细说明，请参阅 [Skype For Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="431af-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="431af-185">错误报告需要两个事项：</span><span class="sxs-lookup"><span data-stu-id="431af-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="431af-186">DisableAutomaticSendTracing 组策略设置在服务器或租户管理中心中设置为 False (这是) 的默认状态。</span><span class="sxs-lookup"><span data-stu-id="431af-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="431af-187">有关详细信息，请参阅 [配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 。</span><span class="sxs-lookup"><span data-stu-id="431af-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="431af-188">最终用户从 "常规" 选项卡中单独选择 " (单击齿轮图标 ![ 表示齿轮的图标， ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) 然后" **选项** "对话框随即打开，并在 Skype for business 客户端中) 显示" **常规** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="431af-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
!["选项" 对话框中 "数据收集" 复选框的屏幕截图](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="431af-190">对于 Skype 会议应用，MeetingUxEnableTelemetry 还控制错误报告功能，但在 Windows 上崩溃时，Watson 设置控制上传崩溃信息。</span><span class="sxs-lookup"><span data-stu-id="431af-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="431af-191">在 "桌面客户端" 对话框中看不到 Skype 会议应用的用户设置。</span><span class="sxs-lookup"><span data-stu-id="431af-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="431af-192">有关详细信息，请参阅 [在 Skype For business 中设置常规选项](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) 。</span><span class="sxs-lookup"><span data-stu-id="431af-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="431af-193">你可以参阅为 [Skype for Business Online 设置网络](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) 以设置你的网络。</span><span class="sxs-lookup"><span data-stu-id="431af-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="431af-194">如果您使用的是由中国的世纪互联运营的 Microsoft 365 或 Office 365，请参阅 [为由世纪互联运营的 Skype for Business Online 设置网络](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="431af-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="431af-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="431af-195">Related topics</span></span>
[<span data-ttu-id="431af-196">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="431af-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
