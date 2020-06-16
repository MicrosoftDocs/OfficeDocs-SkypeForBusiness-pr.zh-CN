---
title: 迁移过程-详细信息
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="cfeae-102">迁移过程-详细信息</span><span class="sxs-lookup"><span data-stu-id="cfeae-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfeae-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cfeae-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cfeae-104">使用以下先决条件和详细步骤将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="cfeae-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="cfeae-105">迁移的先决条件</span><span class="sxs-lookup"><span data-stu-id="cfeae-105">Prerequisites for Migration</span></span>

<span data-ttu-id="cfeae-106">在将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器之前，请确保您已满足以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="cfeae-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="cfeae-107">至少部署一个 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="cfeae-108">如果您有多个 Lync Server 2013 池，请确定哪个 Lync Server 2013 池将成为新 Lync Server 2013 持久聊天服务器池的主池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="cfeae-109">安装 Lync Server 2013、持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="cfeae-110">它将为空（没有类别、聊天室或外接程序）。</span><span class="sxs-lookup"><span data-stu-id="cfeae-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="cfeae-111">在迁移旧版类别、聊天室或外接程序之前，您可以在 Lync Server 2013 的持久聊天服务器部署中创建聊天室、类别或外接程序。</span><span class="sxs-lookup"><span data-stu-id="cfeae-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cfeae-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span><span class="sxs-lookup"><span data-stu-id="cfeae-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="cfeae-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span><span class="sxs-lookup"><span data-stu-id="cfeae-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="cfeae-114">准备要迁移的源数据</span><span class="sxs-lookup"><span data-stu-id="cfeae-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="cfeae-115">执行以下步骤适当准备要迁移的源数据。</span><span class="sxs-lookup"><span data-stu-id="cfeae-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="cfeae-116">备份任何 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的源数据库。</span><span class="sxs-lookup"><span data-stu-id="cfeae-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="cfeae-117">有关备份 SQL Server 的详细信息，请参阅处的 "备份概述（SQL Server）" <https://go.microsoft.com/fwlink/p/?linkid=254851> 。</span><span class="sxs-lookup"><span data-stu-id="cfeae-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cfeae-118">Active Directory 域服务应相同。</span><span class="sxs-lookup"><span data-stu-id="cfeae-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="cfeae-119">作为迁移的一个条件，不能迁移到不同部署中的池（尤其是在不同的 Active Directory 林中）。</span><span class="sxs-lookup"><span data-stu-id="cfeae-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="cfeae-120">检查你的 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天聊天室和类别配置。</span><span class="sxs-lookup"><span data-stu-id="cfeae-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="cfeae-121">对现有旧部署中的类别、聊天室或外接程序所做的任何更改都将通过 "组聊天管理工具" 完成。</span><span class="sxs-lookup"><span data-stu-id="cfeae-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="cfeae-122">Lync server 2013 中对类别、会议室或外接程序进行的任何更改都是由 Lync Server 控制面板或 Windows PowerShell cmdlet 执行的。</span><span class="sxs-lookup"><span data-stu-id="cfeae-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="cfeae-123">按照以下步骤准备要迁移的旧系统。</span><span class="sxs-lookup"><span data-stu-id="cfeae-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="cfeae-124">持久聊天服务器支持单个级别的类别，不同类别的深度分层集。</span><span class="sxs-lookup"><span data-stu-id="cfeae-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="cfeae-125">迁移后，子类别将带有完整父类别名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="cfeae-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="cfeae-126">您最好简化并平整现有类别结构，以便生成的结构满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="cfeae-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="cfeae-127">Verify the **Managers** at the root Category.</span><span class="sxs-lookup"><span data-stu-id="cfeae-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="cfeae-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span><span class="sxs-lookup"><span data-stu-id="cfeae-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="cfeae-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span><span class="sxs-lookup"><span data-stu-id="cfeae-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="cfeae-130">Verify the length of room names.</span><span class="sxs-lookup"><span data-stu-id="cfeae-130">Verify the length of room names.</span></span> <span data-ttu-id="cfeae-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span><span class="sxs-lookup"><span data-stu-id="cfeae-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="cfeae-132">The naming limit is 256 characters, including parent category names.</span><span class="sxs-lookup"><span data-stu-id="cfeae-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="cfeae-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span><span class="sxs-lookup"><span data-stu-id="cfeae-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="cfeae-134">在 Lync Server 2013 中，如果将 "类别**邀请**设置" 设置为 "true"，则可以选择 "真" 或 "假" 来邀请到该类别下的会议室。</span><span class="sxs-lookup"><span data-stu-id="cfeae-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="cfeae-135">但是如果类别邀请设置为 false，则该类别下的聊天室将关闭邀请。</span><span class="sxs-lookup"><span data-stu-id="cfeae-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="cfeae-136">在迁移之前，如果您希望会议室在特定类别下存在，则必须重置旧版 Lync Server 组聊天服务器版本中的邀请设置。</span><span class="sxs-lookup"><span data-stu-id="cfeae-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="cfeae-137">否则，在迁移过程中，Lync Server 2013 将显示警告，并将聊天室设置为默认值 false。</span><span class="sxs-lookup"><span data-stu-id="cfeae-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="cfeae-138">如果在聊天室中使用了文件，则必须在迁移后将文件手动以 XCOPY 的的的新持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="cfeae-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="cfeae-139">工具不会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cfeae-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="cfeae-140">如果你有联合用户和带联合用户的聊天室，请注意持久聊天服务器不支持联合。</span><span class="sxs-lookup"><span data-stu-id="cfeae-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="cfeae-141">带联盟用户的聊天室将被迁移，但用户自己无法访问内容，因为联盟访问不受支持。</span><span class="sxs-lookup"><span data-stu-id="cfeae-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="cfeae-142">标识不想迁移的聊天室，并将它们标记为禁用。</span><span class="sxs-lookup"><span data-stu-id="cfeae-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="cfeae-143">Identify the date beyond which you want to migrate the chat room content.</span><span class="sxs-lookup"><span data-stu-id="cfeae-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="cfeae-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span><span class="sxs-lookup"><span data-stu-id="cfeae-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="cfeae-145">执行迁移</span><span class="sxs-lookup"><span data-stu-id="cfeae-145">Performing the Migration</span></span>

<span data-ttu-id="cfeae-146">执行以下步骤以迁移旧版组聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="cfeae-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="cfeae-147">关闭 Lync Server 2010、组聊天、Office 通信服务器 2007 R2 组聊天或 Lync Server 2013、持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="cfeae-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="cfeae-148">必须停止所有服务，以便有足够的停机时间一次完成此操作。</span><span class="sxs-lookup"><span data-stu-id="cfeae-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="cfeae-149">如上文所述，请务必备份当前的组聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="cfeae-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="cfeae-150">以持久聊天管理员 RBAC 角色（CsPersistentChatAdministrator）的成员身份运行 Windows PowerShell **export-cspersistentchatdata** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfeae-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="cfeae-151">有关导出/导入 cmdlet 的详细信息，请参阅[在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="cfeae-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="cfeae-152">检查导出的内容。</span><span class="sxs-lookup"><span data-stu-id="cfeae-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="cfeae-153">准备好导入之前，请关闭 Lync Server 2013、持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="cfeae-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="cfeae-154">需要停止所有服务，以便有足够的停机时间一次完成此操作。</span><span class="sxs-lookup"><span data-stu-id="cfeae-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="cfeae-155">如果您在迁移之前在 Lync Server 2013 部署中创建了任何类别、聊天室或外接程序，请执行持久聊天数据库的备份。</span><span class="sxs-lookup"><span data-stu-id="cfeae-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="cfeae-156">导出/导入过程将能够将旧数据合并到 Lync Server 2013 部署中，但如果不小心覆盖了该数据库（例如，如果仍存在命名冲突），则需要对该数据库进行备份。</span><span class="sxs-lookup"><span data-stu-id="cfeae-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="cfeae-157">运行 Windows PowerShell **export-cspersistentchatdata** cmdlet （导入工具），并使用**WhatIf**命令，使用迁移的数据填充持久聊天服务器池的后端服务器。</span><span class="sxs-lookup"><span data-stu-id="cfeae-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="cfeae-158">过程中会进行一些转换以适应简化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="cfeae-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="cfeae-159">修复出现的任何错误或警告。</span><span class="sxs-lookup"><span data-stu-id="cfeae-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="cfeae-160">以持久聊天管理员 RBAC 角色（CsPersistentChatAdministrator）的成员身份运行持久聊天服务器 Windows PowerShell **export-cspersistentchatdata** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfeae-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="cfeae-161">有关导出/导入 cmdlet 的详细信息，请参阅[在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="cfeae-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="cfeae-162">您必须将所有上载的文件（整个文件夹） XCOPY 为新的 Lync Server 2013、持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="cfeae-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cfeae-163">Lync 2013 （客户端）不支持上传或查看聊天室中的文件。</span><span class="sxs-lookup"><span data-stu-id="cfeae-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="cfeae-164">您仍可以使用旧客户端在聊天室中发布和查看文件。</span><span class="sxs-lookup"><span data-stu-id="cfeae-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="cfeae-165">将 Lync Server 2010、Group Chat 或 Office 通信服务器 2007 R2 组聊天查找服务器 URI 移植到 Lync Server 2013、持久聊天服务器联系人对象。</span><span class="sxs-lookup"><span data-stu-id="cfeae-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="cfeae-166">如果你的 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天客户端需要在不进行任何客户端配置更改的情况下连接到最新 Lync 2013、持久聊天（客户端），则需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cfeae-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="cfeae-167">删除 ocschat@ 的 " \<domainName\> Com 查找" 服务器用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cfeae-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="cfeae-168">这用于指向 Lync Server 2010 中的 "组聊天" 中的查找服务。</span><span class="sxs-lookup"><span data-stu-id="cfeae-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="cfeae-169">可以在以后卸载池并删除受信任条目。</span><span class="sxs-lookup"><span data-stu-id="cfeae-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="cfeae-170">通过运行具有相同 SIP URI 的 Windows PowerShell cmdlet **CsPersistentChatEndpoint**，创建旧终结点（持久聊天服务器 contact 对象），以便在重新启动服务时，旧客户端将有效工作。</span><span class="sxs-lookup"><span data-stu-id="cfeae-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="cfeae-171">必需的迁移过程此时完成。</span><span class="sxs-lookup"><span data-stu-id="cfeae-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="cfeae-172">Lync 2010 组聊天（客户端）或 Office Communicator 2007 R2 R2 组聊天（客户端）现在可以透明地连接到新的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="cfeae-173">按照 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的这些额外的解除授权步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="cfeae-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="cfeae-174">通过打开新持久聊天服务器池中的所有计算机来启动持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="cfeae-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="cfeae-175">使用 Lync Server 控制面板和 Windows PowerShell cmdlet 验证数据是否已成功迁移。</span><span class="sxs-lookup"><span data-stu-id="cfeae-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="cfeae-176">从组聊天服务器池中的计算机卸载 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天。</span><span class="sxs-lookup"><span data-stu-id="cfeae-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="cfeae-177">使用 Windows PowerShell cmdlet 删除受信任的应用程序和受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cfeae-178">此命令将从中央管理存储和 Active Directory 中的关联的受信任服务条目（TSEs）中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="cfeae-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="cfeae-179">或者，此步骤通过使用拓扑生成器（也有一个专用的节点）运行。</span><span class="sxs-lookup"><span data-stu-id="cfeae-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="cfeae-180">你现在可以开始通过新客户端启用持久聊天服务器功能。</span><span class="sxs-lookup"><span data-stu-id="cfeae-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="cfeae-181">有关启用持久聊天服务器的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cfeae-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cfeae-182">Lync Server 2013 支持多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="cfeae-183">但是，我们支持将 Lync 2010 组聊天或 Office 通信服务器 2007 R2 &nbsp; 组聊天池迁移到单个 Lync server 2013、持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="cfeae-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="cfeae-184">您可以在部署中添加其他新的持久聊天服务器池以满足法规需求（例如，在给定地理位置保留数据）。</span><span class="sxs-lookup"><span data-stu-id="cfeae-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

