---
title: Lync Server 2013：创建网络站点间策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>在 Lync Server 2013 中创建网络站点间策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

*网络站点间策略*定义具有直接 WAN 链接的站点之间的带宽限制。

有关详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 只有当两个网络站点之间有直接交叉链接时，<EM>才</EM>需要网络站点间策略。



</div>

在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。 这两个网站需要应用相应带宽策略配置文件的站点间策略。 下面的示例应用 20Mb\_链接配置文件。

<div>

## <a name="to-create-a-network-intersite-policy"></a>创建网络站点间策略

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行 CsNetworkInterSitePolicy cmdlet 以创建网络站点间策略，并为具有直接交叉链接的两个站点应用相应的带宽策略配置文件。 例如，运行：
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  根据需要重复步骤2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。

</div>

</div>

<span> </span>

</div>

</div>

</div>

