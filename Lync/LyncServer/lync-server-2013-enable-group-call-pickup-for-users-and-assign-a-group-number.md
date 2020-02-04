---
title: Lync Server 2013：为用户启用组呼叫装货并分配组号码
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
ms.openlocfilehash: a5ad9bbc6f5505e5778872a568bdbc80b3f7bf91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="0b51d-102">为 Lync Server 2013 中的用户启用组呼叫装货和分配组号码</span><span class="sxs-lookup"><span data-stu-id="0b51d-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b51d-103">_**主题上次修改时间：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0b51d-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0b51d-104">将呼叫装货组编号添加到 "呼叫驻留" 轨道表之后，您可以为用户分配组号码并为其启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="0b51d-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="0b51d-105">使用辅助扩展功能激活（SEFAUtil）资源工具包工具分配组号码并启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="0b51d-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b51d-106">在混合部署中，不要向处于联机状态的用户分配组呼叫装货组。</span><span class="sxs-lookup"><span data-stu-id="0b51d-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="0b51d-107">处于联机状态的用户不能参与组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="0b51d-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="0b51d-108">也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b51d-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="0b51d-109">分配组号码并为用户启用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="0b51d-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="0b51d-110">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="0b51d-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="0b51d-111">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="0b51d-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="0b51d-112">例如，将组号码 199 分配给用户：</span><span class="sxs-lookup"><span data-stu-id="0b51d-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b51d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b51d-113">See Also</span></span>


[<span data-ttu-id="0b51d-114">在 Lync Server 2013 中禁用用户的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="0b51d-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

