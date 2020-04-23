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
description: 了解如何将用户从 Skype for Business Online 迁移到本地。
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779668"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="7967e-103">将用户从云移动到本地</span><span class="sxs-lookup"><span data-stu-id="7967e-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="7967e-104">如果需要，您可以将以前从本地迁移的用户移动到云（无论是仅使用 Skype for Business Online 还是仅将团队）回本地。</span><span class="sxs-lookup"><span data-stu-id="7967e-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="7967e-105">若要将用户从 Skype for Business Online 或 TeamsOnly 模式移回 Skype for Business Server 的本地部署，请使用 Get-csuser cmdlet 或 Skype for Business Server 控制面板，这两个控制面板都是本地工具。</span><span class="sxs-lookup"><span data-stu-id="7967e-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="7967e-106">将用户移回本地部署时，必须决定将用户移动到哪个池。</span><span class="sxs-lookup"><span data-stu-id="7967e-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="7967e-107">如果用户以前在 TeamsOnly 模式下，而您使用的是 Skype for Business Server 2015 with CU8 的早期版本，则还必须为该用户删除 TeamsUpgradePolicy 的 TeamsOnly 模式分配。</span><span class="sxs-lookup"><span data-stu-id="7967e-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="7967e-108">本地用户不能具有 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="7967e-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="7967e-109">后续版本的 Skype for Business Server 将自动删除此工作分配。</span><span class="sxs-lookup"><span data-stu-id="7967e-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="7967e-110">有关更多详细信息，请参阅[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)。</span><span class="sxs-lookup"><span data-stu-id="7967e-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7967e-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="7967e-111">Prerequisites</span></span>

- <span data-ttu-id="7967e-112">组织必须正确配置 Azure AD Connect 并同步用户的所有相关属性，如[Configure AZURE AD Connect](configure-azure-ad-connect.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="7967e-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="7967e-113">从联机恢复到本地的用户必须已存在于本地 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="7967e-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="7967e-114">必须配置 skype for Business 混合，如[配置 skype For business 混合](configure-federation-with-skype-for-business-online.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="7967e-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="7967e-115">将用户移回本地</span><span class="sxs-lookup"><span data-stu-id="7967e-115">Moving users back to on-premises</span></span>

<span data-ttu-id="7967e-116">将用户从云移回本地之后：</span><span class="sxs-lookup"><span data-stu-id="7967e-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="7967e-117">用户与你的 Skype for Business Server 部署进行交互，了解其功能。</span><span class="sxs-lookup"><span data-stu-id="7967e-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="7967e-118">Skype for business Online 或团队中存在的所有联系人都将迁移到 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="7967e-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="7967e-119">两组联系人合并，然后再迁移回本地。</span><span class="sxs-lookup"><span data-stu-id="7967e-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="7967e-120">此外，团队中预先存在的联系人仍保留在团队中。</span><span class="sxs-lookup"><span data-stu-id="7967e-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="7967e-121">如果用户也使用团队，则他们将无法与 Skype for Business 用户进行互操作，也无法与联盟组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="7967e-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="7967e-122">Skype for Business Online 中的会议*不*会自动迁移回本地。</span><span class="sxs-lookup"><span data-stu-id="7967e-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="7967e-123">用户应重新安排其会议，如果需要，可以使用[会议迁移工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。</span><span class="sxs-lookup"><span data-stu-id="7967e-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="7967e-124">将用户移动到 Get-csuser</span><span class="sxs-lookup"><span data-stu-id="7967e-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="7967e-125">Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。</span><span class="sxs-lookup"><span data-stu-id="7967e-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="7967e-126">在本地环境和 Office 365 组织中，您必须具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="7967e-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="7967e-127">您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`参数指定具有必要的 office 365 管理角色的 office 365 帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="7967e-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="7967e-128">使用 Get-csuser 将用户移动到本地的步骤：</span><span class="sxs-lookup"><span data-stu-id="7967e-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="7967e-129">使用 Identity 参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="7967e-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="7967e-130">使用要承载用户的所需本地池的完全限定域名指定-Target 参数。</span><span class="sxs-lookup"><span data-stu-id="7967e-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="7967e-131">如果您没有一个帐户在本地和 Office 365 中具有足够的权限，请使用-credential 参数在 Office 365 中提供具有足够权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="7967e-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="7967e-132">如果在 Office 365 中具有权限的帐户不以 "on.microsoft.com" 结尾，则必须使用[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的正确值指定-HostedMigrationOverrideUrl 参数。</span><span class="sxs-lookup"><span data-stu-id="7967e-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="7967e-133">可以使用以下 cmdlet 序列将用户移动到 Skype for business Server，并假定 Office 365 凭据是单独的帐户并作为 Get Credential 提示的输入提供。</span><span class="sxs-lookup"><span data-stu-id="7967e-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="7967e-134">使用 Skype for Business Server 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="7967e-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7967e-135">打开 "Skype for Business Server 控制面板" 应用。</span><span class="sxs-lookup"><span data-stu-id="7967e-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="7967e-136">在左侧导航栏中，选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="7967e-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="7967e-137">使用 "**查找**" 查找要移回到本地的用户。</span><span class="sxs-lookup"><span data-stu-id="7967e-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="7967e-138">选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到本地"**。</span><span class="sxs-lookup"><span data-stu-id="7967e-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="7967e-139">在向导中，选择将承载用户的用户池并单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7967e-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="7967e-140">如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Office 365 并拥有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="7967e-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="7967e-141">单击 "**下一步**"，然后再单击一次以移动用户。 **Next**</span><span class="sxs-lookup"><span data-stu-id="7967e-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="7967e-142">请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。</span><span class="sxs-lookup"><span data-stu-id="7967e-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="7967e-143">删除 TeamsOnly 模式</span><span class="sxs-lookup"><span data-stu-id="7967e-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="7967e-144">如果您使用早于 Skype for Business 2015 的版本与 CU8，并且用户将在 TeamsOnly 模式下移回本地，则必须在移动本地用户`TeamsUpgradePolicy`之前删除 UpgradeToTeams 实例。</span><span class="sxs-lookup"><span data-stu-id="7967e-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="7967e-145">您可以使用其他模式显式授予策略，也可以仅删除该用户的现有策略分配以使用全局策略（前提是租户的全局策略不 UpgradeToTeams）。</span><span class="sxs-lookup"><span data-stu-id="7967e-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="7967e-146">若要删除用户对 TeamsUpgradePolicy 的分配，请从 Skype for Business Online PowerShell 窗口中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7967e-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="7967e-147">或者，若要分配不具有 mode = TeamsOnly 的 TeamsUpgradePolicy 的另一个实例，可以将所需实例的名称指定为 cmdlet 中的 PolicyName 参数的值。</span><span class="sxs-lookup"><span data-stu-id="7967e-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="7967e-148">若要查看 TeamsUpgradePolicy 的可用实例的列表，请运行 CsTeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="7967e-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="7967e-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7967e-149">See also</span></span>

[<span data-ttu-id="7967e-150">移动-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="7967e-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
