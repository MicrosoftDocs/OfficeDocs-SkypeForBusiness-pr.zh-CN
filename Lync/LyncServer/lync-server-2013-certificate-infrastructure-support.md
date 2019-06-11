---
title: Lync Server 2013 证书基础结构支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="1d346-102">Lync Server 2013 中的证书基础结构支持</span><span class="sxs-lookup"><span data-stu-id="1d346-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d346-103">_**主题上次修改时间:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="1d346-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="1d346-104">Lync Server 2013 需要一个公钥基础结构 (PKI) 来支持传输层安全 (TLS) 和相互 TLS (MTLS) 连接。</span><span class="sxs-lookup"><span data-stu-id="1d346-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="1d346-105">默认情况下, Lync Server 2013 配置为对客户端到服务器连接使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="1d346-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="1d346-106">MTLS 用于服务器之间的连接。</span><span class="sxs-lookup"><span data-stu-id="1d346-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="1d346-107">MTLS 证书必须由 Lync Server 2013 的受信任的证书颁发机构 (Ca) 颁发。</span><span class="sxs-lookup"><span data-stu-id="1d346-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="1d346-108">Lync 服务器支持从以下 Ca 颁发的证书:</span><span class="sxs-lookup"><span data-stu-id="1d346-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="1d346-109">颁发自内部 CA 的证书:</span><span class="sxs-lookup"><span data-stu-id="1d346-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="1d346-110">Windows Server 2003 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="1d346-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="1d346-111">Windows Server 2008 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="1d346-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="1d346-112">Windows Server 2008 R2 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="1d346-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="1d346-113">Windows Server 2012 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="1d346-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="1d346-114">Windows Server 2012 R2 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="1d346-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="1d346-115">颁发自公共 CA 的证书</span><span class="sxs-lookup"><span data-stu-id="1d346-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="1d346-116">与其他应用程序和服务器 (如 Exchange 2013) 通信需要其他应用程序和产品支持的证书。</span><span class="sxs-lookup"><span data-stu-id="1d346-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="1d346-117">对于2013版本, Lync Server 2013 和其他 Microsoft Server 产品 (包括 Exchange 2013 和 SharePoint Server) 支持用于服务器到服务器身份验证和授权的开放授权 (OAuth) 协议。</span><span class="sxs-lookup"><span data-stu-id="1d346-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="1d346-118">有关详细信息, 请参阅在部署文档或操作文档中[管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="1d346-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="1d346-119">对于运行 Windows 7 操作系统、Windows Server 2008 R2 操作系统和 Microsoft Office Communicator 2007 手机版的客户端的连接, Lync Server 2013 包含对 (但不需要) 使用 SHA-256 签名的 (但不需要) 证书的支持加密哈希函数。</span><span class="sxs-lookup"><span data-stu-id="1d346-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="1d346-120">若要支持使用 SHA-256 的外部访问, 外部证书由使用 SHA-256 的公共 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="1d346-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="1d346-121">有关证书要求的详细信息, 请参阅规划文档中[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d346-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="1d346-122">有关如何对证书使用通配符的详细信息, 请参阅支持文档中的[Lync Server 2013 中的通配符支持](lync-server-2013-wildcard-certificate-support.md)。</span><span class="sxs-lookup"><span data-stu-id="1d346-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

