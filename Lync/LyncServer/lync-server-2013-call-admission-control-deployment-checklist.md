---
title: Lync Server 2013：呼叫许可控制部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 "呼叫许可控制" 部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-22_

使用以下清单验证是否已完成部署呼叫许可控制（CAC）的所有必要配置任务。

  - 如果部署了一个或多个边缘服务器，则每个外部接口 IP 地址都必须添加到网络配置设置中的子网列表中，位掩码为32。 还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    <div>
    

    > [!NOTE]  
    > 不需要边缘服务器实现 CAC。

    
    </div>

  - 确保可以通过 Lync Server 控制面板或通过运行在[Lync server 2013 的 "启用呼叫许可控制](lync-server-2013-enable-call-admission-control.md)" 中指定的 cmdlet 来启用 CAC。

  - 确保已在所有中央站点启用 CAC。 这可以通过拓扑生成器完成。 如果发布时生成警告，*请勿*忽略该警告。

  - 确保已在网络配置设置中配置在企业网络中管理的所有子网。 如果[将子网与 Lync Server 2013 中的网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)，则还必须将每个子网与网络站点相关联。

  - 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。

</div>

<span> </span>

</div>

</div>

</div>

