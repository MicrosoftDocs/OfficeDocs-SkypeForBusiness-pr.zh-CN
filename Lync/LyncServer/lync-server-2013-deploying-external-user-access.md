---
title: Lync Server 2013：部署外部用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960f5d895f821e8d9bbc6fa71f451ee455d88388
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中部署外部用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-23_

为 Microsoft Lync Server 2013 部署边缘组件使未登录到组织内部网络的外部用户（包括经过身份验证和匿名的远程用户、联盟伙伴（包括 XMPP 合作伙伴））可以使用 Lync Server 与组织中的其他用户通信的移动客户端和公共即时消息（IM）服务的用户。 Lync Server 2013 的部署和配置过程与 Lync Server 2010 没有显著不同。 安装和管理工具与 Lync Server 2010 中的工具非常相似。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013&nbsp;边缘服务器安装和配置可能是一个复杂的过程，需要与内部团队进行大量的规划和协调，包括但不限于安全性、网络、防火墙、域名系统（DNS）、负载平衡器和公钥基础结构（PKI）的注意事项。 强烈建议您先查看并使用提供的规划过程和文档，然后再部署外部访问组件。 这将有助于在您执行部署过程时限制意外更改和问题的数量和频率。 有关规划外部用户访问的信息，请参阅<A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中规划外部用户访问</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的外部用户访问的部署清单](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013 的外部用户访问组件的系统要求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [准备在外围网络中为 Lync Server 2013 安装服务器](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [在 Lync Server 2013 中构建边缘和控制器拓扑](lync-server-2013-building-an-edge-and-director-topology.md)

  - [在 Lync Server 2013 中设置控制器](lync-server-2013-setting-up-the-director.md)（可选）

  - [在 Lync Server 2013 中设置边缘服务器](lync-server-2013-setting-up-edge-servers.md)

  - [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 中的 Lync-Skype 连接的预配指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [在 Lync Server 2013 中部署移动功能](lync-server-2013-deploying-mobility.md)

  - [在 Lync Server 2013 中验证边缘部署](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

