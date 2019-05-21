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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 呼叫共享和群组通话分拣允许用户与同事共享传入呼叫, 以便可以在用户不可用时捕获呼叫。
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283476"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="50e5f-103">Microsoft Teams 中的呼叫共享和组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="50e5f-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="50e5f-104">Microsoft 团队的呼叫共享和组呼叫功能允许用户与同事共享传入呼叫, 以便同事可以接听在用户不可用时出现的呼叫。</span><span class="sxs-lookup"><span data-stu-id="50e5f-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="50e5f-105">组呼叫对收件人的干扰比其他呼叫共享形式 (如呼叫转接或同时拨打) 的干扰更少, 因为用户可以配置他们希望如何收到传入共享呼叫的通知 (通过音频和视觉通知, 仅限 visual)"团队" 应用中的 "标题" 或 "横幅", 他们可以决定是否应答。</span><span class="sxs-lookup"><span data-stu-id="50e5f-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="50e5f-106">若要与其他人共享呼叫, 用户将创建呼叫组, 并添加他们想要与之共享其通话的用户。</span><span class="sxs-lookup"><span data-stu-id="50e5f-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="50e5f-107">然后选择 "同时拨打" 或 "转发" 设置。</span><span class="sxs-lookup"><span data-stu-id="50e5f-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="50e5f-108">有关详细信息, 请参阅有关[团队的呼叫转接和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="50e5f-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50e5f-109">用户、呼叫组所有者和呼叫组成员必须位于 "仅限团队" 部署模式。</span><span class="sxs-lookup"><span data-stu-id="50e5f-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="50e5f-110">有关团队部署模式的更多详细信息, 请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="50e5f-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="50e5f-111">需要许可证</span><span class="sxs-lookup"><span data-stu-id="50e5f-111">License required</span></span>

<span data-ttu-id="50e5f-112">用户必须是启用企业语音才能设置和使用呼叫共享和组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="50e5f-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="50e5f-113">有关许可模型的其他详细信息, 请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="50e5f-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="50e5f-114">配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="50e5f-114">Configure group call pickup</span></span>

<span data-ttu-id="50e5f-115">若要设置组呼叫装货, 用户首先配置呼叫组 (这与安全组或 Office 365 组不同), 然后添加他们想要与之共享呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="50e5f-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="50e5f-116">然后, 选择 "同时拨打" 或 "呼叫转接" 设置。</span><span class="sxs-lookup"><span data-stu-id="50e5f-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="50e5f-117">有关详细信息和分步过程, 请参阅[团队中的呼叫转接和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="50e5f-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="50e5f-118">呼叫组创建和通知首选项是用户驱动的功能;管理员不必为其用户配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="50e5f-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="50e5f-119">无法从安全组或 Office 365 组创建呼叫组;它们必须在团队中创建。</span><span class="sxs-lookup"><span data-stu-id="50e5f-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="50e5f-120">管理员应通过用户的**TeamsCallingPolicy AllowCallGroups**设置启用呼叫组。</span><span class="sxs-lookup"><span data-stu-id="50e5f-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="50e5f-121">管理员只能控制此用户是否可以配置呼叫组。</span><span class="sxs-lookup"><span data-stu-id="50e5f-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="50e5f-122">一旦将该位设置为 true, 管理员就无法阻止用户配置和添加呼叫组用户选择的用户。</span><span class="sxs-lookup"><span data-stu-id="50e5f-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="50e5f-123">优缺点</span><span class="sxs-lookup"><span data-stu-id="50e5f-123">Limitations</span></span>

<span data-ttu-id="50e5f-124">一个租户最多可以包含32768个呼叫组。</span><span class="sxs-lookup"><span data-stu-id="50e5f-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="50e5f-125">每个呼叫组中最多只能有5个用户。</span><span class="sxs-lookup"><span data-stu-id="50e5f-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="50e5f-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="50e5f-126">More information</span></span>

[<span data-ttu-id="50e5f-127">团队中的呼叫转接和同时拨打</span><span class="sxs-lookup"><span data-stu-id="50e5f-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)