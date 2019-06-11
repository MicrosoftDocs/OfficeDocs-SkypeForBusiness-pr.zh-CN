---
title: Lync Server 2013：用于 Lync Server 的 Windows Update
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8df575ac6c42bd62db57ed4e6595ced0af32014a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="9a685-102">用于 Lync Server 2013 的 Windows Update</span><span class="sxs-lookup"><span data-stu-id="9a685-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a685-103">_**主题上次修改时间:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="9a685-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="9a685-104">使用 Windows Update 服务经常检查并应用更新和安全更新。</span><span class="sxs-lookup"><span data-stu-id="9a685-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="9a685-105">这样做有助于防止其他系统组件中的漏洞, 这可能会导致攻击者能够使用管理员权限访问运行 Microsoft Lync Server 2013 的服务器, 从而危害 Lync 服务器2013。</span><span class="sxs-lookup"><span data-stu-id="9a685-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="9a685-106">Microsoft SQL Server 2008 Express (64 位版本) 的更新在每个 Lync Server 2013 标准版服务器 (适用于后端数据库) 和所有其他 Lync Server 2013 服务器角色 (对于本地配置存储) 上运行, 除非已升级这些数据库到 SQL Server 2008 R2 Express。</span><span class="sxs-lookup"><span data-stu-id="9a685-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="9a685-107">应将这些数据库视为常规安全更新维护的一部分, 如前端池、监视数据库和存档数据库的后端数据库上的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="9a685-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="9a685-108">最佳做法</span><span class="sxs-lookup"><span data-stu-id="9a685-108">Best Practice</span></span>

  - <span data-ttu-id="9a685-109">通过 Windows 更新保持最新。</span><span class="sxs-lookup"><span data-stu-id="9a685-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

