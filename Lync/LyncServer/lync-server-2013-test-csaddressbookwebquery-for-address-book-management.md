---
title: 'Lync Server 2013: 针对通讯簿管理的测试 CsAddressBookWebQuery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c477c9c899847b1dec28fe70a9b749761dc43689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="64562-102">CsAddressBookWebQuery 在 Lync Server 2013 中的通讯簿管理的测试</span><span class="sxs-lookup"><span data-stu-id="64562-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64562-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64562-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64562-104">哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行 CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="64562-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="64562-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="64562-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="64562-106">与 CsAddressBookService 合成事务类似, 测试 CsAddressBookWebQuery 对通讯簿 Web 查询执行查询以确保其正常运行。</span><span class="sxs-lookup"><span data-stu-id="64562-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="64562-107">该 cmdlet 将连接到 Web 票证身份验证, 并显示在-UserCredential 中指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="64562-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="64562-108">如果经过身份验证, 则 cmdlet 将呈现-TargetSipAddress 信息。</span><span class="sxs-lookup"><span data-stu-id="64562-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="64562-109">如果该 cmdlet 能够检索有关该联系人的信息, 则该 cmdlet 应报告成功。</span><span class="sxs-lookup"><span data-stu-id="64562-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="64562-110">例如：</span><span class="sxs-lookup"><span data-stu-id="64562-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="64562-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64562-111">See Also</span></span>


[<span data-ttu-id="64562-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="64562-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

