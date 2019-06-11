---
title: 'Lync Server 2013: 还原响应组设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af4aace2739a2aee8e2f9dbba2a0cb0779f19a3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="ac878-102">在 Lync Server 2013 中还原响应组设置</span><span class="sxs-lookup"><span data-stu-id="ac878-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac878-103">_**主题上次修改时间:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ac878-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ac878-104">如果你部署了响应组应用程序, 并且需要还原后端服务器或标准版服务器, 你还需要还原响应组配置设置。</span><span class="sxs-lookup"><span data-stu-id="ac878-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="ac878-105">还原响应组配置设置</span><span class="sxs-lookup"><span data-stu-id="ac878-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="ac878-106">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ac878-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="ac878-107">例如：</span><span class="sxs-lookup"><span data-stu-id="ac878-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

