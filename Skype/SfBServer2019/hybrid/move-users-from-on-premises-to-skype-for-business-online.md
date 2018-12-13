---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 了解如何为业务 Online 将用户移至 Skype。
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243995"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="595d9-103">将用户从本地迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="595d9-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="595d9-104">移动用户从内部部署到 Skype 业务 online 后，用户与交互 Skype 业务 online 其功能。</span><span class="sxs-lookup"><span data-stu-id="595d9-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="595d9-105">存在内部部署的任何联系人将 Skype 业务 online 中可用，并且用户组织未来的任何现有会议更新为以便链接指向 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="595d9-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="595d9-106">如果为用户启用音频会议，会议也将包括电话拨入式坐标。</span><span class="sxs-lookup"><span data-stu-id="595d9-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="595d9-107">将用户从内部部署环境迁移到 Skype 业务 online，用于 Move-csuser cmdlet 或 Skype 业务 Server Control Panel，二者是内部部署工具。</span><span class="sxs-lookup"><span data-stu-id="595d9-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="595d9-108">任何用户之前，请确保查看[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)将用户移动到云。</span><span class="sxs-lookup"><span data-stu-id="595d9-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="595d9-109">具有 Move-csuser 移动用户</span><span class="sxs-lookup"><span data-stu-id="595d9-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="595d9-110">可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="595d9-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="595d9-111">[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述，您必须具有足够的权限，这两个内部部署环境中以及与 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="595d9-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="595d9-112">您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口内部 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。</span><span class="sxs-lookup"><span data-stu-id="595d9-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="595d9-113">将用户移动到 online 使用 Move-csuser:</span><span class="sxs-lookup"><span data-stu-id="595d9-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="595d9-114">指定的用户将使用 Identity 参数。</span><span class="sxs-lookup"><span data-stu-id="595d9-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="595d9-115">指定-Target 参数的值"sipfed.online.lync。<span>com"。</span><span class="sxs-lookup"><span data-stu-id="595d9-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="595d9-116">如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用-credential 参数，以提供足够的权限，在 Office 365 中使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="595d9-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="595d9-117">如果在 Office 365 中权限帐户不是以"on.microsoft 结尾。<span>com"，则必须指定-HostedMigrationOverrideUrl 参数，用正确的值[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="595d9-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="595d9-118">以下 cmdlet 序列可用于将用户移至 Skype，业务 online，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。</span><span class="sxs-lookup"><span data-stu-id="595d9-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="595d9-119">与 Skype 的业务 Server 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="595d9-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="595d9-120">打开业务服务器控件 Skype 面板应用程序。</span><span class="sxs-lookup"><span data-stu-id="595d9-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="595d9-121">在左侧导航窗格中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="595d9-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="595d9-122">使用**查找**来查找您想要移动到 Skype 的业务联机用户。</span><span class="sxs-lookup"><span data-stu-id="595d9-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="595d9-123">选择的用户，，然后，从列表上方的**操作**下拉列表中选择**移动到业务 online Skype 的所选的用户**。</span><span class="sxs-lookup"><span data-stu-id="595d9-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="595d9-124">在向导中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="595d9-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="595d9-125">如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="595d9-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="595d9-126">单击**下一步**，然后**下**一次将用户移动。</span><span class="sxs-lookup"><span data-stu-id="595d9-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="595d9-127">请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。</span><span class="sxs-lookup"><span data-stu-id="595d9-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="595d9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="595d9-128">See also</span></span>

[<span data-ttu-id="595d9-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="595d9-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)