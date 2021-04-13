---
title: 将用户移动到云
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
description: 在停用 Skype for Business 本地环境之前移动用户。
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656668"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="28f68-103">在停用本地环境之前移动所需用户</span><span class="sxs-lookup"><span data-stu-id="28f68-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="28f68-104">本文介绍如何在停用本地 Skype for Business 环境之前将所需用户移动到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="28f68-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="28f68-105">这是停止使用本地环境的以下步骤的第 1 步：</span><span class="sxs-lookup"><span data-stu-id="28f68-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="28f68-106">**步骤 1.将所有所需的用户从本地移动到联机。**</span><span class="sxs-lookup"><span data-stu-id="28f68-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="28f68-107"> (本文) </span><span class="sxs-lookup"><span data-stu-id="28f68-107">(This article)</span></span>

- <span data-ttu-id="28f68-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="28f68-108">Step 2.</span></span> <span data-ttu-id="28f68-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="28f68-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="28f68-110">Step 3.</span></span> <span data-ttu-id="28f68-111">[将混合应用程序终结点从本地移动到联机](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="28f68-112">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="28f68-112">Step 4.</span></span> <span data-ttu-id="28f68-113">[删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="28f68-114">将所有所需的用户从本地移动到云</span><span class="sxs-lookup"><span data-stu-id="28f68-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="28f68-115">完成迁移后将继续使用的任何用户必须先从本地迁移到云。</span><span class="sxs-lookup"><span data-stu-id="28f68-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="28f68-116">使用本地管理工具移动用户。</span><span class="sxs-lookup"><span data-stu-id="28f68-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="28f68-117">有关详细信息，请参阅在内部 [部署和云之间移动用户](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="28f68-118">尽管拥有本地 Skype for Business Server 帐户的用户可以使用 Teams，但是这些用户没有 Teams 的全部功能。</span><span class="sxs-lookup"><span data-stu-id="28f68-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="28f68-119">这些用户无法与仍在使用 Skype for Business (用户进行互操作或联合，无论是联机还是本地) 。</span><span class="sxs-lookup"><span data-stu-id="28f68-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="28f68-120">这些用户也无法在 Teams 客户端中接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="28f68-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="28f68-121">因此，必须将这些用户移至联机。</span><span class="sxs-lookup"><span data-stu-id="28f68-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="28f68-122">此步骤还可确保在 Skype for Business Server 中创建的任何联系人或会议都迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="28f68-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="28f68-123">若要检查本地部署中是否有剩余用户，请在 Skype for Business Server PowerShell 窗口中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28f68-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="28f68-124">如果返回了任何用户，请查看输出以确定是否必须将任何帐户移动到云，对于此类用户，请按照此处 [的步骤操作](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="28f68-125">对于不再需要的用户帐户，请运行以下 Skype for Business Server PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="28f68-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="28f68-126">运行Disable-CsUser将删除满足筛选条件的所有用户的所有 Skype for Business 属性。</span><span class="sxs-lookup"><span data-stu-id="28f68-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="28f68-127">在继续之前，请确认今后不再需要这些帐户。</span><span class="sxs-lookup"><span data-stu-id="28f68-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="28f68-128">现在，你已准备好 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="28f68-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28f68-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28f68-129">See also</span></span>

- [<span data-ttu-id="28f68-130">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="28f68-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="28f68-131">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="28f68-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="28f68-132">将混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="28f68-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="28f68-133">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="28f68-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




