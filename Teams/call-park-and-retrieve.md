---
title: 呼叫驻留和检索中的 Microsoft 团队
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 使用呼叫寄存和取回呼叫置于保持状态，云中团队服务中。
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283156"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="4efb8-103">呼叫驻留和检索中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="4efb8-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="4efb8-104">呼叫寄存和取回是一种功能，允许用户将呼叫置于保留在云中团队服务中。</span><span class="sxs-lookup"><span data-stu-id="4efb8-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="4efb8-105">驻留呼叫后，该服务将生成一个唯一的代码调用检索。</span><span class="sxs-lookup"><span data-stu-id="4efb8-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="4efb8-106">寄存呼叫或其他人的用户然后可以使用该代码和支持的应用程序或设备取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="4efb8-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="4efb8-107">下面是一些使用呼叫寄存的常见方案：</span><span class="sxs-lookup"><span data-stu-id="4efb8-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="4efb8-108">前台接待员 parks 呼叫的人在执行出厂中工作。</span><span class="sxs-lookup"><span data-stu-id="4efb8-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="4efb8-109">接待员然后宣布呼叫和代码编号，通过公共地址系统。</span><span class="sxs-lookup"><span data-stu-id="4efb8-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="4efb8-110">被叫的用户可以拿起在工厂团队电话，然后输入代码以取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="4efb8-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="4efb8-111">用户 parks 移动设备上的呼叫，因为设备电池不足电源。</span><span class="sxs-lookup"><span data-stu-id="4efb8-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="4efb8-112">然后，用户可以输入，然后代码从团队桌面电话取回该呼叫。</span><span class="sxs-lookup"><span data-stu-id="4efb8-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="4efb8-113">支持代表性公园客户呼叫和专家取回该呼叫并帮助客户团队通道上发送通知。</span><span class="sxs-lookup"><span data-stu-id="4efb8-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="4efb8-114">专家进入团队客户端取回呼叫中的代码</span><span class="sxs-lookup"><span data-stu-id="4efb8-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4efb8-115">此功能才可用在仅团队部署模式下。</span><span class="sxs-lookup"><span data-stu-id="4efb8-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="4efb8-116">团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="4efb8-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="4efb8-117">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="4efb8-117">License required</span></span>

<span data-ttu-id="4efb8-118">若要寄存并取回呼叫，用户必须是企业语音的用户和管理员必须授予该用户的呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="4efb8-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="4efb8-119">有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="4efb8-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="4efb8-120">呼叫驻留和检索功能可用性</span><span class="sxs-lookup"><span data-stu-id="4efb8-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="4efb8-121">呼叫寄存和取回是当前支持以下客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="4efb8-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="4efb8-122">（支持在仅工作组模式中，使用或不 PSTN 连接。）</span><span class="sxs-lookup"><span data-stu-id="4efb8-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="4efb8-123">功能</span><span class="sxs-lookup"><span data-stu-id="4efb8-123">Capability</span></span> | <span data-ttu-id="4efb8-124">团队桌面</span><span class="sxs-lookup"><span data-stu-id="4efb8-124">Teams Desktop</span></span> | <span data-ttu-id="4efb8-125">团队 Mac 应用程序</span><span class="sxs-lookup"><span data-stu-id="4efb8-125">Teams Mac App</span></span> | <span data-ttu-id="4efb8-126">工作组 Web 应用程序 （边缘）</span><span class="sxs-lookup"><span data-stu-id="4efb8-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="4efb8-127">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="4efb8-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="4efb8-128">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="4efb8-128">Teams IP phone</span></span> | <span data-ttu-id="4efb8-129">Skype 业务 IP 电话</span><span class="sxs-lookup"><span data-stu-id="4efb8-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="4efb8-130">驻留呼叫</span><span class="sxs-lookup"><span data-stu-id="4efb8-130">Park a call</span></span> | <span data-ttu-id="4efb8-131">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-131">Yes</span></span> | <span data-ttu-id="4efb8-132">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-132">Yes</span></span> | <span data-ttu-id="4efb8-133">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-133">Yes</span></span> | <span data-ttu-id="4efb8-134">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-134">Coming soon</span></span> | <span data-ttu-id="4efb8-135">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-135">Coming soon</span></span>| <span data-ttu-id="4efb8-136">否</span><span class="sxs-lookup"><span data-stu-id="4efb8-136">No</span></span> |
| <span data-ttu-id="4efb8-137">取回驻留的呼叫</span><span class="sxs-lookup"><span data-stu-id="4efb8-137">Retrieve a parked call</span></span> | <span data-ttu-id="4efb8-138">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-138">Yes</span></span> | <span data-ttu-id="4efb8-139">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-139">Yes</span></span> | <span data-ttu-id="4efb8-140">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-140">Yes</span></span> | <span data-ttu-id="4efb8-141">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-141">Coming soon</span></span> | <span data-ttu-id="4efb8-142">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-142">Coming soon</span></span>| <span data-ttu-id="4efb8-143">否</span><span class="sxs-lookup"><span data-stu-id="4efb8-143">No</span></span> |
| <span data-ttu-id="4efb8-144">返回未检索到的呼叫拨打</span><span class="sxs-lookup"><span data-stu-id="4efb8-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="4efb8-145">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-145">Yes</span></span> | <span data-ttu-id="4efb8-146">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-146">Yes</span></span> | <span data-ttu-id="4efb8-147">是</span><span class="sxs-lookup"><span data-stu-id="4efb8-147">Yes</span></span> | <span data-ttu-id="4efb8-148">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-148">Coming soon</span></span> | <span data-ttu-id="4efb8-149">即将提供</span><span class="sxs-lookup"><span data-stu-id="4efb8-149">Coming soon</span></span>| <span data-ttu-id="4efb8-150">否</span><span class="sxs-lookup"><span data-stu-id="4efb8-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="4efb8-151">配置呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="4efb8-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="4efb8-152">您必须是管理员能够配置呼叫寄存和取回，和默认情况下禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="4efb8-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="4efb8-153">您可以为用户启用它，并创建使用呼叫寄存策略的用户组。</span><span class="sxs-lookup"><span data-stu-id="4efb8-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="4efb8-154">时为一组用户应用同一策略，他们将能够寄存和取回呼叫之间本身。</span><span class="sxs-lookup"><span data-stu-id="4efb8-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="4efb8-155">若要配置为用户的呼叫寄存和创建呼叫寄存用户组，请按照下面的过程。</span><span class="sxs-lookup"><span data-stu-id="4efb8-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="4efb8-156">有关如何使用呼叫寄存和检索功能的信息，请参阅[寄存团队中的呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="4efb8-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="4efb8-157">配置呼叫寄存和检索与 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4efb8-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="4efb8-158">使用[新建 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="4efb8-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="4efb8-159">使用[授予 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予的呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="4efb8-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4efb8-160">故障排除</span><span class="sxs-lookup"><span data-stu-id="4efb8-160">Troubleshooting</span></span>

<span data-ttu-id="4efb8-161">如果用户不能看到寄存或检索按钮：</span><span class="sxs-lookup"><span data-stu-id="4efb8-161">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="4efb8-162">检查用户具有启用呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="4efb8-162">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="4efb8-163">如果用户尝试检索呼叫，并且不成功，检查以下项目：</span><span class="sxs-lookup"><span data-stu-id="4efb8-163">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="4efb8-164">验证用户使用团队客户端或工作组启用设备/电话</span><span class="sxs-lookup"><span data-stu-id="4efb8-164">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="4efb8-165">分组 – 是呼叫寄存组的成员的用户？</span><span class="sxs-lookup"><span data-stu-id="4efb8-165">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="4efb8-166">岛模式 – 呼叫寄存和取回是团队岛模式中不可用。</span><span class="sxs-lookup"><span data-stu-id="4efb8-166">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="4efb8-167">已检索或终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="4efb8-167">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="4efb8-168">更多信息</span><span class="sxs-lookup"><span data-stu-id="4efb8-168">More information</span></span>

<span data-ttu-id="4efb8-169">[寄存呼叫的团队](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="4efb8-169">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>