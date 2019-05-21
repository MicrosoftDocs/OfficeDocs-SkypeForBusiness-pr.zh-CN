---
title: 对池进行故障转移和故障回复
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303884"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>在 Skype for Business 服务器中故障转移和恢复池失败 

如果单个前端池出现故障且需要故障转移, 或者遇到灾难的池重新联机, 并且你需要将部署还原到正常工作状态, 请使用以下过程。 此外, 还可了解如何故障转移和故障回复用于 Skype for business federation 或 XMPP federation 的边缘池, 或更改与前端池关联的边缘池。

- [故障转移前端池](#fail-over-a-front-end-pool)
- [故障回复池](#fail-back-a-pool)
- [故障切换用于 Skype for business 服务器联合的边缘池](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [在 Skype for Business 服务器中针对 XMPP 联盟使用的边缘池故障转移](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [故障回复用于 Skype for Business 服务器联盟或 XMPP 联合身份验证的边缘池](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [更改与前端池关联的边缘池](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>故障转移前端池

在此过程中, Datacenter1 包含 Pool1, 而 Pool1 失败。 您将在 Datacenter2 中故障转移到 Pool2。

对于池故障转移, 大部分工作都涉及到中央管理存储的故障 (如果需要)。 这一点很重要, 因为中央管理存储在池的用户故障转移时必须正常工作。

此外, 如果前端池出现故障, 但该站点上的边缘池仍在运行, 则必须知道 Edge 池是否将失败的池用作下一个跃点池。 如果是, 则必须将 Edge 池更改为使用不同的前端池, 然后再进行故障转移失败的前端池。 更改下一个跃点设置的方式取决于边缘是将同一站点上的池用作边缘池还是其他网站。

**将 "边缘池" 设置为在同一站点使用下一个跃点池**

1.  打开拓扑生成器, 右键单击需要更改的边缘池, 然后单击 "**编辑属性**"。

2.  单击 "**下一跃点**"。 从**下一个 "跃点池:** " 列表中, 选择现在将用作下一个跃点池的池。

3.  单击 **"确定**", 然后发布所做的更改。

**将边缘池设置为在其他网站上使用下一个跃点池**

1.  打开 Skype for Business 服务器管理外壳窗口, 键入以下 cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在灾难中故障转移池**

1.  通过在 Pool2 中的前端服务器上键入以下 cmdlet 来查找哪个池是中央管理服务器的主机:
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 cmdlet 的结果显示当前托管中央管理服务器的池。 在此过程的其余部分中, 此池称为 CMS\_池。

2.  使用拓扑生成器查找 CMS\_池中运行的 Skype For business 服务器版本。 如果它运行的是 Skype for Business 服务器, 请使用以下 cmdlet 查找池1的备份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    让备份\_池成为备份池。

3.  通过以下 cmdlet 检查中央管理存储的状态:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。 如果它们为空, 则中央管理服务器不可用, 您必须将其故障转移。

4.  如果中央管理存储不可用, 或者中央管理存储在 Pool1 上运行 (即失败的池), 则必须先通过中央管理服务器进行故障转移, 然后才能故障转移池。 如果需要在运行 Skype for Business Server 的池中托管的中央管理服务器上失败, 请使用此过程步骤5中的 cmdlet。 如果不需要故障转移中央管理服务器, 请跳到此过程的步骤7。

5.  要在运行 Skype for Business Server 的池上故障转移中央管理存储, 请执行以下操作:
    
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

7.  通过在 Skype for Business Server Management Shell 窗口中运行以下 cmdlet, 将用户从 Pool1 故障转移到 Pool2:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    由于本过程的前面部分中所执行的检查中央管理存储状态的步骤不是通用的, 因此此 cmdlet 仍会失败, 因为中央管理存储尚未完全故障转移。 在这种情况下, 你必须根据你看到的错误消息修复中央管理存储, 然后再次运行此 cmdlet。
    
    如果你看到以下错误消息, 则你需要更改此网站上的边缘池, 以便在对池进行故障转移之前使用其他池作为下一个跃点。 有关详细信息, 请参阅本主题开头的过程。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>故障回复池

在发生灾难的池重新联机后 (即在此示例中为 Pool1), 请执行以下步骤将你的部署还原到正常的工作状态。

请注意, 故障回复过程需要几分钟才能完成。作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。

通过键入以下 cmdlet 对最初驻留在 Pool1 中的用户进行故障回复, 并已故障转移到 Pool2:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

无需执行其他步骤。 如果您通过中央管理服务器进行了故障转移, 您可以将其保留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>故障切换用于 Skype for business 服务器联合的边缘池 

如果您的 Skype for business Server 联合身份验证配置所在的边缘池已关闭, 则必须将联合身份更改为使用不同的边缘池才能正常工作。

1.  在前端服务器上, 打开拓扑生成器。 展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。

2.  在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。

3.  展开 "**边缘池**", 然后右键单击要用于联盟的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。

4.  在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。

5.  单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。 当系统提示**发布拓扑**时, 单击 "**下一步**"。 发布完成后, 单击 "**完成**"。

6.  在边缘服务器上, 打开 "Skype for Business 服务器部署" 向导。 单击 "**安装或更新 skype for Business 服务器系统**", 然后单击 "**设置" 或 "删除 Skype For business 服务器组件**"。 再次单击 "**运行**"。

7.  单击" **下一步**"。 "摘要" 屏幕将显示执行时的操作。 部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。 单击 "**完成**" 以完成部署。
    
    如果包含失败的 Edge 池的网站包含仍在运行的前端服务器, 则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务, 才能使用仍在运行的远程网站中的边缘池。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>在 Skype for Business 服务器中针对 XMPP 联盟使用的边缘池故障转移 

在你的组织中, 有一个边界池指定为用于 XMPP 联合身份验证的池。 如果此池停止运行, 则必须故障转移 XMPP 联合身份验证才能使用其他边缘池, 然后 XMPP 联盟才能再次工作。

当你首次安装 Edge 池并启用 XMPP 联合身份验证时, 你可以通过为 XMPP 联盟的所有边缘池设置外部 DNS SRV 记录 (而不是仅一个) 来简化灾难恢复过程。 其中每个 SRV 记录都必须具有不同的优先级集。 所有 XMPP 联盟流量都将经历具有最高优先级的 SRV 记录的池。 

在以下过程中, EdgePool1 是最初托管 XMPP 联盟的池, EdgePool2 是池, 它现在将托管 XMPP 联合。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>故障切换用于 XMPP 联盟的边缘池

1.  如果尚未部署另一个边缘池 (除了当前已关闭的), 请部署该池。 

2.  在现在将托管 XMPP 联合身份验证 (EdgePool2) 的新边缘池中的每个边缘服务器上, 运行以下 cmdlet:
    
        Stop-CsWindowsService

3.  运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到 EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此示例中, Site2 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer2.contoso.com 是该池中的边缘服务器的 FQDN。

4.  在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。

5.  如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。 此 SRV 记录必须具有端口值5269。
    
        _xmpp-server._tcp.contoso.com

6.  验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。

7.  在边缘池中的所有边缘服务器上启动服务, 现在将托管 XMPP 联合身份验证:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>故障回复用于 Skype for Business 服务器联盟或 XMPP 联合身份验证的边缘池 

在将用于托管联合身份验证的边缘池重新联机后, 请使用此过程来故障回复 Skype for Business Server 联合身份验证路由和/或 XMPP 联盟路由, 以再次使用此还原的 Edge 池。

1.  在现在再次可用的 Edge 池中, 启动 Edge 服务。

2.  如果你希望恢复 Skype for business Server 联合身份验证路由以使用还原的边缘服务器, 请执行以下操作:
    
      - 在前端服务器上, 打开拓扑生成器。 展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。
    
      - 在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。
    
      - 展开 "**边缘池**", 然后右键单击要用于联盟的原始边缘服务器或边缘服务器池。 选择 "**编辑属性**"。
    
      - 在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。
    
      - 单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。 当系统提示**发布拓扑**时, 单击 "**下一步**"。 发布完成后, 单击 "**完成**"。
    
      - 在边缘服务器上, 打开 "Skype for Business 服务器部署" 向导。 单击 "**安装或更新 skype for Business 服务器系统**", 然后单击 "**设置" 或 "删除 Skype For business 服务器组件**"。 再次单击 "**运行**"。
    
      - 单击" **下一步**"。 "摘要" 屏幕将显示执行时的操作。 部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。 单击 "**完成**" 以完成部署。

3.  如果想要恢复 XMPP 联盟路由以使用还原的边缘服务器, 请执行以下操作:
    
      - 运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到边缘池, 该池现在将托管 XMPP 联合身份验证 (在此示例中, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在此示例中, Site1 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer1.contoso.com 是该池中的边缘服务器的 FQDN。
    
      - 如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。 此 SRV 记录必须具有端口值5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。
    
      - 验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。

4.  如果前端池仍在包含发生故障且已还原的边缘池的网站中运行, 则应在这些前端池上更新 Web 会议服务和 A/V 会议服务, 再次使用其本地网站上的边缘池。

5.  如果与失败的 Edge 池位于同一站点的前端池也失败, 您现在可以使用 Invoke-CsPoolFailback 来故障回复前端池。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>更改与前端池关联的边缘池

如果边缘池已关闭, 但同一网站上的前端池仍在运行, 则需要将前端池设置为在其他网站上使用边缘池, 直到还原失败的边缘池。

1.  在拓扑生成器中, 导航到需要更改的前端池的名称。

2.  右键单击该池, 然后单击 "**编辑属性**"。

3.  在 "**关联**" 部分中的 "**关联 Edge 池 (对于媒体组件)**" 下, 使用下拉框选择要与之关联的 "前端" 池的边缘池。

4.  单击“**确定**”。
