---
title: 准备服务以升级到 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解为组织准备使用云语音服务进行协作和云语音Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ad5887c50b15efc2dcddd000a8f117c2f350ac5
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282182"
---
# <a name="prepare-your-service-for-upgrading-to-teams"></a><span data-ttu-id="fd8dd-103">准备服务以升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="fd8dd-103">Prepare your service for upgrading to Teams</span></span>

<span data-ttu-id="fd8dd-104">![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="fd8dd-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="fd8dd-105">本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="fd8dd-106">在继续之前，请确认已完成之前阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="fd8dd-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="fd8dd-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="fd8dd-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="fd8dd-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="fd8dd-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="fd8dd-109">了解两者共存Skype for Business互操作性Teams</span><span class="sxs-lookup"><span data-stu-id="fd8dd-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="fd8dd-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="fd8dd-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="fd8dd-111">本文概述了为组织准备使用云语音服务进行协作和云语音服务Teams。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-111">This article gives an overview of the requirements for preparing your organization for collaboration and cloud voice services with Teams.</span></span> <span data-ttu-id="fd8dd-112">通过正确准备，你可以确保已准备好向组织提供这些功能。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-112">By preparing properly, you can be sure you're ready to provide these capabilities to your organization.</span></span>

## <a name="onboarding-checklists-and-landing-pages-for-microsoft-teams-rollout"></a><span data-ttu-id="fd8dd-113">载入清单和登陆页面Microsoft Teams推出</span><span class="sxs-lookup"><span data-stu-id="fd8dd-113">Onboarding checklists and landing pages for Microsoft Teams rollout</span></span>

<span data-ttu-id="fd8dd-114">以下清单和登陆页将演练在组织中部署Microsoft Teams的步骤：</span><span class="sxs-lookup"><span data-stu-id="fd8dd-114">The following checklists and landing pages walk you through the steps for deploying Microsoft Teams in your organization:</span></span>

- [<span data-ttu-id="fd8dd-115">为Microsoft 365准备Office 365或Teams</span><span class="sxs-lookup"><span data-stu-id="fd8dd-115">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

- [<span data-ttu-id="fd8dd-116">配置Teams核心功能</span><span class="sxs-lookup"><span data-stu-id="fd8dd-116">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

- [<span data-ttu-id="fd8dd-117">准备网络</span><span class="sxs-lookup"><span data-stu-id="fd8dd-117">Prepare your network</span></span>](prepare-network.md)

- [<span data-ttu-id="fd8dd-118">聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="fd8dd-118">Chat, teams, channels, and apps</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

- [<span data-ttu-id="fd8dd-119">会议和音频会议</span><span class="sxs-lookup"><span data-stu-id="fd8dd-119">Meetings and audio conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

- [<span data-ttu-id="fd8dd-120">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="fd8dd-120">Phone System and PSTN connectivity options</span></span>](cloud-voice-landing-page.md)


<span data-ttu-id="fd8dd-121">这些清单中的任务和活动是核心的"任务"项目，适用于使用 Teams 的协作和语音功能的每一个部署。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-121">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of collaboration and voice capabilities with Teams.</span></span> <span data-ttu-id="fd8dd-122">可以自定义清单，以包含特定于自己的任务旅程的活动Teams任务。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-122">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

<span data-ttu-id="fd8dd-123">使用提供的清单跟踪每个单独活动和任务的状态，并确保未跳过任何关键步骤。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-123">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="fd8dd-124">每个活动包含所需操作的详细说明，并引用可用于完成该活动的其他信息。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-124">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="fd8dd-125">尽管我们建议按顺序遵循清单，但确切顺序取决于部署范围和环境的配置和复杂性。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-125">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="fd8dd-126">它们被组织为支持"绿地"Teams部署 (之前没有 Skype for Business Online 状态) 或者从 Skype for Business Online 升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-126">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or upgrading from Skype for Business Online to Teams.</span></span> <span data-ttu-id="fd8dd-127">如果要从 Skype for Business Online 升级，则你可能已完成其中一些活动，现在可以忽略这些活动。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-127">If you're upgrading from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="fd8dd-128">当您按网站载入用户时，强烈建议使用 [适用于 Voice (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 的站点启用 Playbook) 作为这些清单的补充指南。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-128">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="fd8dd-129">大多数配置设置在 Teams 和 Skype for Business Online 之间很常见。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-129">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="fd8dd-130">使用 Microsoft Teams管理中心配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-130">You use the Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="fd8dd-131">决策点</span><span class="sxs-lookup"><span data-stu-id="fd8dd-131">Decision point</span></span></td><td><ul><li><span data-ttu-id="fd8dd-132">Who将负责监督登记清单的完成情况？</span><span class="sxs-lookup"><span data-stu-id="fd8dd-132">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="fd8dd-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd8dd-133">Next steps</span></span></td><td><ul><li><span data-ttu-id="fd8dd-134">下载载入清单。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-134">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="fd8dd-135">根据组织的部署计划逐步完成登记清单项。</span><span class="sxs-lookup"><span data-stu-id="fd8dd-135">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="fd8dd-136">继续载入</span><span class="sxs-lookup"><span data-stu-id="fd8dd-136">Continue onboarding</span></span>

<span data-ttu-id="fd8dd-137">完成此清单后，继续执行下一步： [进行用户试点](pilot-essentials.md)</span><span class="sxs-lookup"><span data-stu-id="fd8dd-137">After you complete this checklist, proceed to the next step: [Conduct a user pilot](pilot-essentials.md)</span></span>

[//]: # (@Turgay，我注释掉下一段落，因为它是特定于云语音的。)
<!--
As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site to cloud voice, and help ensure that you plan and execute important site-specific activities.
-->