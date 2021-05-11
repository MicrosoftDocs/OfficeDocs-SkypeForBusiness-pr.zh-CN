---
title: 将用户从 Skype for Business Server 2019 移动到 Teams
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
description: 摘要：了解如何迁移用户设置以及将用户移动到Teams。
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306016"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="cd82f-103">将用户从本地移至团队</span><span class="sxs-lookup"><span data-stu-id="cd82f-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="cd82f-104">当用户从本地移动到 Teams Only 时，用户的 Skype for Business 家庭版从本地移动到联机，并且为该用户分配 TeamsUpgradePolicy mode=TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="cd82f-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="cd82f-105">将用户从本地移动到 TeamsOnly 模式后：</span><span class="sxs-lookup"><span data-stu-id="cd82f-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="cd82f-106">来自其他用户的所有传入呼叫 (无论是从 Skype for Business 还是 Teams) 发送，都将进入用户的 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="cd82f-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="cd82f-107">用户将能够与联机或本地部署Skype for Business (其他用户进行) 。</span><span class="sxs-lookup"><span data-stu-id="cd82f-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="cd82f-108">用户将能够与联盟组织的用户通信。</span><span class="sxs-lookup"><span data-stu-id="cd82f-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="cd82f-109">该用户安排的新会议将Teams会议。</span><span class="sxs-lookup"><span data-stu-id="cd82f-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="cd82f-110">用户仍可加入任何Skype for Business会议。</span><span class="sxs-lookup"><span data-stu-id="cd82f-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="cd82f-111">为将来安排的用户预先存在的会议将从本地迁移到Teams。</span><span class="sxs-lookup"><span data-stu-id="cd82f-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="cd82f-112">本地存在的联系人在用户首次登录Teams在用户登录后的不久内可用。</span><span class="sxs-lookup"><span data-stu-id="cd82f-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="cd82f-113">用户无法从会议发起Skype for Business聊天，也无法在 Skype for Business 中安排新Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="cd82f-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="cd82f-114">如果他们尝试打开 Skype for Business 客户端，他们将被重定向以使用Teams如下所示。</span><span class="sxs-lookup"><span data-stu-id="cd82f-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="cd82f-115">如果未Teams客户端，它们将被定向到 web 版本的 Teams使用其浏览器。</span><span class="sxs-lookup"><span data-stu-id="cd82f-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="cd82f-116">![将用户重定向到用户Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="cd82f-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="cd82f-117">在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。</span><span class="sxs-lookup"><span data-stu-id="cd82f-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="cd82f-118">此外，请务必查看迁移和互操作性指南，以指导组织将 Teams 与 Skype for Business 一[Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="cd82f-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="cd82f-119">应禁用统一联系人存储，以将联系人移动到统一联系人Teams。</span><span class="sxs-lookup"><span data-stu-id="cd82f-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="cd82f-120">目前，*有* 两种方法将用户从本地移动到Teams：</span><span class="sxs-lookup"><span data-stu-id="cd82f-120">There are *currently* two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="cd82f-121">如果你使用的是早于 Skype for Business Server 2015 CU8 的版本，移动需要两个步骤 (如果需要，可以将脚本编写为一起作为单个步骤) ：</span><span class="sxs-lookup"><span data-stu-id="cd82f-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="cd82f-122">[将用户从本地Skype for Business Server (移动到) Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="cd82f-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="cd82f-123">在用户位于 Skype for Business Online 中后，为用户分配 mode= TeamsOnly 的 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="cd82f-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="cd82f-124">若要授予 TeamsOnly 模式，请从联机 PowerShell Skype for Business运行以下 cmdlet：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="cd82f-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="cd82f-125">如果你有来自 Skype for Business Server 2015 CU8 或更高版本的管理工具，可以使用上述方法，也可以执行如下所述的一个步骤进行此移动。</span><span class="sxs-lookup"><span data-stu-id="cd82f-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="cd82f-126">此外，还可以选择在将 Skype for Business 客户端移动到 Teams Only 之前提供通知，也可以选择让 Skype for Business 客户端以无提示方式下载 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="cd82f-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="cd82f-127">为准备即将停用 Skype for Business Online，Microsoft 将简化组织在Teams迁移方式。</span><span class="sxs-lookup"><span data-stu-id="cd82f-127">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future.</span></span> <span data-ttu-id="cd82f-128">将用户从本地迁移到 Teams，很快将不再需要指定 切换，将用户直接从本地移动到 `-MoveToTeams` `Move-CsUser` TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="cd82f-128">When moving a user from on-premises to Teams, it will soon no longer be required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises to TeamsOnly.</span></span> <span data-ttu-id="cd82f-129">目前，如果未指定此开关，用户会从本地Skype for Business Server切换到 Skype for Business Online，其模式保持不变。</span><span class="sxs-lookup"><span data-stu-id="cd82f-129">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged.</span></span> <span data-ttu-id="cd82f-130">停用后，使用 将用户从本地迁移到云时，将自动为用户分配 TeamsOnly 模式，并且其从本地会议将自动转换为 Teams 会议，就像 `Move-CsUser` ， 一样，无论是否实际指定了切换。 `-MoveToTeams switch had been specified`</span><span class="sxs-lookup"><span data-stu-id="cd82f-130">After retirement, when moving a user from on-premises to the cloud with `Move-CsUser`, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="cd82f-131">我们希望在 2021 年 7 月 31 日实际停用之前发布此功能。</span><span class="sxs-lookup"><span data-stu-id="cd82f-131">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="cd82f-132">将用户直接从本地Skype for Business移动到仅Teams</span><span class="sxs-lookup"><span data-stu-id="cd82f-132">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="cd82f-133">Skype for Business Server 2015 CU8 以及 Skype for Business Server 2019 中的本地管理工具支持使用 PowerShell 中的 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，在单个步骤中将用户从本地移动到 Teams Only 模式，如下所述。</span><span class="sxs-lookup"><span data-stu-id="cd82f-133">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="cd82f-134">使用Teams移动到Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cd82f-134">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="cd82f-135">Move-CsUser命令行管理程序 PowerShell Skype for Business中提供。</span><span class="sxs-lookup"><span data-stu-id="cd82f-135">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="cd82f-136">以下步骤和所需的权限与将用户移动到 Skype for Business Online 相同，不同点除外，您还必须指定 MoveToTeams 开关，并且必须确保用户除了 Skype for Business Online) 之外，还被授予了 Teams (的许可证。</span><span class="sxs-lookup"><span data-stu-id="cd82f-136">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="cd82f-137">您必须具有本地环境和云服务或 (Microsoft 365 或 Office 365) 的足够权限，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="cd82f-137">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="cd82f-138">您可以使用在两个环境中具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 Microsoft 365 或 Office 365 帐户的 `-Credential` 凭据。</span><span class="sxs-lookup"><span data-stu-id="cd82f-138">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="cd82f-139">若要使用 Move-CsUser 将用户Teams仅模式：</span><span class="sxs-lookup"><span data-stu-id="cd82f-139">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="cd82f-140">使用 参数指定要移动 `Identity` 的用户。</span><span class="sxs-lookup"><span data-stu-id="cd82f-140">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="cd82f-141">使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。</span><span class="sxs-lookup"><span data-stu-id="cd82f-141">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="cd82f-142">指定 `MoveToTeams` 开关。</span><span class="sxs-lookup"><span data-stu-id="cd82f-142">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="cd82f-143">如果您没有一个在本地和云服务 (Microsoft 365 或 Office 365) 中具有足够权限的帐户，请使用 参数在 Office 365 中为帐户 `-credential` 提供足够权限。</span><span class="sxs-lookup"><span data-stu-id="cd82f-143">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="cd82f-144">如果帐户在 Microsoft 365 或 Office 365不会以"onmicrosoft"结尾。 <span>com"，必须指定 参数，并指定正确的 `-HostedMigrationOverrideUrl` 值，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="cd82f-144">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="cd82f-145">以下 cmdlet 序列可用于将用户移动到 TeamsOnly，并假定 Microsoft 365 或 Office 365 凭据是一个单独的帐户，并作为 Get-Credential 提示的输入提供。</span><span class="sxs-lookup"><span data-stu-id="cd82f-145">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="cd82f-146">由于存在需要不同参数的不同情况，因此大多数情况下的默认命令是：</span><span class="sxs-lookup"><span data-stu-id="cd82f-146">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cd82f-147">使用Teams控制面板Skype for Business Server移动到</span><span class="sxs-lookup"><span data-stu-id="cd82f-147">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cd82f-148">打开Skype for Business Server控制面板"应用。</span><span class="sxs-lookup"><span data-stu-id="cd82f-148">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="cd82f-149">在左侧导航栏中，选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="cd82f-149">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="cd82f-150">使用 **"** 查找"查找 (要) 用户的位置Teams。</span><span class="sxs-lookup"><span data-stu-id="cd82f-150">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="cd82f-151">Select the user (s) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Teams**.</span><span class="sxs-lookup"><span data-stu-id="cd82f-151">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="cd82f-152">在向导中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="cd82f-152">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="cd82f-153">如果系统提示，Microsoft 365或Office 365 .onmicrosoft.com 且具有足够权限的帐户登录或登录。</span><span class="sxs-lookup"><span data-stu-id="cd82f-153">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="cd82f-154">单击 **"下\*\*\*\*一步**"，再单击"下一步"以移动用户。</span><span class="sxs-lookup"><span data-stu-id="cd82f-154">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="cd82f-155">请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。</span><span class="sxs-lookup"><span data-stu-id="cd82f-155">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="cd82f-156">通知Skype for Business本地用户即将移动到Teams</span><span class="sxs-lookup"><span data-stu-id="cd82f-156">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="cd82f-157">Skype for Business Server 2015 CU8 和 Skype for Business Server 2019 中的本地管理工具让你能够通知本地 Skype for Business 用户他们即将移动到 Teams。</span><span class="sxs-lookup"><span data-stu-id="cd82f-157">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="cd82f-158">当你启用这些通知时，用户将看到其 Skype for Business 客户端 (Win32、Mac、Web 和移动) 通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cd82f-158">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="cd82f-159">如果用户单击"**试用**"按钮，Teams客户端将启动（如果已安装）;否则，用户将在浏览器中导航到 Teams Web 版本。</span><span class="sxs-lookup"><span data-stu-id="cd82f-159">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="cd82f-160">默认情况下，当启用通知时，Win32 Skype for Business客户端会以静默方式下载 Teams 客户端，以便丰富客户端在将用户移动到"仅Teams模式之前可用;但是，您也可以禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="cd82f-160">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="cd82f-161">通知使用 本地版本进行配置，Win32 客户端的无提示下载通过 `TeamsUpgradePolicy` 本地 `TeamsUpgradeConfiguration` cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="cd82f-161">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="cd82f-162">某些服务器可能需要重新启动才能在 2015 CU8 Skype for Business中工作。</span><span class="sxs-lookup"><span data-stu-id="cd82f-162">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![有关即将移动到 Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="cd82f-164">若要通知本地用户他们即将升级到 Teams，请创建一个 NotifySfBUsers=true 的 TeamsUpgradePolicy 新实例。</span><span class="sxs-lookup"><span data-stu-id="cd82f-164">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="cd82f-165">然后，通过直接向用户分配策略或在站点、池或全局级别设置策略，将策略分配给要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="cd82f-165">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="cd82f-166">以下 cmdlet 可创建并授予用户级别的策略：</span><span class="sxs-lookup"><span data-stu-id="cd82f-166">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="cd82f-167">通过 win32 Teams自动下载Skype for Business通过具有 DownloadTeams 参数的本地 TeamsUpgradeConfiguration cmdlet 进行控制。</span><span class="sxs-lookup"><span data-stu-id="cd82f-167">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="cd82f-168">您可以在全局、站点和池级别创建此配置。</span><span class="sxs-lookup"><span data-stu-id="cd82f-168">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="cd82f-169">例如，以下命令为站点 Redmond1 创建配置：</span><span class="sxs-lookup"><span data-stu-id="cd82f-169">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="cd82f-170">默认情况下，DownloadTeams 的值为 True;但是，只有当给定 *用户的* NotifySfbUser = True 时，才遵守此要求。</span><span class="sxs-lookup"><span data-stu-id="cd82f-170">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd82f-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd82f-171">See also</span></span>

[<span data-ttu-id="cd82f-172">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cd82f-172">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="cd82f-173">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="cd82f-173">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="cd82f-174">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="cd82f-174">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="cd82f-175">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="cd82f-175">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
