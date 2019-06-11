---
title: Lync Server 2013：准备 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e1d7285d743da2270121389bbb5a510fe3b12d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="66872-102">为 Lync Server 2013 准备 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="66872-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66872-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="66872-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="66872-104">在部署和操作 Lync Server 2013 之前, 必须通过扩展架构, 然后创建和配置对象来准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="66872-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="66872-105">架构扩展添加 Lync Server 所需的 Active Directory 类和属性。</span><span class="sxs-lookup"><span data-stu-id="66872-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="66872-106">本部分中的主题介绍如何准备用于部署 Lync Server 的 AD DS 以及如何分配设置和组织单位 (OU) 权限。</span><span class="sxs-lookup"><span data-stu-id="66872-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="66872-107">有关 Lync Server 所需的架构更改的详细信息, 请参阅[Lync server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="66872-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66872-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="66872-108">In This Section</span></span>

  - [<span data-ttu-id="66872-109">Lync Server 2013 的 Active Directory 基础结构要求</span><span class="sxs-lookup"><span data-stu-id="66872-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="66872-110">Lync Server 2013 中的 Active Directory 域服务准备概述</span><span class="sxs-lookup"><span data-stu-id="66872-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="66872-111">在 Lync Server 2013 中准备 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="66872-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="66872-112">在 Lync Server 2013 中准备锁定的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="66872-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="66872-113">在 Lync Server 2013 中授予权限</span><span class="sxs-lookup"><span data-stu-id="66872-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

