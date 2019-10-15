---
title: 团队更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 了解如何更新团队桌面客户端。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba6201d0f1b52b7ebfd869ad699c2eb06eb664d8
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37508796"
---
# <a name="teams-update-process"></a><span data-ttu-id="295c5-103">团队更新流程</span><span class="sxs-lookup"><span data-stu-id="295c5-103">Teams update process</span></span>

<span data-ttu-id="295c5-104">每周更新团队 web 应用。</span><span class="sxs-lookup"><span data-stu-id="295c5-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="295c5-105">团队桌面客户端更新在经过我们的技术采纳计划（点击）严格内部测试和验证后每两周发布一次。</span><span class="sxs-lookup"><span data-stu-id="295c5-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="295c5-106">这通常发生在星期二。</span><span class="sxs-lookup"><span data-stu-id="295c5-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="295c5-107">如果需要关键更新，团队将绕过此计划，并在更新推出后立即发布更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="295c5-108">桌面客户端会自动更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="295c5-109">团队会在后台每隔几小时检查一次更新，下载它，然后等待计算机处于空闲状态，然后再进行无提示安装更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="295c5-110">用户还可以通过在应用的右上角的 "**配置文件**" 下拉菜单上单击 "**检查更新**"，手动下载更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="295c5-111">如果有可用更新，则会在计算机空闲时下载并自动安装该更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="295c5-112">用户需要登录才能下载更新。</span><span class="sxs-lookup"><span data-stu-id="295c5-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="295c5-113">从2019年7月31日开始，团队客户端更新在更新期间使用显著降低网络带宽。</span><span class="sxs-lookup"><span data-stu-id="295c5-113">Starting July 31, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="295c5-114">默认情况下，此项处于打开状态，不需要管理员或用户执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="295c5-114">This is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="295c5-115">Office 365 专业增强版的更新有哪些更新？</span><span class="sxs-lookup"><span data-stu-id="295c5-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="295c5-116">默认情况下，团队通过 office 365 专业增强版的全新安装进行安装，如[使用 office 365 专业增强版部署 Microsoft 团队](https://docs.microsoft.com/DeployOffice/teams-install)中所述。</span><span class="sxs-lookup"><span data-stu-id="295c5-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="295c5-117">团队关注其自己的更新过程（如上文所述），而不是其他分支应用（如 Word 和 Excel）的更新过程。</span><span class="sxs-lookup"><span data-stu-id="295c5-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="295c5-118">若要了解详细信息，请参阅[Office 365 专业增强版更新频道概述](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="295c5-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="295c5-119">对 VDI 的团队更新有何区别？</span><span class="sxs-lookup"><span data-stu-id="295c5-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="295c5-120">虚拟桌面基础结构（VDI）上的团队客户端不会自动更新非 VDI 团队客户端的方式。</span><span class="sxs-lookup"><span data-stu-id="295c5-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="295c5-121">你必须通过安装新 MSI 来更新 VM 映像，如在[VDI 上安装团队](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)的说明中所述。</span><span class="sxs-lookup"><span data-stu-id="295c5-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="295c5-122">必须卸载当前版本才能更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="295c5-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="295c5-123">管理员是否可以部署更新，而不是团队自动更新？</span><span class="sxs-lookup"><span data-stu-id="295c5-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="295c5-124">团队不会授予管理员通过任何交付机制部署更新的能力。</span><span class="sxs-lookup"><span data-stu-id="295c5-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="295c5-125">服务协议</span><span class="sxs-lookup"><span data-stu-id="295c5-125">Servicing agreement</span></span>

<span data-ttu-id="295c5-126">作为现代联机服务，团队客户端每两周自动更新一次。</span><span class="sxs-lookup"><span data-stu-id="295c5-126">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="295c5-127">由于团队由新式生命周期策略管理，因此，预计用户仍可使用最新版本的桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="295c5-127">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="295c5-128">这可确保用户具有最新的功能、性能增强、安全性和服务可靠性。</span><span class="sxs-lookup"><span data-stu-id="295c5-128">This ensures that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="295c5-129">若要开始帮助确定桌面客户端何时过期，如果用户的当前版本介于1到3个月之间，并且有新版本可用，则会显示应用内警报。</span><span class="sxs-lookup"><span data-stu-id="295c5-129">To begin assisting in identifying when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="295c5-130">此应用内消息鼓励用户更新到最新版本的团队，如有必要，可与 IT 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="295c5-130">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="295c5-131">超过三个月的团队桌面客户端用户将看到一个阻止页面，该页面提供了立即更新、与 IT 管理员联系或继续使用 web 上的团队的选项。</span><span class="sxs-lookup"><span data-stu-id="295c5-131">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="295c5-132">首次安装和/或首次运行团队后的桌面客户端版本超过了3个月，则在遇到上述服务信息之前将有28天的宽限期。</span><span class="sxs-lookup"><span data-stu-id="295c5-132">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="295c5-133">在此期间，自动更新过程将更新团队客户端。</span><span class="sxs-lookup"><span data-stu-id="295c5-133">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="295c5-134">如果未更新，用户将看到应用内警报鼓励他们手动更新到最新版本的团队，如有必要，请与 IT 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="295c5-134">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="295c5-135">这包括使用团队桌面客户端作为 Office 365 专业增强版捆绑包的一部分的用户。</span><span class="sxs-lookup"><span data-stu-id="295c5-135">This includes users using the Teams desktop client as part of the Office 365 ProPlus bundle.</span></span>

<span data-ttu-id="295c5-136">团队桌面客户在政府群上的桌面客户当前对此服务协议有例外，直到进一步通知。</span><span class="sxs-lookup"><span data-stu-id="295c5-136">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="295c5-137">有关新版本版本的信息，请查看[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或转**到** > 客户端中**的新增功能**。</span><span class="sxs-lookup"><span data-stu-id="295c5-137">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
