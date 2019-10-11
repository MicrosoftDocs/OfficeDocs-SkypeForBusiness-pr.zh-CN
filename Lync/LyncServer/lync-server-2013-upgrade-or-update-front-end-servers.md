---
title: Lync Server 2013：升级或更新前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-06-28_

企业版池中的前端服务器组织为*升级域*。 这些是池中的前端服务器的子集。 升级域由拓扑生成器自动创建。

升级服务器时，必须一次升级域。 将每台服务器放在一个升级域中，升级它，然后重新启动它，然后再转到另一个升级域。 请务必跟踪目前升级的升级域和服务器。 升级每台服务器时，请使用以下流程图图。

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="升级或更新前端服务器":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>对池中的前端服务器应用升级

1.  在池中的前端服务器上，运行以下 cmdlet：
    
    **Get-CsPoolUpgradeReadinessState**
    
    如果*PoolUpgradeState*的值为 "**忙碌**"，请等待10分钟，然后再次尝试**获取 CsPoolUpgradeReadinessState** 。 如果在每次尝试之间等待10分钟，或者如果你看到 PoolUpgradeState 的**InsufficientActiveFrontEnds**的任何结果，则至少出现三次 "**忙碌**"，或者如果你看到的任何结果 **，** 则该池存在问题。 如果此池与灾难恢复拓扑中的另一个前端池配对，则应将池故障转移到备份池，然后更新此池中的服务器。 有关详细信息，请参阅[在 Lync Server 2013 中故障转移池](lync-server-2013-failing-over-a-pool.md)。
    
    如果*PoolUpgradeState*的值已**准备就绪**，请转到步骤2。

2.  **CsPoolUpgradeReadinessState** cmdlet 还会返回有关池中的每个升级域的信息，以及每个升级域中的前端服务器。 如果包含要升级的一个或一些服务器的升级域的**ReadyforUpgrade**值为**True** ，则现在可以安全地升级这些服务器。 若要执行此操作，请执行下列操作：
    
    1.  通过使用`Stop-CsWindowsService -Graceful -Verbose` cmdlet 停止与即将升级的前端服务器的新连接。
        
        <div>
        

        > [!NOTE]  
        > 如果在计划的服务器停机期间执行这些服务器升级，则可以运行此 cmdlet 而不使用 "-<STRONG>宽容</STRONG>" 参数，如下所示： <STRONG>Stop-CsWindowsService</STRONG>。 这将立即关闭服务，而无需等待已填写的所有现有服务请求。

        
        </div>
    
    2.  升级与此升级域相关联的服务器。
    
    3.  重新启动服务器，确保他们接受新的连接。

3.  对池中的每个升级域重复步骤1和2，直到升级了所有前端服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

