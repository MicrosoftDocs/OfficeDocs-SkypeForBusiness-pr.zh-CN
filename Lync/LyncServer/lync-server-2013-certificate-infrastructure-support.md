---
title: Lync Server 2013 证书基础结构支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1009fbe40092d9b6e6692ad2bc4d5305d7fbf375
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="bd88a-102">Lync Server 2013 中的证书基础结构支持</span><span class="sxs-lookup"><span data-stu-id="bd88a-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd88a-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="bd88a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="bd88a-104">Lync Server 2013 要求使用公钥基础结构（PKI）来支持传输层安全性（TLS）和相互 TLS （MTLS）连接。</span><span class="sxs-lookup"><span data-stu-id="bd88a-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="bd88a-105">默认情况下，Lync Server 2013 配置为对客户端到服务器连接使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="bd88a-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="bd88a-106">MTLS 用于服务器之间的连接。</span><span class="sxs-lookup"><span data-stu-id="bd88a-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="bd88a-107">MTLS 证书必须由适用于 Lync Server 2013 的受信任证书颁发机构（Ca）颁发。</span><span class="sxs-lookup"><span data-stu-id="bd88a-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="bd88a-108">Lync Server 支持从以下 Ca 颁发的证书：</span><span class="sxs-lookup"><span data-stu-id="bd88a-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="bd88a-109">从内部 CA 颁发的证书：</span><span class="sxs-lookup"><span data-stu-id="bd88a-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="bd88a-110">Windows Server 2003 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="bd88a-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="bd88a-111">Windows Server 2008 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="bd88a-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="bd88a-112">Windows Server 2008 R2 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="bd88a-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="bd88a-113">Windows Server 2012 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="bd88a-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="bd88a-114">Windows Server 2012 R2 操作系统 CA</span><span class="sxs-lookup"><span data-stu-id="bd88a-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="bd88a-115">从公共 CA 颁发的证书</span><span class="sxs-lookup"><span data-stu-id="bd88a-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="bd88a-116">与其他应用程序和服务器（如 Exchange 2013）的通信需要其他应用程序和产品支持的证书。</span><span class="sxs-lookup"><span data-stu-id="bd88a-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="bd88a-117">对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。</span><span class="sxs-lookup"><span data-stu-id="bd88a-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="bd88a-118">有关详细信息，请参阅部署文档或操作文档中的[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="bd88a-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="bd88a-119">对于运行 Windows 7 操作系统、Windows Server 2008 R2 操作系统和 Microsoft Office Communicator 2007 Phone Edition 的客户端的连接，Lync Server 2013 支持使用 SHA-256 对（但不需要）证书进行签名加密哈希函数。</span><span class="sxs-lookup"><span data-stu-id="bd88a-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="bd88a-120">要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。</span><span class="sxs-lookup"><span data-stu-id="bd88a-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="bd88a-121">有关证书要求的详细信息，请参阅规划文档中的[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd88a-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="bd88a-122">有关在证书中使用通配符的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)。</span><span class="sxs-lookup"><span data-stu-id="bd88a-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

