---
title: 使用策略管理 Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解 Teams 策略。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460492"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="568ca-103">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="568ca-103">Manage Teams with policies</span></span>

<span data-ttu-id="568ca-104">策略是管理 Teams 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="568ca-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="568ca-105">使用本文导航如何使用策略为组织带来好处。</span><span class="sxs-lookup"><span data-stu-id="568ca-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="568ca-106">策略的使用</span><span class="sxs-lookup"><span data-stu-id="568ca-106">What you use policies for</span></span>

<span data-ttu-id="568ca-107">策略用于在组织中跨不同领域（如消息传递、会议和应用程序）完成许多任务。</span><span class="sxs-lookup"><span data-stu-id="568ca-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="568ca-108">你可以执行一些操作，包括允许用户在团队频道中安排会议、允许用户编辑发送的消息，以及控制用户是否可以将应用固定到 Teams 应用栏。</span><span class="sxs-lookup"><span data-stu-id="568ca-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="568ca-109">如何分配策略</span><span class="sxs-lookup"><span data-stu-id="568ca-109">How to assign policies</span></span>

<span data-ttu-id="568ca-110">根据组织正在尝试完成的任务，可以通过多种不同方式分配策略。</span><span class="sxs-lookup"><span data-stu-id="568ca-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="568ca-111">可以在 Teams 管理中心进行作业和查看作业。</span><span class="sxs-lookup"><span data-stu-id="568ca-111">You can make and view assignments in the Teams admin center.</span></span>

![组策略分配的屏幕截图。](media/group-policy-assignment.png)

<span data-ttu-id="568ca-113">在此处详细了解如何分配 [策略](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="568ca-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="568ca-114">如何管理策略</span><span class="sxs-lookup"><span data-stu-id="568ca-114">How to manage policies</span></span>

<span data-ttu-id="568ca-115">策略通过 Microsoft Teams 管理中心或 [PowerShell 进行管理](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="568ca-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="568ca-116">例如，应用设置策略允许你允许用户上传自定义应用、代表用户安装应用，以及将应用固定到 Teams 应用栏。</span><span class="sxs-lookup"><span data-stu-id="568ca-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="568ca-117">这些策略在 Teams 管理中心中配置。</span><span class="sxs-lookup"><span data-stu-id="568ca-117">These policies are configured in the Teams admin center.</span></span>

![应用设置策略的屏幕截图。](media/app-setup-policy.png)

<span data-ttu-id="568ca-119">此外，会议策略可用于控制 Teams 会议中的音频和视频设置，例如听录、云录制和 IP 音频/视频。</span><span class="sxs-lookup"><span data-stu-id="568ca-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![会议策略的屏幕截图。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="568ca-121">Teams 教育版</span><span class="sxs-lookup"><span data-stu-id="568ca-121">Teams for Education</span></span>

<span data-ttu-id="568ca-122">还可使用 Teams [教育策略向导](easy-policy-setup-edu.md) 轻松设置和管理学习环境的策略。</span><span class="sxs-lookup"><span data-stu-id="568ca-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams 教育策略向导的屏幕截图。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="568ca-124">策略类型</span><span class="sxs-lookup"><span data-stu-id="568ca-124">Types of policies</span></span>

<span data-ttu-id="568ca-125">可以使用 Microsoft Teams 管理以下策略。</span><span class="sxs-lookup"><span data-stu-id="568ca-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="568ca-126">策略类型</span><span class="sxs-lookup"><span data-stu-id="568ca-126">Policy type</span></span> | <span data-ttu-id="568ca-127">说明</span><span class="sxs-lookup"><span data-stu-id="568ca-127">Description</span></span>
------------|------------
[<span data-ttu-id="568ca-128">策略包</span><span class="sxs-lookup"><span data-stu-id="568ca-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="568ca-129">Microsoft Teams 中的策略包是可分配给组织中具有类似角色的用户的预定义策略和设置的集合。</span><span class="sxs-lookup"><span data-stu-id="568ca-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="568ca-130">会议策略</span><span class="sxs-lookup"><span data-stu-id="568ca-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="568ca-131">会议策略用于控制可供会议参与者用于组织中用户安排的会议的功能。</span><span class="sxs-lookup"><span data-stu-id="568ca-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="568ca-132">会议策略包括以下主题。</span><span class="sxs-lookup"><span data-stu-id="568ca-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="568ca-133">- 音频和视频策略</span><span class="sxs-lookup"><span data-stu-id="568ca-133">- Audio and video policies</span></span><br> <span data-ttu-id="568ca-134">- 内容和屏幕共享策略</span><span class="sxs-lookup"><span data-stu-id="568ca-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="568ca-135">- 参与者、来宾和访问策略</span><span class="sxs-lookup"><span data-stu-id="568ca-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="568ca-136">- 常规策略</span><span class="sxs-lookup"><span data-stu-id="568ca-136">- General policies</span></span>
[<span data-ttu-id="568ca-137">语音和呼叫策略</span><span class="sxs-lookup"><span data-stu-id="568ca-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="568ca-138">语音和呼叫策略通过紧急呼叫、呼叫路由和呼叫者 ID 等团队管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="568ca-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="568ca-139">应用策略</span><span class="sxs-lookup"><span data-stu-id="568ca-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="568ca-140">应用策略用于控制 Microsoft Teams 中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="568ca-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="568ca-141">管理员可以允许或阻止用户可以安装哪些应用，将应用程序固定到用户的 Teams 应用栏，并代表用户安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="568ca-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="568ca-142">消息策略</span><span class="sxs-lookup"><span data-stu-id="568ca-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="568ca-143">消息传送策略控制聊天和通道功能可用性。</span><span class="sxs-lookup"><span data-stu-id="568ca-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="568ca-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="568ca-144">Related topics</span></span>

* [<span data-ttu-id="568ca-145">在 Microsoft Teams 中管理反馈策略</span><span class="sxs-lookup"><span data-stu-id="568ca-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="568ca-146">在 Microsoft Teams 中管理团队策略</span><span class="sxs-lookup"><span data-stu-id="568ca-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="568ca-147">在活动日志中查看策略分配</span><span class="sxs-lookup"><span data-stu-id="568ca-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="568ca-148">在 Microsoft Teams 中为实时事件进行设置</span><span class="sxs-lookup"><span data-stu-id="568ca-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="568ca-149">Teams 教育策略和策略包</span><span class="sxs-lookup"><span data-stu-id="568ca-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
