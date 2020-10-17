---
title: Lync Server 2013：删除呼叫寄存通道范围
description: Lync Server 2013：删除呼叫寄存通道范围。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb0bbd34a1f151b32067b7375948f712fa6d902
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544808"
---
# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="9f80c-103">在 Lync Server 2013 中删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="9f80c-103">Delete a Call Park orbit range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f80c-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9f80c-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9f80c-105">使用以下过程之一可删除呼叫寄存通道范围。</span><span class="sxs-lookup"><span data-stu-id="9f80c-105">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="9f80c-106">使用 Lync Server 控制面板删除呼叫寄存轨道范围</span><span class="sxs-lookup"><span data-stu-id="9f80c-106">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="9f80c-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="9f80c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9f80c-108">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9f80c-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9f80c-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9f80c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9f80c-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="9f80c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9f80c-111">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“呼叫寄存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f80c-111">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="9f80c-112">在“呼叫寄存”\*\*\*\* 页上的搜索字段中，键入要删除的通道范围的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="9f80c-112">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="9f80c-113">在通道的结果列表中，单击通道，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f80c-113">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="9f80c-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f80c-114">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="9f80c-115">使用 Windows PowerShell 删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="9f80c-115">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="9f80c-116">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="9f80c-116">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9f80c-117">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f80c-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9f80c-118">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="9f80c-118">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="9f80c-119">例如：</span><span class="sxs-lookup"><span data-stu-id="9f80c-119">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f80c-120">有关更多选项的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="9f80c-120">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f80c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f80c-121">See Also</span></span>


[<span data-ttu-id="9f80c-122">在 Lync Server 2013 中创建或修改呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="9f80c-122">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="9f80c-123">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="9f80c-123">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="9f80c-124">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="9f80c-124">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

