---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af08e6de9b832289e898fd27003b896dd40fa81c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503569"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="832e4-102">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="832e4-102">Migrate Common Area Phones</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="832e4-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="832e4-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="832e4-104">公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="832e4-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="832e4-105">公用区域电话不需要连接到计算机以提供 Lync Server UC 功能。</span><span class="sxs-lookup"><span data-stu-id="832e4-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="832e4-106">将 Lync Server 2010 部署迁移到 Lync Server 2013 之后，您还必须迁移与旧版公用区域电话关联的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="832e4-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="832e4-107">使用 Lync Server 命令行管理程序，将首先检索与 Lync Server 2010 公共区域电话关联的所有 contact 对象，然后将这些对象移到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="832e4-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="832e4-108">**迁移公共区域电话**</span><span class="sxs-lookup"><span data-stu-id="832e4-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="832e4-109">在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="832e4-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="832e4-110">从命令行键入：</span><span class="sxs-lookup"><span data-stu-id="832e4-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="832e4-111">若要验证是否已将所有 contact 对象移至 Lync Server 2013 池，请在 Lync Server 命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="832e4-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="832e4-112">验证所有 contact 对象现在是否与 Lync Server 2013 池相关联。</span><span class="sxs-lookup"><span data-stu-id="832e4-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

