---
title: Lync Server 2013：升级或更新前端服务器
description: Lync Server 2013：升级或更新前端服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569918"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>在 Lync Server 2013 中升级或更新前端服务器

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-06-28_

企业版池中的前端服务器被组织为 *升级域*。 这些是池中的前端服务器的子集。 升级域由拓扑生成器自动创建。

升级服务器时，必须一次升级域。 将每台服务器放在一个升级域中，将其升级，然后重新启动它，然后再转到另一个升级域。 请务必跟踪到目前为止升级了哪些升级域和服务器。 升级每个服务器时，请使用以下流程图图。

![升级或更新前端服务器](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>将升级应用到池中的前端服务器

1.  在池中的前端服务器上，运行以下 cmdlet：
    
    **CsPoolUpgradeReadinessState**
    
    如果 *PoolUpgradeState* 的值正 **忙**，请等待10分钟，然后再次尝试 **CsPoolUpgradeReadinessState** 。 如果在每次尝试之间等待10分钟后又至少看到了3次**繁忙**，或者如果您看到**PoolUpgradeState**的**InsufficientActiveFrontEnds**的任何结果，则该池存在问题。 如果该池与灾难恢复拓扑中的另一个前端池配对，则应将池故障转移到备份池，然后更新该池中的服务器。 有关详细信息，请参阅 [在 Lync Server 2013 中故障转移池](lync-server-2013-failing-over-a-pool.md)。
    
    如果 *PoolUpgradeState* 的值为 **Ready**，请转至步骤 2。

2.  **CsPoolUpgradeReadinessState** cmdlet 还会返回有关池中每个升级域的信息，以及每个升级域中的前端服务器。 如果包含要升级的一个或一台服务器的升级域的 **ReadyforUpgrade** 值为 **True** ，则现在可以安全地升级这些服务器。 为此，请执行以下操作：
    
    1.  使用 cmdlet 停止与要升级的前端服务器的新连接 `Stop-CsWindowsService -Graceful -Verbose` 。
        
        <div>
        

        > [!NOTE]  
        > 如果在计划的服务器停机期间执行这些服务器升级，则可以在不使用 "-<STRONG>宽容</STRONG>" 参数的情况下运行此 cmdlet，如下所示： <STRONG>start-cswindowsservice</STRONG>。 这将立即关闭服务，而无需等待要填充的所有现有服务请求。

        
        </div>
    
    2.  升级与此升级域关联的服务器。
    
    3.  重新启动服务器，并确保它们接受新的连接。

3.  对池中的每个其他升级域重复步骤1和步骤2，直到所有前端服务器都已升级。

</div>

</div>

<span> </span>

</div>

</div>

</div>

