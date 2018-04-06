---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 摘要： 了解如何迁移用户设置并进入用户 Skype 的在线业务。
ms.openlocfilehash: 352798c217cb7495134cb32996db783f7e498ded
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="05192-103">将用户从本地迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05192-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="05192-104">**摘要：**了解如何迁移用户设置并进入用户 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="05192-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="05192-p101">在实际将用户迁移到 Office 365 时，必须首先确认用户帐户已同步到云并为他们分配许可证。为此，请使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="05192-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="05192-107">确认本地用户帐户是否已与 Office 365 同步</span><span class="sxs-lookup"><span data-stu-id="05192-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="05192-108">为您的租户使用租户管理帐户，打开[Office 365 管理中心](https://portal.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="05192-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>  <span data-ttu-id="05192-109">租户管理员帐户应被授予两个 Skype 业务管理员角色和用户管理角色 （或全局管理员角色） 在 Office 365 中执行此功能</span><span class="sxs-lookup"><span data-stu-id="05192-109">Tenant admin accounts should be granted both the Skype for Business Admin Role and the User Management Role (or the Global Admin role) to perform this function in Office 365</span></span>
    
2. <span data-ttu-id="05192-110">在左侧导航窗格中，单击“**用户**”，然后单击“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="05192-110">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="05192-111">单击“**搜索用户**”，然后键入用户的名称。</span><span class="sxs-lookup"><span data-stu-id="05192-111">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="05192-112">确认您看到用户，并且其状态为“**已与 Active Directory 同步**”。</span><span class="sxs-lookup"><span data-stu-id="05192-112">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="05192-113">如果用户尚未同步，则应在三小时内执行下一次自动同步。</span><span class="sxs-lookup"><span data-stu-id="05192-113">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="05192-114">你还可以更早地强制同步。</span><span class="sxs-lookup"><span data-stu-id="05192-114">You can also force a synchronization sooner.</span></span> <span data-ttu-id="05192-115">有关详细信息，请参阅[强制目录同步](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)。</span><span class="sxs-lookup"><span data-stu-id="05192-115">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="05192-116">若要指定 Office 365 中的许可，请参阅[分配业务的 Office 365 的许可证](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="05192-116">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="05192-117">对于在线业务迁移到 Skype 的用户设置</span><span class="sxs-lookup"><span data-stu-id="05192-117">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="05192-118">在开始的在线业务迁移到 Skype 的用户之前，您应该备份与要移动的帐户关联的用户数据。</span><span class="sxs-lookup"><span data-stu-id="05192-118">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="05192-119">并非所有用户数据都会与用户帐户一并移动。</span><span class="sxs-lookup"><span data-stu-id="05192-119">Not all user data is moved with the user account.</span></span> <span data-ttu-id="05192-120">有关信息，请参阅[备份和还原要求： 数据](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="05192-120">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="05192-p105">用户设置随用户帐户一起移动。一些本地设置不随用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="05192-p105">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="05192-123">进入试生产用户 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="05192-123">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="05192-124">转向用户 Skype 的在线业务之前，您可能需要移动几个试用的用户，以确认正确配置您的环境。</span><span class="sxs-lookup"><span data-stu-id="05192-124">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="05192-125">然后，你可以在尝试移动其他用户之前验证功能和服务是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="05192-125">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="05192-126">要移动到您的在线业务的租户的 Skype 的内部用户，运行以下 cmdlet 在 Skype 业务管理程序，对 Microsoft Office 365 租户使用管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="05192-126">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="05192-127">使用要移动的用户的信息替换“username@contoso.com”。</span><span class="sxs-lookup"><span data-stu-id="05192-127">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="05192-128">将用户迁移至 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05192-128">Move users to Skype for Business Online</span></span>

<span data-ttu-id="05192-129">您可以通过使用[Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 移动多个用户使用-筛选器参数选择的用户与特定属性分配给用户帐户，如 RegistrarPool。</span><span class="sxs-lookup"><span data-stu-id="05192-129">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="05192-130">下面的示例中所示，您可以通过管道[移动 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet，返回的用户。</span><span class="sxs-lookup"><span data-stu-id="05192-130">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="05192-131">此外可以使用 OU 参数来检索所有用户在指定的 OU 中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="05192-131">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="05192-132">验证 Online 用户设置和功能</span><span class="sxs-lookup"><span data-stu-id="05192-132">Verify online user settings and features</span></span>

<span data-ttu-id="05192-133">可通过以下方式验证用户是否已成功移动：</span><span class="sxs-lookup"><span data-stu-id="05192-133">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="05192-p109">在 Skype for Business Online 控制面板中查看用户的状态。用于本地用户和联机用户的可视指示器不同。</span><span class="sxs-lookup"><span data-stu-id="05192-p109">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="05192-136">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="05192-136">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```


