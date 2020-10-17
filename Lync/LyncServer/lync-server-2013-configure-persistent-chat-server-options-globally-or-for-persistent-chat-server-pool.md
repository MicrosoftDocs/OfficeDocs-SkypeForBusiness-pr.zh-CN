---
title: Lync Server 2013：全局或永久聊天服务器池配置持久聊天服务器选项
description: Lync Server 2013：全局或永久聊天服务器池配置持久聊天服务器选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564988"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="7a9c8-103">在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="7a9c8-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a9c8-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7a9c8-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7a9c8-105">在 "Lync Server 2013 控制面板" 中，可以使用 **"持久聊天" 页的**"持久**聊天配置**" 部分在应用于所有持久聊天服务器池或特定持久聊天服务器池的持续性聊天设置的全局位置对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-105">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9c8-106">若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="7a9c8-107">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="7a9c8-108">全局配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="7a9c8-108">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="7a9c8-109">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-109">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a9c8-110">从 " **开始** " 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-110">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7a9c8-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-111">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a9c8-112">您还可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-112">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7a9c8-113">有关详细信息，请参阅部署文档中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A> 。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-113">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7a9c8-114">在左侧导航栏中，单击“持久聊天”\*\*\*\*，然后单击“持久聊天配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="7a9c8-115">在 " **持久聊天配置** " 页上，单击 " **新建"，** 然后单击 " **站点配置**"。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-115">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a9c8-116">如果要将配置应用于部署在站点中的所有持久聊天服务器池，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-116">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="7a9c8-117">如果要将配置应用于特定的持久聊天服务器池，请单击 " <STRONG>池配置</STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-117">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="7a9c8-118">在 " **选择站点**" 中，选择要为持久聊天服务器站点配置配置的站点。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-118">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="7a9c8-119">在“新建持久聊天配置”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7a9c8-119">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="7a9c8-p105">在“名称”\*\*\*\* 中，指定新配置设置的名称。默认状态下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="7a9c8-p106">在“默认聊天历史记录”\*\*\*\* 中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a9c8-125">持久聊天服务器将在内存中缓存这些邮件，因此如果增加此数字，将缓存更多的邮件。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-125">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="7a9c8-126">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-126">You can always access historical content by search.</span></span> <span data-ttu-id="7a9c8-127">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-127">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a9c8-p108">在“最大文件大小(KB)”\*\*\*\* 中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”\*\*\*\* 设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a9c8-131">在服务器上强制实施此设置，因为自定义应用程序或以前的 Group Chat 客户端使用 Office 通信服务器 2007 R2 &nbsp; 组聊天服务器或 Lync server 2010，组聊天可以将文件发布到聊天室。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-131">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="7a9c8-132">Lync 2013 客户端不具有文件上传/下载功能，因此，如果您拥有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a9c8-133">在“参与者更新限制”\*\*\*\* 中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-133">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="7a9c8-134">持久聊天服务器将名单信息 (连接到聊天室) 到所有参与者，直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-134">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="7a9c8-135">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-135">By default, the number is 75.</span></span> <span data-ttu-id="7a9c8-136">此限制指示在给定会议室中的参与者的最大数量，超过该数量后，持续聊天服务器将停止向连接的客户端发送有关会议室中存在的人员名单更新。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-136">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="7a9c8-p111">（可选）在“聊天室管理 URL”\*\*\*\* 中，选择聊天室管理 URL。这是基于 Web 的自定义聊天室管理的 URL。如果您不需要自定义聊天室管理，并且只使用默认设置，则将此选项留空。该 URL 设置后，它将被用作内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="7a9c8-141">如果要自定义会议室创建体验并包含特定的业务工作流，则可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，将其承载到某处，并将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-141">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="7a9c8-142">此 URL 将被发送给客户端，以便用户尝试查看/创建聊天室时将被指引到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-142">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="7a9c8-143">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="7a9c8-144">为特定的持久聊天服务器池配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="7a9c8-144">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="7a9c8-145">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-145">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a9c8-146">从 " **开始** " 菜单中选择 "Lync Server 控制面板"，或打开一个浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-146">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7a9c8-147">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a9c8-148">您还可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-148">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7a9c8-149">有关详细信息，请参阅部署文档中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A> 。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-149">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7a9c8-150">在左侧导航栏中，单击“持久聊天”\*\*\*\*，然后单击“持久聊天配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-150">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="7a9c8-151">在“持久聊天配置”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后单击“池配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-151">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="7a9c8-152">在 " **选择服务**" 中，选择与要配置的持久聊天服务器池相关联的服务。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-152">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="7a9c8-153">在“新建持久聊天配置”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7a9c8-153">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="7a9c8-p115">在“名称”\*\*\*\* 中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="7a9c8-p116">在“默认聊天历史记录”\*\*\*\* 中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a9c8-159">持久聊天服务器将在内存中缓存这些邮件，因此如果增加此数字，将缓存更多的邮件。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-159">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="7a9c8-160">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-160">You can always access historical content by search.</span></span> <span data-ttu-id="7a9c8-161">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-161">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a9c8-p118">在“最大文件大小(KB)”\*\*\*\* 中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”\*\*\*\* 设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a9c8-165">由于自定义应用程序或以前的组聊天客户端 (Office 通信服务器 2007 R2 &nbsp; 组聊天服务器或 Lync server 2010，组聊天) 可以将文件发布到聊天室，因此在服务器上强制实施此设置。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-165">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="7a9c8-166">Lync 2013 客户端不具有文件上传/下载功能，因此，如果您拥有纯 Lync 2013 部署或 Lync 2013 客户端，则无法在持久聊天服务器聊天室中发布文件。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-166">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a9c8-167">在“参与者更新限制”\*\*\*\* 中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-167">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="7a9c8-168">持久聊天服务器将名单信息 (连接到聊天室) 到所有参与者，直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-168">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="7a9c8-169">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-169">By default, the number is 75.</span></span> <span data-ttu-id="7a9c8-170">此限制指示在给定会议室中的参与者的最大数量，超过该数量后，持续聊天服务器将停止向连接的客户端发送有关会议室中存在的人员名单更新。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-170">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="7a9c8-p121">在“聊天室管理 URL”\*\*\*\* 中，选择聊天室管理 URL。这是基于 Web 的聊天室管理部署的 URL。如果不需要自定义聊天室管理并且只想使用默认设置，请将此选项留空。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="7a9c8-174">如果要自定义会议室创建体验并包含特定的业务工作流，则可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，将其承载到某处，并将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-174">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="7a9c8-175">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-175">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="7a9c8-176">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a9c8-176">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

