---
title: Lync Server 2013：为用户启用组呼叫装货
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69b17ab937d5dd095565e912b26129706b047e69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="46d24-102">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="46d24-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d24-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="46d24-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="46d24-104">使用 SEFAUtil 资源工具包工具为用户启用组呼叫挑选。</span><span class="sxs-lookup"><span data-stu-id="46d24-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="46d24-105">必须在呼叫寄存通道表中为用户分配一个类型为 "GroupPickup" 的组编号，以便启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="46d24-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="46d24-106">在运行 SEFAUtil 时，可以通过使用/enablegrouppickup 参数，分配呼叫应答组号码并同时启用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="46d24-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="46d24-107">为用户启用组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="46d24-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="46d24-108">使用管理员权限登录到安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="46d24-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="46d24-109">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="46d24-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="46d24-110">例如：</span><span class="sxs-lookup"><span data-stu-id="46d24-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46d24-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="46d24-111">See Also</span></span>


[<span data-ttu-id="46d24-112">在 Lync Server 2013 中向用户分配组呼叫装货号码</span><span class="sxs-lookup"><span data-stu-id="46d24-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="46d24-113">在 Lync Server 2013 中为用户禁用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="46d24-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

