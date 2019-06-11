---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-04_

本主题将指导你完成删除前端池或标准版前端服务器的过程。 删除前端池时, 将在池删除过程中删除属于该池的每个前端服务器。 删除标准版前端服务器时, 必须从拓扑生成器中删除 SQL 应用商店定义。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1.  打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  展开 "**企业版前端池**", 展开 "前端池", 右键单击要删除的前端池, 然后单击 "**删除**"。

4.  发布拓扑, 检查复制状态, 然后根据需要运行 Lync Server 部署向导。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>删除标准版前端服务器

1.  打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  展开**标准版前端服务器**, 右键单击要删除的前端服务器, 然后单击 "**删除**"。

4.  展开 " **sql 存储**", 右键单击与标准版前端服务器关联的 SQL Server 数据库, 然后单击 "**删除**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 必须从标准版前端服务器中删除 collocated SQL Server 数据库的定义。

    
    </div>

5.  发布拓扑, 检查复制状态, 然后根据需要运行 Lync Server 部署向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

