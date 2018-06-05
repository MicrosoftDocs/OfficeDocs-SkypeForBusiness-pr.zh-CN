---
title: 在 Skype for Business Server 2015 中部署统一联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要： 启用统一的联系人存储中 Skype 的业务服务器 2015年。
ms.openlocfilehash: 2004ab4074af98381fbbfdf67ba4ce0bac9503a8
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568715"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="20fe3-103">在 Skype for Business Server 2015 中部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="20fe3-103">Deploy unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20fe3-104">**摘要：** 启用统一的联系人存储中 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="20fe3-104">**Summary:** Enable the unified contact store in Skype for Business Server 2015 .</span></span>
  
<span data-ttu-id="20fe3-105">启用统一的联系人存储库中 Skype 业务服务器 2015年不需要任何拓扑设置。</span><span class="sxs-lookup"><span data-stu-id="20fe3-105">Enabling unified contact store in Skype for Business Server 2015 does not require any topology settings.</span></span> <span data-ttu-id="20fe3-106">要为用户启用统一的联系人存储库，需要：</span><span class="sxs-lookup"><span data-stu-id="20fe3-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="20fe3-107">启用统一的联系人存储库策略（将启用默认值）。</span><span class="sxs-lookup"><span data-stu-id="20fe3-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="20fe3-108">用户登录与 for Business 的 Skype 至少一次。</span><span class="sxs-lookup"><span data-stu-id="20fe3-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="20fe3-109">用户的联系人迁移，这种情况使用 Skype 为企业用户登录时自动发生之后，用户可以访问和管理其业务联系人 Skype 从 Skype 业务、 Outlook 2013 或 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="20fe3-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="20fe3-110">用户不需要登录到 Skype for Business Outlook 或 Outlook Web Access 中管理他们的联系人。</span><span class="sxs-lookup"><span data-stu-id="20fe3-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="20fe3-111">如果用户从登录 for Business 的 Skype 迁移后，联系人和组都可用并且保持最新，但用户无法管理 （即添加、 删除、 移动、 标记，取消标记，或修改） 这些联系人。</span><span class="sxs-lookup"><span data-stu-id="20fe3-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="20fe3-112">为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="20fe3-112">Enable users for unified contact store</span></span>

<span data-ttu-id="20fe3-113">当您部署业务服务器 2015 Skype 并发布拓扑时，统一联系人存储库默认情况下启用为所有用户。</span><span class="sxs-lookup"><span data-stu-id="20fe3-113">When you deploy Skype for Business Server 2015 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="20fe3-114">不需要执行任何其他操作来启用统一的联系人存储库的业务服务器 2015年部署 Skype 后。</span><span class="sxs-lookup"><span data-stu-id="20fe3-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server 2015.</span></span> <span data-ttu-id="20fe3-115">但是， **Set-csuserservicespolicy** cmdlet 可用于自定义哪些用户有统一联系人存储库可用。</span><span class="sxs-lookup"><span data-stu-id="20fe3-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="20fe3-116">可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。</span><span class="sxs-lookup"><span data-stu-id="20fe3-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="20fe3-117">为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="20fe3-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="20fe3-118">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="20fe3-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="20fe3-119">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="20fe3-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="20fe3-120">若要启用全局性针对所有 Skype 业务 Server 用户的统一联系人存储库，中间在 Windows PowerShell 命令行界面以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="20fe3-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="20fe3-121">若要为特定站点的用户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="20fe3-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="20fe3-122">例如：</span><span class="sxs-lookup"><span data-stu-id="20fe3-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="20fe3-123">若要按租户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="20fe3-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="20fe3-124">例如：</span><span class="sxs-lookup"><span data-stu-id="20fe3-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="20fe3-125">若要为特定用户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="20fe3-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="20fe3-126">还可以使用用户别名或 SIP URI 代替用户显示名称。</span><span class="sxs-lookup"><span data-stu-id="20fe3-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="20fe3-127">例如：</span><span class="sxs-lookup"><span data-stu-id="20fe3-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="20fe3-128">在上述示例中，第一个命令创建新的每用户策略的了将 UcsAllowed 标记设置为 True 以命名 UCS 启用用户。</span><span class="sxs-lookup"><span data-stu-id="20fe3-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="20fe3-129">第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="20fe3-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="20fe3-130">将用户迁移到统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="20fe3-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="20fe3-131">用户的联系人都将自动迁移到 Exchange 2013 服务器时用户：</span><span class="sxs-lookup"><span data-stu-id="20fe3-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="20fe3-132">为其分配了将 UcsAllowed 设置为 True 的用户服务策略。</span><span class="sxs-lookup"><span data-stu-id="20fe3-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="20fe3-133">已设置 Exchange 2013 邮箱和已登录该邮箱至少一次。</span><span class="sxs-lookup"><span data-stu-id="20fe3-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="20fe3-134">使用 Skype 业务富客户端中的日志。</span><span class="sxs-lookup"><span data-stu-id="20fe3-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="20fe3-135">如果用户登录 Lync 或早期客户端，或者用户未连接到 Exchange 2013 服务器，请忽略用户服务策略和用户的联系人保留业务服务器在 Skype。</span><span class="sxs-lookup"><span data-stu-id="20fe3-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="20fe3-136">您可以通过以下任一方法来确定是否已迁移用户的联系人：</span><span class="sxs-lookup"><span data-stu-id="20fe3-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="20fe3-137">在客户端计算机上检查以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="20fe3-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="20fe3-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="20fe3-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="20fe3-139">如果用户的联系人存储在 Exchange 2013 中，此项包含 InUCSMode 的值为 2165年的值。</span><span class="sxs-lookup"><span data-stu-id="20fe3-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="20fe3-140">运行**Test-csunifiedcontactstore** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20fe3-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="20fe3-141">在为业务 Server 命令行管理程序命令行 Skype，键入：</span><span class="sxs-lookup"><span data-stu-id="20fe3-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="20fe3-142">如果**Test-csunifiedcontactstore**成功，用户的联系人迁移到统一联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="20fe3-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="20fe3-143">回滚已迁移用户</span><span class="sxs-lookup"><span data-stu-id="20fe3-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="20fe3-144">如果需要回滚统一的联系人存储功能，但仅当您将用户移回到 Exchange 2010 或 Lync Server 2010 回滚联系人。</span><span class="sxs-lookup"><span data-stu-id="20fe3-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="20fe3-145">若要回滚，禁用对用户策略，然后再运行**Invoke-csucsrollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20fe3-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="20fe3-146">只需运行**Invoke-csucsrollback**本身不足以确保永久回滚，因为如果不禁用此策略，则将再次启动统一联系人存储库迁移。</span><span class="sxs-lookup"><span data-stu-id="20fe3-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="20fe3-147">例如，如果用户回滚原因 Exchange 2013 回滚到 Exchange 2010，然后将该用户的邮箱移到 Exchange 2013，统一联系人存储库迁移将启动再次七天后回滚，只要统一的联系人存储仍用户服务策略中为用户启用。</span><span class="sxs-lookup"><span data-stu-id="20fe3-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="20fe3-148">**Move-csuser** cmdlet 自动回滚用户的联系人存储从 Exchange 2013 到 Skype 的业务服务器 2015年在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="20fe3-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server 2015 in the following situations:</span></span>
  
- <span data-ttu-id="20fe3-149">当用户移动 Skype 的业务服务器 2015年到 Microsoft Lync Server 2013 或 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="20fe3-149">When users are moved from Skype for Business Server 2015 to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="20fe3-150">当用户交叉迁移，如当用户从移动 Skype 业务 online 到 Skype 业务服务器 2015年本地，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="20fe3-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server 2015 on-premises, or vice versa.</span></span>
    
<span data-ttu-id="20fe3-p107">如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：</span><span class="sxs-lookup"><span data-stu-id="20fe3-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="20fe3-153">如果用户的联系人迁移到 Exchange 2013，然后迁移后，导入相同的数据之前, 导出的联系人列表会损坏的统一联系人存储数据和联系人列表。</span><span class="sxs-lookup"><span data-stu-id="20fe3-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="20fe3-154">如果后将用户迁移到 Exchange 2013 导出用户数据，回滚迁移，则由于某种原因，在迁移后导入的数据，统一的联系人存储数据和联系人列表会被破坏。</span><span class="sxs-lookup"><span data-stu-id="20fe3-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="20fe3-155">将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保的 Skype 业务服务器管理员已先回滚 Skype 的企业服务器用户联系人从 Exchange 2013 到 Skype 的业务服务器。</span><span class="sxs-lookup"><span data-stu-id="20fe3-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="20fe3-156">回滚统一的联系人存储联系人到 Skype 业务服务器，请参阅过程"回滚统一的联系人存储联系人从 Exchange 2013 收件人 Skype for Business Server，"后面本节中。</span><span class="sxs-lookup"><span data-stu-id="20fe3-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="20fe3-157">**如何回滚用户联系人：** 如果您使用**Move-csuser** cmdlet 的业务服务器 2015 Skype 和 Lync Server 2010 之间移动用户，因为**Move-csuser** cmdlet 自动回滚统一的联系人存储从 Skype 的移动用户时，您可以跳过这些步骤到 Lync Server 2010 的业务服务器 2015。</span><span class="sxs-lookup"><span data-stu-id="20fe3-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="20fe3-158">**Move-csuser**不禁用统一联系人存储库策略，因此当用户移回至 Skype 的业务服务器 2015年重复迁移到统一联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="20fe3-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

