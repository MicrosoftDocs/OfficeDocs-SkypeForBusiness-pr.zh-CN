---
title: Lync Server 2013：用于通讯簿管理的 CsAddressBookConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a055a91aa3f082a48d2defa73cc9a40f7c4a298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0e7f3-102">Lync Server 2013 中的 CsAddressBookConfiguration for Address Book management</span><span class="sxs-lookup"><span data-stu-id="0e7f3-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e7f3-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0e7f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0e7f3-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsAddressBookConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0e7f3-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="0e7f3-106">Get-CsAddressBookConfiguration cmdlet 返回有关已存在的配置的信息。</span><span class="sxs-lookup"><span data-stu-id="0e7f3-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="0e7f3-107">例如：</span><span class="sxs-lookup"><span data-stu-id="0e7f3-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="0e7f3-p102">通过组合 Get-CsAddressBookConfiguration 和 Set-CsAddressBookConfiguration 的功能，管理员可以定义要修改的配置，然后应用修改。例如，对与以下组合：</span><span class="sxs-lookup"><span data-stu-id="0e7f3-p102">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications. For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="0e7f3-110">返回所有站点中的所有配置，并为配置中的 RunTimeOfDay 应用值 23:00。</span><span class="sxs-lookup"><span data-stu-id="0e7f3-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0e7f3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e7f3-111">See Also</span></span>


[<span data-ttu-id="0e7f3-112">CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e7f3-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

