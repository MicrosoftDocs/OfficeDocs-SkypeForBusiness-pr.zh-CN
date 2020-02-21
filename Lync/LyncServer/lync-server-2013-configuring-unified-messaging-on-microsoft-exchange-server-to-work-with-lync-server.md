---
title: Lync Server 2013：在 Microsoft Exchange Server 上配置统一消息以与 Lync Server 一起使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3d90f738741c2815d01041a7d2293e978cd2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>在 Microsoft Exchange Server 上配置统一消息以使用 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-11_

<div>


> [!IMPORTANT]  
> 如果要使用 Exchange 统一消息（UM）为企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务，请阅读规划文档中的<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 中的 Exchange 统一消息集成规划</A>，然后按照本节中的说明进行操作。



</div>

若要将 Exchange 统一消息（UM）配置为使用企业语音，您需要执行以下任务：

  - 在运行 Exchange 统一消息（UM）服务的服务器上配置证书
    
    <div>
    

    > [!NOTE]  
    > 将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。 如果不是，出站呼叫路由将无法按预期工作。

    
    </div>

  - 创建一个或多个 UM SIP URI 拨号计划，以及订阅者访问电话号码（根据需要），然后创建相应的 Lync Server 拨号计划。

  - 使用**exchucutil.ps1**脚本执行以下操作：
    
      - 创建 UM IP 网关。
    
      - 创建 UM 智能寻线。
    
      - 授予 Lync Server 2013 读取 UM Active Directory 域服务对象的权限。

  - 创建 UM 自动助理对象。

  - 创建订阅者访问对象。

  - 为每个用户创建 SIP URI，并将用户与 UM SIP URI 拨号计划关联。

<div>

## <a name="requirements-and-recommendations"></a>要求与建议

在开始之前，本节中的文档假定您已部署以下 Exchange 2013 角色：客户端访问和邮箱。 在 Microsoft Exchange Server 2013 中，Exchange UM 在这些服务器上作为一项服务运行。

有关部署 Exchange 2013 的详细信息，请参阅位于的 Exchange 2013 TechNet 库[https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

另外还需注意以下事项：

  - 如果 Exchange UM 安装在多个林中，则必须为每个 UM 林执行 Exchange Server 集成步骤。 此外，必须将每个 UM 林配置为信任在其中部署 Lync Server 2013 的林，并且必须将部署 Lync Server 2013 的林配置为信任每个 UM 林。

  - 在运行统一消息服务的 Exchange 服务器角色上以及运行 Lync Server 2013 的服务器上执行集成步骤。 在执行 Lync Server 2013 集成步骤之前，应执行 Exchange Server 统一消息集成步骤。
    
    <div>
    

    > [!NOTE]  
    > 若要查看在哪些服务器和管理员角色上执行哪些集成步骤，请参阅<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。

    
    </div>

以下工具必须在每台运行 Exchange UM 的服务器上可用：

  - Exchange 命令行管理程序

  - 脚本 **exchucutil.ps1**，它将执行以下任务：
    
      - 为每个 Lync Server 2013 创建 UM IP 网关。
    
      - 为每个网关创建一个智能寻线。 每个查寻组的引导标识符指定与网关关联的前端池或 Standard Edition 服务器使用的 UM SIP URI 拨号计划。
    
      - 授予 Lync Server 2013 在 Active Directory 域服务中读取 Exchange UM 对象的权限。

</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在运行 Microsoft Exchange Server 统一消息的服务器上配置证书](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

