---
title: 'Lync Server 2013: 针对通讯簿管理的新 CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="bf13d-102">Lync Server 2013 中的通讯簿管理的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf13d-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf13d-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf13d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf13d-104">哪些人可以运行此 cmdlet: 默认情况下, 以下组的成员授权在本地运行 CsWebServiceConfiguration cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="bf13d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="bf13d-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="bf13d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="bf13d-106">Cmdlet CsWebServiceConfiguration 为您的组织中的 Web 服务定义新配置。</span><span class="sxs-lookup"><span data-stu-id="bf13d-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="bf13d-107">Web 服务配置的范围只能在网站或服务级别。</span><span class="sxs-lookup"><span data-stu-id="bf13d-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="bf13d-108">它无法在全局级别创建新的 Web 服务配置。</span><span class="sxs-lookup"><span data-stu-id="bf13d-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="bf13d-109">"通讯簿" 的特别兴趣是 "EnableGroupExansion" 属性。</span><span class="sxs-lookup"><span data-stu-id="bf13d-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="bf13d-110">如果设置为 True, 则 Web 服务可以响应组展开请求。</span><span class="sxs-lookup"><span data-stu-id="bf13d-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="bf13d-111">例如：</span><span class="sxs-lookup"><span data-stu-id="bf13d-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="bf13d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf13d-112">See Also</span></span>


[<span data-ttu-id="bf13d-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf13d-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

