---
title: 出现故障后超过和失败的池
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 23b70817ba75f3a0a6e73cc42a9df9026e17b2d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223505"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>业务服务器失败后超过和失败的 Skype 池中 

如果单个前端池已失败和需要进行故障转移或经历灾难的池恢复联机，您需要部署恢复常规工作状态，请使用以下过程。 此外了解如何进行故障转移和故障回复用于 Skype 业务联盟或 XMPP 联盟的边缘池，或更改与前端池关联的边缘池。

- [故障转移前端池](#fail-over-a-front-end-pool)
- [故障回复池](#fail-back-a-pool)
- [故障转移用于 Skype Business Server 联盟的边缘池](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [故障转移用于 XMPP 联盟中 Skype 业务服务器的边缘池](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [故障回复用于 Skype Business Server 联盟或 XMPP 联盟的边缘池](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [更改与前端池关联的边缘池](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>故障转移前端池

在此过程中，Datacenter1 包含 Pool1，和 Pool1 失败。 您要故障转移到 Pool2 位于 Datacenter2。

池故障转移的工时的大多数涉及失败通过中央管理存储中，如果需要。 这是重要，因为中央管理存储的池的用户都将故障转移时必须能够正常运行。

此外，如果前端池失败，但仍在运行该站点的边缘池，您必须知道的边缘池是否为下一个跃点池使用发生故障的池。 如果是这样，您必须更改要通过发生故障的前端池使用不同的前端池失败前的边缘池。 更改下一个跃点设置的方式取决于是否边缘将使用池的同一站点的边缘池，或不同的网站。

**设置要在同一站点中使用的下一个跃点池的边缘池**

1.  打开拓扑生成器，右键单击边缘池，需要进行更改，然后单击**编辑属性**。

2.  单击**下一个跃点**。 从**下一个跃点池：** 列表中，选择现在将作为下一个跃点池的池。

3.  单击**确定**，然后发布更改。

**设置边缘池用于下一个跃点池位于不同站点**

1.  打开 Skype 业务 Server 命令行管理程序窗口并键入以下 cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**故障转移中灾难的池**

1.  找到哪个池是中央管理服务器的主机，通过在 Pool2 的前端服务器上键入以下 cmdlet:
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 cmdlet 显示哪个池当前承载中央管理服务器的结果。 此过程的其余部分，此池被称为 CMS\_池。

2.  使用拓扑生成器来查找业务 Server 上对 CMS 运行 Skype 版\_池。 如果它业务服务器运行 Skype，使用以下 cmdlet 来查找池 1 的备份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    让备份\_池成为备份池。

3.  检查以下 cmdlet 的中央管理存储的状态：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 应显示 ActiveMasterFQDN 和 activefiletransferagents 是否指向 CMS FQDN\_池。 它们是否为空，中央管理服务器不可用，您必须故障转移。

4.  如果中央管理存储不可用或中央管理存储在 Pool1 上运行 （即，已失败的池），您必须通过的池故障转移前中央管理服务器。 如果您需要已在运行 Business Server Skype 池中承载中央管理服务器故障转移，请使用此过程的步骤 5 中的 cmdlet。 如果您不需要进行故障转移中央管理服务器，请跳过此过程的步骤 7。

5.  故障转移中央管理存储业务服务器运行 Skype 的池上，执行以下操作：
    
      - 首先，检查备份中的后端服务器\_池运行中央管理存储的主体实例，通过键入以下命令：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果主后端服务器备份中\_池是主体，键入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果镜像中备份后端服务器\_池是主体，键入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 验证中央管理服务器故障转移已完成。 键入以下命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 activefiletransferagents 是否指向备份 FQDN\_池。
    
      - 最后，通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值为 True。
        
        跳到步骤 7 中此过程。

6.  在后端服务器的备份上安装中央管理存储\_池。
    
      - 首先，运行以下命令：
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 一台前端最终备份服务器上运行下面的命令\_以强制移动中央管理存储的池：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 验证移动是否完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        检查 ActiveMasterFQDN 和 activefiletransferagents 是否指向备份 FQDN\_池。
    
      - 通过键入以下命令检查所有前端服务器的副本状态：
        
            Get-CsManagementStoreReplicationStatus 
        
        检查所有副本的值为 True。
    
      - 中央管理服务器服务安装在前端服务器备份中的其余部分\_池。 为此，请在所有前端服务器上运行以下命令，存储在此过程前面时强制中央管理使用以外的移动：
        
            Bootstrapper /Setup 

7.  故障转移到 Pool2 将用户从 Pool1，通过 Skype 业务 Server 命令行管理程序窗口中运行以下 cmdlet:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因为检查中央管理存储状态所需的此过程前面部分中的步骤不是通用的则仍可能将此 cmdlet 将失败，因为中央管理存储不尚未完全故障转移。 在这种情况下，您必须修复中央管理存储基于您看到的错误消息，然后再次运行此 cmdlet。
    
    如果您看到以下错误消息，然后您需要更改在其他池用作通过池失败前其下一个跃点此站点的边缘池。 有关详细信息，请参阅本主题的开头的过程。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>故障回复池

经历灾难的池恢复联机后 (也就是说，Pool1 在本例中)，执行以下步骤来使部署常规工作状态。

请注意，故障回复过程需要几分钟时间才能完成。作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。

故障回复的用户最初驻留在 Pool1 中并已故障转移到 Pool2 通过键入以下 cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

没有其他步骤是必需的。 如果您故障转移中央管理服务器，您可以将其置于 Pool2。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>故障转移用于 Skype Business Server 联盟的边缘池 

如果 Skype 了配置 Business Server 联盟的边缘池不可用，则必须更改联合身份验证为使用联合身份验证的其他边缘池以。

1.  在前端服务器上，打开拓扑生成器。 展开**边缘池**，，然后右键单击当前为联盟配置边缘服务器池的边缘服务器。 选择**编辑属性**。

2.  在**编辑属性**在**常规**下，清除**启用联盟，为此边缘池 (端口 5061)**。 单击“确定”****。

3.  展开**边缘池**，，然后右键单击要立即使用联盟的边缘服务器或边缘服务器池。 选择**编辑属性**。

4.  在**编辑属性**在**常规**下，选择**启用联盟，为此边缘池 (端口 5061)**。 单击“确定”****。

5.  单击**操作**，选择**拓扑**，选择**发布**。 当提示您在**发布拓扑**，请单击**下一步**。 完成发布后，单击**完成**。

6.  在边缘服务器上，打开 Skype 的业务 Server 部署向导。 单击**安装或更新 Skype 业务 Server 系统**，然后单击**安装或删除业务服务器组件的 Skype**。 单击**再次运行**。

7.  单击" **下一步**"。 摘要屏幕上将显示操作，为在执行。 完成部署后，单击**查看日志**以查看可用的日志文件。 单击**完成**以完成部署。
    
    如果包含了故障的边缘池的站点包含仍在运行前端服务器，则必须更新的 Web 会议服务和 A / V 会议服务在这些前端池上用于远程边缘池，它是网站仍运行。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>故障转移用于 XMPP 联盟中 Skype 业务服务器的边缘池 

在组织中没有一个指定为池用于 XMPP 联盟的边缘池。 如果此池不可用，您必须先对 XMPP 联盟之前 XMPP 联盟可以再次使用用于其他边缘池。

当您首次安装边缘池，并启用 XMPP 联盟时，您可以通过设置的所有 XMPP 联盟，而不是只需一个边缘池的外部 DNS SRV 记录简化灾难恢复过程。 每个 SRV 记录必须具有不同的优先级设置。 所有 XMPP 联盟流量都遍历具有最高优先级的 SRV 记录的池。 

在下面的过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>故障转移用于 XMPP 联盟的边缘池

1.  如果您已没有其他边缘池 （除了一个其当前已关闭） 部署，部署该池。 

2.  在现在承载 XMPP 联盟 (EdgePool2) 的新边缘池的每台边缘服务器，运行以下 cmdlet:
    
        Stop-CsWindowsService

3.  运行以下 cmdlet 以重建 XMPP 联盟路由指向 EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    本示例中，Site2 是包含现在承载 XMPP 联盟路由的边缘池的站点和 EdgeServer2.contoso.com 为此池中的边缘服务器的 FQDN。

4.  在外部 DNS 服务器上，更改为指向 EdgeServer2.contoso.com 的 XMPP 联盟的 DNS A 记录。

5.  如果您已没有 XMPP 联盟，它解析为现在承载 XMPP 联盟的边缘池的 DNS SRV 记录，您必须添加，如以下示例所示。 此 SRV 记录必须 5269 端口值。
    
        _xmpp-server._tcp.contoso.com

6.  确认现在承载 XMPP 联盟的边缘池已打开的端口 5269 外部。

7.  在现在承载 XMPP 联盟的边缘池的所有边缘服务器上启动服务：
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>故障回复用于 Skype Business Server 联盟或 XMPP 联盟的边缘池 

后失败的边缘池用于主机联盟已经联机后，使用此过程可为 Business Server 联盟路由和/或 XMPP 联盟路由 Skype 要再次将此已还原的边缘池进行故障回复。

1.  在边缘池中，现在可再次，启动边缘服务。

2.  如果您想要进行故障回复 Business Server 联盟路由的 Skype，以使用恢复的边缘服务器，请执行以下操作：
    
      - 在前端服务器上，打开拓扑生成器。 展开**边缘池**，然后右键单击当前为联盟配置边缘服务器池的边缘服务器。 选择**编辑属性**。
    
      - 在**编辑属性**在**常规**下，清除**启用联盟，为此边缘池 (端口 5061)**。 单击“确定”****。
    
      - 展开**边缘池**，然后右键单击要再次使用联合身份验证的原始边缘服务器或边缘服务器池。 选择**编辑属性**。
    
      - 在**编辑属性**在**常规**下，选择**启用联盟，为此边缘池 (端口 5061)**。 单击“确定”****。
    
      - 单击**操作**，选择**拓扑**，选择**发布**。 当提示您在**发布拓扑**，请单击**下一步**。 完成发布后，单击**完成**。
    
      - 在边缘服务器上，打开 Skype 的业务 Server 部署向导。 单击**安装或更新 Skype 业务 Server 系统**，然后单击**安装或删除的 Skype 业务服务器组件**。 单击**再次运行**。
    
      - 单击" **下一步**"。 摘要屏幕上将显示操作，为在执行。 完成部署后，单击**查看日志**以查看可用的日志文件。 单击**完成**以完成部署。

3.  如果您想要进行故障回复 XMPP 联盟路由以使用恢复的边缘服务器，请执行以下操作：
    
      - 运行以下 cmdlet 以重建 XMPP 联盟路由到的边缘池，现在承载 XMPP 联盟 （在本例中为 EdgeServer1）：
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        本示例中，Site1 是包含现在承载 XMPP 联盟路由的边缘池的站点和 EdgeServer1.contoso.com 为此池中的边缘服务器的 FQDN。
    
      - 如果您已没有 XMPP 联盟，它解析为现在承载 XMPP 联盟的边缘池的 DNS SRV 记录，您必须添加，如以下示例所示。 此 SRV 记录必须 5269 端口值。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 服务器上，更改为指向 EdgeServer2.contoso.com 的 XMPP 联盟的 DNS A 记录。
    
      - 确认现在承载 XMPP 联盟的边缘池已打开的端口 5269 外部。

4.  如果前端池保持运行包含失败和已恢复的边缘池的站点，则应更新的 Web 会议服务和 A / V 会议服务在这些前端池再次使用其本地站点的边缘池。

5.  如果为了故障边缘池的同一站点上的前端池也出现故障，您现在可以使用 Invoke – CsPoolFailback 故障回复的前端池。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>更改与前端池关联的边缘池

如果边缘池不可用，但在同一站点的前端池仍在运行，您需要设置要使用不同站点的边缘池，直到还原了故障的边缘池的前端池。

1.  在拓扑生成器中，导航到需要更改的前端池的名称。

2.  右键单击池，，，然后单击**编辑属性**。

3.  在**关联**部分的**关联边缘池 （用于媒体组件）** 下,，使用下拉框选择要与此前端池关联的边缘池。

4.  单击“**确定**”。