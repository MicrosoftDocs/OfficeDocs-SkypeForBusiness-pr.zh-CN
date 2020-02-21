---
title: Lync Server 2013：证书摘要-可扩展消息传递和状态协议（XMPP）联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="c5b48-102">Lync Server 2013 中的证书摘要-可扩展消息传递和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="c5b48-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5b48-103">_**上次修改的主题：** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="c5b48-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="c5b48-p101">用于启用并与可扩展消息传递和状态协议 (XMPP) 伙伴建立通信的证书要求需要 XMPP 域的其他记录。作为使用者替代名称 (SAN) 包含在证书上的记录将成为可以参与 XMPP 通信的域。如果要针对整个域启用 XMPP，则该域可以是根级别域（例如，contoso.com），或者如果要针对用户的子集启用 XMPP，该域也可以是选定的子域（例如，corp.contoso.com、finance.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="c5b48-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c5b48-107">可扩展消息传递和状态协议的证书摘要</span><span class="sxs-lookup"><span data-stu-id="c5b48-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5b48-108">组件</span><span class="sxs-lookup"><span data-stu-id="c5b48-108">Component</span></span></th>
<th><span data-ttu-id="c5b48-109">使用者名称</span><span class="sxs-lookup"><span data-stu-id="c5b48-109">Subject name</span></span></th>
<th><span data-ttu-id="c5b48-110">使用者替代名称 (SAN)/顺序</span><span class="sxs-lookup"><span data-stu-id="c5b48-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="c5b48-111">备注</span><span class="sxs-lookup"><span data-stu-id="c5b48-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5b48-112">分配到边缘服务器或边缘池的访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="c5b48-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="c5b48-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5b48-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5b48-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5b48-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="c5b48-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5b48-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="c5b48-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c5b48-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="c5b48-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5b48-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5b48-118">前三个 SAN 条目是完整边缘服务器的常规 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="c5b48-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="c5b48-119">contoso.com 是在根域级别与 XMPP 合作伙伴联盟所需的条目。</span><span class="sxs-lookup"><span data-stu-id="c5b48-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="c5b48-120">此条目将允许具有后缀 contoso.com 的所有域的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="c5b48-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5b48-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b48-121">See Also</span></span>


[<span data-ttu-id="c5b48-122">Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="c5b48-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="c5b48-123">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="c5b48-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="c5b48-124">为 Lync Server 2013 设置边缘证书</span><span class="sxs-lookup"><span data-stu-id="c5b48-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="c5b48-125">请求-Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="c5b48-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="c5b48-126">Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="c5b48-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

