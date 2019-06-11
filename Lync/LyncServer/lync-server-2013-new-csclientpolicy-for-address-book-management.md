---
title: 'Lync Server 2013: 针对通讯簿管理的新 Set-csclientpolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="365ab-102">Lync Server 2013 中的通讯簿管理的新 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="365ab-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="365ab-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="365ab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="365ab-104">哪些人可以运行此 cmdlet: 默认情况下, 授予以下组的成员运行 Set-csclientpolicy cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="365ab-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="365ab-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="365ab-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="365ab-106">Cmdlet Set-csclientpolicy 定义了大量设置, 可用于为 Lync Server 2013 中提供的功能设置客户端。</span><span class="sxs-lookup"><span data-stu-id="365ab-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="365ab-107">对于通讯簿服务, 参数 AddressBookAvailability 是重要的。</span><span class="sxs-lookup"><span data-stu-id="365ab-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="365ab-108">此参数直接影响客户端可用的选项, 有三种可能的选项:</span><span class="sxs-lookup"><span data-stu-id="365ab-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="365ab-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="365ab-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="365ab-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="365ab-110">WebSearchOnly</span></span>

  - <span data-ttu-id="365ab-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="365ab-111">FileDownloadOnly</span></span>

<span data-ttu-id="365ab-112">定义后, 它决定了客户端如何访问通讯簿。</span><span class="sxs-lookup"><span data-stu-id="365ab-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="365ab-113">如果定义此参数, 则必须定义其中一个选项。</span><span class="sxs-lookup"><span data-stu-id="365ab-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="365ab-114">如果不修改此设置, 则默认 WebSearchAndFileDownload 保持有效。</span><span class="sxs-lookup"><span data-stu-id="365ab-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="365ab-115">例如：</span><span class="sxs-lookup"><span data-stu-id="365ab-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="365ab-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="365ab-116">See Also</span></span>


[<span data-ttu-id="365ab-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="365ab-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

