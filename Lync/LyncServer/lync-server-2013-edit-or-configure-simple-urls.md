---
title: Lync Server 2013：编辑或配置简单 Url
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e77d5ddf74d43cd277a701608e801a65262c929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="dee90-102">在 Lync Server 2013 中编辑或配置简单 Url</span><span class="sxs-lookup"><span data-stu-id="dee90-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee90-103">_**上次修改的主题：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="dee90-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="dee90-p101">此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="dee90-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="dee90-106">Lync Server 2013 使用简单 Url 将内部和外部呼叫定向到前端服务器或控制器上的服务（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="dee90-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="dee90-107">有关简单 Url 的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="dee90-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="dee90-108">您可以从多个选项中选择简单 Url 的格式。</span><span class="sxs-lookup"><span data-stu-id="dee90-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="dee90-109">有关这些选项的详细信息，请参阅规划文档中的[Lync Server 2013 中的简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="dee90-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="dee90-110">默认情况下，将以（例如，拨入简单 URL）的形式配置简单 Url： https://dialin.\<SIP域\></span><span class="sxs-lookup"><span data-stu-id="dee90-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="dee90-111">配置简单 URL</span><span class="sxs-lookup"><span data-stu-id="dee90-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="dee90-112">在拓扑生成器中，右键单击 " **Lync Server** " 节点，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="dee90-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dee90-113">在 "**简单 url** " 窗格中，选择 "**电话访问 Url：（电话**拨入）" 或 "**会议 url：** （满足）" 以进行编辑，然后单击 "**编辑 URL**"。</span><span class="sxs-lookup"><span data-stu-id="dee90-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="dee90-114">将 URL 更新为所需的值，然后单击“确定”\*\*\*\* 保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="dee90-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="dee90-115">此处显示的示例修改了拨入 URL https://pool01.contoso.net/dialin。</span><span class="sxs-lookup"><span data-stu-id="dee90-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="dee90-116">如有必要，使用相同的步骤编辑会议 URL。</span><span class="sxs-lookup"><span data-stu-id="dee90-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="dee90-117">定义可选的管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="dee90-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="dee90-118">在拓扑生成器中，右键单击 " **Lync Server** " 节点，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="dee90-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dee90-119">在 "**管理访问 URL** " 框中，输入要用于对 Lync Server 2013 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="dee90-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="dee90-120">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="dee90-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="dee90-121">最简单的方法是<STRONG> https://admin。</STRONG>&lt;域&gt;。</span><span class="sxs-lookup"><span data-stu-id="dee90-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dee90-122">如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="dee90-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="dee90-123">如果该更改影响简单 URL 的基础，则还必须更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="dee90-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="dee90-124">例如，从https://lync.contoso.com/Meet更改为将https://meet.contoso.com基 URL 从 lync.contoso.com 更改为 meet.contoso.com，因此您需要将 DNS 记录和证书更改为引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dee90-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="dee90-125">如果将简单 URL 从https://lync.contoso.com/Meet更改为https://lync.contoso.com/Meetings，lync.contoso.com 的基 url 将保持不变，因此不需要任何 DNS 或证书更改。</span><span class="sxs-lookup"><span data-stu-id="dee90-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="dee90-126">但是，只要您更改简单的 URL 名称，就必须在每个控制器和前端服务器上运行<STRONG>CsComputer</STRONG> cmdlet 以注册更改。</span><span class="sxs-lookup"><span data-stu-id="dee90-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dee90-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dee90-127">See Also</span></span>


[<span data-ttu-id="dee90-128">在 Lync Server 2013 中规划简单 Url</span><span class="sxs-lookup"><span data-stu-id="dee90-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

