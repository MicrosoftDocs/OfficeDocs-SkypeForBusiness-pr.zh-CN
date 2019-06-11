---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="3d5af-102">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="3d5af-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d5af-103">_**主题上次修改时间:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3d5af-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3d5af-104">常见的区域电话是指通常位于共享工作区或通用区域 (如大厅、厨房或工厂地板) 的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="3d5af-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="3d5af-105">常用的区域电话无需连接到计算机即可提供 Lync Server UC 功能。</span><span class="sxs-lookup"><span data-stu-id="3d5af-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="3d5af-106">将 Lync Server 2010 部署迁移到 Lync Server 2013 之后, 您还必须迁移与旧式公共区域电话相关联的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="3d5af-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="3d5af-107">使用 Lync Server 管理外壳程序将首先检索与 Lync Server 2010 公共区域电话相关联的所有联系人对象, 然后将这些对象移动到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="3d5af-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="3d5af-108">**迁移公共区域电话**</span><span class="sxs-lookup"><span data-stu-id="3d5af-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="3d5af-109">从 Lync Server 2013 前端服务器, 打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3d5af-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3d5af-110">在命令行中, 键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="3d5af-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="3d5af-111">若要验证所有联系人对象是否已被移动到 Lync Server 2013 池, 请从 Lync Server Management Shell 键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="3d5af-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="3d5af-112">验证所有联系人对象现在是否与 Lync Server 2013 池相关联。</span><span class="sxs-lookup"><span data-stu-id="3d5af-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

