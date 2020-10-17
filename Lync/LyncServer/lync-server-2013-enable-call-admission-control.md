---
title: Lync Server 2013：启用呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528759"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="9048d-102">在 Lync Server 2013 中启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="9048d-102">Enable call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9048d-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9048d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9048d-104">配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。</span><span class="sxs-lookup"><span data-stu-id="9048d-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="9048d-105">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9048d-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9048d-106">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9048d-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="9048d-107">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9048d-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="9048d-108">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9048d-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="9048d-109">使用命令行管理程序启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="9048d-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="9048d-110">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9048d-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9048d-p101">运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="9048d-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="9048d-113">如果要在网络中禁用 CAC，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9048d-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="9048d-114">使用 Lync Server 控制面板启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="9048d-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9048d-115">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9048d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9048d-116">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="9048d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9048d-117">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9048d-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9048d-118">单击“全局”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="9048d-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="9048d-119">单击列表中的“全局”\*\*\*\*，然后在“编辑”\*\*\*\* 菜单中选择“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9048d-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9048d-120">在“编辑全局设置”\*\*\*\* 页上，选中“启用呼叫允许控制”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="9048d-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9048d-121">如果要在整个部署中禁用呼叫允许控制，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="9048d-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="9048d-122">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9048d-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

