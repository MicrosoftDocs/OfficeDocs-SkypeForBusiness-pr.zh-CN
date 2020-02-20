---
title: Lync Server 2013：管理 SIP 中继服务提供商的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8be19c6ca5aad78bc82487d8208fb163f62fbcb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>在 Lync Server 2013 中管理 SIP 中继服务提供商的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

若要将 Lync Server 配置为自动在网络中查找客户端，您需要使用网络线路映射填充位置信息服务数据库并发布位置，或链接到已包含正确的外部数据库映射. 作为此过程的一部分，您需要验证 E9-1-1 服务提供商的位置的市政地址。 有关详细信息，请参阅部署文档中的在[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。

使用紧急响应位置（ERL）填充 Location 信息服务数据库，其中包含市政地址和建筑物内的特定地址。 "位置信息服务**位置**" 字段是建筑物内的特定位置，最大长度为20个字符（包括空格）。 在该有限的长度内，请尝试包括以下内容：

  - 一个易于理解的、指示 911 呼叫者的位置的名称，以帮助确保紧急响应者到达市政地址后能够迅速找到具体位置。此位置名称可能包括楼号、楼层数、侧楼标识、房间号码等等。应避免使用仅员工知晓的昵称，这样可能导致紧急响应者找错位置。

  - 位置标识符，以帮助用户轻松了解他们的 Lync 客户端是否选择了正确的位置。 Lync 客户端自动连接并在其标头中显示发现的 **Location** 和 **City** 字段。 一种好的做法是将建筑物的街道地址添加到每个位置标识符（例如，"第一\<层街道\>号"）。 如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。

  - 如果该位置是近似值，因为它是由无线访问点确定的，则可以将该单词添加到附近（例如，"靠近第一层 1234"）。

<div>


> [!NOTE]  
> 在使用 Lync Server 命令行管理程序命令发布添加到中心位置数据库的位置，并将这些位置复制到池的本地存储区之前，这些位置将不可用于客户端。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-publish-the-location-database.md">从 Lync Server 2013 发布位置数据库</A>。



</div>

以下各节讨论在填充和维护位置数据库时需要考虑的注意事项。

<div>

## <a name="populating-the-location-database"></a>填充位置数据库

以下问题可帮助您确定如何填充位置数据库。

  - **使用什么过程填充位置数据库？**  
    数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？

<!-- end list -->

  - **是否具有已包含位置映射的第三方数据库？**  
    通过使用 Lync Server 的辅助位置信息服务选项连接到第三方数据库，可以使用脱机平台对位置进行分组和管理。 此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。 这意味着 Location 信息服务可将来自辅助位置信息服务的多个地址返回到 Lync Server 客户端。 然后用户可以选择最合适的位置。
    
    若要与 Location 信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。 有关详细信息，请\[参阅中的\]"MS-Ms-e911ws： E911 的 Web 服务支持<https://go.microsoft.com/fwlink/p/?linkid=213819>协议规范"。 有关部署辅助位置信息服务的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置辅助位置信息服务](lync-server-2013-configure-a-secondary-location-information-service.md)。

有关填充位置数据库的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。

  - **如何更新位置数据库？**  
    有几种情况需要更新位置数据库，包括添加 Wap、office 缆线（导致不同的交换机分配）和子网扩展。 是直接更新各个位置，还是使用 CSV 文件执行所有位置的批量更新？

<!-- end list -->

  - **是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符进行匹配？**  
    如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回的是未包含在数据库中的机箱 IP 地址或端口 ID，则位置信息服务将无法向客户端返回一个位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

