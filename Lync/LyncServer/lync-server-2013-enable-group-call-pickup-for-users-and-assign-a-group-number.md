---
title: Lync Server 2013：为用户启用组呼叫应答并分配组号码
description: Lync Server 2013：为用户启用组呼叫应答并分配组号码。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559638"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="2b2fa-103">为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码</span><span class="sxs-lookup"><span data-stu-id="2b2fa-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b2fa-104">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2b2fa-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2b2fa-105">将呼叫应答组号码添加到呼叫寄存通道表之后，将组号码分配给用户并为其启用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="2b2fa-106">使用辅助扩展功能激活 (SEFAUtil) 资源工具包工具分配组号码并启用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b2fa-107">在混合部署中，不要向驻留在线的用户分配组呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="2b2fa-108">联机托管的用户不能参与组内呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2b2fa-109">也就是说，其他用户无法应答其呼叫，也不能应答其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="2b2fa-110">为用户分配组号码并启用组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="2b2fa-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="2b2fa-111">使用管理员权限登录到安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="2b2fa-112">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="2b2fa-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="2b2fa-113">例如，若要将组号199分配给用户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2b2fa-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b2fa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b2fa-114">See Also</span></span>


[<span data-ttu-id="2b2fa-115">在 Lync Server 2013 中为用户禁用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="2b2fa-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

