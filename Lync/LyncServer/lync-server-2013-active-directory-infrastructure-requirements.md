---
title: Lync Server 2013： Active Directory 基础结构要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="913ae-102">Lync Server 2013 的 Active Directory 基础结构要求</span><span class="sxs-lookup"><span data-stu-id="913ae-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="913ae-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="913ae-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="913ae-104">在开始为 Lync Server 2013 准备 Active Directory 域服务的过程之前，请确保您的 Active Directory 基础结构满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="913ae-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="913ae-105">您在其中部署 Lync Server 的林中的所有域控制器（包括所有全局编录服务器）都运行以下操作系统之一：</span><span class="sxs-lookup"><span data-stu-id="913ae-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="913ae-106">Windows Server 2012 R2 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="913ae-107">Windows Server 2012 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="913ae-108">Windows Server 2008 R2 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="913ae-109">Windows Server 2008 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="913ae-110">Windows Server 2008 企业版32位</span><span class="sxs-lookup"><span data-stu-id="913ae-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="913ae-111">32 位或 64 位版本的 Windows Server 2003 R2 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="913ae-112">32位或64位版本的 Windows Server 2003 操作系统</span><span class="sxs-lookup"><span data-stu-id="913ae-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="913ae-113">将在其中部署 Lync Server 的所有域都将提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的域功能级别。</span><span class="sxs-lookup"><span data-stu-id="913ae-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="913ae-114">将在其中部署 Lync Server 的林提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的林功能级别。</span><span class="sxs-lookup"><span data-stu-id="913ae-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="913ae-115">若要更改您的域或林功能级别，请参阅 TechNet Library 中的 "提升域和林功能<A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>级别"。</span><span class="sxs-lookup"><span data-stu-id="913ae-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="913ae-116">在部署 Lync Server 计算机或用户的每个域中都会部署一个全局编录。</span><span class="sxs-lookup"><span data-stu-id="913ae-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="913ae-117">Lync Server 2013 支持 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 操作系统中的通用组。</span><span class="sxs-lookup"><span data-stu-id="913ae-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="913ae-118">通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。</span><span class="sxs-lookup"><span data-stu-id="913ae-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="913ae-119">通用组支持（与管理员委派结合使用）简化了 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="913ae-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="913ae-120">例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。</span><span class="sxs-lookup"><span data-stu-id="913ae-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

