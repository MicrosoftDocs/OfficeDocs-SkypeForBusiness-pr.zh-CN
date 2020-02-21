---
title: Lync Server 2013： CsAddressBookConfiguration for Address Book management
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b728ee5a1c644b18a90345a660592e010ea791a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ac0a6-102">Lync Server 2013 中的通讯簿管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac0a6-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac0a6-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ac0a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ac0a6-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Set-CsAddressBookConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ac0a6-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="ac0a6-106">Set-CsAddressBookConfiguration 与 New-CsAddressBookConfiguration cmdlet 类似，不同之处是它用于修改现有配置。</span><span class="sxs-lookup"><span data-stu-id="ac0a6-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="ac0a6-107">例如：</span><span class="sxs-lookup"><span data-stu-id="ac0a6-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="ac0a6-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0a6-108">See Also</span></span>


[<span data-ttu-id="ac0a6-109">CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac0a6-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

