---
title: Lync Server 2013：向用户分配组呼叫装货号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3de74542edc65de68ab5f803934aa671575cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499479"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="e35e1-102">在 Lync Server 2013 中向用户分配组呼叫装货号码</span><span class="sxs-lookup"><span data-stu-id="e35e1-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e35e1-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e35e1-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e35e1-104">将组呼叫应答组号码添加到呼叫寄存通道表后，可以将组分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e35e1-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="e35e1-105">使用辅助扩展功能激活 (SEFAUtil ) 资源工具包工具将呼叫应答组分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e35e1-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e35e1-106">在混合部署中，不要向驻留在线的用户分配组呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="e35e1-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e35e1-107">联机托管的用户不能参与组内呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="e35e1-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e35e1-108">也就是说，其他用户无法应答其呼叫，也不能应答其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e35e1-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="e35e1-109">将组呼叫装货组分配给用户</span><span class="sxs-lookup"><span data-stu-id="e35e1-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="e35e1-110">使用管理员权限登录到安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="e35e1-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="e35e1-111">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="e35e1-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="e35e1-112">例如：</span><span class="sxs-lookup"><span data-stu-id="e35e1-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e35e1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e35e1-113">See Also</span></span>


[<span data-ttu-id="e35e1-114">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="e35e1-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="e35e1-115">在 Lync Server 2013 中为用户禁用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="e35e1-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

