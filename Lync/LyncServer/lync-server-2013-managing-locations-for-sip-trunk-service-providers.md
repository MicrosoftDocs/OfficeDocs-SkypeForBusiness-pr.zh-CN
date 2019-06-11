---
title: 'Lync Server 2013: 管理 SIP 中继服务提供商的位置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>在 Lync Server 2013 中管理 SIP 中继服务提供商的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

若要将 Lync Server 配置为自动查找网络中的客户端, 你需要使用网络 wiremap 填充位置信息服务数据库并发布位置, 或者链接到已包含正确的外部数据库镜像. 作为此过程的一部分，您需要通过 E9-1-1 服务提供商来验证这些位置的城市地址。 有关详细信息, 请参阅在部署文档中的[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。

您可使用紧急响应位置 (ERL) 填充位置信息服务数据库，紧急响应位置由城市地址和建筑物内的特定地址构成。 "位置信息服务**位置**" 字段是建筑物内的特定位置, 最大长度为20个字符 (包括空格)。 在该有限长度内，尽量包含以下内容：

  - 一个易于理解的名称，用于标识 911 呼叫者的位置，以帮助确保紧急响应者在到达该城市地址后迅速找到特定位置。此位置名称可能包括建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，否则可能导致紧急响应者去往错误的位置。

  - 一个位置标识符, 可帮助用户轻松地查看其 Lync 客户端是否已挑选正确的位置。 Lync 客户端将自动连接, 并在其标题中显示发现的**位置**和**城市**字段。 最佳做法是将建筑物的街道地址添加到每个位置标识符 (例如, "第一个楼层\<号\>")。 如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。

  - 如果位置是一个大概位置（因为它是由无线访问点决定的），您可能需要添加词  Near（例如“Near 1st Floor 1234”）。

<div>


> [!NOTE]  
> 添加到中心位置数据库的位置在使用 Lync Server Management Shell 命令发布之前不可用于客户端, 并且将复制到该池的本地存储区。 有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-publish-the-location-database.md">从 Lync Server 2013 发布位置数据库</A>。



</div>

以下各节讨论填充和维护位置数据库时需要考虑的注意事项。

<div>

## <a name="populating-the-location-database"></a>填充位置数据库

以下问题可帮助您确定如何填充位置数据库。

  - **使用什么过程填充位置数据库？**  
    数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？

<!-- end list -->

  - **是否有已包含位置映射的第三方数据库？**  
    通过使用 Lync Server 的辅助位置信息服务选项连接到第三方数据库, 您可以使用脱机平台对位置进行分组和管理。 除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。 这意味着, 位置信息服务可以将来自辅助位置信息服务的多个地址返回到 Lync Server 客户端。 然后，用户可以选择最适合的位置。
    
    若要与位置信息服务集成, 第三方数据库必须遵循 Lync Server 位置请求/响应架构。 有关详细信息, 请\[参阅的 "\]MS-E911WS: Web Services For E911 支持协议<http://go.microsoft.com/fwlink/p/?linkid=213819>规范"。 有关部署辅助位置信息服务的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "配置辅助位置信息" 服务](lync-server-2013-configure-a-secondary-location-information-service.md)。

有关填充位置数据库的详细信息, 请参阅在部署文档中的[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。

  - **如何更新位置数据库？**  
    有许多情形需要更新位置数据库，包括添加 WAP、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？

<!-- end list -->

  - **是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符匹配？**  
    如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回数据库中未包含的机箱 IP 地址或端口 ID, 则位置信息服务将无法将位置返回到客户端。

</div>

</div>

<span> </span>

</div>

</div>

</div>

