---
title: Teams 更新
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文介绍更新 Microsoft Teams 桌面客户端的过程。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119241"
---
# <a name="teams-update-process"></a><span data-ttu-id="81d0c-103">Teams 更新过程</span><span class="sxs-lookup"><span data-stu-id="81d0c-103">Teams update process</span></span>

<span data-ttu-id="81d0c-104">Teams Web 应用每周更新一次。</span><span class="sxs-lookup"><span data-stu-id="81d0c-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="81d0c-105">通过 TAP 技术采用计划进行严格的内部测试和验证后，Teams 桌面客户端更新每两周发布 (一) 。</span><span class="sxs-lookup"><span data-stu-id="81d0c-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="81d0c-106">更新通常在星期二进行。</span><span class="sxs-lookup"><span data-stu-id="81d0c-106">The update usually takes place on a Tuesday.</span></span> <span data-ttu-id="81d0c-107">如果需要关键更新，Teams 将绕过此计划，在更新可用时立即发布。</span><span class="sxs-lookup"><span data-stu-id="81d0c-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="81d0c-108">桌面客户端会自动更新自身。</span><span class="sxs-lookup"><span data-stu-id="81d0c-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="81d0c-109">Teams 每隔几小时在后台检查更新，下载更新，然后等待计算机处于空闲状态，然后以无提示方式安装更新。</span><span class="sxs-lookup"><span data-stu-id="81d0c-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="81d0c-110">用户还可通过在应用右上方的"配置文件"下拉菜单上选择"检查更新"来手动下载更新。</span><span class="sxs-lookup"><span data-stu-id="81d0c-110">Users can also manually download updates by selecting **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="81d0c-111">如果有可用的更新，则当计算机空闲时，将下载更新并静默安装。</span><span class="sxs-lookup"><span data-stu-id="81d0c-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="81d0c-112">用户需要登录，以便下载更新。</span><span class="sxs-lookup"><span data-stu-id="81d0c-112">Users need to be signed in for updates to be downloaded.</span></span>

<span data-ttu-id="81d0c-113">从 2019 年 7 月 31 日开始，Teams 客户端更新在更新期间使用较低的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="81d0c-113">Starting July 31, 2019, Teams client updates use lower network bandwidth during the update.</span></span> <span data-ttu-id="81d0c-114">此更新默认打开，不需要管理员或用户执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="81d0c-114">This update is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="81d0c-115">适用于企业的 Microsoft 365 应用更新怎么样？</span><span class="sxs-lookup"><span data-stu-id="81d0c-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="81d0c-116">Teams 默认安装有新安装的 Microsoft 365 企业版应用，如使用 [适用于企业的 Microsoft 365](/DeployOffice/teams-install)应用部署 Microsoft Teams 中所述。</span><span class="sxs-lookup"><span data-stu-id="81d0c-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).</span></span>

<span data-ttu-id="81d0c-117">团队遵循其更新过程，如上所述。</span><span class="sxs-lookup"><span data-stu-id="81d0c-117">Teams follows its own update process as outlined above.</span></span> <span data-ttu-id="81d0c-118">Teams 不遵循其他办公室应用（如 Word 和 Excel）的更新过程。</span><span class="sxs-lookup"><span data-stu-id="81d0c-118">Teams doesn't follow the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="81d0c-119">有关详细信息，请阅读适用于企业的 [Microsoft 365 应用更新频道概述](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="81d0c-119">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="81d0c-120">VDI 上的 Teams 更新怎么样？</span><span class="sxs-lookup"><span data-stu-id="81d0c-120">What about updates to Teams on VDI?</span></span>


<span data-ttu-id="81d0c-121">虚拟桌面基础结构 (VDI) 上的 Teams 客户端不会以非 VDI Teams 客户端的方式自动更新。</span><span class="sxs-lookup"><span data-stu-id="81d0c-121">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="81d0c-122">必须按照在 VDI 上安装 Teams 的说明中的说明，通过安装新的 MSI [来更新 VM 映像](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="81d0c-122">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](teams-for-vdi.md).</span></span> <span data-ttu-id="81d0c-123">必须卸载当前版本，以更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="81d0c-123">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="81d0c-124">管理员能否部署更新而不是 Teams 自动更新？</span><span class="sxs-lookup"><span data-stu-id="81d0c-124">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="81d0c-125">Teams 不会向管理员提供通过任何传送机制部署更新的能力。</span><span class="sxs-lookup"><span data-stu-id="81d0c-125">Teams doesn't give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="81d0c-126">服务协议</span><span class="sxs-lookup"><span data-stu-id="81d0c-126">Servicing agreement</span></span>

<span data-ttu-id="81d0c-127">作为新式联机服务，Teams 客户端每两周自动更新一次。</span><span class="sxs-lookup"><span data-stu-id="81d0c-127">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="81d0c-128">由于 Teams 受新式生命周期策略约束，因此用户应保持使用桌面客户端的最新版本。</span><span class="sxs-lookup"><span data-stu-id="81d0c-128">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="81d0c-129">自动更新可确保用户具有最新功能、性能增强功能、安全性和服务可靠性。</span><span class="sxs-lookup"><span data-stu-id="81d0c-129">Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="81d0c-130">若要确定桌面客户端何时过期，如果用户的当前版本为 1 个月到 3 个月，并且是否有可用的新版本，则会显示应用内警报。</span><span class="sxs-lookup"><span data-stu-id="81d0c-130">To identify when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="81d0c-131">此应用内消息传送鼓励用户更新到最新版本的 Teams，或者在必要时与 IT 管理员联系以这样做。</span><span class="sxs-lookup"><span data-stu-id="81d0c-131">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="81d0c-132">超过三个月的 Teams 桌面客户端上的用户将看到阻止页面，该页面提供选项用于现在更新、联系 IT 管理员或继续访问 Teams 网页版。</span><span class="sxs-lookup"><span data-stu-id="81d0c-132">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="81d0c-133">首次安装和/或首次运行 Teams 时超过三个月的桌面客户端版本在遇到上述服务信息之前有 28 天的宽限期。</span><span class="sxs-lookup"><span data-stu-id="81d0c-133">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="81d0c-134">在此期间，自动更新过程将更新 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="81d0c-134">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="81d0c-135">如果未更新，用户将看到一个应用内警报，鼓励他们手动更新到最新版本的 Teams。</span><span class="sxs-lookup"><span data-stu-id="81d0c-135">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams.</span></span> <span data-ttu-id="81d0c-136">系统可能会提示用户联系其 IT 管理员以执行更新。</span><span class="sxs-lookup"><span data-stu-id="81d0c-136">The users might be prompted to contact their IT admin to do the update.</span></span> <span data-ttu-id="81d0c-137">这包括使用 Teams 桌面客户端作为 Microsoft 365 企业版应用捆绑包的一部分的用户。</span><span class="sxs-lookup"><span data-stu-id="81d0c-137">This includes users using the Teams desktop client as part of the Microsoft 365 Apps for enterprise bundle.</span></span>

<span data-ttu-id="81d0c-138">在进一步通知之前，政府云上的 Teams 桌面客户端当前对本服务协议有例外。</span><span class="sxs-lookup"><span data-stu-id="81d0c-138">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="81d0c-139">有关新版本的信息，请查看消息 [中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或转到帮助  >  **客户端** 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="81d0c-139">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
