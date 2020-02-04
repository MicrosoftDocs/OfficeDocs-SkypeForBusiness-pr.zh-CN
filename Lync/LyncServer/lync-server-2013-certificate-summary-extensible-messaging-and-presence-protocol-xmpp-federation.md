---
title: Lync Server 2013：证书摘要-可扩展消息传递和状态协议（XMPP）联合身份验证
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
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="57232-102">证书摘要-Lync Server 2013 中的可扩展消息和状态协议（XMPP）联合</span><span class="sxs-lookup"><span data-stu-id="57232-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57232-103">_**主题上次修改时间：** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="57232-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="57232-104">启用和建立与可扩展消息和状态协议（XMPP）合作伙伴的通信的证书要求需要您的 XMPP 域的其他记录。</span><span class="sxs-lookup"><span data-stu-id="57232-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="57232-105">作为主题备用名称（SAN）包含在证书上的记录将是可参与 XMPP 通信的域。</span><span class="sxs-lookup"><span data-stu-id="57232-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="57232-106">如果你想要为整个域启用 XMPP，或者可以选择子域（例如 corp.contoso.com，finance.contoso.com），则域可以是根级别的域（例如 contoso.com），如果要为用户的子集启用 XMPP，也可以选择 "子域" （例如、）。</span><span class="sxs-lookup"><span data-stu-id="57232-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="57232-107">可扩展消息和状态协议的证书摘要</span><span class="sxs-lookup"><span data-stu-id="57232-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57232-108">组件</span><span class="sxs-lookup"><span data-stu-id="57232-108">Component</span></span></th>
<th><span data-ttu-id="57232-109">主题名称</span><span class="sxs-lookup"><span data-stu-id="57232-109">Subject name</span></span></th>
<th><span data-ttu-id="57232-110">使用者备用名称（SAN）/Order</span><span class="sxs-lookup"><span data-stu-id="57232-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="57232-111">备注</span><span class="sxs-lookup"><span data-stu-id="57232-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57232-112">分配到边缘服务器或边缘池的访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="57232-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="57232-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57232-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="57232-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57232-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="57232-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="57232-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="57232-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="57232-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="57232-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="57232-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="57232-118">前三个 SAN 条目是完整边缘服务器的常规 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="57232-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="57232-119">Contoso.com 是与根域级别的 XMPP 合作伙伴进行联盟所需的条目。</span><span class="sxs-lookup"><span data-stu-id="57232-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="57232-120">此条目将允许具有后缀 contoso.com 的所有域的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="57232-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57232-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57232-121">See Also</span></span>


[<span data-ttu-id="57232-122">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="57232-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="57232-123">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="57232-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="57232-124">为 Lync Server 2013 设置边缘证书</span><span class="sxs-lookup"><span data-stu-id="57232-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="57232-125">请求-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="57232-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="57232-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="57232-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

