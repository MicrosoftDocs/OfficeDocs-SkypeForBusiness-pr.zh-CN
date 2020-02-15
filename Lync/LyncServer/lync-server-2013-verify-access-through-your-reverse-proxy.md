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
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>通过你在 Lync Server 2013 中的反向代理验证访问权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-29_

使用以下过程验证用户是否能够访问反向代理上的信息。您可能需要完成防火墙配置和域名系统 (DNS) 配置，才能正确进行访问。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>验证是否能通过 Internet 访问网站

  - 打开 Web 浏览器，在“地址”**** 栏中键入客户端用于访问通讯簿文件和会议网站的 URL，具体如下：
    
      - 对于 "通讯簿服务器"，键入类似于以下的 URL **https://externalwebfarmFQDN/abs** ：其中 externalwebfarmFQDN 是承载通讯簿服务的外部 web 服务的外部 FQDN。 用户应收到 HTTP 质询，因为默认情况下将通讯簿服务器文件夹的目录安全性配置为 Windows 身份验证。
    
      - 对于 "会议"，键入类似于以下的 URL **https://externalwebfarmFQDN/meet** ：其中 externalwebfarmFQDN 是承载会议内容的 web 场的外部 FQDN。 此 URL 应会显示会议的疑难解答页。 或者，确认您的会议的简单 URL 能正常工作。 会议加入的一个简单 URL 示例可能是https://meet.contoso.com
    
      - 对于通讯组展开，请键入类似于以下的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc**。 用户应收到 HTTP 质询，因为默认情况下将通讯组扩展服务的目录安全性配置为 Windows 身份验证。
    
      - 对于 "拨入"，键入与以下**https://externalwebfarmFQDN/dialin**内容类似的简单 URL，其中 externalwebfarmFQDN 是承载电话拨入式会议的拨入寻呼的 web 服务器场的外部 FQDN。 应将用户定向到拨入页。 或者，确认您的电话拨入式会议的简单 URL 能正常工作。 用于拨入的简单 URL 示例可能是https://dialin.contoso.com
    
      - 若要确认自动发现 URL 是否正常运行， https://lyncdiscover请键入。 externaldomainFQDN. 浏览器应提示您打开文件。 选择 "记事本" 将其打开。 典型的响应类似于：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

