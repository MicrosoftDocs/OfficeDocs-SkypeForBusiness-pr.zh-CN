---
title: Lync Server 2013：本地统一消息的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543af1cc9b4dbb437b36273945f9f2cb6112c6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 中的本地统一消息的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-25_

本主题介绍了向 Lync Server 2013 部署提供 Exchange 统一消息（UM）功能所需的 Microsoft Exchange Server 2013 组件。 此外，它还介绍了本地 Exchange UM 集成支持的拓扑。

<div>

## <a name="exchange-server-components"></a>Exchange Server 组件

若要将[集成统一消息和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)中所述的 Exchange UM 功能和服务提供给组织中的企业语音用户，您必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，以承载用户邮箱并为电子邮件和语音邮件提供一个存储位置。 Exchange UM 在 Exchange 邮箱和客户端访问服务器上作为一项服务运行。

有关 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅部署文档中的[部署本地 EXCHANGE um 以提供 Lync Server 2013 语音邮件](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

您可以在同一个林中或多个林中部署 Lync Server 2013 和 Exchange 统一消息（UM）。 如果部署跨越多个林，则必须为每个 Exchange UM 林执行 Exchange 集成步骤。 此外，还必须将每个 Microsoft Exchange 林配置为信任 Lync Server 2013 林，并将 Lync Server 2013 林配置为信任每个 Exchange UM 林。 除了此林信任之外，还必须对 Lync Server 2013 林中的用户对象设置所有用户的 Exchange UM 设置。

Lync Server 2013 支持 Exchange UM 集成的以下拓扑：

  - 单林

  - 单域（即具有单个域的单林）。 Lync Server 2013、Microsoft Exchange 和用户都驻留在同一域中。

  - 多域（即具有一个或多个子域的根域）。 Lync Server 2013 和 Microsoft Exchange 服务器部署在您创建用户的域的不同域中。 Exchange UM 服务器可以部署在其支持的 Lync Server 2013 池的不同域中。

  - 多林（即资源林）。 在单个林中部署 Lync Server 2013，然后在多个林分布用户。 用户的 Exchange UM 属性必须复制到 Lync Server 2013 林。
    
    <div>
    

    > [!NOTE]  
    > 可在多个林中部署 Exchange。 每个 Exchange 组织可以向其用户提供 Exchange UM，也可以将 Exchange UM 部署在与 Lync Server 2013 相同的林中。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

