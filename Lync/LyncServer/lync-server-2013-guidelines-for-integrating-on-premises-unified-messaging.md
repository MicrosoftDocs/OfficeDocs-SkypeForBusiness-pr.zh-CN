---
title: Lync Server 2013：集成本地统一消息的准则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be763250edf7222b900aef88665b3e360e8125c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>集成本地统一消息和 Lync Server 2013 的准则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-25_

以下是在部署企业语音时要考虑的准则和最佳实践：

<div>


> [!IMPORTANT]  
> 仅当您还使用 UCMA 4 时，Exchange 统一消息（UM）才支持 IPv6。



</div>

  - 部署 Lync Server 2013 Standard Edition server 或前端池。 有关安装的详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

  - 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。

  - 在要为其启用 Exchange UM 的用户的每个 Exchange 统一消息（UM）林中部署 Exchange 邮箱服务器角色。 有关安装 Exchange server 角色的详细信息，请参阅 Microsoft Exchange Server 2013 文档。
    
    <div>
    

    > [!IMPORTANT]  
    > 安装 Exchange 统一消息（UM）后，会将其配置为使用自签名证书。<BR>但是，自签名证书不启用 Lync Server 2013 和 Exchange UM 相互信任，这就是为什么需要从两个服务器信任的证书颁发机构请求单独的证书的原因。

    
    </div>

  - 如果 Lync Server 2013 和 Exchange UM 安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林，并将 Lync Server 2013 林信任每个 Exchange 林。 此外，还可以在 Lync Server 2013 林中的 user 对象上设置用户的 Exchange UM 设置，这通常是通过使用脚本或跨林工具（如身份生命周期管理器（ILM））进行的。

  - 必要时，安装 Exchange 管理控制台以管理统一消息服务器。

  - 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。

  - 如果使用早于 Microsoft Exchange Server 2010 Service Pack 1 （SP1）的 Exchange UM 版本，则 Exchange UM SIP URI 拨号计划和企业语音拨号计划的名称。

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>部署冗余 Exchange UM 服务器

<div>


> [!IMPORTANT]  
> 我们建议您为您的组织配置的每个 Exchange UM SIP URI 拨号计划至少部署两台 Exchange UM 服务所运行的服务器。 除了提供扩展容量之外，部署冗余服务器还可提供高可用性。 如果服务器发生故障，可将 Lync Server 2013 配置为故障转移到另一台服务器。



</div>

以下示例配置提供 Exchange UM 恢复能力。

**示例 1：Exchange UM 恢复能力**

![Exchange UM 示例1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 示例1")

在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。 如果 Tukwila 中发生 Exchange UM 中断，域名系统（DNS）应将服务器1和2的一条记录配置为分别指向服务器3和4。 在都柏林的 Exchange UM 发生故障的情况下，应将服务器3和4的 DNS A 记录配置为分别指向 "服务器 1" 和 "2"。

<div>


> [!NOTE]  
> 对于示例 1，还应在每台 Exchange UM 服务器上分配以下证书之一： 
> <UL>
> <LI>
> <P>在使用者替代名称 (SAN) 中使用具有通配符的证书。</P>
> <LI>
> <P>将 SAN 中四个 Exchange UM 服务器的完全限定域名（FQDN）。</P></LI></UL>



</div>

**示例 2：Exchange UM 恢复能力**

![Exchange UM 示例2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 示例2")

在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。

有关如何在 Exchange 2013 上启用或禁用统一消息的详细信息，请参阅位于上[http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)的 "将 EXCHANGE 2013 UM 与 Lync Server 集成"。

有关如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息的详细信息，请参阅：

  - "在[http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)Exchange 2010 上启用统一消息"。

  - "在[http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)Exchange 2010 上禁用统一消息"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[集成本地统一消息和 Lync Server 2013 的部署过程](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

