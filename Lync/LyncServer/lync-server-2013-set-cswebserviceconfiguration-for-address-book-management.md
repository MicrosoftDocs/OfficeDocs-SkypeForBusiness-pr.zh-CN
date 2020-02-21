---
title: Lync Server 2013： CsWebServiceConfiguration for Address Book management
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ddd099b9705e2ec92ebd3e3f177755aed135d9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="7dd0d-102">Lync Server 2013 中的通讯簿管理的 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dd0d-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd0d-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7dd0d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7dd0d-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Set-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7dd0d-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="7dd0d-106">通过 Set-CsWebServiceConfiguration cmdlet，管理员可以重新定义 Web 服务配置中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="7dd0d-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="7dd0d-107">例如：</span><span class="sxs-lookup"><span data-stu-id="7dd0d-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="7dd0d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dd0d-108">See Also</span></span>


[<span data-ttu-id="7dd0d-109">CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dd0d-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

