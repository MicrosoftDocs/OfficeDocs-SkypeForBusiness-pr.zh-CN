---
title: Lync Server 2013：配置呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e318ac448aa046f001022d40bc5680fd62d37378
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中配置呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

呼叫允许控制（CAC）是一种解决方案，它确定是否可以基于可用带宽来建立实时会话，以帮助防止拥挤的网络上的用户的音频/视频质量较差。 CAC 仅控制音频和视频的实时流量，不会影响数据流量。 如果默认 WAN 路径不具有所需的带宽，则 CAC 可以通过 Internet 路径路由呼叫。 有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)。

本节提供了一组示例过程，这些过程阐释了如何在网络中部署和管理 CAC。

<div>


> [!IMPORTANT]  
> 在部署 CAC 之前，必须收集企业网络拓扑所需的所有信息，如以下示例所述：在规划文档中<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">收集 Lync Server 2013</A>中的呼叫允许控制的要求。 此外，请确保已安装并激活 CAC 组件，如在部署文档中的在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或 Standard Edition server</A>中所述。



</div>

<div>


> [!NOTE]  
> 本节中的所有 CAC 部署和管理示例都是使用 Lync Server 命令行管理程序来执行的。 或者，也可以使用 Lync Server 控制面板的 "<STRONG>网络配置</STRONG>" 部分管理 CAC。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置 CAC 的网络区域](lync-server-2013-configure-network-regions-for-cac.md)

  - [在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [在 Lync Server 2013 中配置 CAC 的网络站点](lync-server-2013-configure-network-sites-for-cac.md)

  - [将子网与 Lync Server 2013 中的 CAC 的网络站点关联](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [在 Lync Server 2013 中创建网络区域链接](lync-server-2013-create-network-region-links.md)

  - [在 Lync Server 2013 中创建网络 interregion 路由](lync-server-2013;-create-network-interregion-routes.md)

  - [在 Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)

  - [在 Lync Server 2013 中启用呼叫允许控制](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 的呼叫允许控制部署清单](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

