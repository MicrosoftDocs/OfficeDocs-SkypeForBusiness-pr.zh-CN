---
title: 'Lync Server 2013: Set-CsAddressBookConfiguration for 通讯簿管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edafd6b51da15b3302a9c3f454400325527fa631
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="60baf-102">CsAddressBookConfiguration Lync Server 2013 中的通讯簿管理设置</span><span class="sxs-lookup"><span data-stu-id="60baf-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60baf-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60baf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60baf-104">哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行本地 CsAddressBookConfiguration cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="60baf-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="60baf-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="60baf-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="60baf-106">Set-CsAddressBookConfiguration 与 CsAddressBookConfiguration cmdlet 类似, 但它用于修改现有配置。</span><span class="sxs-lookup"><span data-stu-id="60baf-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="60baf-107">例如：</span><span class="sxs-lookup"><span data-stu-id="60baf-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="60baf-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60baf-108">See Also</span></span>


[<span data-ttu-id="60baf-109">Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="60baf-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

