---
title: 迁移过程-详细信息
description: 迁移过程-详细信息。
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
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569578"
---
# <a name="migration-process---details"></a><span data-ttu-id="7de13-103">迁移过程-详细信息</span><span class="sxs-lookup"><span data-stu-id="7de13-103">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7de13-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7de13-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7de13-105">使用以下先决条件和详细步骤将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="7de13-105">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="7de13-106">迁移的先决条件</span><span class="sxs-lookup"><span data-stu-id="7de13-106">Prerequisites for Migration</span></span>

<span data-ttu-id="7de13-107">在将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器之前，请确保您已满足以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="7de13-107">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="7de13-108">至少部署一个 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="7de13-108">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="7de13-109">如果您有多个 Lync Server 2013 池，请确定哪个 Lync Server 2013 池将成为新 Lync Server 2013 持久聊天服务器池的主池。</span><span class="sxs-lookup"><span data-stu-id="7de13-109">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="7de13-110">安装 Lync Server 2013、持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="7de13-110">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="7de13-111">它将为空（没有类别、聊天室或外接程序）。</span><span class="sxs-lookup"><span data-stu-id="7de13-111">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="7de13-112">在迁移旧版类别、聊天室或外接程序之前，您可以在 Lync Server 2013 的持久聊天服务器部署中创建聊天室、类别或外接程序。</span><span class="sxs-lookup"><span data-stu-id="7de13-112">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7de13-p103">注意这些新创建的项可能与您迁移的旧项冲突。应避免任何命名冲突；否则，在迁移旧数据时将覆盖新创建的项。</span><span class="sxs-lookup"><span data-stu-id="7de13-p103">Be aware that these newly created items may conflict with legacy items that you migrate. Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="7de13-115">准备要迁移的源数据</span><span class="sxs-lookup"><span data-stu-id="7de13-115">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="7de13-116">执行以下步骤适当准备要迁移的源数据。</span><span class="sxs-lookup"><span data-stu-id="7de13-116">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="7de13-117">备份任何 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的源数据库。</span><span class="sxs-lookup"><span data-stu-id="7de13-117">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="7de13-118">有关备份 SQL Server 的详细信息，请参阅上的 "备份概述 (SQL Server) " <https://go.microsoft.com/fwlink/p/?linkid=254851> 。</span><span class="sxs-lookup"><span data-stu-id="7de13-118">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7de13-119">Active Directory 域服务应相同。</span><span class="sxs-lookup"><span data-stu-id="7de13-119">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="7de13-120">作为迁移的一个条件，您无法迁移到不同部署 (中的池（具体来说，在不同的 Active Directory 林中) 。</span><span class="sxs-lookup"><span data-stu-id="7de13-120">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="7de13-121">检查你的 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天聊天室和类别配置。</span><span class="sxs-lookup"><span data-stu-id="7de13-121">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="7de13-122">对现有旧部署中的类别、聊天室或外接程序所做的任何更改都将通过 "组聊天管理工具" 完成。</span><span class="sxs-lookup"><span data-stu-id="7de13-122">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7de13-123">Lync server 2013 中对类别、会议室或外接程序进行的任何更改都是由 Lync Server 控制面板或 Windows PowerShell cmdlet 执行的。</span><span class="sxs-lookup"><span data-stu-id="7de13-123">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="7de13-124">按照以下步骤准备要迁移的旧系统。</span><span class="sxs-lookup"><span data-stu-id="7de13-124">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="7de13-125">持久聊天服务器支持单个级别的类别，不同类别的深度分层集。</span><span class="sxs-lookup"><span data-stu-id="7de13-125">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="7de13-126">迁移后，子类别将带有完整父类别名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="7de13-126">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="7de13-127">您最好简化并平整现有类别结构，以便生成的结构满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="7de13-127">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="7de13-p108">验证根类别是否存在**管理员**。如果此级别存在管理员，则这些用户在迁移后将被添加为**所有聊天室的管理员**。如果这不是组织的要求，则需要从根类别中删除这些管理员。</span><span class="sxs-lookup"><span data-stu-id="7de13-p108">Verify the **Managers** at the root Category. If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration. If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="7de13-p109">验证聊天室名称的长度。迁移后，由于类别结构简化，如果某个子类别下存在聊天室，这些聊天室将带有完整父类别名称的前缀。命名限制为 256 个字符，其中包括父类别名称。您必须验证聊天室名称的长度，并可在名称过长时缩短其长度。</span><span class="sxs-lookup"><span data-stu-id="7de13-p109">Verify the length of room names. After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names. The naming limit is 256 characters, including parent category names. You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="7de13-135">在 Lync Server 2013 中，如果将 "类别 **邀请** 设置" 设置为 "true"，则可以选择 "真" 或 "假" 来邀请到该类别下的会议室。</span><span class="sxs-lookup"><span data-stu-id="7de13-135">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="7de13-136">但是如果类别邀请设置为 false，则该类别下的聊天室将关闭邀请。</span><span class="sxs-lookup"><span data-stu-id="7de13-136">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="7de13-137">在迁移之前，如果想要 (s) 在特定类别中存在，则必须重置旧版 Lync Server 组聊天服务器版本中的邀请设置。</span><span class="sxs-lookup"><span data-stu-id="7de13-137">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="7de13-138">否则，在迁移过程中，Lync Server 2013 将显示警告，并将聊天室设置为默认值 false。</span><span class="sxs-lookup"><span data-stu-id="7de13-138">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="7de13-139">如果在聊天室中使用了文件，则必须在迁移后将文件手动以 XCOPY 的的的新持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="7de13-139">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="7de13-140">工具不会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7de13-140">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="7de13-141">如果你有联合用户和带联合用户的聊天室，请注意持久聊天服务器不支持联合。</span><span class="sxs-lookup"><span data-stu-id="7de13-141">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="7de13-142">带联盟用户的聊天室将被迁移，但用户自己无法访问内容，因为联盟访问不受支持。</span><span class="sxs-lookup"><span data-stu-id="7de13-142">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="7de13-143">标识不想迁移的聊天室，并将它们标记为禁用。</span><span class="sxs-lookup"><span data-stu-id="7de13-143">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="7de13-p113">标识您不想迁移的聊天室内容的截至日期。例如，您可能不想迁移 2010 年 1 月 1 日以前的消息，因为这些消息可能已作废或与迁移不相关。</span><span class="sxs-lookup"><span data-stu-id="7de13-p113">Identify the date beyond which you want to migrate the chat room content. For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="7de13-146">执行迁移</span><span class="sxs-lookup"><span data-stu-id="7de13-146">Performing the Migration</span></span>

<span data-ttu-id="7de13-147">执行以下步骤以迁移旧版组聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="7de13-147">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="7de13-148">关闭 Lync Server 2010、组聊天、Office 通信服务器 2007 R2 组聊天或 Lync Server 2013、持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="7de13-148">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="7de13-149">必须停止所有服务，以便有足够的停机时间一次完成此操作。</span><span class="sxs-lookup"><span data-stu-id="7de13-149">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="7de13-150">如上文所述，请务必备份当前的组聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="7de13-150">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="7de13-151">以持久聊天管理员 RBAC 角色的成员身份运行 Windows PowerShell **export-cspersistentchatdata** Cmdlet (CsPersistentChatAdministrator) 。</span><span class="sxs-lookup"><span data-stu-id="7de13-151">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="7de13-152">有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="7de13-152">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="7de13-153">检查导出的内容。</span><span class="sxs-lookup"><span data-stu-id="7de13-153">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="7de13-154">准备好导入之前，请关闭 Lync Server 2013、持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="7de13-154">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="7de13-155">需要停止所有服务，以便有足够的停机时间一次完成此操作。</span><span class="sxs-lookup"><span data-stu-id="7de13-155">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="7de13-156">如果您在迁移之前在 Lync Server 2013 部署中创建了任何类别、聊天室或外接程序，请执行持久聊天数据库的备份。</span><span class="sxs-lookup"><span data-stu-id="7de13-156">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="7de13-157">导出/导入过程将能够将旧数据合并到 Lync Server 2013 部署中，但您需要备份数据库，以防无意中覆盖了内容 (例如，如果仍存在命名冲突) 。</span><span class="sxs-lookup"><span data-stu-id="7de13-157">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="7de13-158">运行 Windows PowerShell **export-cspersistentchatdata** cmdlet (导入工具) ，使用 **WhatIf** 命令将持久聊天服务器池的后端服务器填充到迁移的数据。</span><span class="sxs-lookup"><span data-stu-id="7de13-158">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="7de13-159">过程中会进行一些转换以适应简化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="7de13-159">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="7de13-160">修复出现的任何错误或警告。</span><span class="sxs-lookup"><span data-stu-id="7de13-160">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="7de13-161">将持久聊天服务器 Windows PowerShell **export-cspersistentchatdata** Cmdlet 作为持久聊天管理员 RBAC 角色的成员运行， (CsPersistentChatAdministrator) 。</span><span class="sxs-lookup"><span data-stu-id="7de13-161">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="7de13-162">有关导出/导入 cmdlet 的详细信息，请参阅 [在 Lync server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="7de13-162">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="7de13-163">您必须将所有已上载的文件 (整个文件夹中) 到新的 Lync Server 2013、持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="7de13-163">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7de13-164">Lync 2013 (客户端) 不支持在聊天室中上载或查看文件。</span><span class="sxs-lookup"><span data-stu-id="7de13-164">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="7de13-165">您仍可以使用旧客户端在聊天室中发布和查看文件。</span><span class="sxs-lookup"><span data-stu-id="7de13-165">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="7de13-166">将 Lync Server 2010、Group Chat 或 Office 通信服务器 2007 R2 组聊天查找服务器 URI 移植到 Lync Server 2013、持久聊天服务器联系人对象。</span><span class="sxs-lookup"><span data-stu-id="7de13-166">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="7de13-167">如果你的 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天客户端需要连接到最新 Lync 2013、持久聊天 (客户端) 在不进行任何客户端配置更改的情况下进行迁移，则需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7de13-167">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="7de13-168">删除 ocschat@ 的 " \<domainName\> Com 查找" 服务器用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7de13-168">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="7de13-169">这用于指向 Lync Server 2010 中的 "组聊天" 中的查找服务。</span><span class="sxs-lookup"><span data-stu-id="7de13-169">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="7de13-170">可以在以后卸载池并删除受信任条目。</span><span class="sxs-lookup"><span data-stu-id="7de13-170">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="7de13-171">通过运行 Windows PowerShell cmdlet **CsPersistentChatEndpoint**持久聊天服务器 contact 对象) ，使用相同的 SIP URI 创建旧终结 (点，以便在重新启动该服务时，旧客户端将有效工作。</span><span class="sxs-lookup"><span data-stu-id="7de13-171">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="7de13-172">必需的迁移过程此时完成。</span><span class="sxs-lookup"><span data-stu-id="7de13-172">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="7de13-173">Lync 2010 Group Chat (客户端) 或 Office Communicator 2007 R2 组聊天 (客户端) 现在可以透明地连接到新的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="7de13-173">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="7de13-174">按照 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天的这些额外的解除授权步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="7de13-174">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="7de13-175">通过打开新持久聊天服务器池中的所有计算机来启动持久聊天服务器服务。</span><span class="sxs-lookup"><span data-stu-id="7de13-175">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="7de13-176">使用 Lync Server 控制面板和 Windows PowerShell cmdlet 验证数据是否已成功迁移。</span><span class="sxs-lookup"><span data-stu-id="7de13-176">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="7de13-177">从组聊天服务器池中的计算机卸载 Lync 2010 组聊天或 Office Communicator 2007 R2 组聊天。</span><span class="sxs-lookup"><span data-stu-id="7de13-177">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="7de13-178">使用 Windows PowerShell cmdlet 删除受信任的应用程序和受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="7de13-178">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7de13-179">此命令将从中央管理存储和关联的受信任的服务条目中删除这些项目， (TSEs) 从 Active Directory 中删除。</span><span class="sxs-lookup"><span data-stu-id="7de13-179">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="7de13-180">或者，此步骤可通过使用拓扑生成器 (受信任的应用程序/池具有一个专用节点，也) 。</span><span class="sxs-lookup"><span data-stu-id="7de13-180">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="7de13-181">你现在可以开始通过新客户端启用持久聊天服务器功能。</span><span class="sxs-lookup"><span data-stu-id="7de13-181">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="7de13-182">有关启用持久聊天服务器的详细信息，请参阅 [在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7de13-182">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7de13-183">Lync Server 2013 支持多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="7de13-183">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="7de13-184">但是，我们支持将 Lync 2010 组聊天或 Office 通信服务器 2007 R2 &nbsp; 组聊天池迁移到单个 Lync server 2013、持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="7de13-184">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="7de13-185">您可以在部署中添加其他新的持久聊天服务器池以满足法规需求 (例如，将数据保留在给定的地理位置) 中。</span><span class="sxs-lookup"><span data-stu-id="7de13-185">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

