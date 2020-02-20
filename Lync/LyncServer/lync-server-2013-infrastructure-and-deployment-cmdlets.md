---
title: Lync Server 2013：基础结构和部署 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 386ad7787eeb3d748e537edc6f1d0fb890fef63b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的基础结构和部署 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

Microsoft Lync Server 2013 中包含的基础结构和部署 cmdlet 在产品的初始安装和部署中可能很有用;在部署 Lync Server 之后，可以使用这些 cmdlet 执行以下操作以验证组件是否按预期方式工作;管理复制设置;并备份和还原 Lync Server 拓扑、策略和配置设置。

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>基础结构和部署 Cmdlet

管理员几乎不需要直接调用多个基础结构和部署。 这是因为，在运行安装程序或拓扑生成器时，将自动调用这些 cmdlet。 （一个主要异常可能是**CsConfiguration** cmdlet，它允许您创建 Lync Server 拓扑、策略和配置设置的备份副本。）但是，如果需要，还可以从 Lync Server 命令行管理程序或脚本中运行基础结构和部署 cmdlet。使用脚本，可以自动执行某些任务。 以下是与基础结构和部署直接相关的 cmdlet 的列表：

**[Lync Server 2013 中的 Active Directory cmdlet](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Lync Server 2013 中的复制 cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [调试-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [调用 CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [新 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[Jn Lync Server 2013 的拓扑 cmdlet](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Start-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Get-cssite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [发布-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Lync Server 2013 中的备份和高可用性 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [调用 CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [调试-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup-Start-cspool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [调用 CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [调用 CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [调用 CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync-Export-csuserdata](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server PowerShell 博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

