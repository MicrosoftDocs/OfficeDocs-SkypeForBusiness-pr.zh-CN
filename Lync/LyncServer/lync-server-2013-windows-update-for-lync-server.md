---
title: Lync Server 2013： Lync Server 的 Windows 更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e70ac17e27508a7922d8353e6142b3b5f05b34e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="55ab8-102">适用于 Lync Server 2013 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="55ab8-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ab8-103">_**上次修改的主题：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="55ab8-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="55ab8-104">使用 Windows Update Services 经常检查和应用更新以及安全更新。</span><span class="sxs-lookup"><span data-stu-id="55ab8-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="55ab8-105">这样做有助于防止其他系统组件中的漏洞，这可能会导致攻击者能够使用管理员权限访问运行 Microsoft Lync Server 2013 的服务器，从而危害 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="55ab8-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="55ab8-106">Microsoft SQL Server 2008 Express （64位版本）的更新在每个 Lync Server 2013 Standard Edition server （针对后端数据库）和所有其他 Lync Server 2013 服务器角色（对于本地配置存储）上运行，除非已升级这些数据库到 SQL Server 2008 R2 Express。</span><span class="sxs-lookup"><span data-stu-id="55ab8-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="55ab8-107">您应将这些数据库视为日常安全更新维护的一部分，就像前端池的后端数据库上的 SQL Server、监控数据库和存档数据库一样。</span><span class="sxs-lookup"><span data-stu-id="55ab8-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="55ab8-108">最佳做法</span><span class="sxs-lookup"><span data-stu-id="55ab8-108">Best Practice</span></span>

  - <span data-ttu-id="55ab8-109">使用 Windows Update 保持系统最新。</span><span class="sxs-lookup"><span data-stu-id="55ab8-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

