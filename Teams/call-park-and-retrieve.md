---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫暂停和检索在 Microsoft Teams 中保留呼叫。
ms.openlocfilehash: efc36a2bc90b64abf2e886c5e768a26704bd6550
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102798"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="cf9fa-103">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="cf9fa-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="cf9fa-104">呼叫暂停和检索是允许用户保留呼叫的一项功能。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="cf9fa-105">当呼叫被停时，服务会生成一个唯一的代码用于调用检索。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="cf9fa-106">然后，将呼叫停放在一起的用户或其他人可以将该代码与受支持的应用或设备一起用于检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="cf9fa-107"> (有关详细信息，请参阅在 [Teams 中停放](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) ) </span><span class="sxs-lookup"><span data-stu-id="cf9fa-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="cf9fa-108">使用呼叫公园的一些常见方案包括：</span><span class="sxs-lookup"><span data-stu-id="cf9fa-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="cf9fa-109">接待员为在工厂中工作的人拨打了电话。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="cf9fa-110">然后，接待员通过公用地址系统报出呼叫和代码号。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="cf9fa-111">然后，呼叫的用户可以在工厂车间拿起 Teams 电话，并输入代码以检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="cf9fa-112">用户将呼叫放在移动设备上，因为设备电池电量不足。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="cf9fa-113">然后，用户可以输入代码以从 Teams 桌面电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="cf9fa-114">支持代表将客户呼叫放在一起，在 Teams 频道上发送公告，让专家检索呼叫并帮助客户。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="cf9fa-115">专家在 Teams 客户端中输入代码以检索呼叫</span><span class="sxs-lookup"><span data-stu-id="cf9fa-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="cf9fa-116">要停放和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫停放策略中。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="cf9fa-117">呼叫暂停和检索仅在 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 部署模式下可用，在 Skype for Business IP 电话上不受支持。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="cf9fa-118">配置呼叫停放和检索</span><span class="sxs-lookup"><span data-stu-id="cf9fa-118">Configure call park and retrieve</span></span>

<span data-ttu-id="cf9fa-119">你必须是 Teams 管理员才能配置呼叫停放和检索。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="cf9fa-120">默认情况下，它处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-120">It is disabled by default.</span></span> <span data-ttu-id="cf9fa-121">你可以为用户启用它，然后使用呼叫允许策略创建用户组。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="cf9fa-122">将同一策略应用到一组用户时，他们可以在用户之间停放和检索调用。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="cf9fa-123">启用呼叫公园策略</span><span class="sxs-lookup"><span data-stu-id="cf9fa-123">To enable a call park policy</span></span>

1. <span data-ttu-id="cf9fa-124">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音**  >  **呼叫""公园策略"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="cf9fa-125">在"**管理策略"选项卡** 上，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="cf9fa-126">为策略命名，然后将"允许 **呼叫停放"切换为**"**开"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![呼叫公园策略设置的屏幕截图](media/call-park-add-policy.png)

4. <span data-ttu-id="cf9fa-128">选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-128">Select **Save**.</span></span>

<span data-ttu-id="cf9fa-129">可以通过在列表中选择策略并单击"编辑"来编辑 **策略**。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="cf9fa-130">若要使策略正常工作，必须将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="cf9fa-131">可以 [单独向用户分配策略](assign-policies.md) 或将其分配到组。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="cf9fa-132">将呼叫部件策略分配给组</span><span class="sxs-lookup"><span data-stu-id="cf9fa-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="cf9fa-133">在"**呼叫公园策略"** 页上的"组 **策略分配**"选项卡上，单击"**添加组"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="cf9fa-134">搜索想要使用的组，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="cf9fa-135">选择与其他组作业相比的排位。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="cf9fa-136">在 **"选择策略**"下，选择要将该组分配到的策略。</span><span class="sxs-lookup"><span data-stu-id="cf9fa-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![公园策略图像](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="cf9fa-138">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="cf9fa-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf9fa-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="cf9fa-139">Related topics</span></span>

[<span data-ttu-id="cf9fa-140">在 Teams 中停放通话</span><span class="sxs-lookup"><span data-stu-id="cf9fa-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="cf9fa-141">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="cf9fa-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="cf9fa-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="cf9fa-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="cf9fa-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="cf9fa-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="cf9fa-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="cf9fa-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)