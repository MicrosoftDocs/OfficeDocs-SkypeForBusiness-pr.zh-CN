---
title: Lync Server 2013：发布对语音路由配置所做的挂起更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec5236f6b40d332617e2e2a5dedeb6a77d752b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="f40ed-102">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="f40ed-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f40ed-103">_**上次修改的主题：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="f40ed-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="f40ed-104">在“语音路由”\*\*\*\* 组的页面中对任何配置设置做出更改后，执行此过程以查看、发布或取消待处理的更改。</span><span class="sxs-lookup"><span data-stu-id="f40ed-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f40ed-105">确保每次只有一个用户修改语音路由配置设置。</span><span class="sxs-lookup"><span data-stu-id="f40ed-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="f40ed-p101">必须通过运行“全部提交”<STRONG></STRONG>命令，同时发布所有待处理的更改。不能选择性地发布待处理的更改。发布待处理的更改前，运行“查看未提交的更改”<STRONG></STRONG>命令并取消任何不希望发布的配置更改。</span><span class="sxs-lookup"><span data-stu-id="f40ed-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="f40ed-109">如果在提交待处理更改前离开“语音路由”<STRONG></STRONG>组中的页面，所有待处理更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="f40ed-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="f40ed-110">但是，可以将当前配置（包括所有待处理的更改）导出至语音配置文件，然后导入并发布已更新的配置。</span><span class="sxs-lookup"><span data-stu-id="f40ed-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="f40ed-111">有关详细信息，请参阅<A href="lync-server-2013-export-a-voice-route-configuration-file.md">在 Lync Server 2013 中导出语音路由配置文件</A>。</span><span class="sxs-lookup"><span data-stu-id="f40ed-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="f40ed-112">查看、发布或取消语音路由配置更改</span><span class="sxs-lookup"><span data-stu-id="f40ed-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="f40ed-113">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="f40ed-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f40ed-114">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f40ed-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f40ed-115">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f40ed-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f40ed-116">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="f40ed-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f40ed-117">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="f40ed-118">在“语音路由”\*\*\*\* 组的每个页面中，对设置做出所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="f40ed-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="f40ed-119">要在不发布更改的情况下查看待处理的更改，请从“提交”\*\*\*\* 菜单中选择“查看未提交的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="f40ed-120">如果要取消任何待处理的更改，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f40ed-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="f40ed-121">从“提交”\*\*\*\* 菜单中选择“取消所有未提交的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="f40ed-122">导航到包含要取消的待处理更改的“语音路由”\*\*\*\* 页的选项卡，选择包含待处理更改的项目，单击“提交”\*\*\*\*，然后单击“取消选择的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="f40ed-123">查看所有待处理的更改并取消其中不希望发布的更改后，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="f40ed-124">在“未提交的语音配置设置”\*\*\*\* 对话框（其中显示所有待处理更改的列表）中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f40ed-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="f40ed-125">当 Lync Server 控制面板提交更改后，将显示 "**已成功发布语音路由配置**" 消息。</span><span class="sxs-lookup"><span data-stu-id="f40ed-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

