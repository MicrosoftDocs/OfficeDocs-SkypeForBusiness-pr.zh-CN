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
ms.openlocfilehash: 88ed32ed07f709e0a047e8fc07e9124bc129adca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>在 Lync Server 2013 中获取位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

在 Lync Server 2013 E9-1-1 部署中，每个与内部连接的 Lync 或 Lync Phone Edition 客户端主动获取其自己的位置。 在 SIP 注册之后，客户端会将其在位置请求中了解到的所有网络连接信息提供到位置信息服务，这是由复制的 SQL Server 数据库支持的 web 服务。 每个中央站点池都有一个位置信息服务，该服务使用网络信息在其记录中查询匹配的位置。 如果存在匹配项，则 Location 信息服务将向客户端返回一个位置。 如果没有匹配项，则可能提示用户手动输入位置（取决于位置策略设置）。 位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式传输回客户端，称为“状态信息数据格式位置对象 (PIDF-LO)”。

Lync Server 客户端在紧急呼叫中包含 PIDF-LO-LO 数据，E9-1-1 服务提供商使用此数据来确定相应的 PSAP 并将呼叫路由到该 PSAP 以及正确的 ESQK，这将允许 PSAP 发送器获取呼叫者的位置。

下图显示了 Lync Server 客户端如何获取位置（基于第三方客户端 MAC 地址的 location 方法除外）：

![客户端如何获取位置图](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "客户端如何获取位置图")

对于获取位置的客户端，必须执行下列步骤：

1.  管理员使用网络线路映射（将各种类型的网络地址映射到相应的紧急响应位置（Erl））填充位置信息服务数据库。

2.  如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。

3.  在注册过程中或在网络发生更改时，内部连接的客户端将包含客户端发现的网络地址的位置请求发送到 Location 信息服务。

4.  位置信息服务查询某个位置的已发布记录，如果找到匹配项，则以 PIDF-LO 格式将 ERL 返回给客户端。

</div>

<span> </span>

</div>

</div>

</div>

