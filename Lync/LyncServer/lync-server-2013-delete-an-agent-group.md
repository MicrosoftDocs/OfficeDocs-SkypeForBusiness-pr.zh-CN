---
title: Lync Server 2013：删除代理组
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
ms.openlocfilehash: eb8ebde61d1ba59952741bffd14e29ae87d482f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="af803-102">在 Lync Server 2013 中删除代理组</span><span class="sxs-lookup"><span data-stu-id="af803-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af803-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="af803-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="af803-104">使用以下过程之一删除代理组。</span><span class="sxs-lookup"><span data-stu-id="af803-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="af803-105">使用 Lync Server "控制面板" 删除代理组</span><span class="sxs-lookup"><span data-stu-id="af803-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="af803-106">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="af803-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="af803-107">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="af803-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af803-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="af803-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af803-109">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af803-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="af803-110">在 "**响应组**" 页面上，在 "搜索" 字段中键入要删除的 agent 组的全名或部分名称。</span><span class="sxs-lookup"><span data-stu-id="af803-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="af803-111">在生成的列表中，单击要删除的组，单击 "**编辑**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="af803-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="af803-112">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="af803-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="af803-113">使用 Windows PowerShell 删除代理组</span><span class="sxs-lookup"><span data-stu-id="af803-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="af803-114">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="af803-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="af803-115">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="af803-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="af803-116">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="af803-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="af803-117">例如：</span><span class="sxs-lookup"><span data-stu-id="af803-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af803-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af803-118">See Also</span></span>


[<span data-ttu-id="af803-119">在 Lync Server 2013 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="af803-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="af803-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="af803-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="af803-121">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="af803-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

