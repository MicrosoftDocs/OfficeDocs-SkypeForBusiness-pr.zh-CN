---
title: 将用户移至云
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在停用本地环境Skype for Business移动用户。
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420807"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="dadf9-103">在停用本地环境之前移动所需用户</span><span class="sxs-lookup"><span data-stu-id="dadf9-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="dadf9-104">本文介绍如何在停用本地部署环境之前，将所需用户Skype for Business Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="dadf9-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="dadf9-105">这是停止使用本地环境的以下步骤的第 1 步：</span><span class="sxs-lookup"><span data-stu-id="dadf9-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="dadf9-106">**步骤 1.将所有所需的用户从本地移动到联机。**</span><span class="sxs-lookup"><span data-stu-id="dadf9-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="dadf9-107"> (本文) </span><span class="sxs-lookup"><span data-stu-id="dadf9-107">(This article)</span></span>

- <span data-ttu-id="dadf9-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="dadf9-108">Step 2.</span></span> <span data-ttu-id="dadf9-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="dadf9-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="dadf9-110">Step 3.</span></span> <span data-ttu-id="dadf9-111">[将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="dadf9-112">请注意，完成此步骤之前，在执行上述步骤 2 这两者之间，将不能发现任何现有的混合应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="dadf9-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="dadf9-113">您应计划在同一维护窗口中执行步骤 2 和步骤 3。</span><span class="sxs-lookup"><span data-stu-id="dadf9-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="dadf9-114">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="dadf9-114">Step 4.</span></span> <span data-ttu-id="dadf9-115">[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="dadf9-116">将所有所需的用户从本地移动到云</span><span class="sxs-lookup"><span data-stu-id="dadf9-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="dadf9-117">完成迁移后将继续使用的任何用户必须先从本地迁移到云。</span><span class="sxs-lookup"><span data-stu-id="dadf9-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="dadf9-118">使用本地管理工具移动用户。</span><span class="sxs-lookup"><span data-stu-id="dadf9-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="dadf9-119">有关详细信息，请参阅在内部 [部署和云之间移动用户](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="dadf9-120">虽然具有本地用户帐户的用户可以使用Skype for Business Server帐户Teams，但是这些用户没有 Teams。</span><span class="sxs-lookup"><span data-stu-id="dadf9-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="dadf9-121">这些用户无法与仍在联机或本地部署Skype for Business (用户进行互操作或) 。</span><span class="sxs-lookup"><span data-stu-id="dadf9-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="dadf9-122">这些用户也无法在客户端客户端中接收 PSTN Teams呼叫。</span><span class="sxs-lookup"><span data-stu-id="dadf9-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="dadf9-123">因此，必须将这些用户移至联机。</span><span class="sxs-lookup"><span data-stu-id="dadf9-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="dadf9-124">此步骤还可确保在迁移时创建的任何Skype for Business Server或会议迁移到Teams。</span><span class="sxs-lookup"><span data-stu-id="dadf9-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="dadf9-125">若要检查本地部署中是否有剩余用户，请在 PowerShell 窗口中Skype for Business Server cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dadf9-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="dadf9-126">如果返回了任何用户，请查看输出以确定是否必须将任何帐户移动到云，对于此类用户，请按照此处 [的步骤操作](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="dadf9-127">对于不再需要的用户帐户，请运行以下 Skype for Business Server PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dadf9-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="dadf9-128">运行Disable-CsUser将删除Skype for Business筛选条件的所有用户的所有属性。</span><span class="sxs-lookup"><span data-stu-id="dadf9-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="dadf9-129">在继续之前，请确认今后不再需要这些帐户。</span><span class="sxs-lookup"><span data-stu-id="dadf9-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="dadf9-130">现在，你已准备好 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="dadf9-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dadf9-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dadf9-131">See also</span></span>

- [<span data-ttu-id="dadf9-132">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="dadf9-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="dadf9-133">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="dadf9-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="dadf9-134">将混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="dadf9-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="dadf9-135">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="dadf9-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




