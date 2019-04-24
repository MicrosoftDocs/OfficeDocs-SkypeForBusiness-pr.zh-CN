---
title: Microsoft Teams 中的呼叫共享和组内呼叫应答
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 调用共享并组呼叫应答让用户与同事共享传入呼叫，以便用户不可用时，可以捕获呼叫。
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211820"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="d0713-103">Microsoft Teams 中的呼叫共享和组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="d0713-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="d0713-104">呼叫共享和组呼叫 Microsoft 团队让的用户共享其传入呼叫与同事，以便同事可以应答，当用户不可用时进行的呼叫的分拣的功能。</span><span class="sxs-lookup"><span data-stu-id="d0713-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="d0713-105">组呼叫应答是呼叫的对中断较小收件人比其他形式的共享 （如呼叫转接或同时响铃），因为用户可配置他们希望如何通知的 （通过音频和可视通知，仅 visual 共享传入呼叫或横幅团队应用程序中），并且他们可以决定是否要应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0713-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="d0713-106">与其他人共享呼叫，用户的呼叫组并将添加他们希望共享具有其呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="d0713-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="d0713-107">然后他们选择同时响铃，或转发设置。</span><span class="sxs-lookup"><span data-stu-id="d0713-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="d0713-108">有关详细信息，请参阅[呼叫转接和同时拨打团队](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="d0713-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0713-109">用户、 呼叫组所有者和呼叫组的成员必须在仅团队部署模式下。</span><span class="sxs-lookup"><span data-stu-id="d0713-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="d0713-110">团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="d0713-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="d0713-111">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="d0713-111">License required</span></span>

<span data-ttu-id="d0713-112">用户必须启用设置和使用呼叫共享和组呼叫应答的企业语音。</span><span class="sxs-lookup"><span data-stu-id="d0713-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="d0713-113">有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d0713-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="d0713-114">配置组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="d0713-114">Configure group call pickup</span></span>

<span data-ttu-id="d0713-115">若要设置组的呼叫应答，用户首次配置 （这是不相同为安全组或 Office 365 组） 的呼叫组，，然后添加他们希望共享具有其呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="d0713-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="d0713-116">然后，他们选择同时响铃，或呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="d0713-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="d0713-117">有关详细信息和分步过程，请参阅[呼叫转接和同时拨打团队](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="d0713-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="d0713-118">呼叫组的创建和通知首选项是用户驱动的功能;管理员不需要配置这些功能的用户。</span><span class="sxs-lookup"><span data-stu-id="d0713-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="d0713-119">无法从安全组或 Office 365 组; 创建呼叫组必须在工作组中创建它们。</span><span class="sxs-lookup"><span data-stu-id="d0713-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="d0713-120">管理员应启用通过**TeamsCallingPolicy AllowCallGroups**设置用户的呼叫组。</span><span class="sxs-lookup"><span data-stu-id="d0713-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="d0713-121">管理员可以仅控制此用户是否可以配置呼叫组。</span><span class="sxs-lookup"><span data-stu-id="d0713-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="d0713-122">一旦位设置为 true，则管理员无法防止其他用户配置和添加他们选择的呼叫组用户。</span><span class="sxs-lookup"><span data-stu-id="d0713-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="d0713-123">限制</span><span class="sxs-lookup"><span data-stu-id="d0713-123">Limitations</span></span>

<span data-ttu-id="d0713-124">租户可以包含最多个 32768 呼叫组。</span><span class="sxs-lookup"><span data-stu-id="d0713-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="d0713-125">可以有 5 个用户每个呼叫组中的最大值。</span><span class="sxs-lookup"><span data-stu-id="d0713-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="d0713-126">更多信息</span><span class="sxs-lookup"><span data-stu-id="d0713-126">More information</span></span>

[<span data-ttu-id="d0713-127">呼叫转接和同时响铃团队中</span><span class="sxs-lookup"><span data-stu-id="d0713-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)