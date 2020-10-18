---
title: Lync Server 2013：用于通讯簿管理的 New-CsWebServiceConfiguration
description: Lync Server 2013：用于通讯簿管理的 New-CsWebServiceConfiguration。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8972f1b4fe71554e6a8925ddebea6303e2f074a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578908"
---
# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="30969-103">Lync Server 2013 中的通讯簿管理 New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="30969-103">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30969-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="30969-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="30969-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 New-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="30969-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="30969-p102">New-CsWebServiceConfiguration cmdlet 为组织中的 Web 服务定义新配置。Web 服务配置的作用域只能是站点级别或服务级别。无法在全局级别创建新的 Web 服务配置。对于通讯簿，尤其值得关注的是 EnableGroupExansion 属性。如果设置为 True，Web 服务可以响应组扩展的请求。</span><span class="sxs-lookup"><span data-stu-id="30969-p102">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization. The scope for the Web Services configuration can only be at the site or service level. It cannot create a new Web Services configuration at the global level. Specifically of interest to the Address Book is the EnableGroupExansion attribute. If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="30969-112">例如：</span><span class="sxs-lookup"><span data-stu-id="30969-112">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="30969-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="30969-113">See Also</span></span>


[<span data-ttu-id="30969-114">新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="30969-114">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

