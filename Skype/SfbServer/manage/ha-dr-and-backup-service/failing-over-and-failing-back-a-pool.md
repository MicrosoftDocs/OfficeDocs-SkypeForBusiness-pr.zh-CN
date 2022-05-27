---
title: 对池进行故障转移和故障回复
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675034"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>在Skype for Business Server中故障转移和故障回复池

如果单个Front-End池失败且需要故障转移，或者遇到灾难的池已恢复联机状态，并且需要将部署还原到正常工作状态，请使用以下过程。 了解如何故障转移和故障回复用于Skype for Business联合身份验证或 XMPP 联合的 Edge 池，或更改与Front-End池关联的 Edge 池。

- [故障转移前端池](#fail-over-a-front-end-pool)
- [故障回复池](#fail-back-a-pool)
- [故障转移用于Skype for Business Server联合的 Edge 池](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [在 Skype for Business Server 中故障转移用于 XMPP 联合的 Edge 池](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [故障回复用于Skype for Business Server联合身份验证或 XMPP 联合的 Edge 池](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [更改与前端池关联的 Edge 池](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>故障转移Front-End池

Datacenter1 包含 Pool1，而 Pool1 已失败。 你将故障转移到位于 Datacenter2 中的 Pool2。

池故障转移的大部分工作包括故障转移中央管理存储（如果需要）。 当池的用户发生故障转移时，中央管理存储必须正常运行。

如果Front-End池失败，但该站点的 Edge 池仍在运行，则必须知道 Edge 池是否使用失败的池作为下一跃点池。 如果这样做，则必须先将 Edge 池更改为使用其他Front-End池，然后才能故障转移失败的Front-End池。 更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。

**将 Edge 池设置为在同一站点使用下一跃点池**

1. 打开拓扑生成器，右键单击需要更改的 Edge 池，然后选择 **“编辑属性**”。

2. 选择 **“下一跃点**”。 从 **“下一跃点池：** 列表”中，选择现在将用作下一跃点池的池。

3. 选择 **“确定**”，然后发布更改。

**将 Edge 池设置为在其他站点使用下一跃点池**

1. 打开 Skype for Business Server Management Shell 窗口并键入以下 cmdlet：

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**在灾难中故障转移池**

1. 在 Pool2 中的Front-End服务器上键入以下 cmdlet，查找中央管理服务器的主机池：

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    此 cmdlet 的结果显示当前托管中央管理服务器的池。 在此过程的其余部分中，此池称为 CMS\_池。

2. 使用拓扑生成器查找 CMS\_池上运行的Skype for Business Server的版本。 如果运行Skype for Business Server，请使用以下 cmdlet 查找池 1 的备份池。

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    让 备份\_Pool 成为备份池。

3. 使用以下 cmdlet 检查中央管理存储的状态：

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。 如果它们为空，则中央管理服务器不可用，必须将其故障转移。

4.  如果中央管理存储不可用，或者如果 Central Management 存储在 Pool1 (（即失败的池) 上运行），则必须在故障转移池之前故障转移中央管理服务器。 如果需要故障转移托管在运行Skype for Business Server的池上的中央管理服务器，请在此过程的步骤 5 中使用该 cmdlet。 如果不需要故障转移中央管理服务器，请跳到此过程的步骤 7。

5.  若要故障转移运行Skype for Business Server的池上的中央管理存储，请执行以下操作：

    1. 首先，键入以下内容，检查备份Pool 中哪个Back-End\_服务器运行中央管理存储的主体实例：

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. 如果 备份Pool 中的主要Back-End\_服务器是主体，请键入：

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. 如果备份Pool 中的\_镜像Back-End服务器是主体，请键入：
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. 验证中央管理服务器故障转移是否已完成。 键入以下命令：
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向 备份\_Pool 的 FQDN。
    
    1. 最后，键入以下内容，检查所有Front-End服务器的副本状态：
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        检查所有副本的值是否为 True。
        
        跳至此过程的第 7 步。

6.  在 备份\_Pool 的后端服务器上安装中央管理存储。
    
    1. 首先，运行以下命令：

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. 在 备份\_Pool 的前端服务器之一上运行下一个命令以强制移动中央管理存储：

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 验证移动是否完成：

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向 备份\_Pool 的 FQDN。
    
    1. 通过键入以下命令检查所有前端服务器的副本状态：

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        检查所有副本的值是否为 True。
    
    1. 在 备份\_Pool 中，在前端服务器的其余部分上安装 Central Management Server 服务。 为此，请在所有前端服务器上运行以下命令，但此过程前面强制中央管理存储移动时使用的命令除外：

        ```console
        Bootstrapper /Setup
        ```

7.  通过在 Skype for Business Server Management Shell 窗口中运行以下 cmdlet，将用户从 Pool1 故障转移到 Pool2：

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    由于此过程前面部分为检查中央管理存储状态而执行的步骤并不普遍，因此此 cmdlet 仍有可能失败，因为中央管理存储尚未完全故障转移。 在这种情况下，必须根据你看到的错误消息修复中央管理存储，然后再次运行此 cmdlet。
    
    如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>故障回复池

在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。

故障回复过程需要几分钟才能完成。 对于包含 20，000 个用户的池，预计最多需要 60 分钟才能进行参考。

通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

无需执行其他步骤。 如果故障转移了中央管理服务器，则可以将其保留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>故障转移用于Skype for Business Server联合的 Edge 池 

如果配置了Skype for Business Server联合身份验证的 Edge 池发生关闭，则必须更改联合身份验证，以使用其他 Edge 池进行联合身份验证才能正常工作。

1.  在前端服务器上，打开拓扑生成器。 展开 **Edge 池**，然后右键单击当前为联合身份验证配置的 Edge 服务器或 Edge 服务器池。 选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。

3.  展开 **Edge 池**，然后右键单击现在要用于联合身份验证的 Edge 服务器或 Edge 服务器池。 选择“编辑属性”。

4.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。

5.  选择 **“操作**”，选择 **“拓扑**”，选择 **“发布**”。 当系统提示 **发布拓扑** 时，请选择 **“下一步**”。 发布完成后，选择 **“完成**”。

6.  在 Edge 服务器上，打开Skype for Business Server部署向导。 选择 **“安装”或“更新Skype for Business Server系统**”，然后选择 **“设置”或“删除Skype for Business Server组件**”。 选择 **“再次运行**”。

7.  选择 **下一步**。 摘要屏幕将显示已执行的操作。 部署完成后，选择 **“查看日志** ”以查看可用的日志文件。 选择 **“完成** ”以完成部署。
    
    如果包含失败的 Edge 池的站点包含仍在运行的前端服务器，则必须更新这些Front-End池上的 Web 会议服务和 A/V 会议服务，才能在仍在运行的远程站点中使用 Edge 池。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>在 Skype for Business Server 中故障转移用于 XMPP 联合的 Edge 池 

在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。

在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。 所有这些 SRV 记录都必须具有不同的优先级设置。 所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。 

在以下过程中，EdgePool1 是最初托管 XMPP 联合身份验证的池，而 EdgePool2 是现在将托管 XMPP 联合的池。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>故障转移用于 XMPP 联合的 Edge 池

1.  如果尚未部署其他 Edge 池 (当前) ，请部署该池。 

2.  在现在承载 XMPP 联盟的新边缘池 (EdgePool2) 中的每个边缘服务器上，运行以下 cmdlet：

    ```powershell
    Stop-CsWindowsService
    ```

3.  运行以下 cmdlet 可将 XMPP 联盟路由重新指向 EdgePool2：

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    在此示例中，Site2 是包括现在承载 XMPP 联盟路由的边缘池的站点，EdgeServer2.contoso.com 是该池中某个边缘服务器的 FQDN。

4.  在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。

5.  如果您尚不具有解析为现在承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加它，如以下示例中所示。此 SRV 记录的端口值必须为 5269。

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  确认现在承载 XMPP 联盟的边缘池具有已外部打开的端口 5269。

7.  在现在承载 XMPP 联盟的边缘池中的所有边缘服务器上启动服务：

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>故障回复用于Skype for Business Server联合身份验证或 XMPP 联合的 Edge 池 

在用于托管联合身份验证的失败 Edge 池重新联机后，使用此过程可以故障回复Skype for Business Server联合身份验证路由和/或 XMPP 联合身份验证路由，以再次使用此还原的 Edge 池。

1.  在此时再次可用的边缘池上，启动边缘服务。

2.  如果要故障回复Skype for Business Server联合路由以使用还原的 Edge Server，请执行以下操作：
    
    1. 在前端服务器上，打开拓扑生成器。 展开 **Edge 池**，然后右键单击当前为联合身份验证配置的 Edge 服务器或 Edge 服务器池。 选择“编辑属性”。
    
    1. 在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。
    
    1. 展开 **Edge 池**，然后右键单击要再次用于联合身份验证的原始 Edge 服务器或 Edge 服务器池。 选择“编辑属性”。
    
    1. 在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。
    
    1. 选择 **“操作**”，选择 **“拓扑**”，选择 **“发布**”。 当系统提示 **发布拓扑** 时，请选择 **“下一步**”。 发布完成后，选择 **“完成**”。
    
    1. 在 Edge 服务器上，打开Skype for Business Server部署向导。 选择 **“安装”或“更新Skype for Business Server系统**”，然后选择 **“设置”或“删除Skype for Business Server组件**”。 选择 **“再次运行**”。
    
    1. 选择 **下一步**。 摘要屏幕将显示已执行的操作。 部署完成后，选择 **“查看日志** ”以查看可用的日志文件。 选择 **“完成** ”以完成部署。

3.  如果想要对 XMPP 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：
    
    1. 运行以下 cmdlet 以将 XMPP 联盟路由重新指向此时将承载 XMPP 联盟的服务器（在此示例中为 EdgeServer1）：
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        在此示例中，Site1 是包含此时将承载 XMPP 联盟路由的边缘池的站点，EdgeServer1.contoso.com 是该池中边缘服务器的 FQDN。
    
    1. 如果您尚未拥有解析到此时将承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加该记录，如下例所示。该 SRV 记录的端口值必须为 5269。

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. 在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。
    
    1. 确认此时将承载 XMPP 联盟的边缘池已将端口 5269 向外部开放。

4.  如果前端池在含有出过故障并且已恢复的边缘池的站点中持续运行，则应该更新这些前端池上的 Web 会议服务和 A/V 会议服务，以在其本地站点上再次使用边缘池。

5.  如果在出现了故障边缘池的同一站点上的前端池也出现故障，则现在可以使用 Invoke–CsPoolFailback 对前端池进行故障回复。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>更改与前端池关联的 Edge 池

如果边缘池出现故障，但同一站点中的前端池仍在运行，您将需要将前端池设置为使用其他站点中的边缘池，直到故障池恢复。

1.  在拓扑生成器中，导航到需要更改的前端池的名称。

2.  右键单击池，然后选择 **“编辑属性**”。

3.  在“关联”部分的“关联边缘池(用于媒体组件)”下，使用下拉框选择要与此前端池关联的边缘池。

4.  选择“**确定**”。
