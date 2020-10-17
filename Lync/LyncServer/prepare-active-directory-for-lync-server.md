---
title: 为 Lync Server 准备 Active Directory
description: 为 Lync Server 准备 Active Directory。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9ff2de825d68f2c7ca9d90cbecdf71e5d00d55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563698"
---
# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="fb9a3-103">为 Lync Server 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="fb9a3-103">Prepare Active Directory for Lync Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb9a3-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fb9a3-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fb9a3-105">在使用 Lync Server 2010 在共存状态中部署 Lync Server 2013 之前，必须执行一些额外的 Active Directory 任务，以配置 Lync Server 2013 的架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-105">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="fb9a3-106">架构扩展添加了 Lync Server 2013 所需的 Active Directory 类和属性。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-106">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="fb9a3-107">有关详细信息，请参阅 [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)主题。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-107">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="fb9a3-108">**为 Lync Server 2013 准备 Active Directory**</span><span class="sxs-lookup"><span data-stu-id="fb9a3-108">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="fb9a3-109">在 Lync Server 2013 前端服务器上，运行 Lync Server 2013 安装程序。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-109">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="fb9a3-110">选择“准备 Active Directory”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-110">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="fb9a3-111">![Lync Server 2013 部署向导，欢迎页面](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 部署向导，欢迎页面")</span><span class="sxs-lookup"><span data-stu-id="fb9a3-111">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="fb9a3-112">完成步骤 1 至 5。</span><span class="sxs-lookup"><span data-stu-id="fb9a3-112">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="fb9a3-113">![部署向导的 Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "部署向导的 Active Directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="fb9a3-113">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

