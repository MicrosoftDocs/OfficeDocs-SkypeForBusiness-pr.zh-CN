---
title: '在 Skype for Business 服务器中部署统一联系人存储 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '摘要: 在 Skype for Business 服务器中启用统一联系人存储。'
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302801"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="fafc8-103">在 Skype for Business 服务器中部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="fafc8-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="fafc8-104">**摘要:** 在 Skype for Business 服务器中启用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="fafc8-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="fafc8-105">在 Skype for Business 服务器中启用统一联系人存储不需要任何拓扑设置。</span><span class="sxs-lookup"><span data-stu-id="fafc8-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="fafc8-106">要为用户启用统一的联系人存储库，需要：</span><span class="sxs-lookup"><span data-stu-id="fafc8-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="fafc8-107">启用统一的联系人存储库策略（将启用默认值）。</span><span class="sxs-lookup"><span data-stu-id="fafc8-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="fafc8-108">用户至少能用 Skype for Business 登录。</span><span class="sxs-lookup"><span data-stu-id="fafc8-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="fafc8-109">迁移用户的联系人后, 当用户使用 Skype for Business 登录时, 将自动发生此情况, 用户可以从 Skype for Business、Outlook 2013 或 Outlook Web Access 访问和管理其 Skype for business 联系人。</span><span class="sxs-lookup"><span data-stu-id="fafc8-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="fafc8-110">用户不必登录到 Skype for Business 即可从 Outlook 或 Outlook Web Access 管理其联系人。</span><span class="sxs-lookup"><span data-stu-id="fafc8-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fafc8-111">如果用户在迁移后从 Skype for Business 登录, 则 "联系人" 和 "组" 可用且是最新的, 但用户无法管理 (即添加、删除、移动、标记、取消标记或修改) 这些联系人。</span><span class="sxs-lookup"><span data-stu-id="fafc8-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="fafc8-112">为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="fafc8-112">Enable users for unified contact store</span></span>

<span data-ttu-id="fafc8-113">部署 Skype for Business 服务器并发布拓扑时, 默认情况下为所有用户启用 "统一联系人存储"。</span><span class="sxs-lookup"><span data-stu-id="fafc8-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="fafc8-114">部署 Skype for Business 服务器后, 无需执行任何其他操作即可启用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="fafc8-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="fafc8-115">但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="fafc8-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="fafc8-116">可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。</span><span class="sxs-lookup"><span data-stu-id="fafc8-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="fafc8-117">为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="fafc8-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="fafc8-118">启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="fafc8-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fafc8-119">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="fafc8-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="fafc8-120">若要为所有 Skype for Business Server 用户全局启用统一联系人存储, 请在 Windows PowerShell 命令行界面上使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fafc8-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="fafc8-121">若要为特定站点的用户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="fafc8-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="fafc8-122">例如：</span><span class="sxs-lookup"><span data-stu-id="fafc8-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="fafc8-123">若要按租户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="fafc8-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="fafc8-124">例如：</span><span class="sxs-lookup"><span data-stu-id="fafc8-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="fafc8-125">若要为特定用户启用统一联系人存储，请在命令提示符中键入：</span><span class="sxs-lookup"><span data-stu-id="fafc8-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="fafc8-126">还可以使用用户别名或 SIP URI 代替用户显示名称。</span><span class="sxs-lookup"><span data-stu-id="fafc8-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="fafc8-127">例如：</span><span class="sxs-lookup"><span data-stu-id="fafc8-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="fafc8-128">在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”的新每用户策略，并将 UcsAllowed 标记设置为 True。</span><span class="sxs-lookup"><span data-stu-id="fafc8-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="fafc8-129">第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="fafc8-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="fafc8-130">将用户迁移到统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="fafc8-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="fafc8-131">当用户执行以下操作时, 用户的联系人会自动迁移到 Exchange 2013 服务器:</span><span class="sxs-lookup"><span data-stu-id="fafc8-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="fafc8-132">为其分配了将 UcsAllowed 设置为 True 的用户服务策略。</span><span class="sxs-lookup"><span data-stu-id="fafc8-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="fafc8-133">已使用 Exchange 2013 邮箱进行了设置, 并且至少已登录到邮箱一次。</span><span class="sxs-lookup"><span data-stu-id="fafc8-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="fafc8-134">使用 Skype for Business 胖客户端登录。</span><span class="sxs-lookup"><span data-stu-id="fafc8-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="fafc8-135">如果用户使用 Lync 或更早的客户端登录, 或者如果用户未连接到 Exchange 2013 服务器, 则将忽略用户服务策略, 并且用户的联系人保留在 Skype for Business 服务器中。</span><span class="sxs-lookup"><span data-stu-id="fafc8-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="fafc8-136">您可以通过以下任一方法来确定是否已迁移用户的联系人：</span><span class="sxs-lookup"><span data-stu-id="fafc8-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="fafc8-137">在客户端计算机上检查以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="fafc8-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="fafc8-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="fafc8-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="fafc8-139">如果用户的联系人存储在 Exchange 2013 中, 则此注册表项包含值为2165的 InUCSMode 值。</span><span class="sxs-lookup"><span data-stu-id="fafc8-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="fafc8-140">运行 **Test-CsUnifiedContactStore** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fafc8-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="fafc8-141">在 Skype for Business Server Management Shell 命令行中, 键入:</span><span class="sxs-lookup"><span data-stu-id="fafc8-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="fafc8-142">如果 **Test-CsUnifiedContactStore** 成功，表明用户的联系人已迁移到统一联系人存储中。</span><span class="sxs-lookup"><span data-stu-id="fafc8-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="fafc8-143">回滚已迁移用户</span><span class="sxs-lookup"><span data-stu-id="fafc8-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="fafc8-144">如果需要回滚 "统一联系人存储" 功能, 请仅在将用户移回 Exchange 2010 或 Lync Server 2010 时, 才返回联系人。</span><span class="sxs-lookup"><span data-stu-id="fafc8-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="fafc8-145">要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fafc8-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="fafc8-146">只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。</span><span class="sxs-lookup"><span data-stu-id="fafc8-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="fafc8-147">例如, 如果由于 Exchange 2013 回退到 Exchange 2010 而回滚用户, 然后将用户的邮箱移动到 Exchange 2013, 则在回滚后的七天内将再次启动统一联系人存储迁移, 只要有统一联系人存储在用户服务策略中仍为用户启用。</span><span class="sxs-lookup"><span data-stu-id="fafc8-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="fafc8-148">在以下情况下, **move-csuser** cmdlet 会将用户的联系人存储从 Exchange 2013 自动回退到 Skype For business 服务器:</span><span class="sxs-lookup"><span data-stu-id="fafc8-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="fafc8-149">当用户从 Skype for Business 服务器移动到 Microsoft Lync Server 2013 或 Lync Server 2010 时。</span><span class="sxs-lookup"><span data-stu-id="fafc8-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="fafc8-150">当用户在本地迁移时, 例如, 当用户从 Skype for Business Online 移动到本地 Skype for business 服务器时, 反之亦然。</span><span class="sxs-lookup"><span data-stu-id="fafc8-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="fafc8-p107">如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：</span><span class="sxs-lookup"><span data-stu-id="fafc8-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="fafc8-153">如果在将用户联系人迁移到 Exchange 2013 之前导出联系人列表, 然后在迁移后导入相同的数据, 则统一联系人存储数据和联系人列表将损坏。</span><span class="sxs-lookup"><span data-stu-id="fafc8-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="fafc8-154">如果你在将用户迁移到 Exchange 2013 后导出用户数据, 请回退迁移, 然后, 出于某些原因, 在迁移后导入数据时, 统一联系人存储数据和联系人列表将损坏。</span><span class="sxs-lookup"><span data-stu-id="fafc8-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="fafc8-155">将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前, Exchange 管理员必须确保 Skype for Business 服务器管理员首先将 Skype for business Server 用户联系人从 Exchange 2013 回退到 Skype for Business企业服务器。</span><span class="sxs-lookup"><span data-stu-id="fafc8-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="fafc8-156">若要将统一联系人存储联系人回滚到 Skype for business 服务器, 请参阅本部分后面部分中的过程 "将统一联系人存储联系人从 Exchange 2013 回滚到 Skype for business 服务器"。</span><span class="sxs-lookup"><span data-stu-id="fafc8-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="fafc8-157">**如何回退用户联系人:** 如果您使用**move-csuser** Cmdlet 在 Skype For business server 2015 和 Lync Server 2010 之间移动用户, 则可以跳过这些步骤, 因为**move-csuser** cmdlet 会在用户从 Skype 移动用户时自动回退统一联系人存储企业服务器2015至 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="fafc8-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="fafc8-158">**Move-move-csuser**不会禁用统一联系人存储策略, 因此如果用户移回 Skype For business Server 2015, 则迁移到统一联系人存储将会重现。</span><span class="sxs-lookup"><span data-stu-id="fafc8-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

