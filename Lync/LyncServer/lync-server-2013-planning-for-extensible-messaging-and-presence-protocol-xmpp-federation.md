---
title: 规划可扩展消息传递和状态协议（XMPP）联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77884bdca8d02a29d98a2a4c2dd116abb72d8f20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3bfee-102">在 Lync Server 2013 中规划可扩展消息和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="3bfee-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bfee-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3bfee-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3bfee-104">早期版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="3bfee-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="3bfee-105">在 Microsoft Lync Server 2013 中，可以将 XMPP 功能部署为功能。</span><span class="sxs-lookup"><span data-stu-id="3bfee-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="3bfee-106">XMPP 功能安装在两个部分中：在边缘服务器上运行的 XMPP 代理，以及在前端服务器上运行的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="3bfee-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="3bfee-107">在[Lync Server 2013 中部署外部用户访问权限](lync-server-2013-deploying-external-user-access.md)中介绍了 XMPP 的部署和配置。通过在防火墙上定义端口和协议规则、配置证书以及添加 DNS 记录，在您计划支持组织中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="3bfee-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="3bfee-108">本节中的以下主题汇总了为您的部署成功规划 XMPP 联合所需的信息。</span><span class="sxs-lookup"><span data-stu-id="3bfee-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3bfee-109">Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。</span><span class="sxs-lookup"><span data-stu-id="3bfee-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="3bfee-110">对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="3bfee-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bfee-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3bfee-111">In This Section</span></span>

  - [<span data-ttu-id="3bfee-112">Lync Server 2013 中的证书摘要-可扩展消息传递和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="3bfee-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="3bfee-113">Lync Server 2013 中的端口摘要-可扩展消息传递和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="3bfee-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="3bfee-114">Lync Server 2013 中的 DNS 摘要-可扩展消息传递和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="3bfee-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bfee-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bfee-115">See Also</span></span>


[<span data-ttu-id="3bfee-116">在 Lync Server 2013 中设置 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="3bfee-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="3bfee-117">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="3bfee-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="3bfee-118">在 Lync Server 2013 中管理 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="3bfee-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="3bfee-119">[Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3bfee-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="3bfee-120">[CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3bfee-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="3bfee-121">[CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3bfee-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

