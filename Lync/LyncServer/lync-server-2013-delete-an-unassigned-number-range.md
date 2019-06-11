---
title: 'Lync Server 2013: 删除未分配的号码范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8bf1bcea1a2f84def783b833d232a44282cab6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="8b7c2-102">在 Lync Server 2013 中删除未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="8b7c2-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b7c2-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8b7c2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8b7c2-104">使用以下过程之一删除公告的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="8b7c2-105">使用 Lync Server "控制面板" 删除未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="8b7c2-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="8b7c2-106">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8b7c2-107">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8b7c2-108">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8b7c2-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8b7c2-110">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“未分配号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="8b7c2-111">在“未分配号码”\*\*\*\* 页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="8b7c2-112">在号码范围的结果列表中，单击名称，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="8b7c2-113">单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="8b7c2-114">使用 Windows PowerShell 删除未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="8b7c2-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="8b7c2-115">以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机, 如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8b7c2-116">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8b7c2-117">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8b7c2-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="8b7c2-118">例如：</span><span class="sxs-lookup"><span data-stu-id="8b7c2-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b7c2-119">有关更多选项的详细信息, 请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="8b7c2-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b7c2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b7c2-120">See Also</span></span>


[<span data-ttu-id="8b7c2-121">在 Lync Server 2013 中创建或修改未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="8b7c2-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="8b7c2-122">Remove-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="8b7c2-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="8b7c2-123">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="8b7c2-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

