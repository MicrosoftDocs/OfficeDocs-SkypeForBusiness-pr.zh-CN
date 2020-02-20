---
title: Lync Server 2013：针对通讯簿管理的 CsAddressBookService 测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8bfb2768ef5b4755bba2fce7b448476b7728151
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="bf92d-102">Lync Server 2013 中的 CsAddressBookService for Address Book management</span><span class="sxs-lookup"><span data-stu-id="bf92d-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf92d-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf92d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf92d-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 Test-CsAddressBookService cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bf92d-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="bf92d-106">Lync Server 2013 包含多个用于启动合成命令的 cmdlet，以确认特定的函数或功能是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="bf92d-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="bf92d-107">Test-CsAddressBookService 确认定义的用户是否可以从通讯簿 Web 服务连接并请求本地文件。</span><span class="sxs-lookup"><span data-stu-id="bf92d-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="bf92d-108">例如：</span><span class="sxs-lookup"><span data-stu-id="bf92d-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="bf92d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf92d-109">See Also</span></span>


[<span data-ttu-id="bf92d-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="bf92d-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

