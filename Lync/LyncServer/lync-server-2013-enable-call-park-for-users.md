---
title: Lync Server 2013：为用户启用呼叫寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="aac73-102">在 Lync Server 2013 中为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="aac73-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aac73-103">_**主题上次修改时间：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="aac73-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="aac73-104">用户不能寄存通话或检索寄存的呼叫，直到它们在语音策略中被启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="aac73-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aac73-105">默认情况下，将对所有用户禁用 "呼叫寄存"。</span><span class="sxs-lookup"><span data-stu-id="aac73-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="aac73-106">你可以在全局范围内或在网站范围或用户范围内启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="aac73-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="aac73-107">用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。</span><span class="sxs-lookup"><span data-stu-id="aac73-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="aac73-108">如果你有多个语音策略，请查看所有策略以启用呼叫寄存，而不仅仅是全局策略。</span><span class="sxs-lookup"><span data-stu-id="aac73-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="aac73-109">使用 Lync Server "控制面板" 为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="aac73-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="aac73-110">以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="aac73-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="aac73-111">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="aac73-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aac73-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aac73-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aac73-113">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aac73-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="aac73-114">单击“语音策略”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aac73-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="aac73-115">双击现有语音策略以打开“编辑语音策略”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="aac73-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="aac73-116">在“呼叫功能”\*\*\*\* 下，选择“启用呼叫寄存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aac73-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="aac73-117">单击“确定”\*\*\*\* 保存语音策略。</span><span class="sxs-lookup"><span data-stu-id="aac73-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="aac73-118">使用 Cmdlet 为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="aac73-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="aac73-119">以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="aac73-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="aac73-120">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="aac73-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aac73-121">运行：</span><span class="sxs-lookup"><span data-stu-id="aac73-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="aac73-122">例如，若要为默认全局语音策略启用呼叫寄存，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aac73-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aac73-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aac73-123">See Also</span></span>


[<span data-ttu-id="aac73-124">在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="aac73-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

