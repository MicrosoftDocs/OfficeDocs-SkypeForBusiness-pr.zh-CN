---
title: Lync Server 2013：配置 Microsoft Exchange Server 统一消息以与 Lync Server 2013 一起工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>配置 Microsoft Exchange Server 统一消息以与 Lync Server 2013 一起工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-11_

<div>


> [!IMPORTANT]  
> 如果要使用 Exchange 统一消息 (UM) 为企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务, 请阅读规划<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">中 Lync Server 2013 中的 Exchange 统一消息集成的规划</A>文档, 然后按照本部分中的说明进行操作。



</div>

要将 Exchange 统一消息 (UM) 配置为使用企业语音, 你需要执行以下任务:

  - 在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书
    
    <div>
    

    > [!NOTE]  
    > 将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。 如果不是, 则出站呼叫路由不会按预期工作。

    
    </div>

  - 创建一个或多个 UM SIP URI 拨号计划, 以及订阅者按需访问电话号码, 然后创建相应的 Lync 服务器拨号计划。

  - 使用**exchucutil**脚本执行以下操作:
    
      - 创建 UM IP 网关。
    
      - 创建 UM 查寻组。
    
      - 授予 Lync Server 2013 权限以读取 UM Active Directory 域服务对象。

  - 创建 UM 自动助理对象。

  - 创建订阅者访问对象。

  - 为每个用户创建 SIP URI 并将用户与 UM SIP URI 拨号计划相关联。

<div>

## <a name="requirements-and-recommendations"></a>要求与建议

开始之前, 本部分中的文档假定你已部署以下 Exchange 2013 角色: 客户端访问和邮箱。 在 Microsoft Exchange Server 2013 中, Exchange UM 在这些服务器上作为一项服务运行。

有关部署 Exchange 2013 的详细信息, 请参阅 Exchange 2013 TechNet 库[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

另请注意以下事项:

  - 如果 Exchange UM 安装在多个林中, 则必须为每个 UM 林执行 Exchange Server 集成步骤。 此外, 必须将每个 UM 林配置为信任在其中部署 Lync Server 2013 的林, 并且必须将用于部署 Lync Server 2013 的林配置为信任每个 UM 林。

  - 在运行统一消息服务的 Exchange 服务器角色上以及运行 Lync Server 2013 的服务器上执行集成步骤。 在执行 Lync Server 2013 集成步骤之前, 应执行 Exchange Server 统一消息集成步骤。
    
    <div>
    

    > [!NOTE]  
    > 若要查看在哪些服务器及其管理员角色上执行哪些集成步骤, 请参阅<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。

    
    </div>

以下工具必须在运行 Exchange UM 的每台服务器上可用:

  - Exchange 命令行管理程序

  - 脚本**exchucutil**, 它执行以下任务:
    
      - 为每个 Lync Server 2013 创建 UM IP 网关。
    
      - 为每个网关创建一个查寻组。 每个查寻组的引导标识符指定与网关相关联的前端池或标准版服务器使用的 UM SIP URI 拨号计划。
    
      - 授予 Lync Server 2013 权限以读取 Active Directory 域服务中的 Exchange UM 对象。

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在运行 Microsoft Exchange Server 统一消息的服务器上配置证书](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [在 Microsoft Exchange for Lync Server 2013 上配置统一消息](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

