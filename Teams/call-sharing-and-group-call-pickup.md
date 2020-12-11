---
title: 呼叫共享和组内呼叫应答
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 呼叫共享和群组呼叫取件允许用户与同事共享传入呼叫，以便当用户不可用时可以捕获呼叫。
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620717"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="76bbb-103">Microsoft Teams 中的呼叫共享和组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="76bbb-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="76bbb-104">Microsoft Teams 的呼叫共享和群组呼叫取件功能允许用户与同事共享其传入呼叫，以便同事可以应答在用户不可用时发生的呼叫。</span><span class="sxs-lookup"><span data-stu-id="76bbb-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="76bbb-105">与其他形式的呼叫共享 (（例如呼叫转发或同时拨打) ）相比，组呼叫取件对收件人的干扰更少，因为用户可以配置如何通过音频和视觉通知、仅可视或 Teams 应用) 中的横幅来接收传入共享呼叫 (的通知，并且他们可决定是否接听。</span><span class="sxs-lookup"><span data-stu-id="76bbb-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="76bbb-106">若要与其他人共享呼叫，用户创建一个呼叫组并添加他们希望与用户共享其呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="76bbb-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="76bbb-107">然后，选择同时响铃或前进设置。</span><span class="sxs-lookup"><span data-stu-id="76bbb-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="76bbb-108">有关详细信息 [，请参阅 Teams 中的呼叫转发和](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 同时拨打。</span><span class="sxs-lookup"><span data-stu-id="76bbb-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="76bbb-109">请注意，只有当移动设备设置为横幅和铃声时，它们才收到通知。</span><span class="sxs-lookup"><span data-stu-id="76bbb-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76bbb-110">用户、呼叫组所有者和呼叫组的成员必须进入"仅 Teams"部署模式。</span><span class="sxs-lookup"><span data-stu-id="76bbb-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="76bbb-111">有关 Teams 部署模式的更多详细信息，请参阅 ["了解 Microsoft Teams 和 Skype for Business 共存和互操作性"](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="76bbb-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="76bbb-112">需要许可证</span><span class="sxs-lookup"><span data-stu-id="76bbb-112">License required</span></span>

<span data-ttu-id="76bbb-113">必须允许用户企业语音，以便设置和使用呼叫共享和群组呼叫取件。</span><span class="sxs-lookup"><span data-stu-id="76bbb-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="76bbb-114">有关许可模型的其他详细信息，请参阅 Microsoft [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="76bbb-114">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="76bbb-115">配置组呼叫取件</span><span class="sxs-lookup"><span data-stu-id="76bbb-115">Configure group call pickup</span></span>

<span data-ttu-id="76bbb-116">要设置组呼叫取件，用户首先配置呼叫组 (这不与安全组或 Microsoft 365 组) 相同，然后添加要与用户共享其呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="76bbb-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="76bbb-117">然后，选择同时拨打或呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="76bbb-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="76bbb-118">有关详细信息和分步过程，请参阅 Teams 中的 [呼叫转发和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="76bbb-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="76bbb-119">呼叫组创建和通知首选项是用户驱动的功能;管理员不需要为用户配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="76bbb-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="76bbb-120">无法从安全组或 Microsoft 365 组创建呼叫组;必须在 Teams 中创建它们。</span><span class="sxs-lookup"><span data-stu-id="76bbb-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="76bbb-121">管理员应该通过 **TeamsCallingPolicy AllowCallGroups 设置为用户** 启用呼叫组。</span><span class="sxs-lookup"><span data-stu-id="76bbb-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="76bbb-122">管理员还可通过 Teams 管理门户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="76bbb-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="76bbb-123">此外，配置的用户还可以直接通过客户端配置其呼叫组。</span><span class="sxs-lookup"><span data-stu-id="76bbb-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="76bbb-124">管理员或最终用户无法相互阻止配置，但 Teams 管理门户和 Teams 客户端应在两处准确显示此关系。</span><span class="sxs-lookup"><span data-stu-id="76bbb-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="76bbb-125">重要提示：当管理员为 (用户关闭呼叫组且呼叫组关系已配置) 时，管理员必须清理 Teams 管理中心中用户的呼叫组关系，以避免不正确的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="76bbb-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="76bbb-126">限制</span><span class="sxs-lookup"><span data-stu-id="76bbb-126">Limitations</span></span>

<span data-ttu-id="76bbb-127">一个租户最多可以包含 32，768 个呼叫组。</span><span class="sxs-lookup"><span data-stu-id="76bbb-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="76bbb-128">每个呼叫组中最多可以有 25 个用户。</span><span class="sxs-lookup"><span data-stu-id="76bbb-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="76bbb-129">更多信息</span><span class="sxs-lookup"><span data-stu-id="76bbb-129">More information</span></span>

[<span data-ttu-id="76bbb-130">Teams 中的呼叫转发和同时拨打</span><span class="sxs-lookup"><span data-stu-id="76bbb-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
