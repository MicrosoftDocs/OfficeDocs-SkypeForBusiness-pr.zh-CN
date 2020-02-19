---
title: Lync Server 2013：部署概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33328e124a1b444b4639b85bc6c1941c55f5ed1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 部署概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-12_

Lync Server 2013 Enterprise Edition 和 Lync Server 2013 Standard Edition 的主要区别在于，Standard Edition 不支持企业版中包含的高可用性功能。 为实现高可用性，您需要将多个前端服务器部署到一个池，然后可以镜像运行 SQL Server 的服务器。 使用 Enterprise Edition，可以选择并置或定义独立的中介服务器。 监视服务器和存档服务器可以使用运行 SQL Server 的独立服务器。 或者，它们可以在数据库服务器上为前端服务器和池运行 SQL Server 实例。

运行 Lync Server 2013 Standard Edition 的服务器适用于从组织的主部署中删除的地理位置较小的组织和远程位置。 在灾难发生时，将两个标准版服务器服务器结合在一起进行故障转移，以支持最高为5000个用户。 您无法像企业版中的前端服务器那样池标准版服务器。 此外，Standard Edition 使用的 SQL Server 数据库是运行 SQL Server Express 的并置服务器，旨在处理 Standard Edition Server 工作负载。 这并不是说所有角色都必须驻留在 Standard Edition 服务器上。 您可以有独立的中介服务器和边缘服务器。 中央管理存储的 SQL Server 数据库和用于 Lync Server 2013 的目的必须驻留在 Standard Edition server 并置和运行 SQL Server 的服务器上。 监视服务器和存档服务器将独立服务器与 SQL Server 数据库一起使用。

</div>

<span> </span>

</div>

</div>

</div>

