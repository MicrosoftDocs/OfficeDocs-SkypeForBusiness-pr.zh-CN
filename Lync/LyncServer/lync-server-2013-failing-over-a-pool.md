---
title: Lync Server 2013：对池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf54f1949627c39291388be248e0029077e9278
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530959"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中对池进行故障转移

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-10-10_

如果某个前端池发生故障并需要进行故障转移，请使用以下过程。在此过程中，Datacenter1 包含 Pool1，而 Pool1 发生了故障。此时，您可以故障转移至位于 Datacenter2 中的 Pool2。

大多数池故障转移的工作涉及到中央管理存储的故障转移（如果需要）。 这一点很重要，因为当池的用户进行故障转移时，中央管理存储必须正常工作。

此外，如果某一前端池发生了故障，但该站点中的边缘池仍在运行，则必须知道边缘池是否将发生故障的池用作下一个跃点池。如果是这样，必须在故障转移发生故障的前端池之前，将边缘池更改为使用其他前端池。更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。

**设置边缘池以使用同一站点中的下一个跃点池**

1.  打开拓扑生成器，右键单击需要更改的边缘池，然后单击 " **编辑属性**"。

2.  单击“下一个跃点”****。从“下一个跃点池:”**** 列表中，选择现在将用作下一个跃点池的池。

3.  单击“确定”****，然后发布更改。

**设置边缘池以使用不同站点中的下一个跃点池**

1.  打开 Lync Server 命令行管理程序窗口并键入以下 cmdlet：
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在发生灾难时对池进行故障转移**

1.  通过在 Pool2 中的前端服务器上键入以下 cmdlet 来查找哪个池是中央管理服务器的主机：
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 cmdlet 的结果显示当前承载中央管理服务器的池。 在此过程的其余部分，此池称为 CMS \_ 池。

2.  使用拓扑生成器查找 CMS 池上运行的 Lync Server 的版本 \_ 。 如果它运行的是 Lync Server 2013，请使用以下 cmdlet 查找池1的备份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    让备份 \_ 池成为备份池。

3.  使用以下 cmdlet 检查中央管理存储的状态：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 池的 FQDN \_ 。 如果它们是空的，则中央管理服务器不可用，您必须将其故障转移。

4.  如果中央管理存储不可用，或者中央管理存储在 Pool1 上运行 (即) 失败的池，则必须先对中央管理服务器进行故障转移，然后再对池进行故障转移。 如果需要对运行 Lync Server 2013 的池上承载的中央管理服务器进行故障转移，请使用此过程的步骤5中的 cmdlet。 如果需要对运行 Lync Server 2010 的池上承载的中央管理服务器进行故障转移，请使用此过程的步骤6中的 cmdlet。 如果不需要对中央管理服务器进行故障转移，请跳到此过程的步骤7。

5.  若要在运行 Lync Server 2013 的池中对中央管理存储进行故障转移，请执行以下操作：
    
      - 首先，通过键入以下命令，检查备份池中的哪个后端服务器 \_ 运行中央管理存储的主体实例：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果备份池中的主后端服务器 \_ 是主体，请键入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果 Backup Pool 中的镜像后端服务器 \_ 是主体，请键入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 验证中央管理服务器故障转移是否已完成。 键入以下命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份池的 FQDN \_ 。
    
      - 最后，通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否为 True。
        
        跳至此过程的第 7 步。

6.  在备份池的后端服务器上安装中央管理存储 \_ 。
    
      - 首先，运行以下命令：
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在备份池的前端服务器之一上运行下一个命令 \_ ，以强制移动中央管理存储：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 验证移动是否完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份池的 FQDN \_ 。
    
      - 通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否为 True。
    
      - 在备份池中的其余前端服务器上安装中央管理服务器服务 \_ 。 若要执行此操作，请在所有前端服务器上运行以下命令，但在此过程前面强制实施中央管理存储移动时使用的服务器除外：
        
            Bootstrapper /Setup 

7.  通过在 Lync Server 命令行管理程序窗口中运行以下 cmdlet，将用户从 Pool1 故障转移到 Pool2：
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    由于在此过程的前几部分中执行的检查中央管理存储状态的步骤并不是通用的，因此此 cmdlet 仍有机会失败，因为中央管理存储尚未完全故障转移。 在这种情况下，您必须根据您看到的错误消息来修复中央管理存储，然后再次运行此 cmdlet。
    
    如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。
    
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

