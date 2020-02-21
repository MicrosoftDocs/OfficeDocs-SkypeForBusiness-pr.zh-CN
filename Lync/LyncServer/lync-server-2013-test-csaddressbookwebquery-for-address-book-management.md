---
title: Lync Server 2013：针对通讯簿管理的 CsAddressBookWebQuery 测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f03ead82f4ec5ebcb09c3bbfa1bba6206b8333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a2c3d-102">Lync Server 2013 中的 CsAddressBookWebQuery for Address Book management</span><span class="sxs-lookup"><span data-stu-id="a2c3d-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c3d-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a2c3d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a2c3d-104">可以运行此 cmdlet 的用户：默认情况下，已授权以下组的成员运行 CsAddressBookWebQuery cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="a2c3d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a2c3d-105">要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2c3d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="a2c3d-106">与 CsAddressBookService 综合事务类似，CsAddressBookWebQuery 对通讯簿 Web 查询执行查询，以确保其正常运行。</span><span class="sxs-lookup"><span data-stu-id="a2c3d-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="a2c3d-107">Cmdlet 将连接到 Web 票证身份验证，并显示在– UserCredential 中指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="a2c3d-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="a2c3d-108">如果经过身份验证，则 cmdlet 将呈现– TargetSipAddress 信息。</span><span class="sxs-lookup"><span data-stu-id="a2c3d-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="a2c3d-109">如果能够检索有关联系人的信息，cmdlet 应报告成功。</span><span class="sxs-lookup"><span data-stu-id="a2c3d-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="a2c3d-110">例如：</span><span class="sxs-lookup"><span data-stu-id="a2c3d-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="a2c3d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2c3d-111">See Also</span></span>


[<span data-ttu-id="a2c3d-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="a2c3d-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

