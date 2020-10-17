---
title: 修改不显式支持或限制的客户端的默认操作
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
ms.openlocfilehash: 213e42a7477202cf40a0b06c79edde49976f0bbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515269"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="58ad1-102">修改在 Lync Server 2013 中未明确支持或不受限制的客户端的默认操作</span><span class="sxs-lookup"><span data-stu-id="58ad1-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ad1-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="58ad1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="58ad1-104">除了指定要在 Lync Server 2013 环境中支持的客户端版本之外，还可以为尚未定义版本策略的客户端指定默认操作。</span><span class="sxs-lookup"><span data-stu-id="58ad1-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="58ad1-105">这使您可以限制在 Lync Server 环境中使用的客户端版本，这有助于控制与支持多个客户端版本相关的成本。</span><span class="sxs-lookup"><span data-stu-id="58ad1-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="58ad1-106">修改未显式支持或限制的客户端的默认操作</span><span class="sxs-lookup"><span data-stu-id="58ad1-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="58ad1-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="58ad1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58ad1-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="58ad1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58ad1-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="58ad1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58ad1-110">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“客户端版本配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58ad1-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="58ad1-111">在“客户端版本配置”\*\*\*\* 页上，双击列表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="58ad1-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="58ad1-112">在“编辑客户端版本配置”\*\*\*\* 对话框中，验证是否已选中“启用版本控制”\*\*\*\* 复选框，然后在“默认操作”\*\*\*\* 下选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="58ad1-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="58ad1-113">**允许**    如果客户端版本与**客户端版本策略**列表中的任何筛选器都不匹配，则允许客户端登录。</span><span class="sxs-lookup"><span data-stu-id="58ad1-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="58ad1-114">**阻止**    如果客户端版本与**客户端版本策略**列表中的任何筛选器都不匹配，则阻止客户端登录。</span><span class="sxs-lookup"><span data-stu-id="58ad1-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="58ad1-115">**带 URL**     的块如果客户端版本与 "**客户端版本策略**" 列表中的任何筛选器都不匹配，则阻止客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="58ad1-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="58ad1-116">**允许 URL**    如果客户端版本与 "**客户端版本策略**" 列表中的任何筛选器都不匹配，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="58ad1-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="58ad1-117">如果选择“使用 URL 阻止”\*\*\*\*，则在“URL”\*\*\*\* 框中键入将包含在错误消息中的客户端下载 URL。</span><span class="sxs-lookup"><span data-stu-id="58ad1-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="58ad1-118">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58ad1-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="58ad1-119">禁用客户端版本控制</span><span class="sxs-lookup"><span data-stu-id="58ad1-119">To disable client version control</span></span>

  - <span data-ttu-id="58ad1-120">要禁用版本控制以允许所有版本的客户端登录，请清除“启用版本控制”\*\*\*\* 复选框，然后单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58ad1-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="58ad1-121">使用 Windows PowerShell Cmdlet 修改默认操作</span><span class="sxs-lookup"><span data-stu-id="58ad1-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="58ad1-122">使用 Windows PowerShell 命令行接口和 **CsClientVersionPolicy** cmdlet 来管理用户尝试使用不是明确支持或受客户端版本策略限制的客户端登录时所采取的默认操作。</span><span class="sxs-lookup"><span data-stu-id="58ad1-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="58ad1-123">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="58ad1-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="58ad1-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="58ad1-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="58ad1-125">配置默认操作以阻止访问</span><span class="sxs-lookup"><span data-stu-id="58ad1-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="58ad1-p104">以下命令可将 Redmond 站点的默认操作设置为“阻止”。这将阻止针对没有客户端版本配置规则的任何客户端的注册。</span><span class="sxs-lookup"><span data-stu-id="58ad1-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="58ad1-128">将默认操作配置为允许访问</span><span class="sxs-lookup"><span data-stu-id="58ad1-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="58ad1-p105">在此示例中，Redmond 站点的默认操作将设置为“允许”。这将允许针对没有客户端版本配置规则的任何客户端的注册。</span><span class="sxs-lookup"><span data-stu-id="58ad1-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="58ad1-131">有关详细信息，请参阅 [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="58ad1-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58ad1-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58ad1-132">See Also</span></span>


[<span data-ttu-id="58ad1-133">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="58ad1-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

