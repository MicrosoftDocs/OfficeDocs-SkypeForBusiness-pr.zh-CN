---
title: Lync Server 2013：对池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中对池进行故障转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-10-10_

如果单个前端池出现故障且需要故障转移, 请使用以下过程。 在此过程中, Datacenter1 包含 Pool1, 而 Pool1 失败。 您将在 Datacenter2 中故障转移到 Pool2。

对于池故障转移, 大部分工作都涉及到中央管理存储的故障 (如果需要)。 这一点很重要, 因为中央管理存储在池的用户故障转移时必须正常工作。

此外, 如果前端池出现故障, 但该站点上的边缘池仍在运行, 则必须知道 Edge 池是否将失败的池用作下一个跃点池。 如果是, 则必须将 Edge 池更改为使用不同的前端池, 然后再进行故障转移失败的前端池。 更改下一个跃点设置的方式取决于边缘是将同一站点上的池用作边缘池还是其他网站。

**将 "边缘池" 设置为在同一站点使用下一个跃点池**

1.  打开拓扑生成器, 右键单击需要更改的边缘池, 然后单击 "**编辑属性**"。

2.  单击 "**下一跃点**"。 从**下一个 "跃点池:** " 列表中, 选择现在将用作下一个跃点池的池。

3.  单击 **"确定**", 然后发布所做的更改。

**将边缘池设置为在其他网站上使用下一个跃点池**

1.  打开 Lync Server Management Shell 窗口, 键入以下 cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在灾难中故障转移池**

1.  通过在 Pool2 中的前端服务器上键入以下 cmdlet 来查找哪个池是中央管理服务器的主机:
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 cmdlet 的结果显示当前托管中央管理服务器的池。 在此过程的其余部分中, 此池称为 CMS\_池。

2.  使用拓扑生成器查找 CMS\_池中运行的 Lync Server 版本。 如果它运行的是 Lync Server 2013, 请使用以下 cmdlet 查找池1的备份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    让备份\_池成为备份池。

3.  通过以下 cmdlet 检查中央管理存储的状态:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。 如果它们为空, 则中央管理服务器不可用, 您必须将其故障转移。

4.  如果中央管理存储不可用, 或者中央管理存储在 Pool1 上运行 (即失败的池), 则必须先通过中央管理服务器进行故障转移, 然后才能故障转移池。 如果需要故障转移运行 Lync Server 2013 的池上托管的中央管理服务器, 请使用此过程步骤5中的 cmdlet。 如果需要故障转移运行 Lync Server 2010 的池上托管的中央管理服务器, 请使用此过程步骤6中的 cmdlet。 如果不需要故障转移中央管理服务器, 请跳到此过程的步骤7。

5.  若要在运行 Lync Server 2013 的池上故障转移中央管理存储, 请执行下列操作:
    
      - 首先, 检查备份\_池中的后端服务器通过键入以下内容来运行中央管理存储的主体实例:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果备份\_池中的主后端服务器是主体, 请键入:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果备份\_池中的镜像后端服务器是主体, 请键入:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 验证中央管理服务器故障转移是否已完成。 键入以下内容:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。
    
      - 最后, 通过键入以下内容检查所有前端服务器的副本状态:
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否均为 True。
        
        跳转到此过程中的步骤7。

6.  在备份\_池的后端服务器上安装中央管理存储。
    
      - 首先, 运行以下命令:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在备份\_池的前端服务器之一上运行下一个命令以强制移动中央管理存储:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 验证移动是否已完成:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。
    
      - 通过键入以下内容检查所有前端服务器的副本状态:
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否均为 True。
    
      - 在备份\_池中的其他前端服务器上安装中央管理服务器服务。 若要执行此操作, 请在所有前端服务器上运行以下命令, 除了在此过程前面强制执行中央管理存储移动时使用的所有服务器:
        
            Bootstrapper /Setup 

7.  通过在 Lync Server Management Shell 窗口中运行以下 cmdlet, 将用户从 Pool1 故障转移到 Pool2:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    由于本过程的前面部分中所执行的检查中央管理存储状态的步骤不是通用的, 因此此 cmdlet 仍会失败, 因为中央管理存储尚未完全故障转移。 在这种情况下, 你必须根据你看到的错误消息修复中央管理存储, 然后再次运行此 cmdlet。
    
    如果你看到以下错误消息, 则你需要更改此网站上的边缘池, 以便在对池进行故障转移之前使用其他池作为下一个跃点。 有关详细信息, 请参阅本主题开头的过程。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

