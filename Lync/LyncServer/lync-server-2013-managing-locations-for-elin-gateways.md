---
title: Lync Server 2013：管理 ELIN 网关的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>在 Lync Server 2013 中管理 ELIN 网关的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

若要使 Lync 服务器自动为网络内的客户端提供位置，需要执行以下任务：

  - 使用网络 wiremap 填充位置信息服务数据库，并在 "公司名称" 字段中包含紧急位置标识号（ELINs）。

  - 发布位置，以供网络中的客户端使用。

  - 将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。

有关如何执行这些任务的详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置位置数据库"](lync-server-2013-configure-the-location-database.md) 。

<div>


> [!NOTE]  
> 添加到中心位置数据库的位置在使用 Lync Server Management Shell 命令发布并复制到池中的本地存储之前，不能用于客户端。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-publish-the-location-database.md">从 Lync Server 2013 发布位置数据库</A>。



</div>

本节介绍在计划更新和维护位置数据库时要考虑的事项。

<div>

## <a name="planning-emergency-locations"></a>规划紧急位置

使用 ELIN 网关时，将使用市政地址、建筑物内的特定位置和每个位置至少一个 ELIN 填充位置信息服务数据库。 在规划阶段，最好决定想要如何命名位置和分配 ELIN。

<div>

## <a name="planning-location-names"></a>规划位置名称

"位置信息服务**位置**" 字段（用于保存建筑物内的特定位置）的最大长度为20个字符（包括空格）。 在该限制长度内，尽量包括以下内容：

  - 一个容易理解的名称，用于标识 911 呼叫者的位置，以确保紧急响应者在到达市政地址后能迅速找到具体位置。此位置名称可包含建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，以防紧急响应者去往错误的位置。

  - 一个位置标识符，可帮助用户轻松地查看其 Lync 客户端是否已挑选正确的位置。 Lync 客户端将自动连接，并在其标题中显示发现的**位置**和**城市**字段。 最佳做法是将建筑物的街道地址添加到每个位置标识符（例如，"第一个楼层\<号\>"）。 如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。

  - 如果位置是一个大概位置（因为它是由无线访问点决定的），您可能需要添加词 Near（例如，“Near 1st Floor 1234”）。

</div>

<div>

## <a name="planning-elins"></a>规划 ELIN

在您决定想要如何将建筑物空间分成多个位置后，需要决定为每个位置分配多少个 ELIN。例如，在多层或多租户建筑物中，可以为建筑物中不同的区域分配不同的紧急区域。通常，建筑物的每层都会被指定为一个位置。每个位置会被分配一个或多个 ELIN，这些 ELIN 用作紧急呼叫时的呼叫号码。请联系您的 PSTN 运营商以获得可用于 ELIN 的电话号码。下表提供了特定街道地址的位置示例。

### <a name="sample-location-and-elin-assignments"></a>位置和 ELIN 分配示例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>建筑物区域</th>
<th>位置</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>第一层</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>第二层</p></td>
<td><p>ppls-2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>第三层</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


您定义的位置应满足以下要求：

  - 在每位置最大区域和每街道地址位置数方面符合当地和国家/地区法规。

  - 足够详细到能够轻松找到紧急呼叫者。

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>填充位置数据库

以下问题将帮助您确定如何填充位置数据库。

  - **使用什么过程填充位置数据库？**  
    数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？

<!-- end list -->

  - **是否有已包含位置映射的第三方数据库？**  
    通过使用 Lync Server 的辅助位置信息服务选项连接到第三方数据库，您可以使用脱机平台对位置进行分组和管理。 除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。 这意味着，位置信息服务可以将来自辅助位置信息服务的多个地址返回到 Lync Server 客户端。 然后，用户可以选择最适合的位置。
    
    若要与位置信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。 有关详细信息， <http://go.microsoft.com/fwlink/p/?linkid=213819>请参阅。 有关部署辅助位置信息服务的详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置辅助位置信息" 服务](lync-server-2013-configure-a-secondary-location-information-service.md)。

有关填充位置数据库的详细信息，请参阅在部署文档中的[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。

</div>

<div>

## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。

  - **如何更新位置数据库？**  
    有许多方案需要更新位置数据，包括添加无线接入点 (WAP)、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？

<!-- end list -->

  - **是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符匹配？**  
    如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回数据库中未包含的机箱 IP 地址或端口 ID，则位置信息服务将无法将位置返回到客户端。

</div>

</div>

<span> </span>

</div>

</div>

</div>

