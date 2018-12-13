---
title: 将用户从内部部署移动到团队
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何迁移用户设置并将用户移动到团队。
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244030"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="51038-103">将用户从内部部署移动到团队</span><span class="sxs-lookup"><span data-stu-id="51038-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="51038-104">当用户移从本地至仅团队时，用户的 Skype 商业主页移从本地至联机和该用户分配 TeamsUpgradePolicy 与 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="51038-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="51038-105">用户移动后从内部部署到 TeamsOnly 模式：</span><span class="sxs-lookup"><span data-stu-id="51038-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="51038-106">所有传入呼叫和 （是否从 Skype 发送适用于商务或团队） 聊天从其他用户，将位于用户的工作组客户端中。</span><span class="sxs-lookup"><span data-stu-id="51038-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="51038-107">用户将能够与其他用户 （是否联机或本地） for Business 使用 Skype 的互操作。</span><span class="sxs-lookup"><span data-stu-id="51038-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span> 
- <span data-ttu-id="51038-108">用户将能够与联盟组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="51038-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="51038-109">该用户安排的新会议是团队会议。</span><span class="sxs-lookup"><span data-stu-id="51038-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="51038-110">用户仍可以加入任何 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="51038-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="51038-111">安排为将来的用户的前现有会议将业务 online 中的内部部署迁移到 Skype。</span><span class="sxs-lookup"><span data-stu-id="51038-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Skype for Business Online.</span></span>
- <span data-ttu-id="51038-112">在用户首次登录后立即中团队, 提供了在本地存在的联系人。</span><span class="sxs-lookup"><span data-stu-id="51038-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="51038-113">用户不能发起呼叫或从业务的 Skype 聊天也不能可以安排 Skype for Business 中的新会议。</span><span class="sxs-lookup"><span data-stu-id="51038-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="51038-114">如果他们尝试打开 Skype 业务客户端，他们将被重定向使用团队，如下所示。</span><span class="sxs-lookup"><span data-stu-id="51038-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="51038-115">如果未安装团队客户端，他们将被导向团队使用其浏览器的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="51038-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="51038-116">![将用户重定向到团队的消息](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="51038-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="51038-117">任何用户之前，请确保查看[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)将用户移动到云。</span><span class="sxs-lookup"><span data-stu-id="51038-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="51038-118">此外请务必查看[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="51038-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>

<span data-ttu-id="51038-119">有两种方法将用户从本地移动到团队：</span><span class="sxs-lookup"><span data-stu-id="51038-119">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="51038-120">如果您正在使用版本早于 Skype 业务服务器 2015 CU8，移动需要两个步骤 （其中均可编制脚本完成一起作为单独的步骤，如果需要）：</span><span class="sxs-lookup"><span data-stu-id="51038-120">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
    - <span data-ttu-id="51038-121">[将用户从业务业务 online Skype （本地） 服务器的 Skype 移动](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="51038-121">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
    - <span data-ttu-id="51038-122">一旦用户驻留在 Skype 的在线，业务分配模式的用户 TeamsUpgradePolicy = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="51038-122">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="51038-123">若要授予 TeamsOnly 模式，请从业务 Online PowerShell 窗口 Skype 运行以下 cmdlet:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="51038-123">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="51038-124">如果您有从 Skype 的业务服务器 2015 CU8 或更高版本的管理工具，您可以使用上面的方法或可以如下所述的一个步骤中此移动。</span><span class="sxs-lookup"><span data-stu-id="51038-124">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="51038-125">此外，您可以选择提供内业务客户端之前将其移至仅团队 Skype 通知以及 （可选） 已由业务客户端 Skype 以无提示方式下载团队客户。</span><span class="sxs-lookup"><span data-stu-id="51038-125">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="51038-126">将直接从 for Business 的 Skype 本地用户移至仅团队</span><span class="sxs-lookup"><span data-stu-id="51038-126">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="51038-127">内部部署管理工具中的业务服务器 2015 CU8，与 Skype 以及中的业务服务器 2019 Skype 使您能够将用户从本地移动到团队仅模式下一步是在 PowerShell Move-csuser cmdlet 或 Skype 用于业务 Se进行服务器控制面板，如下所述。</span><span class="sxs-lookup"><span data-stu-id="51038-127">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="51038-128">将移动到团队使用 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="51038-128">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="51038-129">可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="51038-129">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="51038-130">下面的步骤和所需权限的相同用户移动到 Skype 业务 online，除了之外，还必须指定 MoveToTeams 开关必须确保，也已授予用户许可证 （除了 for Business 的 Skype 的团队Online)。</span><span class="sxs-lookup"><span data-stu-id="51038-130">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="51038-131">您必须具有足够的权限，在本地环境和 Office 365 租户，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="51038-131">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="51038-132">您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口的本地 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。</span><span class="sxs-lookup"><span data-stu-id="51038-132">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="51038-133">若要将用户移动到团队仅模式下使用 Move-csuser:</span><span class="sxs-lookup"><span data-stu-id="51038-133">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="51038-134">指定的用户将使用`Identity`参数。</span><span class="sxs-lookup"><span data-stu-id="51038-134">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="51038-135">指定-Target 参数的值"sipfed.online.lync。<span>com"。</span><span class="sxs-lookup"><span data-stu-id="51038-135">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="51038-136">指定`MoveToTeams`切换。</span><span class="sxs-lookup"><span data-stu-id="51038-136">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="51038-137">如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用`-credential`参数来提供与 Office 365 中的足够权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="51038-137">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="51038-138">如果在 Office 365 中权限帐户不是以"on.microsoft 结尾。<span>com"，则必须指定`-HostedMigrationOverrideUrl`参数，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述为正确值。</span><span class="sxs-lookup"><span data-stu-id="51038-138">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="51038-139">以下 cmdlet 序列可用于将用户移至 TeamsOnly，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。</span><span class="sxs-lookup"><span data-stu-id="51038-139">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51038-140">将移动到团队 Skype 用于业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="51038-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="51038-141">打开业务服务器控件 Skype 面板应用程序。</span><span class="sxs-lookup"><span data-stu-id="51038-141">Open the Skype for Business Server Control Panel app.</span></span>
2.  <span data-ttu-id="51038-142">在左侧导航窗格中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="51038-142">In the left navigation, choose **Users**.</span></span>
3.  <span data-ttu-id="51038-143">使用**查找**来查找您想要将移动到团队的用户。</span><span class="sxs-lookup"><span data-stu-id="51038-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4.  <span data-ttu-id="51038-144">选择的用户，，然后，从列表上方的**操作**下拉列表中选择**移动到团队的所选的用户**。</span><span class="sxs-lookup"><span data-stu-id="51038-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5.  <span data-ttu-id="51038-145">在向导中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51038-145">In the wizard, click **Next**.</span></span>
6.  <span data-ttu-id="51038-146">如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="51038-146">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7.  <span data-ttu-id="51038-147">单击**下一步**，然后**下**一次将用户移动。</span><span class="sxs-lookup"><span data-stu-id="51038-147">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="51038-148">请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。</span><span class="sxs-lookup"><span data-stu-id="51038-148">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="51038-149">通知您 Skype 业务内部部署用户的即将开始移动到团队</span><span class="sxs-lookup"><span data-stu-id="51038-149">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="51038-150">内部部署管理工具中的业务服务器 2015 CU8，与 Skype 以及中的业务服务器 2019 Skype 允许您将通知的其即将移动到团队的业务用户的内部部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="51038-150">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="51038-151">启用这些通知时，用户会看到其 Skype 业务客户端 （Win32、 Mac、 web 和移动） 的通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="51038-151">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="51038-152">如果安装; 如果用户单击**试用**按钮，将启动团队客户端否则，用户将导航到工作组的 web 版本在其浏览器中。</span><span class="sxs-lookup"><span data-stu-id="51038-152">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="51038-153">默认情况下，如果启用了通知，业务客户端的 Win32 Skype 以无提示方式下载团队客户端，这样可将用户移至仅团队模式，则之前的富客户端但是，您还可以禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="51038-153">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="51038-154">配置通知使用内部部署版本中的`TeamsUpgradePolicy`，Win32 客户端的无提示下载控制通过内部部署和`TeamsUpgradeConfiguration`cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51038-154">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

![即将发布移动到团队的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="51038-156">若要通知他们会很快将升级到团队的内部部署用户，请创建 TeamsUpgradePolicy 的新实例与 NotifySfBUsers = true。</span><span class="sxs-lookup"><span data-stu-id="51038-156">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="51038-157">然后将该策略分配给您想要通知，通过直接向用户分配策略或通过策略设置在站点、 池或全局级别的用户。</span><span class="sxs-lookup"><span data-stu-id="51038-157">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="51038-158">以下 cmdlet 创建并授予用户级别策略：</span><span class="sxs-lookup"><span data-stu-id="51038-158">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="51038-159">自动下载通过业务 Win32 客户端 Skype 团队通过内部部署 TeamsUpgradeConfiguration cmdlet 与 DownloadTeams 参数控制。</span><span class="sxs-lookup"><span data-stu-id="51038-159">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="51038-160">您创建此配置的全局、 站点和池级别。</span><span class="sxs-lookup"><span data-stu-id="51038-160">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="51038-161">例如，以下命令创建站点 Redmond1 的配置：</span><span class="sxs-lookup"><span data-stu-id="51038-161">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="51038-162">默认情况下 DownloadTeams 的值为 True;但是，就*只*适用如果 NotifySfbUser 给定用户 = True。</span><span class="sxs-lookup"><span data-stu-id="51038-162">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>


## <a name="see-also"></a><span data-ttu-id="51038-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51038-163">See also</span></span>

[<span data-ttu-id="51038-164">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="51038-164">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[<span data-ttu-id="51038-165">授予 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="51038-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="51038-166">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="51038-166">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="51038-167">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="51038-167">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
