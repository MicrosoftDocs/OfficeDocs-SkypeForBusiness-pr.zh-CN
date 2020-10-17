---
title: Lync Server 2013：回滚已迁移用户
description: Lync Server 2013：回滚已迁移的用户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5993bfd530c84307d3ee5be627b3ed33814be73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559538"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="e6b93-103">在 Lync Server 2013 中回滚已迁移的用户</span><span class="sxs-lookup"><span data-stu-id="e6b93-103">Roll back migrated users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b93-104">_**上次修改的主题：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="e6b93-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e6b93-105">如果需要回滚统一联系人存储功能，请仅在将用户移回 Exchange 2010 或 Lync Server 2010 时才回滚联系人。</span><span class="sxs-lookup"><span data-stu-id="e6b93-105">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e6b93-106">要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6b93-106">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e6b93-107">只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。</span><span class="sxs-lookup"><span data-stu-id="e6b93-107">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e6b93-108">例如，如果由于 Exchange 2013 回滚到 Exchange 2010 而回滚用户，然后将用户邮箱移动到 Exchange 2013，则在回滚之后的七天内将再次启动统一联系人存储迁移，只要用户服务策略中仍为用户启用统一联系人存储库，就会再次启动统一联系人存储迁移。</span><span class="sxs-lookup"><span data-stu-id="e6b93-108">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6b93-109">在下列情况下，Get-csuser cmdlet 会自动 <STRONG>将</STRONG> 用户的联系人存储从 Exchange 2013 回滚到 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="e6b93-109">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e6b93-110">将用户从 Lync Server 2013 移动到 Lync Server 2010 时。</span><span class="sxs-lookup"><span data-stu-id="e6b93-110">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6b93-111">当用户迁移到跨界时，例如，在本地将用户从 Lync Online 移到 Lync Server 2013 时，或者相反。</span><span class="sxs-lookup"><span data-stu-id="e6b93-111">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6b93-p102">如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：</span><span class="sxs-lookup"><span data-stu-id="e6b93-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e6b93-114">如果在将用户的联系人迁移到 Exchange 2013 之前导出联系人列表，然后在迁移后导入相同的数据，则统一联系人存储数据和联系人列表将损坏。</span><span class="sxs-lookup"><span data-stu-id="e6b93-114">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6b93-115">如果你在将用户迁移到 Exchange 2013 之后导出 userdata，请回滚迁移，然后，由于某些原因，在迁移后导入数据，统一联系人存储数据和联系人列表将损坏。</span><span class="sxs-lookup"><span data-stu-id="e6b93-115">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6b93-116">在将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保 Lync server 管理员首先将 Lync Server 用户联系人从 Exchange 2013 回滚到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e6b93-116">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="e6b93-117">若要将统一联系人存储联系人回滚到 Lync Server，请参阅本节后面的过程 "将统一联系人存储联系人从 Exchange 2013 回滚到 Lync Server 2013"。</span><span class="sxs-lookup"><span data-stu-id="e6b93-117">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="e6b93-118">以下过程介绍如何回滚用户联系人。</span><span class="sxs-lookup"><span data-stu-id="e6b93-118">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="e6b93-119">如果使用 **get-csuser** Cmdlet 在 lync server 2013 和 lync server 2010 之间移动用户，则可以跳过这些步骤，因为 **get-csuser** cmdlet 会在将用户从 Lync Server 2013 移动到 lync server 2010 时自动回退 unifed 联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="e6b93-119">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="e6b93-120">**Get-csuser** 不会禁用统一联系人存储策略，因此如果用户移回到 Lync Server 2013 中，则迁移到统一联系人存储将会重现。</span><span class="sxs-lookup"><span data-stu-id="e6b93-120">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="e6b93-121">将 Lync Server 2013 中的用户联系人回退到 Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e6b93-121">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="e6b93-122">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e6b93-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e6b93-p105">为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。（只有您想要确保用户将来不会迁移时，才执行此步骤。）要为单个用户禁用统一联系人存储，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6b93-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e6b93-125">例如：</span><span class="sxs-lookup"><span data-stu-id="e6b93-125">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e6b93-126">在将用户从 Lync Server 2013 移动到 Lync Server 2010 之前，请为 Lync Server 上的指定用户回滚好友列表。</span><span class="sxs-lookup"><span data-stu-id="e6b93-126">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e6b93-127">如果省略此步骤，则将丢失“好友列表”。</span><span class="sxs-lookup"><span data-stu-id="e6b93-127">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e6b93-p106">回滚指定用户。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6b93-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e6b93-130">例如：</span><span class="sxs-lookup"><span data-stu-id="e6b93-130">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e6b93-p107">建议不要使用 –Force 选项来强制回滚。如果使用此选项，则将会丢失用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="e6b93-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="e6b93-133">将统一联系人存储联系人从 Exchange 2013 回退到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b93-133">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="e6b93-134">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e6b93-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e6b93-p108">为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。要为单个用户禁用统一联系人存储，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6b93-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e6b93-137">例如：</span><span class="sxs-lookup"><span data-stu-id="e6b93-137">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e6b93-p109">回滚指定用户。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6b93-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e6b93-140">例如：</span><span class="sxs-lookup"><span data-stu-id="e6b93-140">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e6b93-141">必须先回滚 Lync Server 用户，然后再移动 Exchange 2013 邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6b93-141">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="e6b93-142">在 Lync Server 回滚完成之前，阻止 Exchange 管理员回滚 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e6b93-142">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="e6b93-143">建议不要使用 –Force 选项来强制回滚。</span><span class="sxs-lookup"><span data-stu-id="e6b93-143">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e6b93-144">如果使用此选项，则将会丢失用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="e6b93-144">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e6b93-145">将用户回滚到 Lync Server 后，Exchange 管理员可以将 exchange 用户从 Exchange 2013 回退到 Exchange 2010。</span><span class="sxs-lookup"><span data-stu-id="e6b93-145">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

