---
title: 分配外部用户访问策略
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果用户已启用 Skype for business 服务器的用户，则可以通过向特定用户应用相应的策略来在 Skype for business 服务器控制面板中配置 SIP 联盟、远程用户访问和公共即时消息（IM）连接。
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818323"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="e3fd7-103">将外部用户访问策略分配给启用 Skype for Business 的用户</span><span class="sxs-lookup"><span data-stu-id="e3fd7-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="e3fd7-104">如果用户已启用 Skype for business 服务器的用户，则可以通过向特定用户应用相应的策略来在 Skype for business 服务器控制面板中配置 SIP 联盟、远程用户访问和公共即时消息（IM）连接。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="e3fd7-105">例如，如果你创建了支持远程用户访问的策略，则必须先将其应用于用户，然后用户才能从远程位置连接到 Skype for Business 服务器，并从远程位置与内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="e3fd7-106">若要支持外部用户访问，必须启用对要支持的每种类型的外部用户访问的支持，并配置相应的策略和其他选项以控制其使用。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="e3fd7-107">有关详细信息，请参阅[管理对 Skype for Business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="e3fd7-108">使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="e3fd7-109">将外部用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="e3fd7-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="e3fd7-110">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3fd7-111">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e3fd7-112">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="e3fd7-113">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e3fd7-114">在 "**编辑 Skype For Business 服务器" 用户**的 "**外部访问策略**" 下，选择要应用的用户策略。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="e3fd7-115">自动>设置将应用默认服务器或全局策略设置。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="e3fd7-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e3fd7-116">使用 Windows PowerShell Cmdlet 分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e3fd7-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e3fd7-117">可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 分配每用户外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e3fd7-118">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="e3fd7-119">将每用户外部访问策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="e3fd7-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="e3fd7-120">此命令将每用户外部访问策略 RedmondExternalAccessPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="e3fd7-121">为多个用户分配每个用户的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e3fd7-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="e3fd7-122">此命令将每用户外部访问策略 USAExternalAccessPolicy 分配给在 Active Directory 中的美国组织单位中拥有帐户的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="e3fd7-123">有关此命令中使用的 OU 参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="e3fd7-124">取消分配每用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e3fd7-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="e3fd7-125">此命令取消之前分配给 Ken Myer 的任何每用户外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e3fd7-126">取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e3fd7-127">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="e3fd7-128">有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e3fd7-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


