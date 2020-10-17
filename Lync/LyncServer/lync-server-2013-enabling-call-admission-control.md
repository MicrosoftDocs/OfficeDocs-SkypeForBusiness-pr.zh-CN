---
title: Lync Server 2013：启用呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfe6ae76fd1f6b89178d101337f24ba0089dd35b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500979"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="00814-102">在 Lync Server 2013 中启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="00814-102">Enabling call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00814-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="00814-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="00814-104">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。</span><span class="sxs-lookup"><span data-stu-id="00814-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="00814-105">配置 CAC 网络后，必须启用 CAC 以强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="00814-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="00814-106">您可以使用 Lync Server 控制面板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="00814-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="00814-107">从 Lync Server 控制面板启用 CAC</span><span class="sxs-lookup"><span data-stu-id="00814-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="00814-108">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="00814-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00814-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="00814-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="00814-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="00814-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="00814-111">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“全局”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00814-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="00814-112">在“全局”\*\*\*\* 页上，单击“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="00814-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00814-113">只能为任何 Microsoft Lync Server 2013 部署配置一个网络，因此列表中永远不会有多个网络配置。</span><span class="sxs-lookup"><span data-stu-id="00814-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="00814-114">无法重命名“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="00814-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="00814-115">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00814-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="00814-116">在“编辑全局设置”\*\*\*\* 页上，选中“启用呼叫允许控制”\*\*\*\* 复选框，然后单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00814-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="00814-p104">单击“提交”\*\*\*\* 时，运行配置测试。此时将关闭“编辑全局设置”\*\*\*\* 对话框，并返回到“全局”\*\*\*\* 页。如果在网络配置中发现任何阻止其正常工作的错误或不一致问题（例如，如果每个区域未通过区域间路由连接到其他每个区域），则会收到警告。</span><span class="sxs-lookup"><span data-stu-id="00814-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="00814-p105">如果更改网络配置，则可通过打开“全局”配置并单击“提交”\*\*\*\* 再次运行验证检查。无需先禁用 CAC：保留此复选框的选中状态，并单击“提交”\*\*\*\*。在未对配置进行任何更改的情况下可随时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="00814-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00814-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00814-123">See Also</span></span>


[<span data-ttu-id="00814-124">Lync Server 2013 中的呼叫允许控制概述</span><span class="sxs-lookup"><span data-stu-id="00814-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="00814-125">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="00814-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="00814-126">在 Lync Server 2013 中配置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="00814-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="00814-127">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="00814-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="00814-128">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="00814-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="00814-129">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="00814-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

