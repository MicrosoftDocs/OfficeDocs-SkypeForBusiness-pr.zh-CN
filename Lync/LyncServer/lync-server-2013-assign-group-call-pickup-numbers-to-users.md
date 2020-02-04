---
title: Lync Server 2013：为用户分配组呼叫装货号码
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
ms.openlocfilehash: e65eef9fcf425ad8ea9f36dc57899bb6af924bf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="f2089-102">向 Lync Server 2013 中的用户分配组呼叫的装货号码</span><span class="sxs-lookup"><span data-stu-id="f2089-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2089-103">_**主题上次修改时间：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f2089-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f2089-104">将组呼叫挑选组号码添加到 "呼叫公园轨道" 表后，您可以将组分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f2089-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="f2089-105">使用辅助扩展功能激活（SEFAUtil）资源工具包工具向用户分配呼叫装货组。</span><span class="sxs-lookup"><span data-stu-id="f2089-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2089-106">在混合部署中，不要向处于联机状态的用户分配组呼叫装货组。</span><span class="sxs-lookup"><span data-stu-id="f2089-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="f2089-107">处于联机状态的用户不能参与组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="f2089-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="f2089-108">也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f2089-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="f2089-109">将组呼叫装货组分配给用户</span><span class="sxs-lookup"><span data-stu-id="f2089-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="f2089-110">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="f2089-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="f2089-111">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="f2089-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="f2089-112">例如：</span><span class="sxs-lookup"><span data-stu-id="f2089-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2089-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2089-113">See Also</span></span>


[<span data-ttu-id="f2089-114">在 Lync Server 2013 中为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="f2089-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="f2089-115">在 Lync Server 2013 中禁用用户的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="f2089-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

