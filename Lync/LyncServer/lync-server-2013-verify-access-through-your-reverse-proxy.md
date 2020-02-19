---
title: Lync Server 2013：通过反向代理验证访问权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b26afb358a78e18476efbebf7de4c8088e131f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="c0c8e-102">通过你在 Lync Server 2013 中的反向代理验证访问权限</span><span class="sxs-lookup"><span data-stu-id="c0c8e-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0c8e-103">_**上次修改的主题：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="c0c8e-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="c0c8e-p101">使用以下过程验证用户是否能够访问反向代理上的信息。您可能需要完成防火墙配置和域名系统 (DNS) 配置，才能正确进行访问。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="c0c8e-106">验证是否能通过 Internet 访问网站</span><span class="sxs-lookup"><span data-stu-id="c0c8e-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="c0c8e-107">打开 Web 浏览器，在“地址”\*\*\*\* 栏中键入客户端用于访问通讯簿文件和会议网站的 URL，具体如下：</span><span class="sxs-lookup"><span data-stu-id="c0c8e-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="c0c8e-108">对于 "通讯簿服务器"，键入类似于以下的 URL **https://externalwebfarmFQDN/abs** ：其中 externalwebfarmFQDN 是承载通讯簿服务的外部 web 服务的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="c0c8e-109">用户应收到 HTTP 质询，因为默认情况下将通讯簿服务器文件夹的目录安全性配置为 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="c0c8e-110">对于 "会议"，键入类似于以下的 URL **https://externalwebfarmFQDN/meet** ：其中 externalwebfarmFQDN 是承载会议内容的 web 场的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="c0c8e-111">此 URL 应会显示会议的疑难解答页。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="c0c8e-112">或者，确认您的会议的简单 URL 能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="c0c8e-113">会议加入的一个简单 URL 示例可能是https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0c8e-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="c0c8e-114">对于通讯组展开，请键入类似于以下的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc**。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="c0c8e-115">用户应收到 HTTP 质询，因为默认情况下将通讯组扩展服务的目录安全性配置为 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="c0c8e-116">对于 "拨入"，键入与以下**https://externalwebfarmFQDN/dialin**内容类似的简单 URL，其中 externalwebfarmFQDN 是承载电话拨入式会议的拨入寻呼的 web 服务器场的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="c0c8e-117">应将用户定向到拨入页。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="c0c8e-118">或者，确认您的电话拨入式会议的简单 URL 能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="c0c8e-119">用于拨入的简单 URL 示例可能是https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0c8e-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="c0c8e-120">若要确认自动发现 URL 是否正常运行， https://lyncdiscover请键入。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="c0c8e-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="c0c8e-121">externaldomainFQDN.</span></span> <span data-ttu-id="c0c8e-122">浏览器应提示您打开文件。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="c0c8e-123">选择 "记事本" 将其打开。</span><span class="sxs-lookup"><span data-stu-id="c0c8e-123">Select Notepad to open it.</span></span> <span data-ttu-id="c0c8e-124">典型的响应类似于：</span><span class="sxs-lookup"><span data-stu-id="c0c8e-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

