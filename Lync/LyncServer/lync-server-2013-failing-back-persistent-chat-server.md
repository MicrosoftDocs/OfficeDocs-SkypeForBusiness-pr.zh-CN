---
title: Lync Server 2013：对持久聊天服务器进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ef904-102">在 Lync Server 2013 中对持久聊天服务器进行故障回复</span><span class="sxs-lookup"><span data-stu-id="ef904-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef904-103">_**主题上次修改时间:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ef904-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ef904-104">此过程概述了从持久聊天服务器故障中恢复所需的步骤, 以及从主数据中心重新建立操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="ef904-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="ef904-105">在持久聊天服务器出现故障期间, 主数据中心将受到完全中断, 并且主数据库和镜像数据库将变得不可用。</span><span class="sxs-lookup"><span data-stu-id="ef904-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="ef904-106">主数据中心将故障转移到备份服务器。</span><span class="sxs-lookup"><span data-stu-id="ef904-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="ef904-107">以下过程在备份主数据中心并重新生成服务器后还原正常操作。</span><span class="sxs-lookup"><span data-stu-id="ef904-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="ef904-108">该过程假设主数据中心已从整体中断恢复, 并且已使用拓扑生成器重新生成并重新安装了 mgc 数据库和 mgccomp 数据库。</span><span class="sxs-lookup"><span data-stu-id="ef904-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="ef904-109">该过程还假定在故障转移期间未部署任何新镜像和备份服务器, 并且部署的唯一服务器是备份服务器及其镜像服务器, 如在[Lync server 2013 中通过永久聊天服务器进行了故障转移](lync-server-2013-failing-over-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ef904-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="ef904-110">这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。</span><span class="sxs-lookup"><span data-stu-id="ef904-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="ef904-111">故障恢复持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ef904-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="ef904-112">使用 Lync Server 命令行管理程序中的`Set-CsPersistentChatActiveServer` Cmdlet 从持久聊天服务器活动服务器列表中清除所有服务器。</span><span class="sxs-lookup"><span data-stu-id="ef904-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="ef904-113">这将阻止所有持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。</span><span class="sxs-lookup"><span data-stu-id="ef904-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef904-114">辅助持久聊天服务器上的 SQL Server 代理应在特权帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="ef904-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="ef904-115">尤其需要指出的是，该帐户必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="ef904-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="ef904-116">对于放置备份的网络共享的读取权限。</span><span class="sxs-lookup"><span data-stu-id="ef904-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ef904-117">对于备份将复制到的特定本地目录的写入权限。</span><span class="sxs-lookup"><span data-stu-id="ef904-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="ef904-118">在备份 mgc 数据库上禁用镜像：</span><span class="sxs-lookup"><span data-stu-id="ef904-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="ef904-119">使用 SQL Server Management Studio 连接到 backup mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="ef904-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="ef904-120">右键单击 mgc 数据库，指向“**任务**”，然后单击“**镜像**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="ef904-121">单击“**取消镜像**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="ef904-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="ef904-123">对 mgccomp 数据库执行相同步骤。</span><span class="sxs-lookup"><span data-stu-id="ef904-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="ef904-124">备份 mgc 数据库，使其可以还原为新主数据库：</span><span class="sxs-lookup"><span data-stu-id="ef904-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="ef904-125">使用 SQL Server Management Studio 连接到 backup mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="ef904-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="ef904-p105">右键单击 mgc 数据库，指向“**任务**”，然后单击“**备份**”。随即将显示“**备份数据库**”对话框。</span><span class="sxs-lookup"><span data-stu-id="ef904-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="ef904-128">在“**备份类型**”中，选择“**完全**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="ef904-129">对于“**备份组件**”，请单击“**数据库**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="ef904-130">接受“**名称**”中建议的默认备份集名称，或为备份集输入不同名称。</span><span class="sxs-lookup"><span data-stu-id="ef904-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="ef904-131">\* \<可选\> \*在 "**说明**" 中, 输入备份集的描述。</span><span class="sxs-lookup"><span data-stu-id="ef904-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="ef904-132">从目标列表中删除默认备份位置。</span><span class="sxs-lookup"><span data-stu-id="ef904-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="ef904-p106">使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。</span><span class="sxs-lookup"><span data-stu-id="ef904-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="ef904-135">单击“**确定**”关闭对话框并开始备份过程。</span><span class="sxs-lookup"><span data-stu-id="ef904-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="ef904-136">使用上一步中创建的备份数据库还原主数据库。</span><span class="sxs-lookup"><span data-stu-id="ef904-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="ef904-137">使用 SQL Server Management Studio 连接到主 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="ef904-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="ef904-p107">右键单击 mgc 数据库，指向“**任务**”，指向“**还原**”，然后单击“**数据库**”。随即会显示“**还原数据库**”对话框。</span><span class="sxs-lookup"><span data-stu-id="ef904-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="ef904-140">选择“**自设备**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="ef904-p108">单击浏览按钮，将打开“**指定备份**”对话框。在“**备份媒体**”中，选择“**文件**”。单击“**添加**”，选择您在步骤 3 中创建的备份文件，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="ef904-144">在“**选择用于还原的备份集**”中，选择备份。</span><span class="sxs-lookup"><span data-stu-id="ef904-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="ef904-145">在“**选择页**”窗格中单击“**选项**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="ef904-146">在“**还原选项**”中，选择“**覆盖现有数据库**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="ef904-147">在“**恢复状态**”中，选择“**使数据库处于可以使用的状态**”。</span><span class="sxs-lookup"><span data-stu-id="ef904-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="ef904-148">单击“**确定**”开始还原过程。</span><span class="sxs-lookup"><span data-stu-id="ef904-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="ef904-149">为主数据库配置 SQL Server 日志传送。</span><span class="sxs-lookup"><span data-stu-id="ef904-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="ef904-150">按照在[Lync server 2013 中配置持久聊天服务器以获得高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)的过程, 为主 mgc 数据库建立日志传送。</span><span class="sxs-lookup"><span data-stu-id="ef904-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="ef904-151">设置持久聊天服务器活动服务器。</span><span class="sxs-lookup"><span data-stu-id="ef904-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ef904-152">从 Lync Server 命令行管理程序中, 使用**CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="ef904-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef904-153">所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="ef904-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="ef904-154">将池还原到其正常状态时, 请运行以下 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="ef904-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="ef904-155">有关详细信息, 请参阅[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="ef904-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

