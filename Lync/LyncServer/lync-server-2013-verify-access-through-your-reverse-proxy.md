---
title: Lync Server 2013：验证能否通过反向代理进行访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="6ea03-102">在 Lync Server 2013 中验证能否通过反向代理进行访问</span><span class="sxs-lookup"><span data-stu-id="6ea03-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea03-103">_**主题上次修改时间:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="6ea03-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="6ea03-104">使用以下过程验证用户是否可以访问反向代理上的信息。</span><span class="sxs-lookup"><span data-stu-id="6ea03-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="6ea03-105">你可能需要完成防火墙配置和域名系统 (DNS) 配置, access 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="6ea03-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="6ea03-106">验证是否可以通过 Internet 访问网站</span><span class="sxs-lookup"><span data-stu-id="6ea03-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="6ea03-107">打开 web 浏览器, 在**地址**栏中键入客户端用于访问通讯簿文件和网站的地址栏中的 url, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="6ea03-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="6ea03-108">对于 "通讯簿" 服务器, 请键入类似于以下内容**https://externalwebfarmFQDN/abs**的 URL: 其中 externalwebfarmFQDN 是托管通讯簿服务的外部 web 服务的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6ea03-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="6ea03-109">用户应收到 HTTP 质询, 因为通讯簿服务器文件夹上的目录安全性默认配置为 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ea03-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="6ea03-110">对于会议, 请键入类似于以下内容的 URL **https://externalwebfarmFQDN/meet** : 其中 externalwebfarmFQDN 是托管会议内容的 web 场的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6ea03-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="6ea03-111">此 URL 应显示会议的疑难解答页面。</span><span class="sxs-lookup"><span data-stu-id="6ea03-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="6ea03-112">或者, 确认会议的简单 URL 是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="6ea03-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="6ea03-113">有关会议联接的简单 URL 的示例可能是https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ea03-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="6ea03-114">对于通讯组扩展, 请键入类似于以下内容的 URL **https://externalwebfarmFQDN/GroupExpansion/service.svc**:。</span><span class="sxs-lookup"><span data-stu-id="6ea03-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="6ea03-115">用户应收到 HTTP 质询, 因为通讯组扩展服务上的目录安全性默认配置为 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ea03-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="6ea03-116">对于 "拨入", 键入类似于以下**https://externalwebfarmFQDN/dialin**内容的简单 URL, 其中 externalwebfarmFQDN 是托管电话拨入式会议的拨入页面的 web 场的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6ea03-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="6ea03-117">应将用户定向到拨入页面。</span><span class="sxs-lookup"><span data-stu-id="6ea03-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="6ea03-118">或者, 确认你的简单 URL 拨入功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="6ea03-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="6ea03-119">拨入的简单 URL 示例可能是https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ea03-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="6ea03-120">若要确认自动发现 URL 是否正常工作, https://lyncdiscover请键入。</span><span class="sxs-lookup"><span data-stu-id="6ea03-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="6ea03-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="6ea03-121">externaldomainFQDN.</span></span> <span data-ttu-id="6ea03-122">浏览器应提示您打开文件。</span><span class="sxs-lookup"><span data-stu-id="6ea03-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="6ea03-123">选择 "记事本" 将其打开。</span><span class="sxs-lookup"><span data-stu-id="6ea03-123">Select Notepad to open it.</span></span> <span data-ttu-id="6ea03-124">典型的响应类似于:</span><span class="sxs-lookup"><span data-stu-id="6ea03-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

