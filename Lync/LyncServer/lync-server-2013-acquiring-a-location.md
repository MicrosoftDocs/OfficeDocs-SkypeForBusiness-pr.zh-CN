---
title: Lync Server 2013：获取位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>在 Lync Server 2013 中获取位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-06_

在 Lync Server 2013 E9 部署中，每个内部连接的 Lync 或 Lync Phone 版客户端都将主动获取其自己的位置。 在 SIP 注册后，客户端 furnishes 在位置信息服务（即由复制的 SQL Server 数据库支持的 web 服务）的位置请求中对其自身知道的所有网络连接信息。 每个中心网站池都有一个位置信息服务，该服务使用网络信息查询匹配位置的记录。 如果存在匹配项，则 Location 信息服务将向客户端返回一个位置。 如果没有匹配项，则可能会提示用户手动输入位置（取决于位置策略设置）。 位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式（称为状态信息数据格式位置对象 (PIDF-LO)）传回客户端。

Lync Server 客户端将 PIDF 数据作为紧急呼叫的一部分包括在紧急呼叫中，此数据由 E9 服务提供商用于确定相应的 PSAP 并将该 PSAP 的调用路由到该以及正确的 ESQK，从而允许 PSAP dispatcher 获取呼叫方的位置。

下图显示了 Lync Server 客户端如何获取位置（除第三方基于客户端 MAC 地址的位置方法除外）：

![客户端获取位置的方式的图示](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "客户端获取位置的方式的图示")

对于获取位置的客户端，必须执行下列步骤：

1.  管理员通过网络 wiremap 填充位置信息服务数据库（将各种类型的网络地址映射到相应的紧急响应位置（ERLs））的表。

2.  如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。

3.  在注册期间或网络更改发生时，内部连接的客户端会将包含客户发现的网络地址的位置请求发送到位置信息服务。

4.  位置信息服务查询某个位置的已发布记录，如果找到匹配项，则以 PIDF 格式将 ERL 返回到客户端。

</div>

<span> </span>

</div>

</div>

</div>

