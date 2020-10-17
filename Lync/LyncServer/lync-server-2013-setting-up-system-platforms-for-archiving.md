---
title: Lync Server 2013：设置用于存档的系统平台
description: Lync Server 2013：设置用于存档的系统平台。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554178"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中设置用于存档的系统平台

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

在开始部署存档之前，您必须在满足系统要求的硬件上安装必要的操作系统以及任何其他必备软件：

  - **Lync Server 2013 平台**    Lync Server 2013 部署没有存档服务器。 但是，统一数据收集代理会在前端服务器和 Standard Edition 服务器上运行以捕获要存档的数据，所以不需要单独的系统平台来承载存档功能。

  - **数据存储平台**    在 Lync Server 2013 中，可以使用以下两种方法之一来存储数据：
    
      - **Microsoft Exchange 集成**    如果要使用 Exchange 2013 部署来存储 Lync Server 2013 存档数据，而不是或除了设置单独的数据库来存储存档数据，则 Exchange 部署必须运行 Exchange 2013。 有关为 Exchange 2013 设置系统平台的详细信息，请参阅 Exchange 产品文档。
    
      - **SQL Server**    如果要将单独的 SQL Server 数据库用于存储存档数据，而不是或除了使用 Microsoft Exchange 集成，则必须在部署存档之前为数据库设置系统平台。 特定的系统平台要求取决于是否对存档数据库使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。 有关为这些数据库设置系统平台的详细信息，请参阅 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 产品文档。

  - **文件服务器平台**    Lync Server 2013 将 Lync Server 存档文件存储在您在设置前端服务器或 Standard Edition 服务器时为文件存储指定的同一位置。 您无法为存档文件存储指定其他位置，所以不需要单独的系统平台存档文件存储。 如果使用 Microsoft Exchange 集成，则 Exchange 2013 文件的存档 Lync 通信将存储在 Exchange 2013 服务器上，以供驻留在这些 Exchange 服务器上的用户使用。

</div>

<span> </span>

</div>

</div>

</div>

