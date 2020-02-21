---
title: Lync Server 2013：查看 PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c6ca5761959b8b98cb4eb6a8f17e87c543e788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="da2a6-102">在 Lync Server 2013 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="da2a6-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da2a6-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="da2a6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="da2a6-104">公用电话交换网（PSTN）使用记录指定一类呼叫（如内部、本地或长途），可以由组织中的不同用户或用户组进行。</span><span class="sxs-lookup"><span data-stu-id="da2a6-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="da2a6-105">有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 PSTN 用法记录](lync-server-2013-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="da2a6-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="da2a6-106">使用 Lync Server 控制面板查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="da2a6-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="da2a6-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="da2a6-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="da2a6-108">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="da2a6-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="da2a6-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="da2a6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="da2a6-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="da2a6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da2a6-111">在左侧导航栏中，单击 "**语音路由**"，然后单击 " **PSTN 用法**"。</span><span class="sxs-lookup"><span data-stu-id="da2a6-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="da2a6-112">在 " **PSTN 使用情况**" 页上，突出显示要查看的 pstn 用法记录，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="da2a6-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da2a6-113">选定 PSTN 用法记录的只读页面显示关联的路由和关联的语音策略。</span><span class="sxs-lookup"><span data-stu-id="da2a6-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da2a6-114">使用 Windows PowerShell Cmdlet 查看 PSTN 用法信息</span><span class="sxs-lookup"><span data-stu-id="da2a6-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da2a6-115">您还可以使用 Windows PowerShell 和**CsPstnUsage** CMDLET 查看 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="da2a6-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="da2a6-116">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="da2a6-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="da2a6-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="da2a6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da2a6-118">使用 Windows PowerShell cmdlet 查看 PSTN 用法信息</span><span class="sxs-lookup"><span data-stu-id="da2a6-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="da2a6-119">若要查看有关您的所有 PSTN 用法的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="da2a6-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="da2a6-120">此命令返回与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="da2a6-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="da2a6-121">有关详细信息，请参阅[CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)。</span><span class="sxs-lookup"><span data-stu-id="da2a6-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da2a6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da2a6-122">See Also</span></span>


[<span data-ttu-id="da2a6-123">在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="da2a6-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="da2a6-124">在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="da2a6-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

