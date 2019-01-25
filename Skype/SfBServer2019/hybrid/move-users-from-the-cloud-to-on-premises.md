---
title: 从云到本地移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 了解如何移动用户从 Skype 业务 online 到本地。
ms.openlocfilehash: 7032e7f2968b7861a7fac199fd8ba949980fe770
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530941"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="792ff-103">从云到本地移动用户</span><span class="sxs-lookup"><span data-stu-id="792ff-103">Move users from the cloud to on premises</span></span> 

<span data-ttu-id="792ff-104">如果需要您可以向后移动以前迁移从本地到云 （无论业务联机或团队仅使用 Skype） 的用户在本地。</span><span class="sxs-lookup"><span data-stu-id="792ff-104">If needed, you can move a user who was previously migrated from on premises to the cloud (whether using Skype for Business Online or Teams Only) back to on premises.</span></span> <span data-ttu-id="792ff-105">要将用户从业务联机或 TeamsOnly 模式任一 Skype 移到内部部署的 Skype 业务服务器，用于 Move-csuser cmdlet 或 Skype 业务 Server Control Panel，二者是内部部署工具。</span><span class="sxs-lookup"><span data-stu-id="792ff-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="792ff-106">在将用户移回内部部署到，必须确定哪个池移动到用户。</span><span class="sxs-lookup"><span data-stu-id="792ff-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="792ff-107">如果用户是以前在 TeamsOnly 模式下，并且您将 Skype 比早期版本与 CU8 业务服务器 2015年，然后您还必须删除 TeamsOnly 模式的分配的 TeamsUpgradePolicy 为该用户。</span><span class="sxs-lookup"><span data-stu-id="792ff-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="792ff-108">本地用户不能有模式 = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="792ff-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="792ff-109">Skype 业务服务器的后续版本自动删除此工作分配。</span><span class="sxs-lookup"><span data-stu-id="792ff-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="792ff-110">有关详细信息，请参阅[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)。</span><span class="sxs-lookup"><span data-stu-id="792ff-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="792ff-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="792ff-111">Prerequisites</span></span>

- <span data-ttu-id="792ff-112">组织必须具有正确的 Azure AD 连接，并且同步的用户的所有相关属性[配置 Azure AD 连接](configure-azure-ad-connect.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="792ff-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="792ff-113">正在从 online 回至本地移动用户必须已经存在内部部署 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="792ff-113">The user being moved from online back to on premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="792ff-114">必须配置为业务混合的 Skype，[业务混合配置 Skype](configure-federation-with-skype-for-business-online.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="792ff-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="792ff-115">移动用户后在本地</span><span class="sxs-lookup"><span data-stu-id="792ff-115">Moving users back to on premises</span></span>

<span data-ttu-id="792ff-116">一旦您移动用户从云回内部部署：</span><span class="sxs-lookup"><span data-stu-id="792ff-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="792ff-117">用户与您为其功能的业务服务器部署的 Skype 交互。</span><span class="sxs-lookup"><span data-stu-id="792ff-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="792ff-118">业务联机或团队中任一 Skype 存在任何联系人都将迁移到 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="792ff-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="792ff-119">联系人的两种合并，并在本地然后迁移回中。</span><span class="sxs-lookup"><span data-stu-id="792ff-119">The two sets of contacts are merged and then migrated back to on premises.</span></span>  <span data-ttu-id="792ff-120">此外，团队保持事先团队中的联系人。</span><span class="sxs-lookup"><span data-stu-id="792ff-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="792ff-121">如果用户还使用团队，不会与 Skype 业务用户的互操作的功能，也不能将他们能够与联盟组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="792ff-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="792ff-122">Skype 中的业务联机会议是*不*回自动迁移在本地。</span><span class="sxs-lookup"><span data-stu-id="792ff-122">Meetings in Skype for Business Online are *not* automatically migrated back to on premises.</span></span> <span data-ttu-id="792ff-123">用户应之一重新其会议或者，如果需要，使用[会议迁移工具](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。</span><span class="sxs-lookup"><span data-stu-id="792ff-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="792ff-124">具有 Move-csuser 移动用户</span><span class="sxs-lookup"><span data-stu-id="792ff-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="792ff-125">可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="792ff-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="792ff-126">您必须具有足够的权限，在内部部署环境以及 Office 365 租户，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="792ff-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="792ff-127">您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口内部 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。</span><span class="sxs-lookup"><span data-stu-id="792ff-127">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="792ff-128">若要将用户移动本地使用 Move-csuser:</span><span class="sxs-lookup"><span data-stu-id="792ff-128">To move a user to on premises using Move-CsUser:</span></span>

- <span data-ttu-id="792ff-129">指定的用户将使用 Identity 参数。</span><span class="sxs-lookup"><span data-stu-id="792ff-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="792ff-130">指定将承载用户的所需的本地池的完全限定的域名-目标参数。</span><span class="sxs-lookup"><span data-stu-id="792ff-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="792ff-131">如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用-credential 参数，以提供足够的权限，在 Office 365 中使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="792ff-131">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="792ff-132">如果 Office 365 中的权限的帐户不是以"on.microsoft.com"结尾，则必须用正确的值指定-HostedMigrationOverrideUrl 参数，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="792ff-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="792ff-133">以下 cmdlet 序列可用于将用户移至 Skype，对于业务服务器，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。</span><span class="sxs-lookup"><span data-stu-id="792ff-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="792ff-134">具有业务 Server Control Panel Skype 移动用户</span><span class="sxs-lookup"><span data-stu-id="792ff-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="792ff-135">打开业务服务器控件 Skype 面板应用程序。</span><span class="sxs-lookup"><span data-stu-id="792ff-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="792ff-136">在左侧导航窗格中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="792ff-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="792ff-137">使用**查找**来查找您想要将移回本地用户。</span><span class="sxs-lookup"><span data-stu-id="792ff-137">Use **Find** to locate the user(s) you would like to move back to on premises.</span></span>
4. <span data-ttu-id="792ff-138">选择的用户，，然后从列表上方的**操作**下拉列表中选择**移动到内部部署的所选的用户**。</span><span class="sxs-lookup"><span data-stu-id="792ff-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="792ff-139">在向导中，选择的用户池的承载用户和单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="792ff-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="792ff-140">如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="792ff-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="792ff-141">单击**下一步**，然后**下**一次将用户移动。</span><span class="sxs-lookup"><span data-stu-id="792ff-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="792ff-142">请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。</span><span class="sxs-lookup"><span data-stu-id="792ff-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="792ff-143">删除 TeamsOnly 模式</span><span class="sxs-lookup"><span data-stu-id="792ff-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="792ff-144">如果您正在使用版本早于 Skype 与 CU8 业务 2015年和用户移回到本地 TeamsOnly 模式中，则必须删除 UpgradeToTeams 实例`TeamsUpgradePolicy`本地移动用户之前。</span><span class="sxs-lookup"><span data-stu-id="792ff-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on premises.</span></span> <span data-ttu-id="792ff-145">您可以明确授予具有不同的模式的策略，或只需在删除现有的策略分配的用户 （只要租户的全局策略不 UpgradeToTeams） 使用全局策略。</span><span class="sxs-lookup"><span data-stu-id="792ff-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="792ff-146">若要删除的 TeamsUpgradePolicy 的用户的工作分配，请从业务 Online PowerShell 窗口 Skype 运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="792ff-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="792ff-147">此外，分配的 TeamsUpgradePolicy 另一个实例，它没有模式 = TeamsOnly，您可以为 cmdlet 中的 PolicyName 参数的值指定所需的实例的名称。</span><span class="sxs-lookup"><span data-stu-id="792ff-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="792ff-148">若要查看可用的 TeamsUpgradePolicy 实例的列表，请运行 Get CsTeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="792ff-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="792ff-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="792ff-149">See also</span></span>

<span data-ttu-id="792ff-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="792ff-150">[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)</span></span>
