---
title: Lync Server 2013：对池进行故障转移
TOCTitle: 对池进行故障转移
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204678(v=OCS.15)
ms:contentKeyID: 49312031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对池进行故障转移

 

_**上一次修改主题：** 2014-10-10_

如果某个前端池发生故障并需要进行故障转移，请使用以下过程。在此过程中，Datacenter1 包含 Pool1，而 Pool1 发生了故障。此时，您可以故障转移至位于 Datacenter2 中的 Pool2。

大多数池故障转移工作涉及对 中央管理存储进行故障转移（如果需要）。这很重要，因为在池用户进行故障转移时 中央管理存储必须能够正常运行。

此外，如果某一前端池发生了故障，但该站点中的边缘池仍在运行，则必须知道边缘池是否将发生故障的池用作下一个跃点池。如果是这样，必须在故障转移发生故障的前端池之前，将边缘池更改为使用其他前端池。更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。

**设置边缘池以使用同一站点中的下一个跃点池**

1.  打开拓扑生成器，右键单击需要更改的边缘池，然后单击“编辑属性”。

2.  单击“下一个跃点”。从“下一个跃点池:”列表中，选择现在将用作下一个跃点池的池。

3.  单击“确定”，然后发布更改。

**设置边缘池以使用不同站点中的下一个跃点池**

1.  打开 Lync Server 命令行管理程序窗口并键入以下 cmdlet：
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在发生灾难时对池进行故障转移**

1.  通过在 Pool2 的前端服务器中键入以下 cmdlet 可找到哪个池是 中央管理服务器的主机：
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 cmdlet 的结果显示当前哪个池托管 中央管理服务器。在此过程的其余部分中，此池被称为 CMS\_Pool。

2.  使用拓扑生成器查找在 CMS\_Pool 上运行的 Lync Server 的版本。如果它运行的是 Lync Server 2013，请使用以下 cmdlet 查找 Pool 1 的备份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    让 Backup\_Pool 成为备份池。

3.  使用以下 cmdlet 检查 中央管理存储的状态：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_Pool 的 FQDN。如果它们为空，那么 中央管理服务器不可用，您必须对其进行故障转移。

4.  如果 中央管理存储不可用或者 中央管理存储运行在 Pool1（即发生故障的池）上，那么您必须先对 中央管理服务器进行故障转移，然后再对该池进行故障转移。如果您需要对 中央管理服务器进行故障转移，而它托管在运行 Lync Server 2013 的池上，那么请使用此过程的第 5 步中的 cmdlet。如果您需要对 中央管理服务器进行故障转移，而它托管在运行 Lync Server 2010 的池上，请使用此过程的第 6 步中的 cmdlet。如果您不需要对 中央管理服务器进行故障转移，请跳至此过程的第 7 步。

5.  要在运行 Lync Server 2013 的池上对 中央管理存储进行故障转移，请执行以下操作：
    
      - 首先，通过键入以下命令检查 Backup\_Pool 中的哪台后端服务器运行的是 中央管理存储的主体实例：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果 Backup\_Pool 中的主后端服务器为主体，请键入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果 Backup\_Pool 中的镜像后端服务器为主体，请键入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 验证 中央管理服务器故障转移是否已完成。键入以下命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向 Backup\_Pool 的 FQDN。
    
      - 最后，通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否为 True。
        
        跳至此过程的第 7 步。

6.  在 Backup\_Pool 的后端服务器上安装 中央管理存储。
    
      - 首先，运行以下命令：
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在 Backup\_Pool 的其中一台前端服务器上运行下面的命令以强制移动 中央管理存储：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 验证移动是否完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向 Backup\_Pool 的 FQDN。
    
      - 通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值是否为 True。
    
      - 在 Backup\_Pool 的其余前端服务器上安装 中央管理服务器服务。为此，请在所有前端服务器（除了使用此过程前面的步骤强制移动 中央管理存储时使用的服务器）上运行以下命令：
        
            Bootstrapper /Setup 

7.  通过在 Lync Server 命令行管理程序窗口中运行以下 cmdlet，将用户从 Pool1 故障转移到 Pool2：
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因为此过程前面部分中用于检查 中央管理存储状态的步骤不是通用的，所以此 cmdlet 仍然有可能因为 中央管理存储尚未完全故障转移而失败。在这种情况下，您必须根据显示的错误消息修复 中央管理存储，然后重新运行此 cmdlet。
    
    如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

