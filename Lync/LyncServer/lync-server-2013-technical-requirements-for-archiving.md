---
title: 'Lync Server 2013: 存档的技术要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中存档的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-09_

Lync Server 2013 技术要求包括以下内容:

  - 基础结构要求。

  - 必须为存档安装的必备软件。

  - 存档的数据存储要求。

  - 针对存档部署的扩展要求和注意事项。

  - 存档数据库的性能要求和注意事项。

<div>


> [!NOTE]  
> 缩放和性能信息在此 Lync Server 2013 版本中不可用。



</div>

<div>

## <a name="infrastructure-requirements"></a>基础结构要求

Lync Server 2013 存档基础结构要求与 Lync Server 2013 的部署相同。 有关详细信息, 请参阅在规划文档中[确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)。

</div>

<div>

## <a name="archiving-prerequisites"></a>存档先决条件

Lync Server 2013 简化了存档的先决条件, 原因如下:

  - 存档服务器不再是服务器角色。 统一的数据收集代理在池和标准版服务器中的前端服务器上运行, 用于捕获用于存档的数据, 因此不会为存档设置单独的系统平台。

  - 存档使用 Lync Server 2013 文件存储来临时存储会议内容文件, 因此不会为存档设置单独的文件存储。

  - 在 Lync Server 2013 中, 不需要消息队列。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>存档的数据存储要求

此外, 你还需要设置用于存档存储的基础结构。 这包括以下一项或两项:

  - **Microsoft Exchange 存储**。 Meeting content files, such as PowerPoint presentations, are archived as attachments. 如果要使用 Microsoft Exchange 集成, 以便 Lync 存档数据存储在 Exchange 合规性数据中, 则必须将 Exchange 2013 用于 Exchange 部署, 并确保最大存储空间支持存储会议内容文件。 如果你使用 Microsoft Exchange 集成选项部署存档, 则 Lync 存档数据仅存储 Exchange 2013 服务器上托管的用户的 Exchange 2013 合规性数据。 在使用 Microsoft Exchange 集成选项部署和启用存档之前, 必须部署 Exchange 2013。 如果你选择使用 Exchange 2013 存储, 则无需为存档部署单独的 SQL Server 数据库, 除非你的 Exchange 2013 服务器上未托管 Lync 用户。

  - **用于存档的 SQL Server 数据库存储**。 若要支持未托管在 Exchange 2013 服务器上的用户, 或者不希望使用 Microsoft Exchange 集成选项, 则必须使用 SQL Server 数据库部署存档存储。 Lync Server 2013 支持以下64位版本的 SQL Server:
    
      - Microsoft SQL Server 2008 R2 企业版
    
      - Microsoft SQL Server 2008 R2 标准版
    
      - Microsoft SQL Server 2012 企业版
    
      - Microsoft SQL Server 2012 标准版
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支持存档。 不支持32位版本的 SQL Server。 有关其他 SQL Server 要求和限制, 请参阅在规划文档或支持文档中<A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的数据库软件支持</A>。

    
    </div>
    
    在部署和启用存档之前, 必须设置 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 你还可以稍后创建数据库, 包括安装过程的一部分。 有关 SQL Server 的详细信息, 请参阅 SQL Server 技术[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)中心。

</div>

</div>

<span> </span>

</div>

</div>

</div>

