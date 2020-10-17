---
title: Lync Server 2013：呼叫允许控制部署清单
description: Lync Server 2013：呼叫允许控制部署检查表。
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
ms.openlocfilehash: db7a69bda3048f93089a47b43a0b433946b783f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569188"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的呼叫允许控制部署清单

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。

  - 如果已部署一台或多台边缘服务器，则必须将每个外部接口 IP 地址添加到网络配置设置中的子网列表，其中位掩码为 32。还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    <div>
    

    > [!NOTE]  
    > 边缘服务器无需实现 CAC。

    
    </div>

  - 确保可以通过 Lync Server 控制面板或通过运行在 [Lync server 2013 中启用呼叫允许控制](lync-server-2013-enable-call-admission-control.md)中指定的 cmdlet 来启用 CAC。

  - 确保已在所有中央站点启用 CAC。 可以通过拓扑生成器来完成此操作。 如果发布时生成警告，*请勿* 忽略该警告。

  - 确保已在网络配置设置中配置在企业网络中管理的所有子网。 如果将子网 [与 Lync Server 2013 中的网络站点](lync-server-2013-associate-a-subnet-with-a-network-site.md)关联，则还必须将每个子网与网络站点相关联。

  - 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。

</div>

<span> </span>

</div>

</div>

</div>

