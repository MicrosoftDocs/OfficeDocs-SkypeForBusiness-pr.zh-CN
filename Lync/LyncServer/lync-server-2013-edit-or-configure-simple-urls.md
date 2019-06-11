---
title: Lync Server 2013：编辑或配置简单 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="a7d8c-102">在 Lync Server 2013 中编辑或配置简单 URL</span><span class="sxs-lookup"><span data-stu-id="a7d8c-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7d8c-103">_**主题上次修改时间:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="a7d8c-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="a7d8c-104">此过程不需要本地管理员或特权域组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="a7d8c-105">您应以标准用户身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="a7d8c-106">Lync Server 2013 使用简单的 Url 将内部和外部调用用于前端服务器或控制器上的服务 (如果已部署)。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="a7d8c-107">有关简单 Url 的详细信息, 请参阅规划文档中的在[Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="a7d8c-108">你可以从多个选项中选择简单 Url 的格式。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="a7d8c-109">有关这些选项的详细信息, 请参阅规划文档中[Lync Server 2013 中简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="a7d8c-110">默认情况下, 将以 (例如, 拨入式简单 URL) 的形式配置简单的 Url: https://dialin.\<SIP域\></span><span class="sxs-lookup"><span data-stu-id="a7d8c-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="a7d8c-111">配置简单 Url</span><span class="sxs-lookup"><span data-stu-id="a7d8c-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="a7d8c-112">在拓扑生成器中, 右键单击 " **Lync 服务器**" 节点, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a7d8c-113">在“**简单 URL**”窗格中，选择要编辑的“**电话访问 URL:**”（拨入）或“**会议 URL:**”（会议），然后单击“**编辑 URL**”。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="a7d8c-114">将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="a7d8c-115">此处显示的示例已将拨入 URL 修改为https://pool01.contoso.net/dialin。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="a7d8c-116">如有必要，使用相同的步骤编辑会议 URL。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="a7d8c-117">定义可选的管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="a7d8c-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="a7d8c-118">在拓扑生成器中, 右键单击 " **Lync 服务器**" 节点, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a7d8c-119">在 "**管理访问 URL** " 框中, 输入要用于管理访问 Lync Server 2013 控制面板的简单 URL, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a7d8c-120">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="a7d8c-121">最简单的选项是<STRONG> https://admin。</STRONG>&lt;域&gt;。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7d8c-122">如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="a7d8c-123">如果更改影响简单 URL 的基础, 则必须同时更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="a7d8c-124">例如, 从https://lync.contoso.com/Meet https://meet.contoso.com lync.contoso.com 更改为 meet.contoso.com 的基本 URL, 因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="a7d8c-125">如果将简单 URL 更改https://lync.contoso.com/Meet为 "与https://lync.contoso.com/Meetings", lync.contoso.com 的基 url 保持不变, 因此不需要任何 DNS 或证书更改。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="a7d8c-126">但是, 每当你更改简单的 URL 名称时, 你必须在每个 Director 和前端服务器上运行<STRONG>Enable-CsComputer</STRONG> cmdlet 来注册更改。</span><span class="sxs-lookup"><span data-stu-id="a7d8c-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7d8c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7d8c-127">See Also</span></span>


[<span data-ttu-id="a7d8c-128">在 Lync Server 2013 中规划简单 URL</span><span class="sxs-lookup"><span data-stu-id="a7d8c-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

