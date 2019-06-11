---
title: 'Lync Server 2013: 通讯簿服务器 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634e6ae86a68cece6472d04ba1870159dc9b866f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c734a-102">Lync Server 2013 中的通讯簿服务器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c734a-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c734a-103">_**主题上次修改时间:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="c734a-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="c734a-104">通讯簿服务器是 Active Directory 域服务和 Microsoft Lync Server 2013 之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="c734a-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c734a-105">通讯簿服务器确保存储在 Lync Server 2013 中的用户信息与 Active Directory 中存储的用户信息同步。</span><span class="sxs-lookup"><span data-stu-id="c734a-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="c734a-106">这是通过使用存储在用户数据库中的信息定期同步通讯录文件完成的。</span><span class="sxs-lookup"><span data-stu-id="c734a-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="c734a-107">因此, Lync Server 包含许多用于管理通讯簿服务器的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c734a-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="c734a-108">通讯簿服务器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c734a-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="c734a-109">不能在 Lync Server "控制面板" 中配置通讯簿服务器设置。</span><span class="sxs-lookup"><span data-stu-id="c734a-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="c734a-110">Windows PowerShell 是用于管理这些设置的主要工具。</span><span class="sxs-lookup"><span data-stu-id="c734a-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="c734a-111">以下是与管理通讯簿服务器直接相关的 cmdlet 的列表:</span><span class="sxs-lookup"><span data-stu-id="c734a-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="c734a-112">**通讯簿服务器**</span><span class="sxs-lookup"><span data-stu-id="c734a-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="c734a-113">[CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c734a-114">[新-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c734a-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c734a-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c734a-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c734a-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c734a-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c734a-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c734a-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c734a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c734a-121">See Also</span></span>


[<span data-ttu-id="c734a-122">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="c734a-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

