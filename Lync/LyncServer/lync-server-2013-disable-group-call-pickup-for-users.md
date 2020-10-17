---
title: Lync Server 2013：为用户禁用组呼叫装货
description: Lync Server 2013：为用户禁用组呼叫挑选。
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
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568188"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="d4f87-103">在 Lync Server 2013 中为用户禁用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d4f87-103">Disable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f87-104">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d4f87-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d4f87-105">使用以下过程可禁用用户的组间电话装货。</span><span class="sxs-lookup"><span data-stu-id="d4f87-105">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4f87-106">当您为用户禁用组呼叫应答时，分配给该用户的呼叫应答组号码将不会保留。</span><span class="sxs-lookup"><span data-stu-id="d4f87-106">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="d4f87-107">如果您随后想要为该用户重新启用组呼叫应答，则必须使用/enablegrouppickup 参数再次分配呼叫应答组号码。</span><span class="sxs-lookup"><span data-stu-id="d4f87-107">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="d4f87-108">为用户禁用组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="d4f87-108">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="d4f87-109">使用管理员权限登录到安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="d4f87-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="d4f87-110">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="d4f87-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="d4f87-111">例如：</span><span class="sxs-lookup"><span data-stu-id="d4f87-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4f87-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f87-112">See Also</span></span>


[<span data-ttu-id="d4f87-113">在 Lync Server 2013 中向用户分配组呼叫装货号码</span><span class="sxs-lookup"><span data-stu-id="d4f87-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="d4f87-114">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d4f87-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

