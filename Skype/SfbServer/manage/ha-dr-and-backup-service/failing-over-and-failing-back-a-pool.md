---
title: 对池进行故障转移和故障回复
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 55377e77a5b365a4db149ee69b6cd796e373a80b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849965"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>对池中的池进行Skype for Business Server

如果单个 Front-End 池出现故障且需要进行故障恢复，或者遇到灾难的池重新联机，并且您需要将部署还原为正常工作状态，请使用以下过程。 了解如何对用于联盟或 XMPP 联盟Skype for Business进行故障转移和故障回复，或更改与 Front-End 池关联的边缘池。

- [对前端池进行故障转移](#fail-over-a-front-end-pool)
- [对池进行故障回复](#fail-back-a-pool)
- [对用于联盟的边缘池Skype for Business Server故障转移](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [故障转移用于 XMPP 联盟的边缘池Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [故障回复用于联盟或 XMPP 联盟Skype for Business Server边缘池](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [更改与前端池关联的边缘池](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>故障转移Front-End池

Datacenter1 包含 Pool1，而 Pool1 已失败。 将故障切换至位于 Datacenter2 中的 Pool2。

池故障转移的多数工作都涉及对中央管理存储进行故障转移（如果需要）。 当池的用户进行故障管理时，中央管理存储必须工作正常。

如果Front-End池出现故障，但该站点中的边缘池仍在运行，则必须知道边缘池是否将故障池用作下一个跃点池。 如果是这样，则必须将边缘池更改为使用另一Front-End池，然后再对发生故障的Front-End池。 更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。

**将边缘池设置为在同一站点使用下一个跃点池**

1. 打开拓扑生成器，右键单击需要更改的边缘池，然后选择编辑 **属性**。

2. 选择"**下一个跃点"。** 从" **下一个跃点池："** 列表中，选择现在将用作下一个跃点池的池。

3. 选择 **"** 确定"，然后发布更改。

**将边缘池设置为在不同站点使用下一个跃点池**

1. 打开"Skype for Business Server命令行管理程序"窗口并键入以下 cmdlet：

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**在灾难中对池进行故障转移**

1. 在 Pool2 中的中央管理服务器上键入以下 cmdlet，Front-End中央管理服务器的主机池：

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    此 cmdlet 的结果显示当前托管中央管理服务器的池。 在此过程的其余部分中，此池称为 CMS \_ 池。

2. 使用拓扑生成器查找在 CMS Skype for Business Server运行的版本 \_ 。 如果它正运行Skype for Business Server，请使用以下 cmdlet 查找池 1 的备份池。

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    让备份 \_ 池成为备份池。

3. 使用下列 cmdlet 检查中央管理存储的状态：

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 池的 \_ FQDN。 如果它们为空，中央管理服务器将不可用，您必须进行故障转移。

4.  如果中央管理存储不可用，或者中央管理存储在 Pool1 (（即故障池) ）上运行，则必须在故障转移池之前对中央管理服务器进行故障转移。 如果需要对托管在运行 Skype for Business Server 池上的中央管理服务器进行故障转移，请使用此过程步骤 5 中的 cmdlet。 如果不需要对中央管理服务器进行故障转移，请跳到此过程的步骤 7。

5.  若要对运行中央管理存储的池进行Skype for Business Server，请执行下列操作：

    1. 首先，键入Back-End检查备份池中的哪个服务器运行中央管理存储 \_ 的主体实例：

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. 如果备份Back-End服务器 \_ 的主服务器是主体，请键入：

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. 如果备份Back-End中的镜像服务器 \_ 是主体，请键入：
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. 验证中央管理服务器故障转移是否已完成。 键入以下命令：
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否指向备份池的 \_ FQDN。
    
    1. 最后，通过键入以下内容检查Front-End服务器的副本状态：
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        检查所有副本的值是否为 True。
        
        跳至此过程的第 7 步。

6.  在备份池的后端服务器上安装中央管理 \_ 存储。
    
    1. 首先，运行以下命令：

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. 在备份池的一台前端服务器上运行下一个命令以强制移动 \_ 中央管理存储：

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 验证移动是否完成：

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否指向备份池的 \_ FQDN。
    
    1. 通过键入以下命令检查所有前端服务器的副本状态：

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        检查所有副本的值是否为 True。
    
    1. 在备份池中的其余前端服务器上安装中央管理 \_ 服务器服务。 为此，请在所有前端服务器上运行以下命令，除了在此过程前面强制中央管理存储移动时所使用的命令：

        ```console
        Bootstrapper /Setup
        ```

7.  在命令行管理程序窗口中运行以下 cmdlet，将用户从 Pool1 故障转移Skype for Business Server Pool2：

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    由于此过程的前面部分为检查中央管理存储状态而执行的步骤并不通用，所以此 cmdlet 仍然有可能失败，因为中央管理存储尚未完全故障转移。 在这种情况下，必须基于看到的错误消息修复中央管理存储，然后再次运行此 cmdlet。
    
    如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>对池进行故障回复

在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。

故障回复过程需要几分钟才能完成。 作为参考，预计 20，000 个用户池最多需要 60 分钟。

通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

无需执行其他步骤。 如果对中央管理服务器进行故障管理，可以将它留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>对用于联盟的边缘池Skype for Business Server故障转移 

如果已配置联盟Skype for Business Server池关闭，则必须更改联盟以使用不同的边缘池，联盟工作。

1.  在前端服务器上，打开拓扑生成器。 展开 **"边缘** 池"，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。

3.  展开 **"边缘** 池"，然后右键单击现在要用于联盟的边缘服务器或边缘服务器池。 选择“编辑属性”。

4.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。

5.  选择 **"操作"，** 选择 **"拓扑"，** 选择"**发布"。** 当"发布拓扑 **"上看到提示时，选择**"下一 **步"。** 完成发布后，**选择完成。**

6.  在边缘服务器上，打开"Skype for Business Server部署"向导。 选择 **"安装或** Skype for Business Server系统"，然后选择"**安装或删除Skype for Business Server组件"。** 选择 **"再次运行"。**

7.  选择 **下一步**。 摘要屏幕将显示已执行的操作。 部署完成后，选择" **查看日志"** 以查看可用的日志文件。 选择 **"完成** "以完成部署。
    
    如果包含故障边缘池的站点包含仍在运行的前端服务器，则必须更新这些 Front-End 池上的 Web 会议服务和 A/V 会议服务，以使用仍在运行的远程站点中的边缘池。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>故障转移用于 XMPP 联盟的边缘池Skype for Business Server 

在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。

在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。 所有这些 SRV 记录都必须具有不同的优先级设置。 所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。 

在下面的过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在将承载 XMPP 联盟的池。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>对用于 XMPP 联盟的边缘池进行故障转移

1.  如果除当前位于其他边缘池 (，尚未部署其他边缘) ，请部署该池。 

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

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>故障回复用于联盟或 XMPP 联盟Skype for Business Server边缘池 

在用于承载联盟的故障边缘池重新联机后，使用此过程对 Skype for Business Server 联盟路由和/或 XMPP 联盟路由进行故障回复，以再次使用此还原的边缘池。

1.  在此时再次可用的边缘池上，启动边缘服务。

2.  如果要对联盟路由Skype for Business Server故障回复以使用还原的边缘服务器，请执行下列操作：
    
    1. 在前端服务器上，打开拓扑生成器。 展开 **"边缘** 池"，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择“编辑属性”。
    
    1. 在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。
    
    1. 展开 **"边缘** 池"，然后右键单击要再次用于联盟的原始边缘服务器或边缘服务器池。 选择“编辑属性”。
    
    1. 在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。 选择“**确定**”。
    
    1. 选择 **"操作"，** 选择 **"拓扑"，** 选择"**发布"。** 当"发布拓扑 **"上看到提示时，选择**"下一 **步"。** 完成发布后，**选择完成。**
    
    1. 在边缘服务器上，打开"Skype for Business Server部署"向导。 选择 **"安装或更新Skype for Business Server系统**"，然后选择"**安装或删除Skype for Business Server组件"。** 选择 **"再次运行"。**
    
    1. 选择 **下一步**。 摘要屏幕将显示已执行的操作。 部署完成后，选择" **查看日志"** 以查看可用的日志文件。 选择 **"完成** "以完成部署。

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


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>更改与前端池关联的边缘池

如果边缘池出现故障，但同一站点中的前端池仍在运行，您将需要将前端池设置为使用其他站点中的边缘池，直到故障池恢复。

1.  在拓扑生成器中，导航到需要更改的前端池的名称。

2.  右键单击该池，然后选择"编辑 **属性"。**

3.  在“关联”部分的“关联边缘池(用于媒体组件)”下，使用下拉框选择要与此前端池关联的边缘池。

4.  选择“**确定**”。
