---
title: 'Lync Server 2013: Set-Set-csclientpolicy for 通讯簿管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248a04692327d93293e5bc5d37e650322b415ccb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="228dd-102">Set-csclientpolicy Lync Server 2013 中的通讯簿管理设置</span><span class="sxs-lookup"><span data-stu-id="228dd-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="228dd-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="228dd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="228dd-104">哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行本地 Set-csclientpolicy cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="228dd-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="228dd-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="228dd-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="228dd-106">与 Set-csclientpolicy 类似, Set-csclientpolicy cmdlet 允许你修改已存在的客户端设置。</span><span class="sxs-lookup"><span data-stu-id="228dd-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="228dd-107">例如：</span><span class="sxs-lookup"><span data-stu-id="228dd-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="228dd-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="228dd-108">See Also</span></span>


[<span data-ttu-id="228dd-109">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="228dd-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

