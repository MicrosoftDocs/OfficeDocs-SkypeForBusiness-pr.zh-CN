---
title: 将用户从云移动到本地
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
ms.custom: ''
description: 了解如何将用户从 Skype for Business Online 移动到本地。
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110608"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="d1acc-103">将用户从云移动到本地</span><span class="sxs-lookup"><span data-stu-id="d1acc-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="d1acc-104">如果需要，可以将之前从本地迁移的用户移动到云 (无论是使用 Skype for Business Online 还是仅 Teams) 迁移到本地。</span><span class="sxs-lookup"><span data-stu-id="d1acc-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="d1acc-105">若要将用户从 Skype for Business Online 或 TeamsOnly 模式移回 Skype for Business Server 本地部署，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。</span><span class="sxs-lookup"><span data-stu-id="d1acc-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="d1acc-106">将用户移回本地部署时，必须决定将用户移动到哪个池。</span><span class="sxs-lookup"><span data-stu-id="d1acc-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="d1acc-107">如果用户之前使用的是 TeamsOnly 模式，并且你使用的是低于 Skype for Business Server 2015 CU8 的早期版本，则还必须删除该用户的 TeamsUpgradePolicy 的 TeamsOnly 模式分配。</span><span class="sxs-lookup"><span data-stu-id="d1acc-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="d1acc-108">本地用户不能具有 mode= TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="d1acc-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="d1acc-109">后续版本的 Skype for Business Server 会自动删除此分配。</span><span class="sxs-lookup"><span data-stu-id="d1acc-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="d1acc-110">有关详细信息，请参阅 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)。</span><span class="sxs-lookup"><span data-stu-id="d1acc-110">For more details, see [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1acc-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="d1acc-111">Prerequisites</span></span>

- <span data-ttu-id="d1acc-112">组织必须正确配置 Azure AD Connect，并同步用户的所有相关属性，如配置 [Azure AD Connect 中所述](configure-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="d1acc-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="d1acc-113">从联机移回本地的用户必须已存在于本地 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="d1acc-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="d1acc-114">必须配置 Skype for Business 混合，如配置 [Skype for Business 混合中所述](configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="d1acc-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="d1acc-115">将用户移回本地</span><span class="sxs-lookup"><span data-stu-id="d1acc-115">Moving users back to on-premises</span></span>

<span data-ttu-id="d1acc-116">将用户从云移回本地后：</span><span class="sxs-lookup"><span data-stu-id="d1acc-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="d1acc-117">用户与其功能的 Skype for Business Server 部署交互。</span><span class="sxs-lookup"><span data-stu-id="d1acc-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="d1acc-118">Skype for Business Online 或 Teams 中存在的任何联系人都迁移到 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="d1acc-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="d1acc-119">合并这两组联系人，然后迁移回本地。</span><span class="sxs-lookup"><span data-stu-id="d1acc-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="d1acc-120">此外，Teams 中预先存在的联系人仍保留在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="d1acc-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="d1acc-121">如果用户还使用 Teams，他们将不能与 Skype for Business 用户进行互操作，也无法与联盟组织的用户通信。</span><span class="sxs-lookup"><span data-stu-id="d1acc-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="d1acc-122">Skype for Business Online 中的会议 *不会自动* 迁移回本地。</span><span class="sxs-lookup"><span data-stu-id="d1acc-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="d1acc-123">用户应重新安排其会议，或者使用会议迁移 [工具（如果需要](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)）。</span><span class="sxs-lookup"><span data-stu-id="d1acc-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="d1acc-124">使用迁移功能Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d1acc-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="d1acc-125">Move-CsUser本地 Skype for Business 命令行管理程序 PowerShell 窗口提供。</span><span class="sxs-lookup"><span data-stu-id="d1acc-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="d1acc-126">您必须在本地环境和云服务组织 (Microsoft 365 或 Office 365) 中拥有足够的权限，如所需的管理凭据[中所述。](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="d1acc-126">You must have sufficient privileges in both the on-premises environment as well as the cloud service organization (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="d1acc-127">可以在两个环境中使用具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 `-Credential` Microsoft 365 或 Office 365 帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d1acc-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="d1acc-128">若要使用 Move-CsUser 将用户移动到本地：</span><span class="sxs-lookup"><span data-stu-id="d1acc-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="d1acc-129">使用 Identity 参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="d1acc-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="d1acc-130">使用将承载用户的所需本地池的完全限定域名指定 -Target 参数。</span><span class="sxs-lookup"><span data-stu-id="d1acc-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="d1acc-131">如果您没有一个在本地和云服务 (Microsoft 365 或 Office 365) 中具有足够权限的帐户，请使用 -credential 参数在 Microsoft 365 或 Office 365 中向帐户提供足够权限。</span><span class="sxs-lookup"><span data-stu-id="d1acc-131">If you do not have one account with sufficient permissions in both on-premises and the cloud service (Microsoft 365 or Office 365), use the -credential parameter to supply an account with sufficient permissions in Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="d1acc-132">如果在 Microsoft 365 或 Office 365 中具有权限的帐户没有以"on.microsoft.com"结尾，则必须指定 -HostedMigrationOverrideUrl 参数，并指定正确的值，如[](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所需的管理凭据中所述。</span><span class="sxs-lookup"><span data-stu-id="d1acc-132">If the account with permissions in Microsoft 365 or Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="d1acc-133">以下 cmdlet 序列可用于将用户移动到 Skype for Business Server，并假定 Microsoft 365 或 Office 365 凭据是一个单独的帐户，并作为 Get-Credential 提示的输入提供。</span><span class="sxs-lookup"><span data-stu-id="d1acc-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="d1acc-134">使用 Skype for Business Server 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="d1acc-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d1acc-135">打开 Skype for Business Server 控制面板应用。</span><span class="sxs-lookup"><span data-stu-id="d1acc-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="d1acc-136">在左侧导航栏中，选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="d1acc-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="d1acc-137">使用 **"** 查找"查找 (要) 回本地部署的用户。</span><span class="sxs-lookup"><span data-stu-id="d1acc-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="d1acc-138">Select the user (s) ， and then from the **Action** dropdown above the list， choose **Move selected users to on-premises**.</span><span class="sxs-lookup"><span data-stu-id="d1acc-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="d1acc-139">在向导中，选择将承载用户的用户池，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1acc-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="d1acc-140">如果系统提示，使用以 .onmicrosoft.com 结尾且具有足够权限的帐户登录到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d1acc-140">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="d1acc-141">单击 **"下\*\*\*\*一步**"，再单击"下一步"以移动用户。</span><span class="sxs-lookup"><span data-stu-id="d1acc-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="d1acc-142">请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。</span><span class="sxs-lookup"><span data-stu-id="d1acc-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="d1acc-143">删除 TeamsOnly 模式</span><span class="sxs-lookup"><span data-stu-id="d1acc-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="d1acc-144">如果你使用的是早于 Skype for Business 2015 CU8 的版本，并且用户正在 TeamsOnly 模式下移回本地，则必须删除 的 UpgradeToTeams 实例，然后才能在本地移动 `TeamsUpgradePolicy` 用户。</span><span class="sxs-lookup"><span data-stu-id="d1acc-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="d1acc-145">你可以显式授予采用不同模式的策略，或者只需删除该用户的现有策略分配，以使用全局策略 (只要租户的全局策略不是 UpgradeToTeams) 。</span><span class="sxs-lookup"><span data-stu-id="d1acc-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="d1acc-146">若要删除用户的 TeamsUpgradePolicy 分配，请从 Skype for Business Online PowerShell 窗口运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d1acc-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="d1acc-147">或者，若要分配另一个没有 mode=TeamsOnly 的 TeamsUpgradePolicy 实例，可以在 cmdlet 中将所需实例的名称指定为 PolicyName 参数的值。</span><span class="sxs-lookup"><span data-stu-id="d1acc-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="d1acc-148">若要查看 TeamsUpgradePolicy 的可用实例列表，请运行 Get-CsTeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="d1acc-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="d1acc-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1acc-149">See also</span></span>

[<span data-ttu-id="d1acc-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d1acc-150">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)