---
title: 'Lync Server 2013: 用于通讯簿管理的 CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e88d13a910a7883f88ceadc28225cbaa85bb17b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e4dcd-102">Lync Server 2013 中的 CsWebServiceConfiguration 管理通讯簿</span><span class="sxs-lookup"><span data-stu-id="e4dcd-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4dcd-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4dcd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4dcd-104">哪些人可以运行此 cmdlet: 默认情况下, 授权以下组的成员在本地运行 CsWebServiceConfiguration cmdlet: RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="e4dcd-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="e4dcd-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="e4dcd-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="e4dcd-106">CsWebServiceConfiguration 返回您的组织中当前使用的 Web 服务配置的信息。</span><span class="sxs-lookup"><span data-stu-id="e4dcd-106">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization.</span></span> <span data-ttu-id="e4dcd-107">通讯簿服务感兴趣是通讯组列表扩展功能的状态。</span><span class="sxs-lookup"><span data-stu-id="e4dcd-107">Of interest to the Address Book Services is the status of Distribution List Expansion function.</span></span> <span data-ttu-id="e4dcd-108">如果属性 EnableGroupExpansion 为 True, 则您的组织当前允许组扩展。</span><span class="sxs-lookup"><span data-stu-id="e4dcd-108">If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="e4dcd-109">例如：</span><span class="sxs-lookup"><span data-stu-id="e4dcd-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="e4dcd-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4dcd-110">See Also</span></span>


[<span data-ttu-id="e4dcd-111">CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="e4dcd-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

