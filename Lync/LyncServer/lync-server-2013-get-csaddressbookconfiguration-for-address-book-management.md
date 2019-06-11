---
title: 'Lync Server 2013: 用于通讯簿管理的 CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32cf7be49d38db8f0b5b520247830f65cac5a3c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="eb6e2-102">Lync Server 2013 中的 CsAddressBookConfiguration 管理通讯簿</span><span class="sxs-lookup"><span data-stu-id="eb6e2-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb6e2-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="eb6e2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="eb6e2-104">哪些人可以运行此 cmdlet: 默认情况下, 授权以下组的成员在本地运行 CsAddressBookConfiguration cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="eb6e2-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="eb6e2-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="eb6e2-106">Cmdlet CsAddressBookConfiguration 返回有关已存在的配置的信息。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="eb6e2-107">例如：</span><span class="sxs-lookup"><span data-stu-id="eb6e2-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="eb6e2-108">将 CsAddressBookConfiguration 和 CsAddressBookConfiguration 的功能结合起来, 管理员可以定义要修改的配置, 然后应用修改。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-108">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications.</span></span> <span data-ttu-id="eb6e2-109">例如, 下面的组合:</span><span class="sxs-lookup"><span data-stu-id="eb6e2-109">For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="eb6e2-110">返回所有网站中的所有配置, 并对配置应用23:00 小时的 RunTimeOfDay。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eb6e2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb6e2-111">See Also</span></span>


[<span data-ttu-id="eb6e2-112">CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb6e2-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

