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
description: 了解 Microsoft 如何收集人口普查、使用率和错误数据，以了解 Teams 和 Skype for Business 的使用情况和问题，以便计划产品改进。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651222"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="daf16-103">Skype for Business 和 Microsoft Teams 数据收集做法</span><span class="sxs-lookup"><span data-stu-id="daf16-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="daf16-104">Skype for Business Server 和 Skype for Business Online 以及 Skype for Business 和 Microsoft Teams 应用程序收集数据，帮助 Microsoft 了解这些产品的使用方式以及发生了哪些类型的错误，例如登录错误。</span><span class="sxs-lookup"><span data-stu-id="daf16-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="daf16-105">此信息可帮助我们了解使用模式、计划新功能，以及诊断和解决问题区域。</span><span class="sxs-lookup"><span data-stu-id="daf16-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="daf16-106">虽然某些使用率数据是自动收集的，但其他数据只能在管理员和/或用户选择允许时收集。</span><span class="sxs-lookup"><span data-stu-id="daf16-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="daf16-107">数据收集分为以下三类：</span><span class="sxs-lookup"><span data-stu-id="daf16-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="daf16-108">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="daf16-108">Census data</span></span>

- <span data-ttu-id="daf16-109">使用率数据</span><span class="sxs-lookup"><span data-stu-id="daf16-109">Usage data</span></span>

- <span data-ttu-id="daf16-110">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="daf16-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="daf16-111">人口普查数据</span><span class="sxs-lookup"><span data-stu-id="daf16-111">Census data</span></span>

<span data-ttu-id="daf16-112">获取人口普查数据完全是为了提供、支持和改进 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="daf16-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="daf16-113">Microsoft Teams 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="daf16-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="daf16-114">它包括环境信息，如设备和操作系统版本，以及区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="daf16-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="daf16-115">它还包括用于登录尝试和失败的计数器。</span><span class="sxs-lookup"><span data-stu-id="daf16-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="daf16-116">以下是收集的人口普查数据的一些具体示例：</span><span class="sxs-lookup"><span data-stu-id="daf16-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="daf16-117">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="daf16-117">**Data type**</span></span>|<span data-ttu-id="daf16-118">**示例**</span><span class="sxs-lookup"><span data-stu-id="daf16-118">**Example**</span></span>|<span data-ttu-id="daf16-119">**注释**</span><span class="sxs-lookup"><span data-stu-id="daf16-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="daf16-120">AppName</span><span class="sxs-lookup"><span data-stu-id="daf16-120">AppName</span></span>  <br/> |<span data-ttu-id="daf16-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="daf16-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="daf16-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="daf16-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="daf16-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="daf16-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="daf16-124">OSName</span><span class="sxs-lookup"><span data-stu-id="daf16-124">OSName</span></span>  <br/> |<span data-ttu-id="daf16-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="daf16-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="daf16-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="daf16-126">OSVersion</span></span>  <br/> |<span data-ttu-id="daf16-127">8.3</span><span class="sxs-lookup"><span data-stu-id="daf16-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="daf16-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="daf16-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="daf16-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="daf16-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="daf16-130">UserID</span><span class="sxs-lookup"><span data-stu-id="daf16-130">UserID</span></span>  <br/> |<span data-ttu-id="daf16-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="daf16-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="daf16-132">这个 ID 被散列两次：一次在客户端上，一次在遥测服务上。</span><span class="sxs-lookup"><span data-stu-id="daf16-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="daf16-133">散列可确保 ID 无法链接到特定用户。</span><span class="sxs-lookup"><span data-stu-id="daf16-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="daf16-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="daf16-134">DeviceID</span></span>  <br/> |<span data-ttu-id="daf16-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="daf16-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="daf16-136">设备 ID 是在设备上随机生成一次并发送到遥测服务的 GUID。</span><span class="sxs-lookup"><span data-stu-id="daf16-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="daf16-137">人口普查数据不包含任何标识你的组织或用户的信息。</span><span class="sxs-lookup"><span data-stu-id="daf16-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="daf16-138">有关详细信息，请参阅 [Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="daf16-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="daf16-139">人口普查数据在默认情况下处于打开状态，管理员或最终用户无法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="daf16-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="daf16-140">使用率数据</span><span class="sxs-lookup"><span data-stu-id="daf16-140">Usage data</span></span>

<span data-ttu-id="daf16-141">使用率数据包括诸如呼叫次数、发送或接收的即时消息数量、加入的会议数量、使用的功能的频率以及稳定性问题等信息。</span><span class="sxs-lookup"><span data-stu-id="daf16-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="daf16-142">使用率数据中可能包含标识你的组织的信息，如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="daf16-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="daf16-143">以下是收集的使用率数据的一些具体示例：</span><span class="sxs-lookup"><span data-stu-id="daf16-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="daf16-144">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="daf16-144">**Data type**</span></span>|<span data-ttu-id="daf16-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="daf16-145">**Example**</span></span>|<span data-ttu-id="daf16-146">**注释**</span><span class="sxs-lookup"><span data-stu-id="daf16-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="daf16-147">发送的即时消息</span><span class="sxs-lookup"><span data-stu-id="daf16-147">IM Sent</span></span>  <br/> |<span data-ttu-id="daf16-148">12</span><span class="sxs-lookup"><span data-stu-id="daf16-148">12</span></span>  <br/> ||
|<span data-ttu-id="daf16-149">已接收即时消息</span><span class="sxs-lookup"><span data-stu-id="daf16-149">IM Received</span></span>  <br/> |<span data-ttu-id="daf16-150">5</span><span class="sxs-lookup"><span data-stu-id="daf16-150">5</span></span>  <br/> ||
|<span data-ttu-id="daf16-151">加入会议（尝试）</span><span class="sxs-lookup"><span data-stu-id="daf16-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="daf16-152">5</span><span class="sxs-lookup"><span data-stu-id="daf16-152">5</span></span>  <br/> ||
|<span data-ttu-id="daf16-153">加入会议（成功）</span><span class="sxs-lookup"><span data-stu-id="daf16-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="daf16-154">4</span><span class="sxs-lookup"><span data-stu-id="daf16-154">4</span></span>  <br/> ||
|<span data-ttu-id="daf16-155">通话/会议纪要</span><span class="sxs-lookup"><span data-stu-id="daf16-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="daf16-156">30 分钟</span><span class="sxs-lookup"><span data-stu-id="daf16-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="daf16-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="daf16-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="daf16-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="daf16-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="daf16-159">这是在 Office 365 中注册的组织的名称，以明文形式传输，这意味着它没有被模糊处理。</span><span class="sxs-lookup"><span data-stu-id="daf16-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="daf16-160">使用率数据不包含任何标识用户的信息。</span><span class="sxs-lookup"><span data-stu-id="daf16-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="daf16-161">默认情况下，使用率数据收集处于打开状态，但本地管理员可以使用 Skype for Business Server 上的 DisableAutomaticSendTracing 组策略设置将其关闭。</span><span class="sxs-lookup"><span data-stu-id="daf16-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="daf16-162">关闭此设置将影响组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="daf16-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="daf16-163">有关详细信息，请参阅[配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="daf16-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="daf16-164">最终用户无法启用或禁用使用率数据收集。</span><span class="sxs-lookup"><span data-stu-id="daf16-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="daf16-165">对于 Skype 会议应用程序和 Join Launcher 网页，控制遥测的方法是通过以下策略：</span><span class="sxs-lookup"><span data-stu-id="daf16-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="daf16-166">此策略默认为 false，因此默认情况下遥测收集处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="daf16-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="daf16-167">此设置为每个池，并控制将 Skype 会议应用程序连接到该服务器上主持的会议的所有用户。</span><span class="sxs-lookup"><span data-stu-id="daf16-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="daf16-168">错误报告数据</span><span class="sxs-lookup"><span data-stu-id="daf16-168">Error reporting data</span></span>

<span data-ttu-id="daf16-169">错误报告数据可包含有关性能和可靠性、设备配置、网络连接质量、错误代码、错误日志和异常的信息。</span><span class="sxs-lookup"><span data-stu-id="daf16-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="daf16-170">以下是收集的错误报告数据的一些具体示例：</span><span class="sxs-lookup"><span data-stu-id="daf16-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="daf16-171">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="daf16-171">**Data type**</span></span>|<span data-ttu-id="daf16-172">**示例**</span><span class="sxs-lookup"><span data-stu-id="daf16-172">**Example**</span></span>|<span data-ttu-id="daf16-173">**注释**</span><span class="sxs-lookup"><span data-stu-id="daf16-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="daf16-174">消息方向</span><span class="sxs-lookup"><span data-stu-id="daf16-174">Message direction</span></span>  <br/> |<span data-ttu-id="daf16-175">传入</span><span class="sxs-lookup"><span data-stu-id="daf16-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="daf16-176">对话状态</span><span class="sxs-lookup"><span data-stu-id="daf16-176">Conversation state</span></span>  <br/> |<span data-ttu-id="daf16-177">空闲</span><span class="sxs-lookup"><span data-stu-id="daf16-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="daf16-178">对话线程 ID</span><span class="sxs-lookup"><span data-stu-id="daf16-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="daf16-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span><span class="sxs-lookup"><span data-stu-id="daf16-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="daf16-180">UserID</span><span class="sxs-lookup"><span data-stu-id="daf16-180">UserID</span></span>  <br/> |<span data-ttu-id="daf16-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="daf16-181">amosmarble</span></span> <br/> |<span data-ttu-id="daf16-182">ID 以明文形式发送，遥测服务在存储它之前对其进行哈希处理</span><span class="sxs-lookup"><span data-stu-id="daf16-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="daf16-183">错误报告数据还可能包含个人身份信息，例如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI)。</span><span class="sxs-lookup"><span data-stu-id="daf16-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="daf16-184">有关所收集内容的详细说明，请参阅 [Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="daf16-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="daf16-185">错误报告需要两个事项：</span><span class="sxs-lookup"><span data-stu-id="daf16-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="daf16-186">在服务器或租户管理中心中，DisableAutomaticSendTracing 组策略设置设置为False（这是默认状态）。</span><span class="sxs-lookup"><span data-stu-id="daf16-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="daf16-187">有关详细信息，请参阅[配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="daf16-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="daf16-188">最终用户从 Skype for Business 客户端的“常规”选项卡（单击齿轮图标![代表齿轮的图标](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)，然后“**选项**”对话框打开并显示“**常规**”选项卡）单独选择加入。</span><span class="sxs-lookup"><span data-stu-id="daf16-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![“选项”对话框中“数据收集”复选框的屏幕截图](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="daf16-190">对于 Skype 会议应用，MeetingUxEnableTelemetry 还控制错误报告，不过对于 Windows 上崩溃，Watson 设置控制上传崩溃信息。</span><span class="sxs-lookup"><span data-stu-id="daf16-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="daf16-191">Skype 会议应用程序没有你在“桌面客户端”对话框中看到的用户设置。</span><span class="sxs-lookup"><span data-stu-id="daf16-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="daf16-192">有关详细信息，请参阅 [在 Skype for Business 中设置常规选项](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。</span><span class="sxs-lookup"><span data-stu-id="daf16-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="daf16-193">你可以参阅[为 Skype for Business Online 设置网络](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)以设置网络。</span><span class="sxs-lookup"><span data-stu-id="daf16-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="daf16-194">如果您在中国使用由世纪互联运营的 Microsoft 365 或 Office 365，请参阅[为世纪互联运营的 Skype for Business Online 设置网络](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="daf16-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="daf16-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="daf16-195">Related topics</span></span>
[<span data-ttu-id="daf16-196">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="daf16-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
