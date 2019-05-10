---
title: 团队更新过程
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 了解如何更新团队桌面客户端。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829093"
---
# <a name="teams-update-process"></a><span data-ttu-id="9daa3-103">团队更新过程</span><span class="sxs-lookup"><span data-stu-id="9daa3-103">Teams update process</span></span>

<span data-ttu-id="9daa3-104">每周更新团队 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9daa3-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="9daa3-105">团队桌面客户端发布更新后严格的内部测试和验证每两周通过我们技术应用程序 （点击）。</span><span class="sxs-lookup"><span data-stu-id="9daa3-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="9daa3-106">这通常发生于星期二。</span><span class="sxs-lookup"><span data-stu-id="9daa3-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="9daa3-107">如果需要关键更新，则团队将绕过此计划，并为可用发布更新。</span><span class="sxs-lookup"><span data-stu-id="9daa3-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="9daa3-108">桌面客户端自动更新本身。</span><span class="sxs-lookup"><span data-stu-id="9daa3-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="9daa3-109">团队检查更新后台每隔几小时，将其，下载，然后等待以无提示方式安装更新之前处于空闲状态的计算机。</span><span class="sxs-lookup"><span data-stu-id="9daa3-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="9daa3-110">用户可以通过单击顶部的**配置文件**下拉列表菜单上的**检查更新**手动下载更新应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="9daa3-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="9daa3-111">如果提供更新，则它将下载并以无提示方式安装在计算机空闲时。</span><span class="sxs-lookup"><span data-stu-id="9daa3-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="9daa3-112">用户需要更新下载登录。</span><span class="sxs-lookup"><span data-stu-id="9daa3-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="9daa3-113">更新 Office 365 ProPlus 呢？</span><span class="sxs-lookup"><span data-stu-id="9daa3-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="9daa3-114">团队是默认安装的新安装的 Office 365 ProPlus[与 Office 365 ProPlus 部署 Microsoft 团队](https://docs.microsoft.com/DeployOffice/teams-install)中所述。</span><span class="sxs-lookup"><span data-stu-id="9daa3-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="9daa3-115">团队遵循上述，自己更新过程，并不其他办公室应用程序，例如 Word 和 Excel 的更新过程。</span><span class="sxs-lookup"><span data-stu-id="9daa3-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="9daa3-116">向工作组 VDI 上更新呢？</span><span class="sxs-lookup"><span data-stu-id="9daa3-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="9daa3-117">团队客户端上虚拟桌面基础结构 (VDI) 不会自动更新 VDI 团队客户端的方式。</span><span class="sxs-lookup"><span data-stu-id="9daa3-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="9daa3-118">您必须通过向[VDI 上安装的工作组](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)的说明中所述安装新的 MSI 来更新虚拟机映像。</span><span class="sxs-lookup"><span data-stu-id="9daa3-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="9daa3-119">您必须先卸载要更新为新版本的当前版本。</span><span class="sxs-lookup"><span data-stu-id="9daa3-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="9daa3-120">可以 admins 部署更新而不是团队自动更新？</span><span class="sxs-lookup"><span data-stu-id="9daa3-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="9daa3-121">团队不使管理员能够通过任何交付机制部署更新。</span><span class="sxs-lookup"><span data-stu-id="9daa3-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
