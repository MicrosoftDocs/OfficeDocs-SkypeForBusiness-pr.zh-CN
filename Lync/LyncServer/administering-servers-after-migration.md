---
title: 迁移后服务器的管理
description: 迁移后管理服务器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Administering servers after migration
ms:assetid: 7b08f048-c951-4050-b77c-0fff351620e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205023(v=OCS.15)
ms:contentKeyID: 48184582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24ea310f02a7622fbf3b73160714520d3c47ac3b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544998"
---
# <a name="administering-servers-after-migration"></a><span data-ttu-id="3cc45-103">迁移后服务器的管理</span><span class="sxs-lookup"><span data-stu-id="3cc45-103">Administering servers after migration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc45-104">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3cc45-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3cc45-105">通常，使用的管理工具必须与要管理的服务器版本对应。</span><span class="sxs-lookup"><span data-stu-id="3cc45-105">In general, you must use the administrative tool that corresponds to the server version that you want to manage.</span></span> <span data-ttu-id="3cc45-106">您不能在同一台计算机上安装 Lync Server 2010 和 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="3cc45-106">You cannot install the Lync Server 2010 and the Lync Server 2013 administrative tools on the same computer.</span></span> <span data-ttu-id="3cc45-107">此外，不会在每台服务器上自动安装 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="3cc45-107">Also, the Lync Server 2013 Control Panel is not installed automatically on each server.</span></span> <span data-ttu-id="3cc45-108">若要安装 Lync Server 2013 控制面板，请按照部署文档中的 " [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md) " 主题中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="3cc45-108">To install the Lync Server 2013 Control Panel, follow the procedure inside the topic [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Deployment documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3cc45-109">在部署 Lync Server 2013 的试点池之后，不能使用 Lync Server 2010 拓扑生成器或 Lync Server 2010 控制面板管理任何 Lync Server 2013 资源。</span><span class="sxs-lookup"><span data-stu-id="3cc45-109">After a Lync Server 2013 pilot pool is deployed, you cannot use Lync Server 2010 Topology Builder or Lync Server 2010 Control Panel to manage any Lync Server 2013 resources.</span></span> <span data-ttu-id="3cc45-110">您必须使用 Lync Server 2013 工具来管理 Lync Server 2013 和 Lync Server 2010 资源。</span><span class="sxs-lookup"><span data-stu-id="3cc45-110">You must use Lync Server 2013 tools to manage Lync Server 2013 and Lync Server 2010 resources.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

