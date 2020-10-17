---
title: Lync Server 2013：通讯簿服务器 cmdlet
description: Lync Server 2013：通讯簿服务器 cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4fef903d25f0d2707410e017f4eb280282bbdab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553028"
---
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="eb148-103">Lync Server 2013 中的通讯簿服务器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb148-103">Address Book Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb148-104">_**上次修改的主题：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="eb148-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="eb148-105">通讯簿服务器是 Active Directory 域服务和 Microsoft Lync Server 2013 之间的中介。</span><span class="sxs-lookup"><span data-stu-id="eb148-105">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="eb148-106">通讯簿服务器可确保 Lync Server 2013 中存储的用户信息与 Active Directory 中存储的用户信息同步。</span><span class="sxs-lookup"><span data-stu-id="eb148-106">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="eb148-107">这是通过定期将通讯簿文件与用户数据库中存储的信息同步来实现的。</span><span class="sxs-lookup"><span data-stu-id="eb148-107">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="eb148-108">因此，Lync Server 包含许多用于管理通讯簿服务器的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb148-108">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="eb148-109">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="eb148-109">Address Book Server Cmdlets</span></span>

<span data-ttu-id="eb148-110">您不能在 Lync Server 控制面板中配置通讯簿服务器设置。</span><span class="sxs-lookup"><span data-stu-id="eb148-110">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="eb148-111">Windows PowerShell 是用于管理这些设置的主要工具。</span><span class="sxs-lookup"><span data-stu-id="eb148-111">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="eb148-112">以下是与管理通讯簿服务器直接相关的 cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="eb148-112">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="eb148-113">**通讯簿服务器**</span><span class="sxs-lookup"><span data-stu-id="eb148-113">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="eb148-114">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-114">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eb148-115">[新 CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-115">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eb148-116">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-116">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eb148-117">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-117">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eb148-118">[更新-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-118">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eb148-119">[调试-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-119">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eb148-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eb148-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb148-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb148-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb148-122">See Also</span></span>


[<span data-ttu-id="eb148-123">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="eb148-123">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

