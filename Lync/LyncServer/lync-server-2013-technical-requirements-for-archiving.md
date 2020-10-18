---
title: Lync Server 2013：存档的技术要求
description: Lync Server 2013：存档的技术要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6100753ad2c62424eb68c8c258094ba51848170e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577168"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中存档的技术要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

Lync Server 2013 技术要求包括以下各项：

  - 基础结构要求。

  - 存档所必须安装的必备软件。

  - 存档的数据存储要求。

  - 存档部署的缩放要求和注意事项。

  - 存档数据库的性能要求和注意事项。

<div>


> [!NOTE]  
> 此 Lync Server 2013 版本中不提供缩放和性能信息。



</div>

<div>

## <a name="infrastructure-requirements"></a>基础结构要求

Lync Server 2013 存档基础结构要求与部署 Lync Server 2013 的要求相同。 有关详细信息，请参阅规划文档中的 [确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md) 。

</div>

<div>

## <a name="archiving-prerequisites"></a>存档必备组件

Lync Server 2013 出于以下原因，简化了存档的先决条件：

  - 存档服务器不再是服务器角色。相反，统一数据收集代理在池中的前端服务器和 Standard Edition 服务器上运行以捕获存档数据，因此您无需针对存档设置单独的系统平台。

  - 存档将 Lync Server 2013 文件存储用于会议内容文件的临时存储，因此您不需要为存档设置单独的文件存储。

  - 在 Lync Server 2013 中，不需要消息队列。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>存档的数据存储要求

此外，您需要为存档存储设置基础结构。这包括以下一个或两个存储：

  - **Microsoft Exchange 存储**。 会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。 如果要使用 Microsoft Exchange 集成，以便将 Lync 存档数据与 Exchange 合规性数据存储在一起，则必须将 Exchange 2013 用于 Exchange 部署，并确保最大存储大小支持存储会议内容文件。 如果使用 Microsoft Exchange 集成选项部署存档，Lync 存档数据将仅存储在 Exchange 2013 服务器上的用户的 Exchange 2013 合规性数据中。 在使用 Microsoft Exchange 集成选项部署和启用存档之前，必须部署 Exchange 2013。 如果选择使用 Exchange 2013 存储，则无需为存档部署单独的 SQL Server 数据库，除非您的 Lync 用户没有驻留在 Exchange 2013 服务器上。

  - **用于存档的 SQL Server 数据库存储**。 若要支持不驻留在 Exchange 2013 服务器上的用户，或者不希望使用 Microsoft Exchange 集成选项，则必须使用 SQL Server 数据库部署存档存储。 Lync Server 2013 支持以下64位版本的 SQL Server：
    
      - Microsoft SQL Server 2008 R2 企业版
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 企业版
    
      - Microsoft SQL Server 2012 标准版
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支持存档。 32位版本的 SQL Server 不受支持。 有关其他 SQL Server 要求和限制，请参阅规划文档中或可支持性文档中的 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的数据库软件支持</A> 。

    
    </div>
    
    在部署和启用存档之前，必须设置 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您稍后还可创建数据库（包括在安装过程中）。 有关 SQL Server 的详细信息，请参阅 SQL Server 技术中心 [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

