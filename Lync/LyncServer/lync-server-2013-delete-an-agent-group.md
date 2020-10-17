---
title: Lync Server 2013：删除代理组
description: Lync Server 2013：删除代理组。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dded2db0957e37a624d7e8bf3a06e102f8d35cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553678"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="486ff-103">在 Lync Server 2013 中删除代理组</span><span class="sxs-lookup"><span data-stu-id="486ff-103">Delete an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="486ff-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="486ff-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="486ff-105">使用以下过程之一删除代理组。</span><span class="sxs-lookup"><span data-stu-id="486ff-105">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="486ff-106">使用 Lync Server 控制面板删除代理组</span><span class="sxs-lookup"><span data-stu-id="486ff-106">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="486ff-107">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="486ff-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="486ff-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="486ff-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="486ff-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="486ff-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="486ff-110">在左侧导航栏中，单击 **“响应组”**，然后单击 **“组”**。</span><span class="sxs-lookup"><span data-stu-id="486ff-110">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="486ff-111">在 " **响应组** " 页上，在 "搜索" 字段中键入要删除的代理组的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="486ff-111">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="486ff-112">在生成的列表中，单击要删除的组，单击 " **编辑**"，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="486ff-112">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="486ff-113">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="486ff-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="486ff-114">使用 Windows PowerShell 删除代理组</span><span class="sxs-lookup"><span data-stu-id="486ff-114">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="486ff-115">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="486ff-115">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="486ff-116">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="486ff-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="486ff-117">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="486ff-117">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="486ff-118">例如：</span><span class="sxs-lookup"><span data-stu-id="486ff-118">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="486ff-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="486ff-119">See Also</span></span>


[<span data-ttu-id="486ff-120">在 Lync Server 2013 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="486ff-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="486ff-121">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="486ff-121">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="486ff-122">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="486ff-122">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

