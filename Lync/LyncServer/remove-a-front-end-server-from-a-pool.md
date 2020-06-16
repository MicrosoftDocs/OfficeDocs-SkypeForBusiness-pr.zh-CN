---
title: 从池中删除前端服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef9df56c094bb5d7a3972a7c062905cbc4a844a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

Microsoft Lync Server 2010 Enterprise Edition 前端服务器不能作为独立计算机存在。 必须将其定义为前端池，即使池中只有一台计算机也是如此。

本主题将指导您完成从现有前端池删除单个前端服务器的过程。 如果前端服务器是池中的最后一台服务器，或者如果要完全删除池，请参阅[删除前端池或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。 在删除前端池之前，无需删除单个前端服务器。 删除池时，会删除每个前端服务器。

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

1.  打开 Lync Server 2013 前端服务器，打开拓扑生成器。

2.  导航到 "Lync Server 2010" 节点。

3.  展开 " **Enterprise Edition 前端池**"，再展开要删除的前端服务器的前端池，右键单击要删除的前端服务器，然后单击 "**删除**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

