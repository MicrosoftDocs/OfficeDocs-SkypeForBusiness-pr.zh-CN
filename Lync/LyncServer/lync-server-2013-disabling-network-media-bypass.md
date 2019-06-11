---
title: 'Lync Server 2013: 禁用网络媒体旁路'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="5ea18-102">在 Lync Server 2013 中禁用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="5ea18-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea18-103">_**主题上次修改时间:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="5ea18-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="5ea18-104">媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。</span><span class="sxs-lookup"><span data-stu-id="5ea18-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="5ea18-105">媒体绕过允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="5ea18-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="5ea18-106">有关何时使用 "媒体绕过" 的详细信息, 请参阅 "规划" 部分中的 "[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)"。可以从 Lync Server 控制面板禁用 "媒体绕过"。</span><span class="sxs-lookup"><span data-stu-id="5ea18-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="5ea18-107">有关启用和配置中间词跳过的详细信息, 请参阅[在 Lync Server 2013 中启用网络媒体旁路](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5ea18-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="5ea18-108">禁用媒体绕过</span><span class="sxs-lookup"><span data-stu-id="5ea18-108">To disable media bypass</span></span>

1.  <span data-ttu-id="5ea18-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5ea18-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ea18-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="5ea18-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5ea18-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5ea18-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5ea18-112">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。</span><span class="sxs-lookup"><span data-stu-id="5ea18-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="5ea18-113">在 "**全局**" 页面上, 单击 "**全局**配置"。</span><span class="sxs-lookup"><span data-stu-id="5ea18-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="5ea18-114">始终只有一种配置, 它始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="5ea18-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="5ea18-115">在 "**编辑**" 菜单上, 单击 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5ea18-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="5ea18-116">在 "**编辑全局设置**" 页面上, 清除 "**启用绕过媒体**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="5ea18-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="5ea18-117">单击 "**提交**" 保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5ea18-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea18-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea18-118">See Also</span></span>


[<span data-ttu-id="5ea18-119">在 Lync Server 2013 中启用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="5ea18-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

