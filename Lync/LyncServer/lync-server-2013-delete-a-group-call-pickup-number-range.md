---
title: Lync Server 2013：删除组呼叫装货号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179bde8b8e23cc21fb95fa93e3c6cbeb7f381630
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="ede03-102">在 Lync Server 2013 中删除组呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="ede03-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ede03-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ede03-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ede03-104">使用以下过程可删除组内呼叫装货号码范围。</span><span class="sxs-lookup"><span data-stu-id="ede03-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="ede03-105">删除呼叫应答组号码范围</span><span class="sxs-lookup"><span data-stu-id="ede03-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="ede03-106">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="ede03-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ede03-107">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ede03-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ede03-108">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ede03-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="ede03-109">例如：</span><span class="sxs-lookup"><span data-stu-id="ede03-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ede03-110">有关更多选项的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="ede03-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ede03-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ede03-111">See Also</span></span>


[<span data-ttu-id="ede03-112">在 Lync Server 2013 中创建或修改呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="ede03-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="ede03-113">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ede03-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="ede03-114">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ede03-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

