---
title: Lync Server 2013：为用户启用统一联系人存储
description: Lync Server 2013：为用户启用统一联系人存储。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2249249d314e13d840b276e46f1fe38ad271664a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572728"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="a94e2-103">在 Lync Server 2013 中为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="a94e2-103">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a94e2-104">_**上次修改的主题：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="a94e2-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="a94e2-105">当您部署 Lync Server 2013 并发布拓扑时，默认情况下会为所有用户启用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="a94e2-105">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="a94e2-106">部署 Lync Server 2013 后，无需执行任何其他操作即可启用统一的联系人存储。</span><span class="sxs-lookup"><span data-stu-id="a94e2-106">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="a94e2-107">但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一的联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="a94e2-107">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="a94e2-108">可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。</span><span class="sxs-lookup"><span data-stu-id="a94e2-108">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="a94e2-109">为用户启用统一的联系人存储库</span><span class="sxs-lookup"><span data-stu-id="a94e2-109">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="a94e2-110">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a94e2-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a94e2-111">执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="a94e2-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="a94e2-112">若要为所有 Lync Server 用户全局启用统一联系人存储，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a94e2-112">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="a94e2-113">若要为特定站点的用户启用统一的联系人存储库，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a94e2-113">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="a94e2-114">例如：</span><span class="sxs-lookup"><span data-stu-id="a94e2-114">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="a94e2-115">若要按租户启用统一的联系人存储库，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a94e2-115">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="a94e2-116">例如：</span><span class="sxs-lookup"><span data-stu-id="a94e2-116">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="a94e2-117">若要为特定用户启用统一的联系人存储库，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a94e2-117">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a94e2-118">还可以使用用户别名或 SIP URI 代替用户显示名称。</span><span class="sxs-lookup"><span data-stu-id="a94e2-118">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="a94e2-119">例如：</span><span class="sxs-lookup"><span data-stu-id="a94e2-119">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a94e2-p102">在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”<EM></EM>的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="a94e2-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

