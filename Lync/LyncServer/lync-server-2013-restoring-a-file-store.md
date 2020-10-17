---
title: Lync Server 2013：还原文件存储
description: Lync Server 2013：还原文件存储。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543828"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>在 Lync Server 2013 中还原文件存储

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

Standard Edition 的文件存储通常位于 Standard Edition server 上。 Enterprise Edition 的文件存储通常位于文件服务器或群集上。 以下过程介绍了如何还原文件存储。

<div>

## <a name="to-restore-a-file-store"></a>还原文件存储

1.  如果文件存储失败，请将相应的文件存储从 $Backup 复制 \\ 到文件服务器或 Standard Edition 服务器上的文件存储位置，然后共享该文件夹。
    
    <div>
    

    > [!IMPORTANT]  
    > 已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。

    
    </div>

2.  如有必要，请设置文件存储 (Acl) 的访问控制列表。 在命令行中键入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 只有在还原过程中未运行拓扑生成器时，才需要执行此步骤。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

