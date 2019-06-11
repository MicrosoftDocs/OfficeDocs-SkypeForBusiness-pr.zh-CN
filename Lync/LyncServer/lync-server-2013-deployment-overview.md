---
title: Lync Server 2013：部署概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 部署概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-12_

Lync Server 2013 企业版和 Lync Server 2013 标准版之间的主要区别是标准版不支持企业版中包含的高可用性功能。 为了获得高可用性, 你需要将多个前端服务器部署到一个池, 然后你可以镜像运行 SQL Server 的服务器。 使用企业版, 您可以选择 collocate 或定义独立的中介服务器。 监视服务器和存档服务器可以使用运行 SQL Server 的独立服务器。 或者, 他们可以在数据库服务器上为前端服务器和池运行 SQL Server 实例。

运行 Lync Server 2013 标准版的服务器适用于从组织的主部署中删除的较小组织和远程位置。 在灾难情况下, 将两个标准版服务器服务器结合在一起以进行故障转移, 从而支持最多5000用户。 不能像企业版中的前端服务器那样对标准版服务器进行池化。 此外, 标准版使用的 SQL Server 数据库是运行 SQL Server Express 的 collocated 服务器, 设计用于处理标准版服务器工作负荷。 这并不是说所有角色必须驻留在标准版服务器上。 你可以有独立的中介服务器和边缘服务器。 用于中央管理存储的 SQL Server 数据库和适用于 Lync Server 2013 的用途必须驻留在标准版服务器 collocated 上, 并与运行 SQL Server 的服务器配合。 监视服务器和存档服务器将独立服务器与 SQL Server 数据库结合使用。

</div>

<span> </span>

</div>

</div>

</div>

