---
title: 启用远程呼叫控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9dac1765d017f16493dcaf2d38e792b615bc52b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>启用远程呼叫控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

远程呼叫控制使用户能够使用 Lync Server 2013 控制其桌面专用交换机（PBX）电话。 如果您在旧版环境中部署了远程呼叫控制并且想要迁移它的 Lync Server 2013，则需要执行以下任务：

1.  安装并配置 SIP/CSTA 网关以与 PBX 进行通信。 在部署 Lync Server 2013 试点池时，您需要执行此步骤。

2.  在合并拓扑并迁移策略和设置之后，请将 Lync Server 2013 配置为将 CSTA 请求路由到 SIP/CSTA 网关。 该步骤是自动迁移后要执行的手动步骤。 要配置 CSTA 请求的路由，请执行以下操作：
    
      - 删除旧版授权主机条目（在 Lync Server 2013 中称为 "*受信任的服务器项*"）。 如果要从旧版部署中迁移用户，请确保在 "Lync Server 2013" 引导池上配置新的受信任应用程序项之前，先删除为 SIP/CSTA 网关创建的所有现有授权主机条目。 有关如何删除旧版授权主机条目的详细信息，请参阅[删除授权主机条目](remove-an-authorized-host-entry.md)。
    
      - 为远程呼叫控制配置静态路由。 您可以为希望支持远程呼叫控制的单个池配置静态路由，也可以配置一个全局静态路由，以便未配置池级静态路由的每个池使用全局静态路由。 有关如何配置静态路由的详细信息，请参阅部署文档中的在[Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。
    
      - 在您希望支持远程呼叫控制的每个池中为远程呼叫控制配置受信任应用程序条目。 有关如何配置受信任的应用程序条目的详细信息，请参阅部署文档中的在[Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

3.  如果部署了使用传输控制协议（TCP）连接到 Lync Server 2013 的 SIP/CSTA 网关，请在拓扑生成器中定义网关的 IP 地址。 有关定义 IP 地址的详细信息，请参阅部署文档中的在[Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

4.  通过启用远程呼叫控制并分配线路服务器统一资源标识符（URI）和线路 URI，为 Lync 2013 用户配置远程呼叫控制。 将用户从旧版部署迁移到 Lync Server 2013 时，远程呼叫控制设置将随其他用户设置一起迁移。

5.  如果您在旧部署中自定义了通讯簿电话号码规范化规则，则完成策略和设置的自动迁移后，需要执行一些手动操作以迁移自定义的规范化规则。 如果未自定义规范化规则，通讯簿将随拓扑的其余部分一起迁移。 有关手动迁移自定义规范化规则的详细信息，请参阅[Migrate Address Book](migrate-address-book_1.md)。

</div>

<span> </span>

</div>

</div>

</div>

