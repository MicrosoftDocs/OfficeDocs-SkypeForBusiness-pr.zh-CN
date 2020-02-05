---
title: 将用户从 Skype for Business Server 2019 移动到团队
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
description: 摘要：了解如何迁移用户设置并将用户移动到团队。
ms.openlocfilehash: c719741323c0e1bc8435adf10364356d069e8774
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726742"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="dc16d-103">将用户从本地移动到团队</span><span class="sxs-lookup"><span data-stu-id="dc16d-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="dc16d-104">当用户仅从本地移动到团队时，用户的 Skype for Business 主页将从本地移动到联机，并向用户分配模式 = TeamsOnly 的 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="dc16d-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="dc16d-105">将用户从本地移动到 TeamsOnly 模式后：</span><span class="sxs-lookup"><span data-stu-id="dc16d-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="dc16d-106">来自其他用户（无论是从 Skype for Business 还是团队发送）的所有传入呼叫和聊天都将在用户的团队客户端中进行陆地。</span><span class="sxs-lookup"><span data-stu-id="dc16d-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="dc16d-107">用户将能够与使用 Skype for Business 的其他用户交互操作（无论是在线还是在本地）。</span><span class="sxs-lookup"><span data-stu-id="dc16d-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="dc16d-108">用户将能够与联合组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="dc16d-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="dc16d-109">由该用户计划的新会议是团队会议。</span><span class="sxs-lookup"><span data-stu-id="dc16d-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="dc16d-110">用户仍可以加入任何 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="dc16d-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="dc16d-111">为未来安排的用户的预先存在的会议将从本地迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="dc16d-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="dc16d-112">在用户首次登录后，会立即在本地的联系人中使用已存在的联系人。</span><span class="sxs-lookup"><span data-stu-id="dc16d-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="dc16d-113">用户不能从 Skype for Business 发起呼叫或聊天，也不能在 Skype for Business 中安排新会议。</span><span class="sxs-lookup"><span data-stu-id="dc16d-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="dc16d-114">如果他们尝试打开 Skype for Business 客户端，它们将被重定向到使用如下所示的团队。</span><span class="sxs-lookup"><span data-stu-id="dc16d-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="dc16d-115">如果未安装团队客户端，则会使用浏览器将其定向到团队的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="dc16d-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="dc16d-116">![将用户重定向到团队的邮件](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="dc16d-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="dc16d-117">在移动任何用户之前，请务必查看将用户移动到云的[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="dc16d-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="dc16d-118">此外，请务必查看[与 Skype For business 一起使用团队的组织的迁移和互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="dc16d-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="dc16d-119">应在本地 SfB 帐户上禁用统一联系人存储库，以便将联系人移动到团队。</span><span class="sxs-lookup"><span data-stu-id="dc16d-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="dc16d-120">有两种方法可以将用户从本地移动到团队：</span><span class="sxs-lookup"><span data-stu-id="dc16d-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="dc16d-121">如果使用早于 Skype for business Server 2015 CU8 的版本，则移动需要两个步骤（可以通过脚本将其作为一个步骤进行脚本，如果需要）：</span><span class="sxs-lookup"><span data-stu-id="dc16d-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="dc16d-122">[将用户从 skype For Business Server （本地）移动到 skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="dc16d-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="dc16d-123">一旦用户托管在 Skype for Business Online 中，请将用户 TeamsUpgradePolicy 分配为 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="dc16d-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="dc16d-124">若要授予 TeamsOnly 模式，请从 Skype for Business Online PowerShell 窗口运行以下 cmdlet：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="dc16d-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="dc16d-125">如果您具有来自 Skype for Business Server 2015 CU8 或更高版本的管理工具，则可以使用上面的方法，也可以按如下所述在一个步骤中进行移动。</span><span class="sxs-lookup"><span data-stu-id="dc16d-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="dc16d-126">此外，您可以选择在 Skype for business 客户端中提供通知，然后在将其仅移动到团队之前，也可以选择让 Skype for Business 客户端自行下载团队客户端。</span><span class="sxs-lookup"><span data-stu-id="dc16d-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="dc16d-127">仅将本地用户从 Skype for Business 直接移动到团队</span><span class="sxs-lookup"><span data-stu-id="dc16d-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="dc16d-128">Skype for business Server 2015 中的本地管理员工具使用 CU8 以及 Skype for Business Server 2019 中的本地管理员工具，您可以使用 PowerShell 中的 Get-csuser cmdlet 或 Skype for Business Se，在一个步骤中将用户从 "仅本地" 移动到 "仅工作组" 模式。rver "控制面板"，如下所述。</span><span class="sxs-lookup"><span data-stu-id="dc16d-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="dc16d-129">使用 Get-csuser 移动到团队</span><span class="sxs-lookup"><span data-stu-id="dc16d-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="dc16d-130">Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。</span><span class="sxs-lookup"><span data-stu-id="dc16d-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="dc16d-131">以下步骤和所需的权限与将用户移动到 Skype for business Online 相同，不同之处在于，您还必须指定 MoveToTeams 开关，并且必须确保用户也已为团队授予许可证（除了 Skype for Business）。Online）。</span><span class="sxs-lookup"><span data-stu-id="dc16d-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="dc16d-132">在本地环境和 Office 365 租户中，您必须具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="dc16d-132">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="dc16d-133">您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`参数指定具有必要的 office 365 管理角色的 office 365 帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="dc16d-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="dc16d-134">使用 Get-csuser 将用户移动到仅限工作组模式的步骤：</span><span class="sxs-lookup"><span data-stu-id="dc16d-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="dc16d-135">使用`Identity`参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="dc16d-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="dc16d-136">指定值为 "sipfed.online.lync.com>" 的-Target 参数。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="dc16d-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="dc16d-137">指定`MoveToTeams`开关。</span><span class="sxs-lookup"><span data-stu-id="dc16d-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="dc16d-138">如果您没有一个帐户在本地和 Office 365 中具有足够的权限，请使用`-credential`参数在 Office 365 中提供具有足够权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="dc16d-138">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="dc16d-139">如果在 Office 365 中具有权限的帐户不以 ".onmicrosoft" 结尾。<span>com "，必须使用正确的`-HostedMigrationOverrideUrl`值指定参数，如[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="dc16d-139">If the account with permissions in Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="dc16d-140">可以使用以下 cmdlet 序列将用户移动到 TeamsOnly，并假定 Office 365 凭据是单独的帐户并作为 Get Credential 提示的输入提供。</span><span class="sxs-lookup"><span data-stu-id="dc16d-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dc16d-141">移动到使用 Skype for Business Server 控制面板的团队</span><span class="sxs-lookup"><span data-stu-id="dc16d-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dc16d-142">打开 "Skype for Business Server 控制面板" 应用。</span><span class="sxs-lookup"><span data-stu-id="dc16d-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="dc16d-143">在左侧导航栏中，选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="dc16d-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="dc16d-144">使用 "**查找**" 查找要移到团队的用户。</span><span class="sxs-lookup"><span data-stu-id="dc16d-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="dc16d-145">选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到团队**"。</span><span class="sxs-lookup"><span data-stu-id="dc16d-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="dc16d-146">在向导中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc16d-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="dc16d-147">如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Office 365 并拥有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="dc16d-147">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="dc16d-148">单击 "**下一步**"，然后再单击一次以移动用户。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dc16d-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="dc16d-149">请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。</span><span class="sxs-lookup"><span data-stu-id="dc16d-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="dc16d-150">将即将推出的 Skype for business 本地用户通知给团队</span><span class="sxs-lookup"><span data-stu-id="dc16d-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="dc16d-151">Skype for business Server 2015 中的本地管理员工具使用 CU8 以及 Skype for Business Server 2019 中的本地管理员工具，您可以将即将到来的 Skype for Business 用户通知给团队。</span><span class="sxs-lookup"><span data-stu-id="dc16d-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="dc16d-152">启用这些通知后，用户将在其 Skype for Business 客户端（Win32、Mac、web 和手机）中看到通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dc16d-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="dc16d-153">如果用户单击 "**尝试**" 按钮，则团队客户端将在已安装的情况下启动;否则，用户将在其浏览器中导航到团队的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="dc16d-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="dc16d-154">默认情况下，启用通知后，Win32 Skype for Business 客户端将以无提示方式下载团队客户端，以便在用户仅将用户移动到 "仅工作组" 模式之前可以使用富客户端;但是，也可以禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="dc16d-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="dc16d-155">使用内部部署版本配置通知`TeamsUpgradePolicy`，并通过内部部署`TeamsUpgradeConfiguration` cmdlet 控制 Win32 客户端的无提示下载。</span><span class="sxs-lookup"><span data-stu-id="dc16d-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="dc16d-156">某些服务器可能需要重新启动，这样才能在 Skype for Business 2015 with CU8 中工作。</span><span class="sxs-lookup"><span data-stu-id="dc16d-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![即将到来的转到团队的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="dc16d-158">若要通知本地用户他们很快将升级到团队，请创建一个新的 TeamsUpgradePolicy 实例，并 NotifySfBUsers = true。</span><span class="sxs-lookup"><span data-stu-id="dc16d-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="dc16d-159">然后，通过将策略直接分配给用户或在站点、池或全局级别设置策略，将该策略分配给要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="dc16d-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="dc16d-160">以下 cmdlet 创建并授予用户级策略：</span><span class="sxs-lookup"><span data-stu-id="dc16d-160">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="dc16d-161">通过 Skype for Business Win32 客户端自动下载团队是通过内部部署 TeamsUpgradeConfiguration cmdlet 和 DownloadTeams 参数进行控制的。</span><span class="sxs-lookup"><span data-stu-id="dc16d-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="dc16d-162">您可以在全局、站点和池级别上创建此配置。</span><span class="sxs-lookup"><span data-stu-id="dc16d-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="dc16d-163">例如，以下命令将创建网站 Redmond1 的配置：</span><span class="sxs-lookup"><span data-stu-id="dc16d-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="dc16d-164">默认情况下，DownloadTeams 的值为 True;但是，仅当给定用户的 NotifySfbUser = True 时*才*会生效。</span><span class="sxs-lookup"><span data-stu-id="dc16d-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc16d-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc16d-165">See also</span></span>

[<span data-ttu-id="dc16d-166">移动-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="dc16d-166">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="dc16d-167">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dc16d-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="dc16d-168">与 Skype for Business 一起使用团队的组织的迁移和互操作性指南</span><span class="sxs-lookup"><span data-stu-id="dc16d-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="dc16d-169">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="dc16d-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
