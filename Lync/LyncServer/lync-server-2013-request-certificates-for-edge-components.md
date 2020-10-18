---
title: Lync Server 2013：请求边缘组件的证书
description: Lync Server 2013：请求边缘组件的证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579008"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="e3749-103">在 Lync Server 2013 中请求边缘组件的证书</span><span class="sxs-lookup"><span data-stu-id="e3749-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3749-104">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e3749-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e3749-105">支持外部用户访问所需的证书包括公共证书颁发机构 (CA) 颁发的证书和内部企业 CA 颁发的证书：</span><span class="sxs-lookup"><span data-stu-id="e3749-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="e3749-106">边缘服务器和反向代理的外部接口所需的证书必须由公共 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="e3749-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="e3749-107">内部接口所需的证书可以由公共 CA 或内部企业 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="e3749-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="e3749-108">我们建议使用内部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA 来创建这些证书，以使用公用证书的费用保存。</span><span class="sxs-lookup"><span data-stu-id="e3749-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e3749-109">处理证书请求可能需要花费一些时间（特别是向公共 CA 提交的请求），因此应提前请求边缘服务器的证书，以确保开始部署边缘服务器组件时证书可用。</span><span class="sxs-lookup"><span data-stu-id="e3749-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="e3749-110">有关边缘服务器的证书要求摘要，请参阅 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中的外部用户访问的证书要求</A>。</span><span class="sxs-lookup"><span data-stu-id="e3749-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e3749-111">虽然可以选择将公共 CA 用于内部边缘证书，但是我们建议您将内部企业 CA 用于其他证书，以将证书的成本降到最低。</span><span class="sxs-lookup"><span data-stu-id="e3749-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="e3749-112">有关边缘服务器的证书要求摘要，请参阅 [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e3749-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3749-113">安装边缘服务器时，安装程序会提供证书向导，以促进请求、分配和安装证书的任务，如为 <A href="lync-server-2013-set-up-edge-certificates.md">Lync Server 2013 设置边缘证书</A> 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="e3749-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="e3749-114">如果要在安装边缘服务器之前请求证书 (例如，为了在边缘服务器组件的实际部署期间节省时间) ，可以使用内部服务器执行此操作，前提是确保这些证书是可导出的并包含所有必需的主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="e3749-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="e3749-115">本文档不提供使用内部服务器请求证书的过程。</span><span class="sxs-lookup"><span data-stu-id="e3749-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="e3749-116">从公共 CA 请求证书</span><span class="sxs-lookup"><span data-stu-id="e3749-116">Request certificates from a public CA</span></span>

<span data-ttu-id="e3749-117">您的边缘服务器部署需要一个公共证书，用于边缘服务器的外部接口，用于访问边缘服务、Web 会议边缘服务和 A/V 身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="e3749-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="e3749-118">此证书必须具有可导出的私钥，以确保 A/V 身份验证服务在池中的所有边缘服务器上使用相同的密钥。</span><span class="sxs-lookup"><span data-stu-id="e3749-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="e3749-119">与 Microsoft Internet 安全性和加速 (ISA) Server 2006 或 Microsoft Forefront 威胁管理网关2010一起使用的反向代理也需要公共证书。</span><span class="sxs-lookup"><span data-stu-id="e3749-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="e3749-120">从内部企业 CA 请求证书</span><span class="sxs-lookup"><span data-stu-id="e3749-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="e3749-p106">内部边缘接口所需的证书可由公共证书颁发机构 (CA) 或内部 CA 颁发。使用内部企业 CA 可以帮助最大限度地降低证书成本。如果组织部署了内部 CA，则应由内部 CA 颁发内部边缘的证书。对内部证书使用内部企业 CA 可降低证书成本。</span><span class="sxs-lookup"><span data-stu-id="e3749-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="e3749-125">有关边缘组件的证书要求摘要，请参阅 [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e3749-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="e3749-126">有关使用公用 CA 获取证书的详细信息，请参阅 [Lync Server 2013 中的请求证书的边缘组件](lync-server-2013-request-certificates-for-edge-components.md)。</span><span class="sxs-lookup"><span data-stu-id="e3749-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="e3749-127">有关请求、安装和分配证书的详细信息，请参阅 [设置适用于 Lync Server 2013 的边缘证书](lync-server-2013-set-up-edge-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="e3749-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

