---
title: Lync Server 2013：设置用于存档的系统平台
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
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中设置用于存档的系统平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

在开始部署存档之前，必须在满足系统要求的硬件上安装所需的操作系统和任何其他必备软件：

  - **Lync server 2013 平台**   Lync server 2013 部署没有存档服务器。 相反，统一的数据收集代理运行在前端服务器和标准版服务器上以捕获用于存档的数据，因此不需要单独的系统平台来托管存档。

  - **数据存储平台**   在 Lync Server 2013 中，可以通过以下任一操作来存储数据：
    
      - **Microsoft Exchange 集成**   如果你想要使用 Exchange 2013 部署来存储 Lync Server 2013 存档数据，而不是设置单独的数据库以存储存档数据，则 exchange 部署必须运行 exchange 2013。 有关为 Exchange 2013 设置系统平台的详细信息，请参阅 Exchange 产品文档。
    
      - **SQL server**   如果要使用单独的 SQL server 数据库存储存档数据，而不是使用 Microsoft Exchange 集成，则必须在部署存档之前为数据库设置系统平台。 特定系统平台要求取决于您对存档数据库使用的是 Microsoft SQL Server 2008 R2 还是 Microsoft SQL Server 2012。 有关为这些数据库设置系统平台的详细信息，请参阅 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 产品文档。

  - **文件服务器平台**   Lync server 2013 将 lync server 存档文件存储在设置前端服务器或标准版服务器时为文件存储指定的相同位置。 不能为存档文件存储指定单独的位置，因此存档文件存储不需要单独的系统平台。 如果你使用 Microsoft Exchange 集成，Exchange 2013 将为存档的 Lync 通信的文件存储在 Exchange 2013 服务器上，供驻留在这些 Exchange 服务器上的用户使用。

</div>

<span> </span>

</div>

</div>

</div>

