---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b004426c65157ef7ad1120728c9daeea1b68f161
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

本主题将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，会将属于池的每台前端服务器作为池删除过程的一部分删除。 删除 Standard Edition 前端服务器时，必须从拓扑生成器中删除 SQL 存储定义。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1.  打开拓扑生成器。

2.  导航到 "Lync Server 2010" 节点。

3.  展开 " **Enterprise Edition 前端池**"，再展开 "前端池"，右键单击要删除的前端池，然后单击 "**删除**"。

4.  发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>删除 Standard Edition 前端服务器

1.  打开拓扑生成器。

2.  导航到 "Lync Server 2010" 节点。

3.  展开**Standard Edition 前端服务器**，右键单击要删除的前端服务器，然后单击 "**删除**"。

4.  展开 " **sql 存储**"，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击 "**删除**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必须从 Standard Edition 前端服务器中删除并置 SQL Server 数据库的定义。

    
    </div>

5.  发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

