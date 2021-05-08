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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237958"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="3f932-103">将用户从本地迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f932-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="3f932-104">将用户从本地移动到 Skype for Business Online 后，用户与 Skype for Business Online 进行交互，以使用其功能。</span><span class="sxs-lookup"><span data-stu-id="3f932-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="3f932-105">本地存在的任何联系人都将在 Skype for Business Online 中可用，并且用户为将来组织的任何现有会议都将更新为 ，以便链接指向 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="3f932-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="3f932-106">如果用户启用了音频会议，则会议还将包括拨入坐标。</span><span class="sxs-lookup"><span data-stu-id="3f932-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="3f932-107">若要将用户从本地环境移动到 Skype for Business Online，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。</span><span class="sxs-lookup"><span data-stu-id="3f932-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3f932-108">在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。</span><span class="sxs-lookup"><span data-stu-id="3f932-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="3f932-109">使用迁移功能Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="3f932-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="3f932-110">Move-CsUser命令行管理程序 PowerShell Skype for Business中提供。</span><span class="sxs-lookup"><span data-stu-id="3f932-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="3f932-111">您必须在内部部署环境以及 Microsoft 365/Office 365 组织中具有足够的权限，如所需的管理[凭据中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="3f932-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="3f932-112">您可以使用在两个环境中具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 Microsoft 365 或 Office 365 帐户的 `-Credential` 凭据。</span><span class="sxs-lookup"><span data-stu-id="3f932-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="3f932-113">若要使用 Move-CsUser 将用户移动到联机：</span><span class="sxs-lookup"><span data-stu-id="3f932-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="3f932-114">使用 Identity 参数指定要移动的用户。</span><span class="sxs-lookup"><span data-stu-id="3f932-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="3f932-115">使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。</span><span class="sxs-lookup"><span data-stu-id="3f932-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="3f932-116">如果您没有一个在本地和 Office 365 中具有足够权限的帐户，请使用 -credential 参数在 Office 365 中为帐户提供足够权限。</span><span class="sxs-lookup"><span data-stu-id="3f932-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="3f932-117">如果具有 Office 365 的帐户不会以".onmicrosoft"结尾。 <span>com"， then you must specify the -HostedMigrationOverrideUrl parameter， with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="3f932-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="3f932-118">以下 cmdlet 序列可用于将用户移动到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="3f932-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="3f932-119">它假定Microsoft 365或Office 365凭据是一个单独的帐户，并作为输入提供给 Get-Credential 提示。</span><span class="sxs-lookup"><span data-stu-id="3f932-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="3f932-120">如果管理员帐户启用了 MFA (多重身份验证) ，则不要指定 -Credential 参数。</span><span class="sxs-lookup"><span data-stu-id="3f932-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="3f932-121">将提示管理员输入凭据。</span><span class="sxs-lookup"><span data-stu-id="3f932-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="3f932-122">使用"控制面板Skype for Business Server移动用户</span><span class="sxs-lookup"><span data-stu-id="3f932-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="3f932-123">打开Skype for Business Server控制面板"应用。</span><span class="sxs-lookup"><span data-stu-id="3f932-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="3f932-124">在左侧导航栏中，选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="3f932-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="3f932-125">使用 **"** 查找"查找 (要) 移动到 Skype for Business Online 的用户。</span><span class="sxs-lookup"><span data-stu-id="3f932-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="3f932-126">Select the user (the) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Skype for Business Online**.</span><span class="sxs-lookup"><span data-stu-id="3f932-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="3f932-127">在向导中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="3f932-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="3f932-128">如果系统提示，Microsoft 365或Office 365 .onmicrosoft.com 且具有足够权限的帐户登录或登录。</span><span class="sxs-lookup"><span data-stu-id="3f932-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="3f932-129">单击 **"下\*\*\*\*一步**"，再单击"下一步"以移动用户。</span><span class="sxs-lookup"><span data-stu-id="3f932-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="3f932-130">请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。</span><span class="sxs-lookup"><span data-stu-id="3f932-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f932-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f932-131">See also</span></span>

[<span data-ttu-id="3f932-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="3f932-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)