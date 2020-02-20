---
title: Lync Server 2013：通讯簿服务器 cmdlet
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
ms.openlocfilehash: fe9a7462edb8df2741a8c783cff17e62bfe848eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ba9f1-102">Lync Server 2013 中的通讯簿服务器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ba9f1-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba9f1-103">_**上次修改的主题：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="ba9f1-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="ba9f1-104">通讯簿服务器是 Active Directory 域服务和 Microsoft Lync Server 2013 之间的中介。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ba9f1-105">通讯簿服务器可确保 Lync Server 2013 中存储的用户信息与 Active Directory 中存储的用户信息同步。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="ba9f1-106">这是通过定期将通讯簿文件与用户数据库中存储的信息同步来实现的。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="ba9f1-107">因此，Lync Server 包含许多用于管理通讯簿服务器的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="ba9f1-108">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ba9f1-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="ba9f1-109">您不能在 Lync Server 控制面板中配置通讯簿服务器设置。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="ba9f1-110">Windows PowerShell 是用于管理这些设置的主要工具。</span><span class="sxs-lookup"><span data-stu-id="ba9f1-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="ba9f1-111">以下是与管理通讯簿服务器直接相关的 cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="ba9f1-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="ba9f1-112">**通讯簿服务器**</span><span class="sxs-lookup"><span data-stu-id="ba9f1-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="ba9f1-113">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ba9f1-114">[新 CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ba9f1-115">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ba9f1-116">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ba9f1-117">[更新-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ba9f1-118">[调试-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ba9f1-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ba9f1-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ba9f1-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba9f1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9f1-121">See Also</span></span>


[<span data-ttu-id="ba9f1-122">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="ba9f1-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

