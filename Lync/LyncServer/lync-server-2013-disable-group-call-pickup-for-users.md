---
title: Lync Server 2013：为用户禁用组呼叫装货
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="149c8-102">在 Lync Server 2013 中禁用用户的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="149c8-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="149c8-103">_**主题上次修改时间：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="149c8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="149c8-104">使用以下过程可禁用用户的组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="149c8-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="149c8-105">当您为用户禁用组呼叫装货时，分配给该用户的呼叫装货组号码将不会保留。</span><span class="sxs-lookup"><span data-stu-id="149c8-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="149c8-106">如果随后想要为该用户重新启用组呼叫装货，则必须使用/enablegrouppickup 参数再次分配呼叫装货组编号。</span><span class="sxs-lookup"><span data-stu-id="149c8-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="149c8-107">为用户禁用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="149c8-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="149c8-108">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="149c8-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="149c8-109">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="149c8-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="149c8-110">例如：</span><span class="sxs-lookup"><span data-stu-id="149c8-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="149c8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="149c8-111">See Also</span></span>


[<span data-ttu-id="149c8-112">向 Lync Server 2013 中的用户分配组呼叫的装货号码</span><span class="sxs-lookup"><span data-stu-id="149c8-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="149c8-113">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="149c8-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

