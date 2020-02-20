---
title: Lync Server 2013：还原响应组设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c663441496d7a08a656095da4371376912fadc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="b1ee3-102">在 Lync Server 2013 中还原响应组设置</span><span class="sxs-lookup"><span data-stu-id="b1ee3-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1ee3-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b1ee3-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b1ee3-104">如果部署了响应组应用程序，并且需要还原后端服务器或 Standard Edition 服务器，则还需要还原响应组配置设置。</span><span class="sxs-lookup"><span data-stu-id="b1ee3-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="b1ee3-105">还原响应组配置设置</span><span class="sxs-lookup"><span data-stu-id="b1ee3-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="b1ee3-106">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="b1ee3-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="b1ee3-107">例如：</span><span class="sxs-lookup"><span data-stu-id="b1ee3-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

