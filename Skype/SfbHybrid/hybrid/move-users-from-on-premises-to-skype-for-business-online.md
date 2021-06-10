---
title: 将用户从本地迁移至 Skype for Business Online
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
description: 了解如何将用户移动到 Skype for Business Online。
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863193"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="53b63-103">将用户从本地迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="53b63-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="53b63-104">将用户从本地移动到 Skype for Business Online 后，用户与 Skype for Business Online 进行交互，以使用其功能。</span><span class="sxs-lookup"><span data-stu-id="53b63-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="53b63-105">本地存在的任何联系人都将在 Skype for Business Online 中可用，并且用户为将来组织的任何现有会议都将更新为 ，以便链接指向 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="53b63-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="53b63-106">如果用户启用了音频会议，则会议还将包括拨入坐标。</span><span class="sxs-lookup"><span data-stu-id="53b63-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="53b63-107">若要将用户从本地环境移动到 Skype for Business Online，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。</span><span class="sxs-lookup"><span data-stu-id="53b63-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="53b63-108">在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。</span><span class="sxs-lookup"><span data-stu-id="53b63-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="53b63-109">为准备即将停用 Skype for Business Online，Microsoft 简化了组织移动到 Teams。</span><span class="sxs-lookup"><span data-stu-id="53b63-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="53b63-110">将用户从本地迁移到云时，现在会自动为用户分配 TeamsOnly 模式，其从本地会议自动转换为 Teams 会议，就像已指定交换机一样，无论是否实际指定了交换机。 `-MoveToTeams`</span><span class="sxs-lookup"><span data-stu-id="53b63-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="53b63-111">停用 Skype for Business Online 之前，需要将用户从本地迁移到 Skype for Business Online 的组织可以通过在将用户移至 *TeamsOnly* 后更新用户模式，分两步完成此操作。</span><span class="sxs-lookup"><span data-stu-id="53b63-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="53b63-112">但是，在近期内，将不再可以将 TeamsOnly 模式分配给托管在云中的用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="53b63-113">使用迁移功能Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="53b63-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="53b63-114">Move-CsUser命令行管理程序 PowerShell Skype for Business中提供。</span><span class="sxs-lookup"><span data-stu-id="53b63-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="53b63-115">您必须在内部部署环境以及 Microsoft 365 组织中具有足够的权限，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="53b63-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="53b63-116">您可以在这两个环境中使用具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 Microsoft 365 帐户的 `-Credential` 凭据。</span><span class="sxs-lookup"><span data-stu-id="53b63-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="53b63-117">若要使用 Move-CsUser 将用户移动到联机：</span><span class="sxs-lookup"><span data-stu-id="53b63-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="53b63-118">使用 Identity 参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="53b63-119">使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。</span><span class="sxs-lookup"><span data-stu-id="53b63-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="53b63-120">如果您没有一个在本地和 Microsoft 365 中具有足够权限的帐户，请使用 -credential 参数在 Microsoft 365 中为帐户提供足够权限。</span><span class="sxs-lookup"><span data-stu-id="53b63-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="53b63-121">如果具有此权限的帐户Microsoft 365以".onmicrosoft"结尾。 <span>com"， then you must specify the -HostedMigrationOverrideUrl parameter， with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="53b63-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="53b63-122">以下 cmdlet 序列可用于将用户移动到 Skype for Business Online 并将租户默认模式分配给用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="53b63-123">它假定Microsoft 365凭据是一个单独的帐户，并作为输入提供给 Get-Credential 提示。</span><span class="sxs-lookup"><span data-stu-id="53b63-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="53b63-124">如果管理员帐户启用了 MFA (多重身份验证) ，则不要指定 -Credential 参数。</span><span class="sxs-lookup"><span data-stu-id="53b63-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="53b63-125">将提示管理员输入凭据。</span><span class="sxs-lookup"><span data-stu-id="53b63-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="53b63-126">使用"控制面板Skype for Business Server移动用户Teams管理中心</span><span class="sxs-lookup"><span data-stu-id="53b63-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="53b63-127">打开Skype for Business Server控制面板"应用。</span><span class="sxs-lookup"><span data-stu-id="53b63-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="53b63-128">在左侧导航栏中，选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="53b63-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="53b63-129">使用 **"** 查找"查找 (要) 移动到 Skype for Business Online 的用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="53b63-130">Select the user (s) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Skype for Business Online** or Move selected users to **Teams**.</span><span class="sxs-lookup"><span data-stu-id="53b63-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="53b63-131">这两个选项最初都会将用户移动到 TeamsOnly 模式，但在移动后，你可以分配另一种模式。</span><span class="sxs-lookup"><span data-stu-id="53b63-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="53b63-132">在向导中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="53b63-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="53b63-133">如果系统提示，请Microsoft 365以 .onmicrosoft.com 结尾且具有足够权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="53b63-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="53b63-134">单击 **"下\*\*\*\*一步**"，再单击"下一步"以移动用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="53b63-135">请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。</span><span class="sxs-lookup"><span data-stu-id="53b63-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="53b63-136">打开Teams管理中心，然后选择左侧导航栏中的"用户"。</span><span class="sxs-lookup"><span data-stu-id="53b63-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="53b63-137">在 listview 中单击所需的用户。</span><span class="sxs-lookup"><span data-stu-id="53b63-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="53b63-138">单击 **"升级**"部分中的"编辑 **Teams升级"。**</span><span class="sxs-lookup"><span data-stu-id="53b63-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="53b63-139">在右侧飞出中，选择所需的共存模式， **然后单击应用**。</span><span class="sxs-lookup"><span data-stu-id="53b63-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="53b63-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53b63-140">See also</span></span>

[<span data-ttu-id="53b63-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="53b63-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
