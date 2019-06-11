---
title: 'Lync Server 2013: 为用户启用组呼叫装货'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54abf04c7c0d892e5cc58938866592f96cc1776
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="4ad2f-102">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="4ad2f-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ad2f-103">_**主题上次修改时间:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="4ad2f-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4ad2f-104">使用 SEFAUtil 资源工具包工具为用户启用组呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="4ad2f-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="4ad2f-105">必须在 "呼叫停止轨道" 表中向用户分配一个包含 "GroupPickup" 的组编号, 以便启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="4ad2f-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="4ad2f-106">当您运行 SEFAUtil 时, 您可以分配一个呼叫装货组编号, 并使用/enablegrouppickup 参数同时启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="4ad2f-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="4ad2f-107">为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="4ad2f-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="4ad2f-108">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="4ad2f-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="4ad2f-109">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="4ad2f-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="4ad2f-110">例如：</span><span class="sxs-lookup"><span data-stu-id="4ad2f-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ad2f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ad2f-111">See Also</span></span>


[<span data-ttu-id="4ad2f-112">向 Lync Server 2013 中的用户分配组呼叫的装货号码</span><span class="sxs-lookup"><span data-stu-id="4ad2f-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="4ad2f-113">在 Lync Server 2013 中禁用用户的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="4ad2f-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

