---
title: 在 Microsoft Teams 中设置网络Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何管理会议网络研讨会Teams策略。
ms.openlocfilehash: 739c0b5494b0ecc5b9a20fd8db4756313848325b
ms.sourcegitcommit: e5d6a2c3ad45c1285016b93ec4c7afea907d71a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275514"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="b57a3-103">在 Microsoft Teams 中设置网络Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b57a3-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="b57a3-104">本文将帮助你将组织设置为举办网络研讨会。</span><span class="sxs-lookup"><span data-stu-id="b57a3-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="b57a3-105">什么是网络研讨会？</span><span class="sxs-lookup"><span data-stu-id="b57a3-105">What are webinars?</span></span>

<span data-ttu-id="b57a3-106">网络研讨会是结构化会议，教师和参与者具有明确的角色，通常用于培训或销售和营销潜在顾客生成方案。</span><span class="sxs-lookup"><span data-stu-id="b57a3-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="b57a3-107">在组织中设置网络研讨会后，用户可以安排网络研讨会并向与会者开放注册。</span><span class="sxs-lookup"><span data-stu-id="b57a3-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="b57a3-108">与包含许多讨论和任务分配的传统会议不同，网络研讨会适用于交互式演示文稿，并提供用于与会者分析的工具。</span><span class="sxs-lookup"><span data-stu-id="b57a3-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="b57a3-109">允许用户使用 PowerShell 安排网络研讨会</span><span class="sxs-lookup"><span data-stu-id="b57a3-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="b57a3-110">可以在 Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet 中使用以下属性为 Teams 中的网络研讨会设置。</span><span class="sxs-lookup"><span data-stu-id="b57a3-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="b57a3-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="b57a3-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="b57a3-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="b57a3-112">WhoCanRegister</span></span>
- <span data-ttu-id="b57a3-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b57a3-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="b57a3-114">有关 cmdlet 详细信息，请阅读[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b57a3-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b57a3-115">在运行这些 cmdlet 之前，必须连接到 Skype for Business PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b57a3-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="b57a3-116">有关详细信息，请参阅使用[powerShell Skype for Business管理 Microsoft 365 Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="b57a3-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="b57a3-117">允许用户计划网络研讨会</span><span class="sxs-lookup"><span data-stu-id="b57a3-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="b57a3-118">若要允许组织中用户计划网络研讨会，请运行：</span><span class="sxs-lookup"><span data-stu-id="b57a3-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="b57a3-119">配置谁可以注册网络研讨会</span><span class="sxs-lookup"><span data-stu-id="b57a3-119">Configure who can register for webinars</span></span>

<span data-ttu-id="b57a3-120">可以将注册限制为仅组织内部用户，或者向租户内外的每个人开放注册。</span><span class="sxs-lookup"><span data-stu-id="b57a3-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="b57a3-121">默认情况下 **，WhoCanRegister** 已启用，并设置为"每个人 **"。**</span><span class="sxs-lookup"><span data-stu-id="b57a3-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="b57a3-122">如果要关闭会议注册，将 **WhoCanRegister 设置为** **False。**</span><span class="sxs-lookup"><span data-stu-id="b57a3-122">If you want to turn off meeting registration, set **WhoCanRegister** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b57a3-123">请记住 **，AllowPrivateMeetingScheduling** 必须设置为 **True，WhoCanRegister** 可正常工作。 </span><span class="sxs-lookup"><span data-stu-id="b57a3-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **WhoCanRegister** to work.</span></span> <span data-ttu-id="b57a3-124">此外，需要在"Microsoft 列表"中设置SharePoint。</span><span class="sxs-lookup"><span data-stu-id="b57a3-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="b57a3-125">有关详细信息，请参阅 Microsoft [列表的控件设置](/sharepoint/control-lists)。</span><span class="sxs-lookup"><span data-stu-id="b57a3-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="b57a3-126">**若要 *仅* 允许您的组织中的用户注册网络研讨会，请运行：**</span><span class="sxs-lookup"><span data-stu-id="b57a3-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="b57a3-127">然后，运行：</span><span class="sxs-lookup"><span data-stu-id="b57a3-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="b57a3-128">**若要允许任何人（包括匿名用户）注册网络研讨会，请运行：**</span><span class="sxs-lookup"><span data-stu-id="b57a3-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="b57a3-129">然后，运行：</span><span class="sxs-lookup"><span data-stu-id="b57a3-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="b57a3-130">如果在会议设置中关闭匿名加入，则匿名用户无法加入网络研讨会。</span><span class="sxs-lookup"><span data-stu-id="b57a3-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="b57a3-131">若要了解并启用此设置，请参阅会议[Teams。](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b57a3-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="b57a3-132">收集会议出席情况</span><span class="sxs-lookup"><span data-stu-id="b57a3-132">Collect meeting attendance</span></span>

<span data-ttu-id="b57a3-133">如果希望组织者分析谁注册和参加网络研讨会，则需要启用 **AllowEngagementReport** 策略。</span><span class="sxs-lookup"><span data-stu-id="b57a3-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="b57a3-134">为此，请运行 PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="b57a3-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="b57a3-135">配置网络研讨会设置</span><span class="sxs-lookup"><span data-stu-id="b57a3-135">Configure webinar settings</span></span>

<span data-ttu-id="b57a3-136">为网络研讨会启用环境后，无需进一步管理管理员。</span><span class="sxs-lookup"><span data-stu-id="b57a3-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="b57a3-137">策略控制向网络研讨会组织者显示的选项。</span><span class="sxs-lookup"><span data-stu-id="b57a3-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b57a3-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="b57a3-138">Related topics</span></span>

- [<span data-ttu-id="b57a3-139">会议策略 - Teams - 常规</span><span class="sxs-lookup"><span data-stu-id="b57a3-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="b57a3-140">Set-CsTeamsMeetingPolicy 文档</span><span class="sxs-lookup"><span data-stu-id="b57a3-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
