---
title: Lync Server 2013：配置会议邀请
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="8c7c8-102">在 Lync Server 2013 中配置会议邀请</span><span class="sxs-lookup"><span data-stu-id="8c7c8-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c7c8-103">_**上次修改的主题：** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="8c7c8-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="8c7c8-104">您可以通过在会议邀请正文中添加以下可选项目，从而自定义由 Lync 2013 的联机会议外接程序发送的会议邀请：</span><span class="sxs-lookup"><span data-stu-id="8c7c8-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="8c7c8-105">**你组织的徽标**使用 "徽标 URL" 选项将组织的徽标添加到会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="8c7c8-106">如果将会议邀请发送给组织外部的人员，则该图像应位于公开发布的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="8c7c8-107">支持的图像格式为 GIF 和 JPG。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="8c7c8-108">尽管 Lync Server 2013 将无大小限制的 URL 存储在图像上，但为了获得最佳效果，图像的最大大小应为30像素（高为188像素宽）。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="8c7c8-109">**自定义帮助或支持链接**为您的组织的帮助或支持团队网站添加 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="8c7c8-110">如果将会议邀请发送给组织外部的人员，则 URL 应公开可用。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="8c7c8-111">最大 URL 长度为 1 KB。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="8c7c8-112">**法律免责声明文本**添加将在所有会议邀请中显示的法律文本或免责声明的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="8c7c8-113">如果将会议邀请发送给组织外部的人员，则 URL 应公开可用。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="8c7c8-114">最大 URL 长度为 1 KB。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="8c7c8-115">**自定义页脚文本**添加将在邀请中呈现为自定义页脚的文本。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="8c7c8-116">可添加的文本的最大长度为 2 KB。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="8c7c8-117">您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="8c7c8-118">**使用 Lync Server 控制面板自定义会议邀请的具体方法**</span><span class="sxs-lookup"><span data-stu-id="8c7c8-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="8c7c8-119">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8c7c8-120">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c7c8-121">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c7c8-122">在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="8c7c8-123">在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8c7c8-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="8c7c8-p106">要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="8c7c8-p107">要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="8c7c8-130">执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="8c7c8-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="8c7c8-131">在 "**徽标 URL** " 字段中，键入您组织的徽标图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="8c7c8-132">在 "**帮助 URL** " 字段中，键入您的组织的帮助或支持网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="8c7c8-133">在 "**法律文本**" 字段中，键入要包含在会议邀请中的法律文本或免责声明的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="8c7c8-134">在 "**自定义页脚" 文本**字段中，键入页脚文本，最高为 2 KB。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="8c7c8-135">**使用 Lync Server 命令行管理程序自定义会议邀请**</span><span class="sxs-lookup"><span data-stu-id="8c7c8-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="8c7c8-136">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8c7c8-137">运行**get-csmeetingconfiguration**或**get-csmeetingconfiguration** cmdlet 以创建或配置会议邀请选项。</span><span class="sxs-lookup"><span data-stu-id="8c7c8-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="8c7c8-138">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="8c7c8-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

