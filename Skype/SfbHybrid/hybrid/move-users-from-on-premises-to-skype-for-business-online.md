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
ms.openlocfilehash: d77bef77204a2b33d8fa8001cc54e19bf447b55f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779688"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="4aca5-103">将用户从本地迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4aca5-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="4aca5-104">将用户从本地迁移到 Skype for business Online 后，用户将与 Skype for Business Online 进行交互，了解其功能。</span><span class="sxs-lookup"><span data-stu-id="4aca5-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="4aca5-105">在 Skype for Business Online 中将提供本地的所有联系人，并且在将来组织的任何现有会议将更新为，以便这些链接指向 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="4aca5-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="4aca5-106">如果用户已启用音频会议，则会议还将包括拨入坐标。</span><span class="sxs-lookup"><span data-stu-id="4aca5-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="4aca5-107">若要将用户从本地环境移动到 Skype for Business Online，请使用 Get-csuser cmdlet 或 Skype for Business Server 控制面板，这两个控制面板都是本地工具。</span><span class="sxs-lookup"><span data-stu-id="4aca5-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="4aca5-108">在移动任何用户之前，请务必查看将用户移动到云的[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="4aca5-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="4aca5-109">将用户移动到 Get-csuser</span><span class="sxs-lookup"><span data-stu-id="4aca5-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="4aca5-110">Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。</span><span class="sxs-lookup"><span data-stu-id="4aca5-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="4aca5-111">在本地环境和 Office 365 组织中，您必须具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="4aca5-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="4aca5-112">您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`参数指定具有必要的 office 365 管理角色的 office 365 帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="4aca5-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="4aca5-113">使用 Get-csuser 将用户移动到联机状态的步骤：</span><span class="sxs-lookup"><span data-stu-id="4aca5-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="4aca5-114">使用 Identity 参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="4aca5-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="4aca5-115">指定值为 "sipfed.online.lync.com>" 的-Target 参数。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="4aca5-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="4aca5-116">如果您没有一个帐户在本地和 Office 365 中具有足够的权限，请使用-credential 参数在 Office 365 中提供具有足够权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="4aca5-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="4aca5-117">如果在 Office 365 中具有权限的帐户不以 ". .onmicrosoft" 结尾。<span>com "，则必须使用[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的正确值指定-HostedMigrationOverrideUrl 参数。</span><span class="sxs-lookup"><span data-stu-id="4aca5-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="4aca5-118">可以使用以下 cmdlet 序列将用户移动到 Skype for business Online，并假定 Office 365 凭据是单独的帐户并作为 Get Credential 提示的输入提供。</span><span class="sxs-lookup"><span data-stu-id="4aca5-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="4aca5-119">如果管理员帐户已启用 MFA （多重身份验证），请不要指定-Credential 参数。</span><span class="sxs-lookup"><span data-stu-id="4aca5-119">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="4aca5-120">系统将提示管理员输入凭据。</span><span class="sxs-lookup"><span data-stu-id="4aca5-120">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="4aca5-121">使用 Skype for Business Server 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="4aca5-121">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="4aca5-122">打开 "Skype for Business Server 控制面板" 应用。</span><span class="sxs-lookup"><span data-stu-id="4aca5-122">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="4aca5-123">在左侧导航栏中，选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="4aca5-123">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="4aca5-124">使用 "**查找**" 查找要迁移到 Skype For business Online 的用户。</span><span class="sxs-lookup"><span data-stu-id="4aca5-124">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="4aca5-125">选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到 Skype for business Online**"。</span><span class="sxs-lookup"><span data-stu-id="4aca5-125">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="4aca5-126">在向导中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4aca5-126">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="4aca5-127">如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Office 365 并拥有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="4aca5-127">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="4aca5-128">单击 "**下一步**"，然后再单击一次以移动用户。 **Next**</span><span class="sxs-lookup"><span data-stu-id="4aca5-128">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="4aca5-129">请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。</span><span class="sxs-lookup"><span data-stu-id="4aca5-129">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="4aca5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4aca5-130">See also</span></span>

[<span data-ttu-id="4aca5-131">移动-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="4aca5-131">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
