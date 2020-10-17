---
title: Lync Server 2013：向网络站点添加位置策略
description: Lync Server 2013：将位置策略添加到网络站点。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567918"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中向网络站点添加位置策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

下面的示例演示如何将在[Lync Server 2013 中的 "创建位置策略](lync-server-2013-create-location-policies.md)" 中定义的**Redmond**位置策略添加到现有网络站点，以及如何创建使用**Redmond**位置策略的新网络站点。

有关使用网络站点的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **新 CsNetworkSite**

  - **CsNetworkSite**

  - **CsNetworkSite**

  - **CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>为现有网络站点分配位置策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet 以修改现有网络站点。
    
    将 **Redmond** 标记的位置策略分配给名为 **Redmond**的现有网络站点。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>为新的网络站点分配位置策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet 以创建新的网络站点。
    
    在网络区域中创建新的网络站点，并分配 **Redmond** 带标记的位置策略。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

