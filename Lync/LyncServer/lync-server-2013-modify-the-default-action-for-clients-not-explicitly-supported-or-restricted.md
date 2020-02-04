---
title: 修改不明确支持或限制的客户端的默认操作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0262bface172c965d12fc276bc08882cac8348ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="eb107-102">修改在 Lync Server 2013 中未明确支持或限制的客户端的默认操作</span><span class="sxs-lookup"><span data-stu-id="eb107-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb107-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eb107-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eb107-104">除了指定你希望在 Lync Server 2013 环境中支持的客户端版本，还可以为尚未定义版本策略的客户端指定默认操作。</span><span class="sxs-lookup"><span data-stu-id="eb107-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="eb107-105">这使你能够限制 Lync Server 环境中使用的客户端版本，这有助于你控制与支持多个客户端版本相关联的成本。</span><span class="sxs-lookup"><span data-stu-id="eb107-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="eb107-106">修改不明确支持或限制的客户端的默认操作</span><span class="sxs-lookup"><span data-stu-id="eb107-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="eb107-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="eb107-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eb107-108">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="eb107-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eb107-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="eb107-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eb107-110">在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**"。</span><span class="sxs-lookup"><span data-stu-id="eb107-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="eb107-111">在 "**客户端版本配置**" 页面上，双击列表中的**全局**配置。</span><span class="sxs-lookup"><span data-stu-id="eb107-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="eb107-112">在 "**编辑客户端版本配置**" 对话框中，验证已选中 "**启用版本控制**" 复选框，然后在 "**默认操作**" 下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="eb107-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="eb107-113">\*\*\*\*   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，允许客户端登录。</span><span class="sxs-lookup"><span data-stu-id="eb107-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="eb107-114">\*\*\*\*   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，则 Block 将阻止客户端登录。</span><span class="sxs-lookup"><span data-stu-id="eb107-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="eb107-115">**带 url**   的块阻止客户端在客户端版本与**客户端版本策略**列表中的任何筛选器不匹配时登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="eb107-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="eb107-116">**允许使用 URL**   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="eb107-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="eb107-117">如果选择了 "**带 URL 的块**"，请在 " **URL** " 框中键入要包含在错误消息中的客户端下载 URL。</span><span class="sxs-lookup"><span data-stu-id="eb107-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="eb107-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="eb107-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="eb107-119">禁用客户端版本控制</span><span class="sxs-lookup"><span data-stu-id="eb107-119">To disable client version control</span></span>

  - <span data-ttu-id="eb107-120">若要在不考虑客户端版本的情况下禁用版本控制以允许所有客户端登录，请清除 "**启用版本控制**" 复选框，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="eb107-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eb107-121">使用 Windows PowerShell Cmdlet 修改默认操作</span><span class="sxs-lookup"><span data-stu-id="eb107-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eb107-122">使用 Windows PowerShell 命令行界面和**CsClientVersionPolicy** cmdlet 管理用户尝试使用不是由客户端版本策略明确支持或限制的客户端尝试登录时所采取的默认操作。</span><span class="sxs-lookup"><span data-stu-id="eb107-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="eb107-123">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="eb107-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eb107-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="eb107-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="eb107-125">配置默认操作阻止访问</span><span class="sxs-lookup"><span data-stu-id="eb107-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="eb107-126">以下命令设置雷德蒙网站块的默认操作。</span><span class="sxs-lookup"><span data-stu-id="eb107-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="eb107-127">这将阻止不存在任何客户端版本配置规则的任何客户端的注册。</span><span class="sxs-lookup"><span data-stu-id="eb107-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="eb107-128">将默认操作配置为允许访问</span><span class="sxs-lookup"><span data-stu-id="eb107-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="eb107-129">在此示例中，雷德蒙网站的默认操作设置为 "允许"。</span><span class="sxs-lookup"><span data-stu-id="eb107-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="eb107-130">这将允许为不存在任何客户端版本配置规则的任何客户端注册。</span><span class="sxs-lookup"><span data-stu-id="eb107-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="eb107-131">有关详细信息，请参阅[CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="eb107-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb107-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb107-132">See Also</span></span>


[<span data-ttu-id="eb107-133">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="eb107-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

